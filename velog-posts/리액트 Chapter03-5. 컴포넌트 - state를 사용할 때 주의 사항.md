<h1 id="35-state를-사용할-때-주의-사항">3.5 state를 사용할 때 주의 사항</h1>
<h4 id="⚠️state-값을-바꾸어야-할-때는-setstate-혹은-usestate의-세터-함수를-사용해야-한다">⚠️state 값을 바꾸어야 할 때는 setState 혹은 useState의 세터 함수를 사용해야 한다.</h4>
<h4 id="❌-잘못된-코드">❌ 잘못된 코드</h4>
<pre><code class="language-jsx">// 클래스형 컴포넌트에서
this.state.number = this.state.number +1;
this.state.array = this.array.push(2);
this.state.object.value = 5;

// 함수형 컴포넌트에서
const [object,setObject] = useState({a: 1, b: 1});
object.b = 2;</code></pre>
<hr />
<h3 id="❓배열이나-객체를-업데이트-할-때는">❓배열이나 객체를 업데이트 할 때는?</h3>
<h4 id="❗배열이나-객체-사본을-만들어-사본에-값을-업데이트-하고-사본의-상태를-setstate나-세터-함수로-업데이트">❗배열이나 객체 사본을 만들어 사본에 값을 업데이트 하고 사본의 상태를 setState나 세터 함수로 업데이트</h4>
<h4 id="✍️-사본을-만들어-업데이트하기">✍️ 사본을 만들어 업데이트하기</h4>
<pre><code class="language-jsx">// 객체 다루기
const object = { a: 1, b: 2, c: 3 };
const nextObject = { ...object, b: 2 }; // 사본을 만들어서 b 값만 덮어 쓰기

// 배열 다루기
const array = [
  { id: 1, value: true },
  { id: 2, value: true },
  { id: 3, value: false }
];
let nextArray = array.concat({ id: 4 }); // 새 항목 추가
nextArray.filter(item =&gt; item.id !== 2 ); // id가 2인 항목 제거
nextArray.map(item =&gt; (item.id === 1 ? {...item, value: false } : item)); // id가 1인 항목의 value를 false로 설정</code></pre>
<ul>
<li>객체 사본 생성 : <code>spread</code> 연산자 사용 - <code>...</code></li>
<li>배열 사본 생성 : 배열 내장 함수 사용</li>
</ul>
<hr />
<h1 id="36-컴포넌트-정리">3.6 컴포넌트 정리</h1>
<ul>
<li>컴포넌트를 만들어서 내보내고 불러오는 방법 : <code>import</code>와 <code>export</code></li>
<li><code>props</code> 와 <code>state</code><ul>
<li>둘 다 컴포넌트에서 사용하거나 렌더링할 데이터를 담고 있음</li>
<li><strong><code>props</code> : 부모 컴포넌트가 설정</strong></li>
<li><strong><code>state</code> : 컴포넌트 자체적으로 지닌 값 - 컴포넌트 내부에서 값 업데이트 가능</strong></li>
</ul>
</li>
</ul>
<blockquote>
<h3 id="❓-props를-사용하면-무조건-값이-고정적일까">❓ props를 사용하면 무조건 값이 고정적일까?</h3>
</blockquote>
<h4 id="❗부모-컴포넌트의-state를-자식-컴포넌트의-props로-전달하여-props를-유동적으로-사용-가능">❗부모 컴포넌트의 state를 자식 컴포넌트의 props로 전달하여 props를 유동적으로 사용 가능</h4>
<ol>
<li>부모 컴포넌트의 <strong><code>state</code>를 자식 컴포넌트의 <code>props</code>로</strong> 전달</li>
<li>자식 컴포넌트에서 특정 이벤트 발생 시 <strong>부모 컴포넌트의 메서드 호출</strong>
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/f55498d5-e2da-4b61-81cf-b1bfe92c7313/image.png" /></li>
</ol>
<ul>
<li><code>state</code>와 <code>useState</code><ul>
<li>리액트 측에서 함수 컴포넌트와 Hooks 사용 권장</li>
<li><code>useState</code>를 적극 활용</li>
</ul>
</li>
</ul>