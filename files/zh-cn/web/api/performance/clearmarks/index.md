---
title: Performance.clearMarks()
slug: Web/API/Performance/clearMarks
---
<div>{{APIRef("User Timing API")}}</div>

<p><strong><code>clearMarks()</code></strong> 这个方法可以从浏览器的 performance entry 缓存中移除声明的标记。如果调用这个方法时没有传递参数， 则所有带有{{domxref("PerformanceEntry.entryType","entry type")}}这类标记的{{domxref("PerformanceEntry","performance entries")}} 将从 performance entry 缓存区中被移除。</p>

<h2 id="用法">用法</h2>

<pre class="syntaxbox"><em>performance</em>.clearMarks();
<em>performance</em>.clearMarks(name);
</pre>

<h3 id="参数">参数</h3>

<dl>
 <dt>name {{optional_inline}}</dt>
 <dd>{{domxref("DOMString")}} 表示时间戳的名字，如果没有提供这个参数， 则所有带有{{domxref("PerformanceEntry.entryType","entry type")}}这类标记的{{domxref("PerformanceEntry","performance entries")}} 将从 performance entry 缓存区中被移除。</dd>
</dl>

<h3 id="返回值">返回值</h3>

<p>无</p>

<h2 id="例子">例子</h2>

<p>下面的例子演示<code>clearMarks() 的两种用法。</code></p>

<pre class="brush: js">function clear_mark(name) {
  if (performance.clearMarks === undefined) {
    console.log("performance.clearMarks Not supported");
    return;
  }
  //移除所有标记了此名称的 peformance entry
  performance.clearMarks(name);
}
function clear_all_marks() {
  if (performance.clearMarks === undefined) {
    console.log("performance.clearMarks Not supported");
    return;
  }
  //从 performance 缓冲区中移除所有标记的 performance entry
  performance.clearMarks();
}
</pre>

<h2 id="规范">规范</h2>

{{Specifications}}

<h2 id="浏览器兼容性">浏览器兼容性</h2>

{{Compat("api.Performance.clearMarks")}}