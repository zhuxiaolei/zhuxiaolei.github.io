---
layout: post
title: "Activity前端设计之流程文件xml组织"
date: 2017-04-28 
description: "Activity前端设计之流程文件xml组织"
tag: JAVA 
---  
 
## 正文：
　页面提交数据——JSON_xml

### 代码　

	{
	    "resourceId": "44c31bf4f41f45ab9709ac298baa68b0",
	    "properties": {
	        "process_id": "ShawRay",
	        "name": "ShawRay",
	        "documentation": "",
	        "process_author": "ShawRay",
	        "process_version": "",
	        "process_namespace": "http://www.activiti.org/processdef",
	        "executionlisteners": "",
	        "eventlisteners": "",
	        "signaldefinitions": "",
	        "messagedefinitions": ""
	    },
	    "stencil": {
	        "id": "BPMNDiagram"
	    },
	    "childShapes": [
	        {
	            "resourceId": "sid-01AB15D9-AE5A-4778-B444-7F91A307031F",
	            "properties": {
	                "overrideid": "start",
	                "name": "开始",
	                "documentation": "",
	                "executionlisteners": "",
	                "initiator": "",
	                "formkeydefinition": "",
	                "formproperties": ""
	            },
	            "stencil": {
	                "id": "StartNoneEvent"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-DF57E19F-95D6-4F0A-B5A8-D04CF7C9E834"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 217.5,
	                    "y": 126
	                },
	                "upperLeft": {
	                    "x": 187.5,
	                    "y": 96
	                }
	            },
	            "dockers": []
	        },
	        {
	            "resourceId": "sid-A498A3CD-164D-41A2-98D6-405CBB89BEB0",
	            "properties": {
	                "overrideid": "userTask1",
	                "name": "人工节点",
	                "documentation": "人工节点",
	                "asynchronousdefinition": "false",
	                "exclusivedefinition": true,
	                "executionlisteners": "",
	                "multiinstance_type": "None",
	                "multiinstance_cardinality": "",
	                "multiinstance_collection": "",
	                "multiinstance_variable": "",
	                "multiinstance_condition": "",
	                "isforcompensation": "false",
	                "usertaskassignment": "",
	                "formkeydefinition": "",
	                "duedatedefinition": "",
	                "prioritydefinition": "",
	                "formproperties": "",
	                "tasklisteners": ""
	            },
	            "stencil": {
	                "id": "UserTask"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-D2857D5D-261B-4845-807D-02723888D842"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 350,
	                    "y": 145.5
	                },
	                "upperLeft": {
	                    "x": 270,
	                    "y": 76.5
	                }
	            },
	            "dockers": []
	        },
	        {
	            "resourceId": "sid-DF57E19F-95D6-4F0A-B5A8-D04CF7C9E834",
	            "properties": {
	                "overrideid": "",
	                "name": "",
	                "documentation": "",
	                "conditionsequenceflow": "",
	                "executionlisteners": "",
	                "defaultflow": "false"
	            },
	            "stencil": {
	                "id": "SequenceFlow"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-A498A3CD-164D-41A2-98D6-405CBB89BEB0"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 269.52734375,
	                    "y": 111
	                },
	                "upperLeft": {
	                    "x": 217.77734375,
	                    "y": 111
	                }
	            },
	            "dockers": [
	                {
	                    "x": 15,
	                    "y": 15
	                },
	                {
	                    "x": 40,
	                    "y": 34.5
	                }
	            ],
	            "target": {
	                "resourceId": "sid-A498A3CD-164D-41A2-98D6-405CBB89BEB0"
	            }
	        },
	        {
	            "resourceId": "sid-4B28A438-D0C4-439D-A9F4-3CF5A1EE2CDB",
	            "properties": {
	                "overrideid": "end",
	                "name": "结束",
	                "documentation": "",
	                "executionlisteners": ""
	            },
	            "stencil": {
	                "id": "EndNoneEvent"
	            },
	            "childShapes": [],
	            "outgoing": [],
	            "bounds": {
	                "lowerRight": {
	                    "x": 598,
	                    "y": 125
	                },
	                "upperLeft": {
	                    "x": 570,
	                    "y": 97
	                }
	            },
	            "dockers": []
	        },
	        {
	            "resourceId": "sid-1AEE8821-3C9D-4B37-BA7F-F25B140BFC63",
	            "properties": {
	                "overrideid": "userTask2",
	                "name": "人工节点",
	                "documentation": "",
	                "asynchronousdefinition": "false",
	                "exclusivedefinition": true,
	                "executionlisteners": "",
	                "multiinstance_type": "None",
	                "multiinstance_cardinality": "",
	                "multiinstance_collection": "",
	                "multiinstance_variable": "",
	                "multiinstance_condition": "",
	                "isforcompensation": "false",
	                "usertaskassignment": "",
	                "formkeydefinition": "",
	                "duedatedefinition": "",
	                "prioritydefinition": "",
	                "formproperties": "",
	                "tasklisteners": ""
	            },
	            "stencil": {
	                "id": "UserTask"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-27C91C2A-228A-44B8-A646-DB2EA6948F6E"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 492,
	                    "y": 143.5
	                },
	                "upperLeft": {
	                    "x": 420,
	                    "y": 78.5
	                }
	            },
	            "dockers": []
	        },
	        {
	            "resourceId": "sid-27C91C2A-228A-44B8-A646-DB2EA6948F6E",
	            "properties": {
	                "overrideid": "",
	                "name": "",
	                "documentation": "",
	                "conditionsequenceflow": "",
	                "executionlisteners": "",
	                "defaultflow": "false"
	            },
	            "stencil": {
	                "id": "SequenceFlow"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-4B28A438-D0C4-439D-A9F4-3CF5A1EE2CDB"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 570,
	                    "y": 111
	                },
	                "upperLeft": {
	                    "x": 493,
	                    "y": 111
	                }
	            },
	            "dockers": [
	                {
	                    "x": 36,
	                    "y": 32.5
	                },
	                {
	                    "x": 14,
	                    "y": 14
	                }
	            ],
	            "target": {
	                "resourceId": "sid-4B28A438-D0C4-439D-A9F4-3CF5A1EE2CDB"
	            }
	        },
	        {
	            "resourceId": "sid-D2857D5D-261B-4845-807D-02723888D842",
	            "properties": {
	                "overrideid": "",
	                "name": "",
	                "documentation": "",
	                "conditionsequenceflow": "",
	                "executionlisteners": "",
	                "defaultflow": "false",
	                "showdiamondmarker": false
	            },
	            "stencil": {
	                "id": "SequenceFlow"
	            },
	            "childShapes": [],
	            "outgoing": [
	                {
	                    "resourceId": "sid-1AEE8821-3C9D-4B37-BA7F-F25B140BFC63"
	                }
	            ],
	            "bounds": {
	                "lowerRight": {
	                    "x": 419.640625,
	                    "y": 111
	                },
	                "upperLeft": {
	                    "x": 350.921875,
	                    "y": 111
	                }
	            },
	            "dockers": [
	                {
	                    "x": 40,
	                    "y": 34.5
	                },
	                {
	                    "x": 36,
	                    "y": 32.5
	                }
	            ],
	            "target": {
	                "resourceId": "sid-1AEE8821-3C9D-4B37-BA7F-F25B140BFC63"
	            }
	        }
	    ],
	    "bounds": {
	        "lowerRight": {
	            "x": 1200,
	            "y": 950
	        },
	        "upperLeft": {
	            "x": 0,
	            "y": 0
	        }
	    },
	    "stencilset": {
	        "url": "stencilsets/bpmn2.0/bpmn2.0.json",
	        "namespace": "http://b3mn.org/stencilset/bpmn2.0#"
	    },
	    "ssextensions": []
	}


转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！
