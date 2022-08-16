---
title: AudioContext.createScriptProcessor()
slug: Web/API/BaseAudioContext/createScriptProcessor
---
<p>{{APIRef("Web Audio API")}}{{deprecated_header}}</p>

<div>
<p>{{ domxref("AudioContext") }} 接口的<code>createScriptProcessor()</code> 方法创建一个{{domxref("ScriptProcessorNode")}} 用于通过 JavaScript 直接处理音频。</p>
</div>

<h2 id="语法">语法</h2>

<pre class="brush: js">var audioCtx = new AudioContext();
myScriptProcessor = audioCtx.createScriptProcessor(<code>bufferSize</code>, <code>numberOfInputChannels</code>, <code>numberOfOutputChannels</code>);</pre>

<h3 id="Parameters">参数</h3>

<dl>
 <dt><code>bufferSize</code></dt>
 <dd>缓冲区大小，以样本帧为单位。具体来讲，缓冲区大小必须是下面这些值当中的某一个：256, 512, 1024, 2048, 4096, 8192, 16384. 如果不传，或者参数为 0，则取当前环境最合适的缓冲区大小，取值为 2 的幂次方的一个常数，在该 node 的整个生命周期中都不变。<br>
 该取值控制着<code>audioprocess事件被分派的频率，以及每一次调用多少样本帧被处理</code>. 较低 bufferSzie 将导致一定的延迟。较高的 bufferSzie 就要注意避免音频的崩溃和故障。推荐作者不要给定具体的缓冲区大小，让系统自己选一个好的值来平衡延迟和音频质量。</dd>
 <dt><code>numberOfInputChannels</code></dt>
 <dd>值为整数，用于指定输入 node 的声道的数量，默认值是 2，最高能取 32.</dd>
 <dt><code>numberOfOutputChannels</code></dt>
 <dd>值为整数，用于指定输出 node 的声道的数量，默认值是 2，最高能取 32.</dd>
</dl>

<div class="warning">
<p><strong>警告：</strong> Webkit (version 31) 要求调用这个方法的时候必须传入一个有效的 bufferSize .</p>
</div>

<div class="note">
<p><strong>备注：</strong> <code>numberOfInputChannels</code>和<code>numberOfOutputChannels</code>的值不能同时为0，二者同时为0是无效的</p>
</div>

<h3 id="Description">返回</h3>

<p>A {{domxref("ScriptProcessorNode")}}.</p>

<h2 id="示例">示例</h2>

<p><code>下面的例子展示了一个ScriptProcessorNode的基本用法，数据源取自</code> {{ domxref("AudioContext.decodeAudioData") }}, 给每一个音频样本加一点白噪声，然后通过{{domxref("AudioDestinationNode")}}播放 (其实这个就是系统的扬声器)。 对于每一个声道和样本帧，在把结果当成输出样本之前，<code>scriptNode.onaudioprocess方法关联</code><code>audioProcessingEvent</code> ，并用它来遍历每输入流的每一个声道，和每一个声道中的每一个样本，并添加一点白噪声。</p>

<div class="note">
<p><strong>备注：</strong> 完整的示例参照 <a href="https://mdn.github.io/webaudio-examples/script-processor-node/">script-processor-node</a> github (查看源码 <a href="https://github.com/mdn/webaudio-examples/blob/master/script-processor-node/index.html">source code</a>.)</p>
</div>

<pre class="brush: js">var myScript = document.querySelector('script');
var myPre = document.querySelector('pre');
var playButton = document.querySelector('button');

// Create AudioContext and buffer source
var audioCtx = new AudioContext();
source = audioCtx.createBufferSource();

// Create a ScriptProcessorNode with a bufferSize of 4096 and a single input and output channel
var scriptNode = audioCtx.createScriptProcessor(4096, 1, 1);
console.log(scriptNode.bufferSize);

// load in an audio track via XHR and decodeAudioData

function getData() {
  request = new XMLHttpRequest();
  request.open('GET', 'viper.ogg', true);
  request.responseType = 'arraybuffer';
  request.onload = function() {
    var audioData = request.response;

    audioCtx.decodeAudioData(audioData, function(buffer) {
    myBuffer = buffer;
    source.buffer = myBuffer;
  },
    function(e){"Error with decoding audio data" + e.err});
  }
  request.send();
}

// Give the node a function to process audio events
scriptNode.onaudioprocess = function(audioProcessingEvent) {
  // The input buffer is the song we loaded earlier
  var inputBuffer = audioProcessingEvent.inputBuffer;

  // The output buffer contains the samples that will be modified and played
  var outputBuffer = audioProcessingEvent.outputBuffer;

  // Loop through the output channels (in this case there is only one)
  for (var channel = 0; channel &lt; outputBuffer.numberOfChannels; channel++) {
    var inputData = inputBuffer.getChannelData(channel);
    var outputData = outputBuffer.getChannelData(channel);

    // Loop through the 4096 samples
    for (var sample = 0; sample &lt; inputBuffer.length; sample++) {
      // make output equal to the same as the input
      outputData[sample] = inputData[sample];

      // add noise to each output sample
      outputData[sample] += ((Math.random() * 2) - 1) * 0.2;
    }
  }
}

getData();

// wire up play button
playButton.onclick = function() {
  source.connect(scriptNode);
  scriptNode.connect(audioCtx.destination);
  source.start();
}

// When the buffer source stops playing, disconnect everything
source.onended = function() {
  source.disconnect(scriptNode);
  scriptNode.disconnect(audioCtx.destination);
}
</pre>

<h2 id="规范">规范</h2>

<p>自 2014 年 8 月 29 日 <a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createscriptprocessor">Web Audio API 规范</a>发布以来，此特性已被弃用。它不再有望成为标准。</p>

<p>它已被 <a href="/zh-CN/docs/Web/API/AudioWorklet">AudioWorklet</a> 和 {{domxref("AudioWorkletNode")}} 接口所取代。</p>

<h2 id="浏览器兼容性">浏览器兼容性</h2>

{{Compat}}

<h2 id="See_also">See also</h2>

<ul>
 <li><a href="/en-US/docs/Web_Audio_API/Using_Web_Audio_API">Using the Web Audio API</a></li>
</ul>