---
title: AudioContext.destination
slug: Web/API/BaseAudioContext/destination
---
<p>{{ APIRef("Web Audio API") }}</p>

<div>
<p>{{ domxref("AudioContext") }}的<code>destination属性返回一个</code>{{ domxref("AudioDestinationNode") }}表示 context 中所有音频（节点）的最终目标节点，一般是音频渲染设备，比如扬声器。</p>
</div>

<h2 id="语法">语法</h2>

<pre class="brush: js">var audioCtx = new AudioContext();
gainNode.connect(audioCtx.destination);</pre>

<h3 id="返回值">返回值</h3>

<p>An {{ domxref("AudioDestinationNode") }}.</p>

<h2 id="例子">例子</h2>

<div class="note">
<p><strong>注意</strong>：想要完整的例子，可以去看看<a href="https://github.com/mdn/">MDN Github repo</a>的 DEMO，比如<a href="https://github.com/mdn/panner-node">panner-node</a></p>
</div>

<pre class="brush: js; highlight[8]">var AudioContext = window.AudioContext || window.webkitAudioContext;
var audioCtx = new AudioContext();
// Older webkit/blink browsers require a prefix

var oscillatorNode = audioCtx.createOscillator();
var gainNode = audioCtx.createGain();

oscillatorNode.connect(gainNode);
gainNode.connect(audioCtx.destination);
</pre>

<h2 id="规范">规范</h2>

{{Specifications}}

<h2 id="浏览器兼容性">浏览器兼容性</h2>

{{Compat("api.BaseAudioContext.destination")}}

<h2 id="另见">另见</h2>

<ul>
 <li><a href="/en-US/docs/Web_Audio_API/Using_Web_Audio_API">Using the Web Audio API</a></li>
</ul>