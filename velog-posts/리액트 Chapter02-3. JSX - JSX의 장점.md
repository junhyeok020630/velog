<h1 id="23-jsx의-장점">2.3 JSX의 장점</h1>
<h2 id="231-보기-쉽고-익숙하다">2.3.1 보기 쉽고 익숙하다</h2>
<ul>
<li>일반 JS로 작성한 코드와 비교해 훨씬 <strong>가독성이 높고 작성하기 쉬움</strong><ul>
<li>HTML 코드 작성과 유사</li>
<li>JS로 작성 시 요소들을 일일이 생성해야 함</li>
</ul>
</li>
</ul>
<hr />
<h2 id="232-더욱-높은-활용도">2.3.2 더욱 높은 활용도</h2>
<ul>
<li><p><code>div</code>나 <code>span</code>같은 HTML 태그 뿐만 아니라 <strong>컴포넌트도 JSX 안에서 작성 가능</strong></p>
<ul>
<li><p><code>index.js</code>에서 <code>APP</code> 컴포넌트 사용하기</p>
<pre><code class="language-javascript">
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  &lt;React.StrictMode&gt;
    &lt;App /&gt;
  &lt;/React.StrictMode&gt;
);
</code></pre>
</li>
</ul>
<pre><code>* APP **컴포넌트를 HTML 태그처럼 사용**
---</code></pre></li>
<li><p><code>ReactDOM.createRoot(document.getElementById('root'));
  root.render()</code></p>
<ul>
<li><strong>컴포넌트를 페이지에 렌더링</strong>하는 역할</li>
<li>react-dom 모듈을 불러와 사용 가능</li>
<li>함수의 파라미터 : <strong>페이지에 렌더링할 내용</strong>을 JSX 형태로 작성</li>
<li><code>document.getElementById('root')</code> : 파라미터의 JSX를 <strong>렌더링할 document 내부 요소</strong> - <strong>id가 root인 요소</strong>에 렌더링(index.html내부에 존재)</li>
</ul>
<hr />
</li>
<li><p><code>React.StrictMode</code></p>
<ul>
<li>리액트 프로젝트에서 리액트의 레거시 기능들을 사용하지 못하게 하는 기능</li>
<li>문자열 ref, componentWillMount 같이 옛날 기능을 사용했을 때 경고 출력</li>
</ul>
</li>
</ul>