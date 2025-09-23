<ul>
<li>이벤트 : <strong>사용자가 웹 브라우저에서 DOM 요소들과 상호 작용</strong>하는 것<ul>
<li><code>onmouseover</code> : 마우스 커서를 올렸을 때 이벤트</li>
<li><code>onClick</code> : 클릭했을 때 이벤트</li>
<li><code>onchange</code> : Form 요소의 값이 바뀔 때 이벤트</li>
</ul>
</li>
</ul>
<h4 id="✍️-html의-이벤트-핸들링---testhtml">✍️ HTML의 이벤트 핸들링 - test.html</h4>
<pre><code class="language-html">&lt;!DOCTYPE html&gt;
&lt;html&gt;
  &lt;head&gt;
    &lt;meta charset=&quot;utf-8&quot;&gt;
    &lt;meta name=&quot;viewport&quot; content=&quot;width=device-width&quot;&gt;
    &lt;title&gt;JS Bin&lt;/title&gt;
  &lt;/head&gt;
  &lt;body&gt;
    &lt;button onclick=&quot;alert('excuted')&quot;&gt;
      Click Me
    &lt;/button&gt;
  &lt;/body&gt;
&lt;/html&gt;</code></pre>
<h4 id="🖥️-실행-화면">🖥️ 실행 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/807ab05e-7e3c-48ad-bb31-b901be11d173/image.png" /></p>
<ul>
<li>버튼 클릭 시 <code>alert</code> 함수를 사용하여 메시지 박스 출력</li>
<li><strong><code>HTML</code>에서는 이벤트를 실행하기 위해 <code>&quot; &quot;</code> 사이에 JS 코드 작성</strong></li>
</ul>
<hr />
<h1 id="41-리액트의-이벤트-시스템">4.1 리액트의 이벤트 시스템</h1>
<ul>
<li>HTML 이벤트와 인터페이스가 동일하여 비슷한 사용법<pre><code class="language-javascript">import React, { useState } from 'react';
</code></pre>
</li>
</ul>
<p>const Say = () =&gt; {
    const [message, setMessage] = useState('');
    const onClickEnter = () =&gt; setMessage('안녕하세요!');
    const onClickLeave = () =&gt; setMessage('안녕히 가세요!');</p>
<pre><code>const [color, setColor] = useState('black');
return (
    &lt;div&gt;
        &lt;button onClick={onClickEnter}&gt;입장&lt;/button&gt;
        &lt;button onClick={onClickLeave}&gt;퇴장&lt;/button&gt;
        (...)</code></pre><h2 id="">```</h2>
<h2 id="411-이벤트를-사용할-때-주의-사항">4.1.1 이벤트를 사용할 때 주의 사항</h2>
<h4 id="1-이벤트-이름은-카멜-표기법으로-작성">1. 이벤트 이름은 카멜 표기법으로 작성</h4>
<ul>
<li>HTML의 <code>onclick</code> -&gt; <code>onClick</code></li>
<li>HTML의 <code>onkeyup</code> -&gt; <code>onKeyUp</code><h4 id="2-이벤트에-실행할-js-코드를-전달하는-것이-아닌-함수-형태의-값-전달">2. 이벤트에 실행할 JS 코드를 전달하는 것이 아닌 함수 형태의 값 전달</h4>
</li>
<li>HTML : <code>&quot; &quot;</code> 안에 실행할 코드 작성</li>
<li>리액트 : 함수 형태의 객체 전달<ol>
<li>화살표 함수 문법으로 함수 전달 </li>
<li>렌더링 부분 외부에 미리 만들어서 전달<h4 id="3-dom-요소에만-이벤트-설정-가능">3. DOM 요소에만 이벤트 설정 가능</h4>
</li>
</ol>
</li>
<li><code>div</code>, <code>button</code>, <code>input</code>, <code>form</code>, <code>span</code> 등의 DOM 요소에는 이벤트 설정 가능<ul>
<li>직접 만든 컴포넌트에는 이벤트를 자체적으로 설정 불가능<ul>
<li>ex) <code>MyComponent</code>에 <code>onClick</code> 값을 설정한다면 <code>MyComponent</code>를 클릭할 때 함수를 실행하는 것이 아닌 이름이 <code>onClick</code>인 <code>props</code>를 <code>MyComponent</code>에게 전달하는 역할</li>
</ul>
</li>
<li>전달받은 props를 컴포넌트 내부의 DOM 이벤트로 설정하는 것은 가능<pre><code class="language-jsx">&lt;div onClick={this.props.onClick}&gt;
     { /* (...) */ }
&lt;/div&gt;</code></pre>
<h2 id="412-이벤트-종류">4.1.2 이벤트 종류</h2>
</li>
</ul>
</li>
<li>리액트에서 지원하는 이벤트 종류<ul>
<li>Clipboard</li>
<li>Composition</li>
<li>Keyboard</li>
<li>Focus</li>
<li>Form</li>
<li>Mouse</li>
<li>Selection</li>
<li>Touch</li>
<li>UI</li>
<li>Wheel</li>
<li>Media</li>
<li>Image</li>
<li>Animation</li>
<li>Transition</li>
</ul>
</li>
</ul>