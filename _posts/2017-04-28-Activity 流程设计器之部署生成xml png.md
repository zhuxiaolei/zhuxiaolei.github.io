---
layout: post
title: "Activity 流程设计器之部署生成xml png"
date: 2017-04-28 
description: "Activity 流程设计器之部署生成xml png"
tag: JAVA 
---  
 
## 正文：
　递归设置图形

### 代码　

	private void readShapeDI(JsonNode objectNode, double parentX, double parentY, Map<String, JsonNode> shapeMap, Map<String, JsonNode> sourceRefMap,
			BpmnModel bpmnModel) {
		//获取childShapesJSON节点
		if (objectNode.get(EDITOR_CHILD_SHAPES) != null) {
			//遍历当前jsonChildNode-childShapes
			for (JsonNode jsonChildNode : objectNode.get(EDITOR_CHILD_SHAPES)) {
				//获取模板ID
				String stencilId = BpmnJsonConverterUtil.getStencilId(jsonChildNode);
				//sequence flows are on root level （顺序流）
				if (STENCIL_SEQUENCE_FLOW.equals(stencilId) == false) {
					//创建Activity图像对象
					GraphicInfo graphicInfo = new GraphicInfo();
					//获取界限JSON
					JsonNode boundsNode = jsonChildNode.get(EDITOR_BOUNDS);
					//获取左上角坐标
					ObjectNode upperLeftNode = (ObjectNode) boundsNode.get(EDITOR_BOUNDS_UPPER_LEFT);
					//设置X坐标值
					graphicInfo.setX(upperLeftNode.get(EDITOR_BOUNDS_X).asDouble() + parentX);
					//设计Y坐标值
					graphicInfo.setY(upperLeftNode.get(EDITOR_BOUNDS_Y).asDouble() + parentY);
					//获取右下角坐标
					ObjectNode lowerRightNode = (ObjectNode) boundsNode.get(EDITOR_BOUNDS_LOWER_RIGHT);
					graphicInfo.setWidth(lowerRightNode.get(EDITOR_BOUNDS_X).asDouble() - graphicInfo.getX() + parentX);
					graphicInfo.setHeight(lowerRightNode.get(EDITOR_BOUNDS_Y).asDouble() - graphicInfo.getY() + parentY);

					String childShapeId = jsonChildNode.get(EDITOR_SHAPE_ID).asText();
					//设置Key(获取properties的属性overrideid) Value（GraphicInfo对象）
					bpmnModel.addGraphicInfo(BpmnJsonConverterUtil.getElementId(jsonChildNode), graphicInfo);

					shapeMap.put(childShapeId, jsonChildNode);

					ArrayNode outgoingNode = (ArrayNode) jsonChildNode.get("outgoing");
					//设置当前节点走向
					if ((outgoingNode != null) && (outgoingNode.size() > 0)) {
						for (JsonNode outgoingChildNode : outgoingNode) {
							JsonNode resourceNode = outgoingChildNode.get(EDITOR_SHAPE_ID);

							if (resourceNode != null) {
								sourceRefMap.put(resourceNode.asText(), jsonChildNode);
							}
						}
					}

					readShapeDI(jsonChildNode, graphicInfo.getX(), graphicInfo.getY(), shapeMap, sourceRefMap, bpmnModel);
				}
			}
		}
	}


### 过滤所有的顺序流
	
	private void filterAllEdges(JsonNode objectNode, Map<String, JsonNode> edgeMap, Map<String, List<JsonNode>> sourceAndTargetMap,
		Map<String, JsonNode> shapeMap, Map<String, JsonNode> sourceRefMap) {
		if (objectNode.get(EDITOR_CHILD_SHAPES) != null) {
			for (JsonNode jsonChildNode : objectNode.get(EDITOR_CHILD_SHAPES)) {
				ObjectNode childNode = (ObjectNode) jsonChildNode;
				String stencilId = BpmnJsonConverterUtil.getStencilId(childNode);
				//判断是否是子流程
				if (STENCIL_SUB_PROCESS.equals(stencilId)) {
					filterAllEdges(childNode, edgeMap, sourceAndTargetMap, shapeMap, sourceRefMap);
				} else if (STENCIL_SEQUENCE_FLOW.equals(stencilId) || STENCIL_ASSOCIATION.equals(stencilId)) {
					//SequenceFlow 和 Association 类型 获取顺序流走向
					String childEdgeId = BpmnJsonConverterUtil.getElementId(childNode);
					JsonNode targetNode = childNode.get("target");

					if ((targetNode != null) && (targetNode.isNull() == false)) {
						String targetRefId = targetNode.get(EDITOR_SHAPE_ID).asText();
						List<JsonNode> sourceAndTargetList = new ArrayList<JsonNode>();
						sourceAndTargetList.add(sourceRefMap.get(childNode.get(EDITOR_SHAPE_ID).asText()));
						sourceAndTargetList.add(shapeMap.get(targetRefId));
						sourceAndTargetMap.put(childEdgeId, sourceAndTargetList);
					}

					edgeMap.put(childEdgeId, childNode);
				}
			}
		}
	}

### 读取顺序流数据输入

	private void readEdgeDI(Map<String, JsonNode> edgeMap, Map<String, List<JsonNode>> sourceAndTargetMap, BpmnModel bpmnModel) {
		//遍历顺序流
		for (String edgeId : edgeMap.keySet()) {
			JsonNode edgeNode = edgeMap.get(edgeId);
			//获取节点指向
			List<JsonNode> sourceAndTargetList = sourceAndTargetMap.get(edgeId);

			JsonNode sourceRefNode = null;
			JsonNode targetRefNode = null;

			if ((sourceAndTargetList != null) && (sourceAndTargetList.size() > 1)) {
				//来源节点（也可以理解为当前节点）
				sourceRefNode = sourceAndTargetList.get(0);
				//目标节点（也可以理解为走向下一个节点）
				targetRefNode = sourceAndTargetList.get(1);
			}

			if (sourceRefNode == null) {
				LOGGER.info("Skipping edge {} because source ref is null", edgeId);

				continue;
			}

			if (targetRefNode == null) {
				LOGGER.info("Skipping edge {} because target ref is null", edgeId);

				continue;
			}
			//设置节点容器大小
			JsonNode dockersNode = edgeNode.get(EDITOR_DOCKERS);
			double sourceDockersX = dockersNode.get(0).get(EDITOR_BOUNDS_X).asDouble();
			double sourceDockersY = dockersNode.get(0).get(EDITOR_BOUNDS_Y).asDouble();
			//获取来源节点图像对象
			GraphicInfo sourceInfo = bpmnModel.getGraphicInfo(BpmnJsonConverterUtil.getElementId(sourceRefNode));
			//获取目标节点图像对象
			GraphicInfo targetInfo = bpmnModel.getGraphicInfo(BpmnJsonConverterUtil.getElementId(targetRefNode));
			//根据坐标+大小设置图像X坐标
			double sourceRefLineX = sourceInfo.getX() + sourceDockersX;
			double sourceRefLineY = sourceInfo.getY() + sourceDockersY;

			double nextPointInLineX;
			double nextPointInLineY;

			nextPointInLineX = dockersNode.get(1).get(EDITOR_BOUNDS_X).asDouble();
			nextPointInLineY = dockersNode.get(1).get(EDITOR_BOUNDS_Y).asDouble();

			if (dockersNode.size() == 2) {
				nextPointInLineX += targetInfo.getX();
				nextPointInLineY += targetInfo.getY();
			}
			//Line2D工具包
			Line2D firstLine = new Line2D(sourceRefLineX, sourceRefLineY, nextPointInLineX, nextPointInLineY);

			String sourceRefStencilId = BpmnJsonConverterUtil.getStencilId(sourceRefNode);
			String targetRefStencilId = BpmnJsonConverterUtil.getStencilId(targetRefNode);

			List<GraphicInfo> graphicInfoList = new ArrayList<GraphicInfo>();

			AbstractContinuousCurve2D source2D = null;
			//园图形
			if (DI_CIRCLES.contains(sourceRefStencilId)) {
				source2D = new Circle2D(sourceInfo.getX() + sourceDockersX, sourceInfo.getY() + sourceDockersY, sourceDockersX);
			} else if (DI_RECTANGLES.contains(sourceRefStencilId)) {//矩形图形
				source2D = createRectangle(sourceInfo);
			} else if (DI_GATEWAY.contains(sourceRefStencilId)) {//网关图形
				source2D = createGateway(sourceInfo);
			}

			if (source2D != null) {
				//返回曲线与指定直线的交点。结果数组的长度是交点的个数。
				Collection<Point2D> intersections = source2D.intersections(firstLine);

				if ((intersections != null) && (intersections.size() > 0)) {
					Point2D intersection = intersections.iterator().next();
					graphicInfoList.add(createGraphicInfo(intersection.x(), intersection.y()));
				} else {
					graphicInfoList.add(createGraphicInfo(sourceRefLineX, sourceRefLineY));
				}
			}

			Line2D lastLine = null;

			if (dockersNode.size() > 2) {
				for (int i = 1; i < (dockersNode.size() - 1); i++) {
					double x = dockersNode.get(i).get(EDITOR_BOUNDS_X).asDouble();
					double y = dockersNode.get(i).get(EDITOR_BOUNDS_Y).asDouble();
					graphicInfoList.add(createGraphicInfo(x, y));
				}

				double startLastLineX = dockersNode.get(dockersNode.size() - 2).get(EDITOR_BOUNDS_X).asDouble();
				double startLastLineY = dockersNode.get(dockersNode.size() - 2).get(EDITOR_BOUNDS_Y).asDouble();

				double endLastLineX = dockersNode.get(dockersNode.size() - 1).get(EDITOR_BOUNDS_X).asDouble();
				double endLastLineY = dockersNode.get(dockersNode.size() - 1).get(EDITOR_BOUNDS_Y).asDouble();

				endLastLineX += targetInfo.getX();
				endLastLineY += targetInfo.getY();

				lastLine = new Line2D(startLastLineX, startLastLineY, endLastLineX, endLastLineY);
			} else {
				lastLine = firstLine;
			}

			AbstractContinuousCurve2D target2D = null;

			if (DI_RECTANGLES.contains(targetRefStencilId)) {
				target2D = createRectangle(targetInfo);
			} else if (DI_CIRCLES.contains(targetRefStencilId)) {
				double targetDockersX = dockersNode.get(dockersNode.size() - 1).get(EDITOR_BOUNDS_X).asDouble();
				double targetDockersY = dockersNode.get(dockersNode.size() - 1).get(EDITOR_BOUNDS_Y).asDouble();

				target2D = new Circle2D(targetInfo.getX() + targetDockersX, targetInfo.getY() + targetDockersY, targetDockersX);
			} else if (DI_GATEWAY.contains(targetRefStencilId)) {
				target2D = createGateway(targetInfo);
			}

			if (target2D != null) {
				Collection<Point2D> intersections = target2D.intersections(lastLine);

				if ((intersections != null) && (intersections.size() > 0)) {
					Point2D intersection = intersections.iterator().next();
					graphicInfoList.add(createGraphicInfo(intersection.x(), intersection.y()));
				} else {
					graphicInfoList.add(createGraphicInfo(lastLine.getPoint2().x(), lastLine.getPoint2().y()));
				}
			}

			bpmnModel.addFlowGraphicInfoList(edgeId, graphicInfoList);

			// if sequence has a name, just add a label graphic info
			if (!"".equals(edgeNode.get("properties").get("name"))) {
				bpmnModel.addLabelGraphicInfo(edgeId, createGraphicInfo(graphicInfoList.get(0).getX(), graphicInfoList.get(0).getY()));
			}
		}
	}


转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！
