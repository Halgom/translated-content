---
title: SVGGeometryElement.getPointAtLength()
slug: Web/API/SVGGeometryElement/getPointAtLength
---
<div>{{APIRef("SVG")}}</div>

<p><code><strong>SVGGeometryElement.getPointAtLength()</strong></code> 方法沿路径返回给定距离的点。</p>

<div class="note">
<p><strong>Note:</strong> This method was originally part of the {{domxref("SVGPathElement")}} interface. SVG 2 introduced the {{domxref("SVGGeometryElement")}} interface and moved the property to it.</p>
</div>

<h2 id="Syntax">Syntax</h2>

<pre class="syntaxbox">DOMPoint <var>someElement</var>.getPointAtLength(float <var>distance</var>);
</pre>

<h3 id="Parameters">Parameters</h3>

<dl>
 <dt>distance</dt>
 <dd>A float referring to the distance along the path.</dd>
</dl>

<h3 id="Return_value">Return value</h3>

<p>A {{domxref("DOMPoint")}} indicating the point at a given distance along the path.</p>

<h2 id="Specifications">Specifications</h2>

{{Specifications}}

<h2 id="Browser_compatibility">Browser compatibility</h2>



<p>{{Compat("api.SVGGeometryElement.getPointAtLength")}}</p>