<ul>
<li>리액트를 사용하여 UI를 설계할 때 사용자가 볼 수 있는 요소는 여러 컴포넌트로 구성</li>
<li>일정 관리 애플리케이션
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/0dc36cd1-bc21-4c00-9802-516e34beddb4/image.png" /></li>
</ul>
<h4 id="네가지-컴포넌트로-구성">네가지 컴포넌트로 구성</h4>
<ol>
<li>전체적인 틀을 잡아주는 <code>TodoTemplate</code> 컴포넌트<ul>
<li>화면 중앙 사각형 레이아웃</li>
</ul>
</li>
<li>새로운 항목을 추가할 수 있는 <code>TodoInput</code> 컴포넌트<ul>
<li>화면의 검정색 영역</li>
</ul>
</li>
<li>할 일 항목을 여러개 보여주는 <code>TodoList</code> 컴포넌트</li>
<li><code>TodoList</code>에서 각 항목을 보여주기 위해 사용되는 <code>TodoItem</code> 컴포넌트</li>
</ol>
<h3 id="컴포넌트의-기능">컴포넌트의 기능</h3>
<ul>
<li>단순 템플릿 이상의 기능 제공</li>
</ul>
<ol>
<li><strong>데이터가 주어졌을 때 이에 맞춰 UI 생성</strong></li>
<li><strong>라이프사이클 API</strong>를 이용해 <strong>컴포넌트가 화면에 나타날 때, 사라질 때, 변화가 일어날 때 작업 처리</strong> 가능</li>
<li>*<em>임의 메서드를 만들어 특별한 기능 추가 *</em> 가능</li>
</ol>
<hr />
<h1 id="31-클래스형-컴포넌트">3.1 클래스형 컴포넌트</h1>
<ul>
<li><p>2장에서 보았던 App 컴포넌트는 <strong>함수형 컴포넌트</strong></p>
<h4 id="✍️-함수형-컴포넌트">✍️ 함수형 컴포넌트</h4>
<pre><code class="language-javascript">import './App.css';

function App() {
  const name = '리액트';
  return &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;;
}

export default App;</code></pre>
<h4 id="✍️-app-컴포넌트를-클래스형-컴포넌트로-변경">✍️ App 컴포넌트를 클래스형 컴포넌트로 변경</h4>
<pre><code class="language-javascript">import './App.css';
import React, { Component } from 'react';

class App extends Component {
  render() {
    const name = 'react';
    return &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;;
  }
}

export default App;</code></pre>
</li>
<li><p>함수 컴포넌트와 동일한 역할 수행</p>
</li>
<li><p>클래스형 컴포넌트를 사용하는 이유</p>
<ul>
<li><strong>state 기능 및 라이프사이클 기능</strong> 사용 가능</li>
<li><strong>임의 메서드 정의</strong> 가능</li>
</ul>
</li>
</ul>
<hr />
<blockquote>
<h3 id="es6의-클래스-문법">ES6의 클래스 문법</h3>
<ul>
<li><p>ES6 이전에는 JS에 클래스가 없었음</p>
<ul>
<li>클래스 개념을 prototype을 통해 구현<h4 id="✍️-es6-이전-문법">✍️ ES6 이전 문법</h4>
<pre><code class="language-javascript">function Dog(name) {
this.name = name;
}
</code></pre>
</li>
</ul>
<p>Dog.prototype.say = function() {
 console.log(this.name + ': 멍멍');
}
var dog = new Dog('검둥이');
dog.say(); // 검둥이 : 멍멍</p>
<pre><code>#### ES6 이후 문법
```javascript
class Dog {
 constructor(name) {
    this.name = name;
 }
 say() {
    console.log(this.name + ': 멍멍');
 }
}

const dog = new Dog('흰둥이');
dog.say(); // 흰둥이: 멍멍</code></pre></li>
</ul>
</blockquote>
<hr />
<h2 id="클래스형-컴포넌트-유의-사항">클래스형 컴포넌트 유의 사항</h2>
<ul>
<li>클래스형 컴포넌트에서 <code>render</code> 함수는 필수<ul>
<li><code>render</code> 함수 내부에서 렌더링할 JSX 반환</li>
</ul>
</li>
</ul>
<hr />
<h2 id="함수-컴포넌트와-클래스-컴포넌트의-차이점">함수 컴포넌트와 클래스 컴포넌트의 차이점</h2>
<h3 id="👍-함수-컴포넌트의-장점">👍 함수 컴포넌트의 장점</h3>
<ul>
<li>클래스형 컴포넌트보다 선언하기 편리함</li>
<li>메모리 자원 클래스형 컴포넌트보다 절약 가능</li>
<li>프로젝트 완성 후 배포시에도 함수 컴포넌트가 결과물의 파일 크기가 더 작음<ul>
<li>성능과 파일 크기 면에서 큰 차이가 없으므로 유의미한 정도는 아님</li>
</ul>
</li>
</ul>
<h3 id="👎-함수-컴포넌트의-단점">👎 함수 컴포넌트의 단점</h3>
<ul>
<li><code>state</code>와 <code>라이프사이클 API</code>의 사용 불가<ul>
<li>리액트 16.8 이후 *<em><code>Hooks</code> 기능으로 해결됨 *</em><ul>
<li>클래스형 컴포넌트와 완전히 동일하지는 않지만 유사한 작업 수행 가능</li>
</ul>
</li>
</ul>
</li>
</ul>
<h4 id="리액트-공식-메뉴얼에서는-함수-컴포넌트와-hooks-사용-권장">리액트 공식 메뉴얼에서는 함수 컴포넌트와 Hooks 사용 권장</h4>
<blockquote>
<h4 id="우선-클래스형-컴포넌트로-리액트의-기본기를-익히고-후반부에-함수-컴포넌트와-hooks를-기반으로-컴포넌트를-작성하자">우선 클래스형 컴포넌트로 리액트의 기본기를 익히고 후반부에 함수 컴포넌트와 Hooks를 기반으로 컴포넌트를 작성하자!!</h4>
</blockquote>