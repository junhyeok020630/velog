<h1 id="32-첫-컴포넌트-생성">3.2 첫 컴포넌트 생성</h1>
<ul>
<li>컴포넌트 생성 과정<ol>
<li>파일 만들기</li>
<li>코드 작성하기</li>
<li>모듈 내보내기 및 불러오기</li>
</ol>
</li>
</ul>
<hr />
<h2 id="321-src-디렉터리에-mycomponentjs-파일-생성">3.2.1 src 디렉터리에 MyComponent.js 파일 생성</h2>
<ul>
<li>컴포넌트 코드를 선언할 파일 생성<h4 id="src-디렉터리-내-mycomponentjs-생성">src 디렉터리 내 MyComponent.js 생성</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/4c6814d3-564f-4e79-b709-9205c40532ca/image.png" /></p>
<hr />
<h2 id="322-코드-작성">3.2.2 코드 작성</h2>
<h4 id="✍️-함수-컴포넌트로-작성---mycomponent">✍️ 함수 컴포넌트로 작성 - MyComponent</h4>
<pre><code class="language-javascript">  const MyComponent = () =&gt; {
    return &lt;div&gt;나의 새롭고 멋진 컴포넌트&lt;/div&gt;;
  };

  export default MyComponent;</code></pre>
<ul>
<li>함수 작성 시 <code>function</code> 키워드 대신 화살표 함수 사용<ul>
<li><code>() =&gt; {}</code> : ES6에 도입된 문법</li>
</ul>
</li>
</ul>
<blockquote>
<h3 id="❓-화살표-함수">❓ 화살표 함수</h3>
<ul>
<li><p>ES6에서 함수를 표현하는 새로운 방식</p>
</li>
<li><p>function을 완전 대체 X</p>
<ul>
<li>함수를 파라미터로 전달할 때 유용</li>
</ul>
</li>
</ul>
<hr />
<ul>
<li>예시<h4 id="✍️-function-사용">✍️ function 사용</h4>
<pre><code class="language-javascript">setTimeout(function() {
 console.log('hello world');
}, 1000); </code></pre>
<h4 id="✍️-화살표-함수-사용">✍️ 화살표 함수 사용</h4>
<pre><code class="language-javascript">setTimeout(() =&gt; {
 console.log('hello world');
},1000);</code></pre>
</li>
</ul>
<hr />
<h4 id="기존-function과는-가르키는-this-값이-달라-대체-불가능">기존 function과는 가르키는 this 값이 달라 대체 불가능</h4>
<ul>
<li>⚠️ <strong>일반 함수의 this = 자신이 종속된 객체</strong> - 함수 호출에 반환한 객체<pre><code class="language-javascript">function BlackDog() {
 this.name = '흰둥이';
 return {
     name: '검둥이',
     bark: function() {
         console.log(this.name + '멍멍!');
     }
 }
}
</code></pre>
</li>
</ul>
<p>const blackDog = new BlackDog();
blackDog.bark(); // 검둥이 : 멍멍!</p>
<pre><code>* ⚠️ **화살표 함수의 this = 자신이 종속된 인스턴스** - 함수 그 자체의 인스턴스
```javascript
function WhiteDog() {
   this.name = '흰둥이';
   return {
       name: '검둥이',
       bark: () =&gt; {
           console.log(this.name + '멍멍!');
       }
   }
}

const whiteDog = new WhiteDog();
blackDog.bark(); // 흰둥이 : 멍멍!</code></pre><ul>
<li><p>화살표 함수는 값을 연산하여 바로 반환해야 할 때 가독성을 높일 수 있음</p>
<ul>
<li>따로 <code>{ }</code>를 열지 않으면 연산한 값 그대로 반환<pre><code class="language-javascript">function twice(value) {
return value * 2;
}
</code></pre>
</li>
</ul>
<p>const triple = (value) =&gt; value * 3</p>
<pre><code></code></pre></li>
</ul>
<h4 id="함수-컴포넌트를-선언할-때는-두-방식이-차이가-없지만-화살표-함수를-사용해-간결하게-표현-가능">함수 컴포넌트를 선언할 때는 두 방식이 차이가 없지만 화살표 함수를 사용해 간결하게 표현 가능</h4>
</blockquote>
<hr />
<h3 id="❗-reactjs-code-snippet-활용하기">❗ Reactjs Code Snippet 활용하기</h3>
<ul>
<li>컴포넌트를 간편하고 빠르게 생성할 수 있도록 도와주는 VS Code 확장 프로그램</li>
<li>에디터에 <code>rsc</code>를 입력 후 <code>Enter</code></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/466562b8-969a-41f5-a9f1-a267e0c7d0cb/image.png" /></p>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/68fba38a-1074-440f-8448-1c1a5835801b/image.png" /></p>
<ul>
<li>클래스형 컴포넌트는 <code>rcc</code>로 사용 가능</li>
</ul>
<hr />
<h2 id="323-모듈-내보내기-및-불러오기">3.2.3 모듈 내보내기 및 불러오기</h2>
<h3 id="3231-모듈-내보내기export">3.2.3.1 모듈 내보내기(export)</h3>
<p>** <code>export default MyComponent</code> **</p>
<ul>
<li>다른 파일에서 해당 컴포넌트를 <code>import</code> 할 때 필요한 코드</li>
</ul>
<hr />
<h3 id="3232-모듈-불러오기import">3.2.3.2 모듈 불러오기(import)</h3>
<h4 id="✍️-app-컴포넌트에서-mycomponent-불러오기">✍️ App 컴포넌트에서 MyComponent 불러오기</h4>
<pre><code class="language-javascript">  const MyComponent = () =&gt; {
    return &lt;div&gt;나의 새롭고 멋진 컴포넌트&lt;/div&gt;;
  };

  export default MyComponent;</code></pre>
<h4 id="🖥️-출력화면">🖥️ 출력화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/4f47edd5-3d2a-4f5f-a50b-fa3a09ccba95/image.png" /></p>