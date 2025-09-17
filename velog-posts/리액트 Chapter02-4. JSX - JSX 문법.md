<h1 id="24-jsx-문법">2.4 JSX 문법</h1>
<h2 id="241-감싸인-요소">2.4.1 감싸인 요소</h2>
<ul>
<li><p>컴포넌트에 여러 요소가 있다면 반드시 <strong>부모 요소 하나</strong>로 감싸야 한다.</p>
<h4 id="⚠️잘못된-코드">⚠️잘못된 코드</h4>
<pre><code class="language-javascript"> function App() {
   return (
     &lt;h1&gt;리액트 안녕!&lt;/h1&gt;
     &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
   );
 }

 export default App;</code></pre>
<ul>
<li>컴포넌트에 <code>h1</code>태그와 <code>h2</code> 두개의 요소 존재</li>
</ul>
<h4 id="❌-오류-문장">❌ 오류 문장</h4>
<pre><code>  SyntaxError: C:\ReactStudy2025-2\hello-react\src\App.js:
  Adjacent JSX elements must be wrapped in an enclosing tag. 
  Did you want a JSX fragment &lt;&gt;...&lt;/&gt;? (4:4)

  2 |   return ( 
  3 |     &lt;h1&gt;리액트 안녕!&lt;/h1&gt;
&gt; 4 |     &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
    |     ^
  5 |   );</code></pre><hr />
<h4 id="✍️-해결-코드">✍️ 해결 코드</h4>
<pre><code class="language-javascript">  function App() {
    return (
      &lt;div&gt;
        &lt;h1&gt;리액트 안녕!&lt;/h1&gt;
        &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
      &lt;/div&gt;
    );
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/df1217e9-a970-40db-900b-dcc3d3fb04b2/image.png" /></p>
</li>
</ul>
<blockquote>
<h3 id="❓리액트-컴포넌트에서는-왜-하나의-요소로-여러-개의-요소를-감싸주어야-할까">❓리액트 컴포넌트에서는 왜 하나의 요소로 여러 개의 요소를 감싸주어야 할까?</h3>
<p> ❗<strong>컴포넌트 내부에는 하나의 DOM 트리 구조로 이루어져야한다는 규칙 존재</strong> </p>
<blockquote>
<p>Virtual DOM에서 컴포넌트 변화를 감지해 낼 때 효율적으로 비교하기 위해</p>
</blockquote>
</blockquote>
<hr />
<h3 id="div-대신-fragment-사용-가능"><code>div</code> 대신 <code>Fragment</code> 사용 가능</h3>
<h4 id="✍️fragment-사용-코드">✍️<code>Fragment</code> 사용 코드</h4>
<pre><code class="language-javascript">
   import { Fragment } from &quot;react&quot;;

   function App() {
     return (
       &lt;Fragment&gt;
         &lt;h1&gt;리액트 안녕!&lt;/h1&gt;
         &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
       &lt;/Fragment&gt;
     );
   } 

   export default App;</code></pre>
<h4 id="✍️-간략화-코드">✍️ 간략화 코드</h4>
<pre><code class="language-javascript">
   import { Fragment } from &quot;react&quot;;

   function App() {
     return (
       &lt;&gt;
         &lt;h1&gt;리액트 안녕!&lt;/h1&gt;
         &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
       &lt;/&gt;
     );
   } 

   export default App;</code></pre>
<h4 id="🖥️-출력-화면-1">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/123414e5-c5f0-4597-8c63-7229e5aa0754/image.png" /></p>
<hr />
<h2 id="242-자바스크립트-표현">2.4.2 자바스크립트 표현</h2>
<ul>
<li><p>JSX 내부에서 <strong>자바스크립트 표현식 사용 가능</strong></p>
<ul>
<li><strong><code>{ }</code></strong> 로 JS 코드를 감싸 사용 가능<h4 id="✍️-javascript-값을-jsx안에-렌더링하기">✍️ javascript 값을 JSX안에 렌더링하기</h4>
</li>
</ul>
<pre><code class="language-javascript">  import { Fragment } from &quot;react&quot;;

  function App() {
    const name = '리액트';
    return (
      &lt;&gt;
        &lt;h1&gt;{name} 안녕!&lt;/h1&gt;
        &lt;h2&gt;잘 작동하니?&lt;/h2&gt;
      &lt;/&gt;
    );
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면-2">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/a505ac01-5eb1-4256-94e0-194acabc7ac4/image.png" /></p>
<hr />
<blockquote>
<h3 id="❓es6의-const와-let">❓ES6의 const와 let</h3>
<ul>
<li>const : 상수 선언 키워드</li>
<li>let : 변수 선언 키워드</li>
</ul>
<h4 id="⚠️es6-이전에는-var-사용">⚠️ES6 이전에는 var 사용</h4>
<ul>
<li>var의 scope는 함수 단위<pre><code class="language-javascript">function myFunction() {
  var a = &quot;hello&quot;;
   if(true) {
     var a = &quot;bye&quot;;
     console.log(a); //bye
   }
   console.log(a); // bye
}
myFunction();</code></pre>
</li>
<li>if 문 외부에서 a에 접근해도 변경된 값 출력<h4 id="❗let과-const는-scope가-블록-단위">❗let과 const는 scope가 블록 단위</h4>
<pre><code class="language-javascript">function myFunction() {
  let a = 1;
   if(true) {
     let a = 2;
     console.log(a); // 2
   }
   console.log(a); // 1
}
myFunction();</code></pre>
</li>
<li>if 문 내부의 a와 외부의 a는 다른 변수</li>
<li>⚠️ let과 const는 같은 블록 내부에서 사용 시 중복 선언 불가능</li>
</ul>
<blockquote>
<ul>
<li>var : ES6에서 사용할 일 없음</li>
<li>let : 한 번 선언한 후 값이 유동적으로 변할 수 있을 때 (ex. for문)</li>
<li>const : 한 번 설정한 후 변할 일이 없는 값에 사용</li>
</ul>
</blockquote>
</blockquote>
<hr />
<h2 id="243-if문-대신-조건부-연산자">2.4.3 If문 대신 조건부 연산자</h2>
<ul>
<li><p>JSX 내부의 JS 표현식에서 <strong><code>if</code>문 사용 불가능</strong></p>
</li>
<li><p>조건문이 필요할 때 사용하는 방법 2가지</p>
<ol>
<li>JSX 밖에서 if 문을 사용하여 사전에 값 설정</li>
<li><code>{ }</code> 내부에서 조건부 연산자(삼항 연산자 사용<h4 id="✍️-조건부-연산자-활용-코드">✍️ 조건부 연산자 활용 코드</h4>
<pre><code class="language-javascript">function App() {
const name = '리액트'; // '뤼액트'
return (
 &lt;div&gt;
   {name === '리액트' ? (
     &lt;h1&gt;리액트입니다.&lt;/h1&gt;
   ) : (
     &lt;h1&gt;리액트가 아닙니다.&lt;/h1&gt;
   )}
 &lt;/div&gt;
);
}
</code></pre>
</li>
</ol>
<p>export default App;</p>
<pre><code>#### 🖥️ 출력 화면(1) - name = '리액트'
</code></pre></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/4c809f5e-2417-4892-8e04-4a5b308886d9/image.png" /></p>
<h4 id="🖥️-출력-화면2---name--뤼액트">🖥️ 출력 화면(2) - name = '뤼액트'</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/4ea7aeab-dbb1-4179-9dfa-0a22937f6920/image.png" /></p>
<hr />
<h2 id="244-and-연산자를-사용한-조건부-렌더링">2.4.4 AND 연산자(&amp;&amp;)를 사용한 조건부 렌더링</h2>
<ul>
<li>특정 조건을 만족할 때 내용을 보여주고, 만족하지 않을 때 아무것도 렌더링하지 않음<h4 id="✍️-조건부-연산자를-활용한-구현">✍️ 조건부 연산자를 활용한 구현</h4>
</li>
</ul>
<pre><code class="language-javascript">  function App() {
    const name = '뤼액트';
    return (
      &lt;div&gt;
        {name === '리액트' ? &lt;h1&gt;리액트입니다.&lt;/h1&gt; : null}
      &lt;/div&gt;
    );
  }

  export default App;</code></pre>
<h4 id="✍️--연산자를-활용한-조건부-렌더링">✍️ <code>&amp;&amp;</code> 연산자를 활용한 조건부 렌더링</h4>
<pre><code class="language-javascript">  function App() {
    const name = '뤼액트'; // '리액트
    return (
      &lt;div&gt;
        {name === '리액트' &amp;&amp; &lt;h1&gt;리액트입니다.&lt;/h1&gt;}
      &lt;/div&gt;
    );
  }

  export default App;</code></pre>
<h4 id="🖥️-출력화면1---name--뤼액트">🖥️ 출력화면(1) - name = '뤼액트'</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/b3533248-33cc-4898-bce0-72188962c5c9/image.png" /></p>
<h4 id="🖥️-출력화면2---name--리액트">🖥️ 출력화면(2) - name = '리액트'</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/be8b3c1b-0a37-4c32-80fe-e9574b4bec67/image.png" /></p>
<blockquote>
<h3 id="❓--연산자로-조건부-렌더링이-가능한-이유">❓ &amp;&amp; 연산자로 조건부 렌더링이 가능한 이유</h3>
<h4 id="❗-리액트에서-false를-렌더링할-때는-null과-마찬가지로-아무것도-나타나지-않는다">❗ 리액트에서 false를 렌더링할 때는 null과 마찬가지로 아무것도 나타나지 않는다.</h4>
<blockquote>
<p><strong>⚠️ 0은 falsy한 값이지만 예외적으로 화면에 출력한다.</strong></p>
<ul>
<li>✍️ 예시<pre><code class="language-javascript">const number = 0;
return number &amp;&amp; &lt;div&gt;내용&lt;/div&gt;</code></pre>
</li>
<li>🖥️ 출력 화면
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/2e5ca177-fb16-4d22-8929-70a96ba2b25a/image.png" /></li>
</ul>
</blockquote>
<hr />
<h3 id="❓-jsx는-언제-괄호로-감싸야-할까">❓ JSX는 언제 괄호로 감싸야 할까?</h3>
<h4 id="❗-주로-여러-줄로-작성할-때-괄호로-감싼다-필수는-아니고-선택-사항">❗ 주로 여러 줄로 작성할 때 괄호로 감싼다. (필수는 아니고 선택 사항)</h4>
</blockquote>
<hr />
<h2 id="245-undefined를-렌더링하지-않기">2.4.5 undefined를 렌더링하지 않기</h2>
<h4 id="⚠️-리액트-컴포넌트에서는-함수에서-undefined만-반환하여-렌더링-하면-오류-발생">⚠️ 리액트 컴포넌트에서는 함수에서 undefined만 반환하여 렌더링 하면 오류 발생</h4>
<h4 id="✍️-undefined만-반환하는-코드">✍️ undefined만 반환하는 코드</h4>
<pre><code class="language-javascript">  import './App.css';

  function App() {
    const name = undefined;
    return name;
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면-3">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/53291a51-ddcc-405c-afc7-4cb8a9be4fdc/image.png" /></p>
<blockquote>
<h3 id="❓-왜-에러가-발생하지-않고-null을-반환했을-때와-같은-결과일까">❓ 왜 에러가 발생하지 않고 null을 반환했을 때와 같은 결과일까?</h3>
<h4 id="❗react-18-버전-이후로--undefined를-반환해도-null과-같이-아무것도-렌더링-하지-않는-것과-동일한-결과를-낸다-에러-발생-x">❗React 18 버전 이후로  undefined를 반환해도 null과 같이 아무것도 렌더링 하지 않는 것과 동일한 결과를 낸다. (에러 발생 X)</h4>
<blockquote>
<ul>
<li>예전에는 <code>Nothing was returned from render</code> 런타임 에러 발생</li>
</ul>
</blockquote>
</blockquote>
<hr />
<h4 id="✍️-예외-처리를-통해-undefined-반환-방지">✍️ 예외 처리를 통해 undefined 반환 방지</h4>
<pre><code class="language-javascript">  import './App.css';

  function App() {
    const name = undefined;
    return name || '값이 undefined 입니다.';
  }

  export default App;</code></pre>
<h4 id="출력-화면">출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/43d64341-9101-4547-9c0e-6310333e4902/image.png" /></p>
<hr />
<h4 id="✍️-jsx-내부에서-undefined-렌더링은-허용---리액트-18-이후로-무의미">✍️ <del>JSX 내부에서 undefined 렌더링은 허용</del> - 리액트 18 이후로 무의미</h4>
<pre><code class="language-javascript">  import './App.css';

  function App() {
    const name = undefined;
    return &lt;div&gt; {name} &lt;/div&gt;;  
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면-4">🖥️ <del>출력 화면</del></h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/567a08a9-5c84-43d6-80f0-6c7b89b1e360/image.png" /></p>
<hr />
<h4 id="✍️-jsx-내부에서-예외-처리-코드">✍️ JSX 내부에서 예외 처리 코드</h4>
<pre><code class="language-javascript">  import './App.css';

  function App() {
    const name = undefined;
    return &lt;div&gt;{name || '리액트'}&lt;/div&gt;;  
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면-5">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/59301f8e-28a0-4974-98c9-15bc1da31751/image.png" /></p>
<hr />
<h2 id="246-인라인-스타일링">2.4.6 인라인 스타일링</h2>
<ul>
<li>리액트에서 DOM 요소에 스타일을 적용할 때는 <strong>문자열 형태로 넣는 것이 아니라 객체 형태</strong>로 넣어야 한다.</li>
<li>스타일 이름 중 <code>background-color</code> 같이 -문자는 <code>backgroundColor</code> 처럼 <strong>camelCase</strong>로 대체</li>
</ul>
<h4 id="✍️-style-예시-코드">✍️ style 예시 코드</h4>
<pre><code class="language-javascript">  function App() {
    const name = '리액트';
    const style = {
      backgroundColor: 'black',
      color: 'aqua',
      fontSize: '48px',
      fontWeight: 'bold',
      padding: 16
    };

    return &lt;div style={style}&gt;{name}&lt;/div&gt;;  
  }

  export default App;</code></pre>
<h4 id="✍️-미리-선언하지-않고-바로-style-값-지정">✍️ 미리 선언하지 않고 바로 style 값 지정</h4>
<pre><code class="language-javascript">  function App() {
    const name = '리액트';

    return (
      &lt;div 
        style={{
          backgroundColor: 'black',
          color: 'aqua',
          fontSize: '48px',
          fontWeight: 'bold',
          padding: 16 // 단위 생략 시 px
        }}
      &gt;
        {name}
      &lt;/div&gt;
    );  
  }

  export default App;</code></pre>
<h4 id="🖥️-출력-화면-6">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/cbc4c6c7-e90c-4684-bcdf-afe552cba2a5/image.png" /></p>
<hr />
<h2 id="247-class-대신-classname">2.4.7 class 대신 className</h2>
<ul>
<li><p>일반 HTML의 CSS 클래스 사용</p>
<ul>
<li><code>&lt;div class = &quot;myClass&quot;&gt;&lt;/div&gt;</code></li>
</ul>
</li>
<li><p>JSX : <code>class</code> -&gt; <code>className</code></p>
<h3 id="classname-사용-예시">className 사용 예시</h3>
<h4 id="✍️-1-사용할-css-파일-appcss-수정">✍️ 1. 사용할 css 파일 App.css 수정</h4>
<pre><code class="language-css">.react {
  background : aqua;
  color : black;
  font-size: 48px;
  font-weight: bold;
  padding: 16px;
}</code></pre>
<h4 id="✍️-2-appjs에서-class-불러오기">✍️ 2. App.js에서 class 불러오기</h4>
<pre><code class="language-javascript">import './App.css';

function App() {
  const name = '리액트';
  return &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;;
}

export default App;</code></pre>
<h4 id="🖥️-출력-화면-7">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/1b82cac2-9a2f-4392-9893-48cd64f1b9c3/image.png" /></p>
<blockquote>
<h4 id="classname이-아닌-class-값을-설정해도-스타일이-적용되지만-개발자-도구의-console-탭에서-경고-발생">className이 아닌 class 값을 설정해도 스타일이 적용되지만 개발자 도구의 Console 탭에서 경고 발생</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/21582b81-50ed-462d-aa6f-43a06b3de0a2/image.png" /></p>
<blockquote>
<ul>
<li>리액트 16 이후로 class를 className으로 변환시켜 주고 경고 발생 (이전에는 오류 발생)</li>
</ul>
</blockquote>
</blockquote>
<hr />
<h2 id="248-꼭-닫아야-하는-태그">2.4.8 꼭 닫아야 하는 태그</h2>
<ul>
<li><p>HTML에서는 태그를 닫지 않은 상태로 코드를 작성하기도 함</p>
<ul>
<li><code>&lt;input&gt;</code>, <code>&lt;br&gt;</code> 등등</li>
</ul>
</li>
<li><p><strong>JSX에서는 태그를 닫지 않을 경우 오류 발생</strong></p>
<h4 id="⚠️-오류-발생-코드">⚠️ 오류 발생 코드</h4>
<pre><code class="language-javascript">import './App.css';
import { Fragment } from 'react';

function App() {
  const name = '리액트';
  return (
    &lt;&gt;
      &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;
      &lt;input&gt;
    &lt;/&gt;
  );
}

export default App;</code></pre>
<h4 id="❌-오류-결과">❌ 오류 결과</h4>
<pre><code>ERROR in [eslint]
src\App.js
  Line 10:7:  Parsing error: Unterminated JSX contents. (10:7)

webpack compiled with 2 errors</code></pre></li>
</ul>
<hr />
<h4 id="✍️-input-태그를-닫아서-해결">✍️ input 태그를 닫아서 해결</h4>
<pre><code class="language-javascript">  import './App.css';
  import { Fragment } from 'react';

  function App() {
    const name = '리액트';
    return (
      &lt;&gt;
        &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;
        &lt;input&gt;&lt;/input&gt;
      &lt;/&gt;
    );
  }

  export default App;</code></pre>
<h4 id="✍️-self-closing-태그의-활용">✍️ self-closing 태그의 활용</h4>
<pre><code class="language-javascript">import './App.css';
  import { Fragment } from 'react';

  function App() {
    const name = '리액트';
    return (
      &lt;&gt;
        &lt;div className=&quot;react&quot;&gt;{name}&lt;/div&gt;
        &lt;input /&gt;
      &lt;/&gt;
    );
  }</code></pre>
<h4 id="🖥️-출력화면">🖥️ 출력화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/d5eb3e82-ec49-4a34-9aa8-49abbd8246fe/image.png" /></p>
<hr />
<h2 id="249-주석">2.4.9 주석</h2>
<ul>
<li><p>JS와 다른 주석 작성 방법</p>
</li>
<li><p><strong>JSX 내부</strong>에 주석 작성</p>
<ul>
<li><strong><code>{/* ... */}</code></strong>와 같은 형식으로 작성 (여러 줄 작성 가능</li>
</ul>
</li>
<li><p><strong>시작 태그</strong>를 여러 줄로 작성할 때</p>
<ul>
<li>내부에 <strong><code>// ...</code></strong>과 같은 형태의 주석 작성 가능</li>
</ul>
</li>
<li><p>⚠️ 일반 JS 처럼 아무데나 주석을 작성하면 그 주석은 페이지에 고스란히 표현</p>
<h4 id="✍️-주석-예시-코드">✍️ 주석 예시 코드</h4>
<pre><code class="language-javascript">import './App.css';
import { Fragment } from 'react';

function App() {
  const name = '리액트';
  return (
    &lt;&gt;
      {/* 주석은 이렇게 작성합니다. */}
      &lt;div
        className=&quot;react&quot; // 시작 태그를 여러 줄로 작성하명 여기에 주석 작성 가능
      &gt;
        {name}
      &lt;/div&gt;
      // 하지만 이런 주석이나
      /* 이런 주석은 페이지에 그대로 표현 */
      &lt;input /&gt;
    &lt;/&gt;
  );
}

export default App;</code></pre>
<h4 id="🖥️-출력-화면-8">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/f1c27f63-48c5-4214-a7f5-8153b113234f/image.png" /></p>