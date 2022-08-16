---
title: Element.children
slug: Web/API/Element/children
---
<p>{{ APIRef("DOM") }}</p>

<p><code><strong>Element.children</strong></code> 是一个只读属性，返回 一个 Node 的子{{domxref("Element","elements")}} ，是一个动态更新的 {{domxref("HTMLCollection")}}。</p>

<h2 id="Syntax_and_values">语法</h2>

<pre>var <em>children</em> = <em>node</em>.children;</pre>

<pre class="eval">var <em>elList</em> = elementNodeReference.children;
</pre>

<h2 id="Notes">备注</h2>

<p><code>children</code> 属性为只读属性，对象类型为 {{ domxref("HTMLCollection") }}，你可以使用 <code>elementNodeReference.children[1].nodeName</code> 来获取某个子元素的标签名称。</p>

<h2 id="Example">例子</h2>

<pre class="brush: js">// parg 是一个指向&lt;p&gt;元素的对象引用
if (parg.childElementCount)
// 检查这个&lt;p&gt;元素是否有子元素
// 译者注:childElementCount 有兼容性问题
 {
   var children = parg.children;
   for (var i = 0; i &lt; children.length; i++)
   {
   // 通过 children[i] 来获取每个子元素
   // 注意:List 是一个 live 的 HTMLCollection 对象，在这里添加或删除 parg 的子元素节点，都会立即改变 List 的值。
   };
 };
</pre>

<h2 id="规范">规范</h2>

{{Specifications}}

<h2 id="浏览器兼容性">浏览器兼容性</h2>

{{Compat("api.Element.children")}}

<h2 id="相关链接">相关链接</h2>

<ul>
 <li>The {{domxref("Element")}} and {{domxref("ChildNode")}} pure interfaces.</li>
 <li>
  <div class="syntaxbox">Object types implementing this pure interface: {{domxref("Document")}}, {{domxref("Element")}}, and {{domxref("DocumentFragment")}}.</div>
 </li>
</ul>