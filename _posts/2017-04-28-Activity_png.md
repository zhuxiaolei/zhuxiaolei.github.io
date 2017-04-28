---
layout: post
title: "Activity前端设计之流程图片组织数据"
date: 2017-04-28 
description: "Activity前端设计之流程图片组织数据"
tag: JAVA 
---  
 
## 正文：
　前端设计器提交的SVG数据-用于生成图片

### 代码　

	<svg
	    xmlns="http://www.w3.org/2000/svg"
	    xmlns:oryx="http://oryx-editor.org" id="sid-D855498F-F0C3-4C17-98C9-D6FF3E6A77BF" width="648" height="195.5"
	    xmlns:xlink="http://www.w3.org/1999/xlink"
	    xmlns:svg="http://www.w3.org/2000/svg">
	    <defs>
	        <marker id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517start" refX="1" refY="5" markerUnits="userSpaceOnUse" markerWidth="17" markerHeight="11" orient="auto">
		  		undefined
				
	            <path id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517default" d="M 5 0 L 11 10" fill="white" stroke="#585858" stroke-width="1" display="none"/>
	        </marker>
	        <marker id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517end" refX="15" refY="6" markerUnits="userSpaceOnUse" markerWidth="15" markerHeight="12" orient="auto">
	            <path id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517arrowhead" d="M 0 1 L 15 6 L 0 11z" fill="#585858" stroke="#585858" stroke-linejoin="round" stroke-width="2"/>
	        </marker>
	        <marker id="sid-767EB326-704F-4488-9FC2-B3C9AC630419start" refX="1" refY="5" markerUnits="userSpaceOnUse" markerWidth="17" markerHeight="11" orient="auto">
		  		undefined
				
	            <path id="sid-767EB326-704F-4488-9FC2-B3C9AC630419default" d="M 5 0 L 11 10" fill="white" stroke="#585858" stroke-width="1" display="none"/>
	        </marker>
	        <marker id="sid-767EB326-704F-4488-9FC2-B3C9AC630419end" refX="15" refY="6" markerUnits="userSpaceOnUse" markerWidth="15" markerHeight="12" orient="auto">
	            <path id="sid-767EB326-704F-4488-9FC2-B3C9AC630419arrowhead" d="M 0 1 L 15 6 L 0 11z" fill="#585858" stroke="#585858" stroke-linejoin="round" stroke-width="2"/>
	        </marker>
	        <marker id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62start" refX="1" refY="5" markerUnits="userSpaceOnUse" markerWidth="17" markerHeight="11" orient="auto">
		  		undefined
				
	            <path id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62default" d="M 5 0 L 11 10" fill="white" stroke="#585858" stroke-width="1" display="none"/>
	        </marker>
	        <marker id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62end" refX="15" refY="6" markerUnits="userSpaceOnUse" markerWidth="15" markerHeight="12" orient="auto">
	            <path id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62arrowhead" d="M 0 1 L 15 6 L 0 11z" fill="#585858" stroke="#585858" stroke-linejoin="round" stroke-width="2"/>
	        </marker>
	    </defs>
	    <svg id="underlay-container"/>
	    <g stroke="none" font-family="Verdana, sans-serif" font-size-adjust="none" font-style="normal" font-variant="normal" font-weight="normal" line-heigth="normal" font-size="12">
	        <g class="stencils">
	            <g class="me"/>
	            <g class="children">
	                <g id="svg-sid-01AB15D9-AE5A-4778-B444-7F91A307031F">
	                    <g class="stencils" transform="translate(187.5, 96)">
	                        <g class="me">
	                            <g pointer-events="fill" id="sid-7FDA8E45-0C34-462C-89B5-D966AA8E5F6B" title="开始事件">
	                                <circle id="sid-7FDA8E45-0C34-462C-89B5-D966AA8E5F6Bbg_frame" cx="15" cy="15" r="15" stroke="#585858" fill="#ffffff" stroke-width="1"/>
	                                <text font-size="11" id="sid-7FDA8E45-0C34-462C-89B5-D966AA8E5F6Btext_name" x="15" y="32" oryx:align="top center" stroke="#373e48" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(0 15 32)" oryx:fontSize="11" text-anchor="middle">
	                                    <tspan dy="11" x="15" y="32">开始</tspan>
	                                </text>
	                            </g>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets" transform="translate(187.5, 96)">
	                            <g pointer-events="all" display="none" transform="translate(7, 7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                        </g>
	                    </g>
	                </g>
	                <g id="svg-sid-A498A3CD-164D-41A2-98D6-405CBB89BEB0">
	                    <g class="stencils" transform="translate(270, 76.5)">
	                        <g class="me">
	                            <g pointer-events="fill" oryx:minimumSize="50 40" id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80" title="用户任务">
	                                <rect id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80text_frame" oryx:anchors="bottom top right left" x="1" y="1" width="74" height="68" rx="10" ry="10" stroke="none" stroke-width="0" fill="none"/>
	                                <rect id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80bg_frame" oryx:resize="vertical horizontal" x="0" y="0" width="80" height="69" rx="10" ry="10" stroke="#bbbbbb" stroke-width="1" fill="#f9f9f9"/>
	                                <text font-size="12" id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80text_name" x="40" y="34" oryx:align="middle center" oryx:fittoelem="text_frame" stroke="#373e48" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(0 40 34)" oryx:fontSize="12" text-anchor="middle">
	                                    <tspan x="40" y="34" dy="5">人工节点</tspan>
	                                </text>
	                                <g id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80userTask" transform="translate(3,3)">
	                                    <path oryx:anchors="top left" style="fill:#d1b575;stroke:none;" d="m 1,17 16,0 0,-1.7778 -5.333332,-3.5555 0,-1.7778 c 1.244444,0 1.244444,-2.3111 1.244444,-2.3111 l 0,-3.0222 C 12.555557,0.8221 9.0000001,1.0001 9.0000001,1.0001 c 0,0 -3.5555556,-0.178 -3.9111111,3.5555 l 0,3.0222 c 0,0 0,2.3111 1.2444443,2.3111 l 0,1.7778 L 1,15.2222 1,17 17,17" id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80_sid-3288DF80-F92C-4124-B61A-2ED028F31A80_17"/>
	                                </g>
	                                <g id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80parallel" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" d=" M36.00000000000001 59  v8  M40.00000000000001 59  v8  M44.00000000000001 59  v8 " stroke-width="2" id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80_sid-3288DF80-F92C-4124-B61A-2ED028F31A80_18"/>
	                                </g>
	                                <g id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80sequential" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" stroke-width="2" d=" M35.800000000000004 65  h10  M35.800000000000004 61  h10  M35.800000000000004 57  h10 " id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80_sid-3288DF80-F92C-4124-B61A-2ED028F31A80_19"/>
	                                </g>
	                                <g id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80compensation" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" d=" M49.60000000000001 63  L53.60000000000001 59  L53.60000000000001 67  L49.60000000000001 63  L49.60000000000001 59  L45.60000000000001 63  L49.60000000000001 67  L49.60000000000001 63 " stroke-width="1" id="sid-3288DF80-F92C-4124-B61A-2ED028F31A80_sid-3288DF80-F92C-4124-B61A-2ED028F31A80_20"/>
	                                </g>
	                            </g>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets" transform="translate(270, 76.5)">
	                            <g pointer-events="all" display="none" transform="translate(-7, 9.25)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(-7, 26.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(-7, 43.75)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(12, 60)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(32, 60)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(52, 60)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(71, 9.25)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(71, 26.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(71, 43.75)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(12, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(32, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(52, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(32, 26.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                        </g>
	                    </g>
	                </g>
	                <g id="svg-sid-4B28A438-D0C4-439D-A9F4-3CF5A1EE2CDB">
	                    <g class="stencils" transform="translate(570, 97)">
	                        <g class="me">
	                            <g pointer-events="fill" id="sid-89CAE98F-110B-4CC4-9E3D-11ECAD90BED3" title="结束事件">
	                                <circle id="sid-89CAE98F-110B-4CC4-9E3D-11ECAD90BED3bg_frame" cx="14" cy="14" r="14" stroke="#585858" fill="#ffffff" stroke-width="3"/>
	                                <text font-size="11" id="sid-89CAE98F-110B-4CC4-9E3D-11ECAD90BED3text_name" x="14" y="30" oryx:align="top center" stroke="#373e48" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(0 14 30)" oryx:fontSize="11" text-anchor="middle">
	                                    <tspan dy="11" x="14" y="30">结束</tspan>
	                                </text>
	                            </g>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets" transform="translate(570, 97)">
	                            <g pointer-events="all" display="none" transform="translate(6, 6)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                        </g>
	                    </g>
	                </g>
	                <g id="svg-sid-1AEE8821-3C9D-4B37-BA7F-F25B140BFC63">
	                    <g class="stencils" transform="translate(420, 78.5)">
	                        <g class="me">
	                            <g pointer-events="fill" oryx:minimumSize="50 40" id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307" title="用户任务">
	                                <rect id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307text_frame" oryx:anchors="bottom top right left" x="1" y="1" width="66" height="64" rx="10" ry="10" stroke="none" stroke-width="0" fill="none"/>
	                                <rect id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307bg_frame" oryx:resize="vertical horizontal" x="0" y="0" width="72" height="65" rx="10" ry="10" stroke="#bbbbbb" stroke-width="1" fill="#f9f9f9"/>
	                                <text font-size="12" id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307text_name" x="36" y="32" oryx:align="middle center" oryx:fittoelem="text_frame" stroke="#373e48" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(0 36 32)" oryx:fontSize="12" text-anchor="middle">
	                                    <tspan x="36" y="32" dy="5">人工节点</tspan>
	                                </text>
	                                <g id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307userTask" transform="translate(3,3)">
	                                    <path oryx:anchors="top left" style="fill:#d1b575;stroke:none;" d="m 1,17 16,0 0,-1.7778 -5.333332,-3.5555 0,-1.7778 c 1.244444,0 1.244444,-2.3111 1.244444,-2.3111 l 0,-3.0222 C 12.555557,0.8221 9.0000001,1.0001 9.0000001,1.0001 c 0,0 -3.5555556,-0.178 -3.9111111,3.5555 l 0,3.0222 c 0,0 0,2.3111 1.2444443,2.3111 l 0,1.7778 L 1,15.2222 1,17 17,17" id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_17"/>
	                                </g>
	                                <g id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307parallel" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" d=" M32 55  v8  M36 55  v8  M40 55  v8 " stroke-width="2" id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_18"/>
	                                </g>
	                                <g id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307sequential" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" stroke-width="2" d=" M31.72 61  h10  M31.72 57  h10  M31.72 53  h10 " id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_19"/>
	                                </g>
	                                <g id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307compensation" display="none">
	                                    <path oryx:anchors="bottom" fill="none" stroke="#bbbbbb" d=" M44.64 59  L48.64 55  L48.64 63  L44.64 59  L44.64 55  L40.64 59  L44.64 63  L44.64 59 " stroke-width="1" id="sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_sid-27FB3C93-77F2-4E60-9DCE-CD0B80B74307_20"/>
	                                </g>
	                            </g>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets" transform="translate(420, 78.5)">
	                            <g pointer-events="all" display="none" transform="translate(-7, 8.25)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(-7, 24.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(-7, 40.75)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(10, 56)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(28, 56)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(46, 56)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(63, 8.25)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(63, 24.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(63, 40.75)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(10, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(28, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(46, -7)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                            <g pointer-events="all" display="none" transform="translate(28, 24.5)">
	                                <circle cx="8" cy="8" r="4" stroke="none" fill="red" fill-opacity="0.3"/>
	                            </g>
	                        </g>
	                    </g>
	                </g>
	            </g>
	            <g class="edge">
	                <g id="svg-sid-DF57E19F-95D6-4F0A-B5A8-D04CF7C9E834">
	                    <g class="stencils">
	                        <g class="me">
	                            <g pointer-events="painted">
	                                <path id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517_1" d="M217.77734375 111L269.52734375 111 " stroke="#585858" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" marker-start="url(#sid-104F2267-8E5A-486F-9F69-FD0CE3506517start)" marker-end="url(#sid-104F2267-8E5A-486F-9F69-FD0CE3506517end)"/>
	                            </g>
	                            <text id="sid-104F2267-8E5A-486F-9F69-FD0CE3506517text_name" x="225" y="103" oryx:edgePosition="startTop" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(360 217 111)" oryx:fontSize="12" text-anchor="start"/>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets"/></g>
	                </g>
	                <g id="svg-sid-27C91C2A-228A-44B8-A646-DB2EA6948F6E">
	                    <g class="stencils">
	                        <g class="me">
	                            <g pointer-events="painted">
	                                <path id="sid-767EB326-704F-4488-9FC2-B3C9AC630419_1" d="M493 111L570 111 " stroke="#585858" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" marker-start="url(#sid-767EB326-704F-4488-9FC2-B3C9AC630419start)" marker-end="url(#sid-767EB326-704F-4488-9FC2-B3C9AC630419end)"/>
	                            </g>
	                            <text id="sid-767EB326-704F-4488-9FC2-B3C9AC630419text_name" x="501" y="103" oryx:edgePosition="startTop" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(360 493 111)" oryx:fontSize="12" text-anchor="start"/>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets"/></g>
	                </g>
	                <g id="svg-sid-D2857D5D-261B-4845-807D-02723888D842">
	                    <g class="stencils">
	                        <g class="me">
	                            <g pointer-events="painted">
	                                <path id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62_1" d="M350.921875 111L419.640625 111 " stroke="#585858" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" marker-start="url(#sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62start)" marker-end="url(#sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62end)"/>
	                            </g>
	                            <text id="sid-B375DFBB-FAEA-490D-B73C-CE80E89C9E62text_name" x="358" y="103" oryx:edgePosition="startTop" stroke-width="0pt" letter-spacing="-0.01px" transform="rotate(360 350 111)" oryx:fontSize="12" text-anchor="start"/>
	                        </g>
	                        <g class="children" style="overflow:hidden"/>
	                        <g class="edge"/></g>
	                    <g class="controls">
	                        <g class="dockers"/>
	                        <g class="magnets"/></g>
	                </g>
	            </g>
	        </g>
	        <g class="svgcontainer">
	            <g display="none" transform="translate(416, 74.5)">
	                <rect x="0" y="0" stroke-width="1" stroke="#777777" fill="none" stroke-dasharray="2,2" pointer-events="none" width="80" height="73"/>
	            </g>
	            <g display="none">
	                <path stroke-width="1" stroke="silver" fill="none" stroke-dasharray="5,5" pointer-events="none"/>
	            </g>
	            <g display="none">
	                <path stroke-width="1" stroke="silver" fill="none" stroke-dasharray="5,5" pointer-events="none"/>
	            </g>
	            <g/></g>
	    </g>
	</svg>



转载请注明原地址，朱肖磊的博客：[http://zhuxiaolei.github.io](http://zhuxiaolei.github.io) 谢谢！
