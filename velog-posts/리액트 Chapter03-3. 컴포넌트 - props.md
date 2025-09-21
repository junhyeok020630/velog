<h1 id="33-props">3.3 props</h1>
<ul>
<li><code>props</code> : properties를 줄인 표현, <strong>컴포넌트 속성을 설정</strong>할 때 사용하는 요소<ul>
<li>해당 컴포넌트를 <strong>불러와 사용하는 부모 컴포넌트</strong>에서 설정 가능</li>
<li><strong>App 컴포넌트가 MyComponent의 부모 컴포넌트</strong></li>
</ul>
</li>
</ul>
<hr />
<h2 id="331-jsx-내부에서-props-렌더링">3.3.1 JSX 내부에서 props 렌더링</h2>
<ul>
<li>MyComponent를 name 이라는 props를 렌더링 하도록 수정</li>
<li>props 값은 <strong>컴포넌트 함수의 파라미터</strong>로 받아와 사용 가능</li>
<li>props 렌더링 시 <strong>JSX 내부에서 <code>{ }</code></strong> 기호로 감싸줌</li>
</ul>
<h4 id="✍️-mycomponent-수정---name-이라는-props-렌더링">✍️ MyComponent 수정 - name 이라는 props 렌더링</h4>
<pre><code class="language-javascript">  const MyComponent = (props) =&gt; {
    return &lt;div&gt;안녕하세요, 제 이름은 {props.name}입니다.&lt;/div&gt;;
  };

  export default MyComponent;</code></pre>
<hr />
<h2 id="332-컴포넌트를-사용할-때-props-값-지정하기">3.3.2 컴포넌트를 사용할 때 props 값 지정하기</h2>
<ul>
<li><p>App 컴포넌트에서 MyComponent의 props 갑 지정</p>
<h4 id="✍️-appjs에서-props-값-지정하기">✍️ App.js에서 props 값 지정하기</h4>
<pre><code class="language-javascript">import MyComponent from './MyComponent';

const App = () =&gt; {
    return &lt;MyComponent name=&quot;React&quot; /&gt;;
};

export default App;</code></pre>
</li>
</ul>
<h4 id="🖥️-출력-화면">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/457b0c38-45e8-4c85-8295-3167faccb580/image.png" /></p>
<hr />
<h2 id="333-props-기본값-설정-defaultprops">3.3.3 props 기본값 설정: defaultProps</h2>
<h4 id="✍️-appjs에서-설정한-name-값을-지우고-다시-저장">✍️ App.js에서 설정한 name 값을 지우고 다시 저장</h4>
<pre><code class="language-javascript">    (...) // 코드 생략 표시
     return &lt;MyComponent /&gt;;
    (...) // 코드 생략 표시</code></pre>
<h4 id="🖥️-출력-화면-1">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/55319131-1a68-4e92-ab86-bb035f002e99/image.png" /></p>
<hr />
<h4 id="✍️-defaultprops-지정하기---리액트-18-이전-버전"><del>✍️ defaultProps 지정하기 - 리액트 18 이전 버전</del></h4>
<pre><code class="language-javascript">  const MyComponent = (props) =&gt; {
    return &lt;div&gt;안녕하세요, 제 이름은 {props.name}입니다.&lt;/div&gt;;
  };

  MyComponent.defaultProps = {
    name: '기본 이름'
  };

  export default MyComponent;</code></pre>
<hr />
<h4 id="✍️-리액트-18-이후-defaultprops-지정하기">✍️ 리액트 18 이후 defaultProps 지정하기</h4>
<ol>
<li><p>기본 매개변수 전달하기</p>
<pre><code class="language-javascript">const MyComponent = ({name = &quot;기본이름}) =&gt; {
   return &lt;div&gt;안녕하세요, 제 이름은 {name}입니다.&lt;/div&gt;;
 };

 export default MyComponent;</code></pre>
</li>
<li><p>props 기본값 지정</p>
<pre><code class="language-javascript">const MyComponent = (props) =&gt; {
   const { name = '기본 이름' } = props;
   return &lt;div&gt;안녕하세요, 제 이름은 {name}입니다.&lt;/div&gt;;
 };

 export default MyComponent;</code></pre>
<h4 id="🖥️-출력-화면-2">🖥️ 출력 화면</h4>
</li>
</ol>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/77d40d41-12ee-441a-99e0-c2e3efa2a65d/image.png" /></p>
<hr />
<h2 id="334-태그-사이의-내용을-보여-주는-children">3.3.4 태그 사이의 내용을 보여 주는 children</h2>
<ul>
<li><p>컴포넌트 태그 사이의 내용을 보여주는 props</p>
<h4 id="✍️-childern---appjs-수정">✍️ childern - App.js 수정</h4>
<pre><code class="language-javascript">import MyComponent from './MyComponent';

const App = () =&gt; {
    return &lt;MyComponent&gt;리액트&lt;/MyComponent&gt;;
};

export default App;</code></pre>
<h4 id="✍️-children---태그-사이에-작성된-문자-불러오기---mycomponentjs-수정">✍️ children - 태그 사이에 작성된 문자 불러오기 - MyComponent.js 수정</h4>
<pre><code class="language-javascript">const MyComponent = (props) =&gt; {
    const { name = '기본 이름' } = props;
    return (
        &lt;div&gt;
            안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
            childen 값은 {props.children}
            입니다.
        &lt;/div&gt;
    );
};

export default MyComponent;</code></pre>
<h4 id="🖥️-출력-화면-3">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/69875b8c-f1d4-4d47-8872-8b2187750241/image.png" /></p>
<hr />
<h2 id="335-비구조화-할당-문법을-통해-props-내부-값-추출하기">3.3.5 비구조화 할당 문법을 통해 props 내부 값 추출하기</h2>
<ul>
<li>현재는 props 값을 조회하기 위해 <code>props.name</code>, <code>props.children</code> 같이 <code>props.</code> 키워드 사용<ul>
<li>작업의 간편화를 위해 ES6에서 <strong>비구조화 할당 문법을 통해 내부 값 바로 추출 가능</strong></li>
</ul>
</li>
</ul>
<h4 id="✍️-비구조화-할당-문법---mycomponentjs-수정">✍️ 비구조화 할당 문법 - MyComponent.js 수정</h4>
<pre><code class="language-javascript">  const MyComponent = (props) =&gt; {
      const { name = '기본 이름', children } = props;
      return (
          &lt;div&gt;
              안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
              childen 값은 {children}
              입니다.
          &lt;/div&gt;
      );
  };

  export default MyComponent;</code></pre>
<blockquote>
<ul>
<li>리액트 18 이후 default 설정 방법 = 비구조화 할당 문법 내부에서 설정</li>
<li>** 비구조화 할당 ** = 객체에서 값을 추출하는 문법<ul>
<li>== 구조 분해 문법</li>
</ul>
</li>
</ul>
</blockquote>
<h4 id="✍️-비구조화-할당---함수의-파라미터에서-사용">✍️ 비구조화 할당 - 함수의 파라미터에서 사용</h4>
<ul>
<li><p><strong>객체인 함수의 파라미터(<code>{name, children}</code>)을 비구조화</strong>해서 사용</p>
<pre><code class="language-javascript">
  const MyComponent = ({ name = '기본 이름', children }) =&gt; {
        return (
          &lt;div&gt;
            안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
            childen 값은 {children}
            입니다.
          &lt;/div&gt;
        );
  };
  export default MyComponent;</code></pre>
<h4 id="🖥️-출력-화면-4">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/3d2d15aa-76c3-4a61-8d16-1af5c0600e56/image.png" /></p>
<hr />
<h2 id="336-proptypes를-통한-props-검증">3.3.6 propTypes를 통한 props 검증</h2>
<ul>
<li>컴포넌트의 필수 props를 지정하거나 props의 타입을 지정할 때 사용</li>
<li><code>defaultProp</code>와 유사하게 <code>propTypes</code> 지정 가능<ul>
<li>사용을 위해 <strong><code>import</code></strong> 필수</li>
</ul>
</li>
</ul>
<h4 id="✍️-name-prop의-타입을-string으로-지정---mycomponentjs-수정"><del>✍️ name prop의 타입을 String으로 지정 - MyComponent.js 수정</del></h4>
<pre><code class="language-javascript">  import PropTypes from 'prop-types';

  const MyComponent = ({ name = '기본 이름', children }) =&gt; {
      return (
          &lt;div&gt;
              안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
              childen 값은 {children}
              입니다.
          &lt;/div&gt;
      );
  };

  MyComponent.propTypes = {
      name: PropTypes.string,
  };

  export default MyComponent;</code></pre>
<h4 id="✍️-proptypes-적용-확인---appjs-수정">✍️ propTypes 적용 확인 - App.js 수정</h4>
<ul>
<li><p>name 값을 숫자로 전달</p>
<pre><code class="language-javascript">  import MyComponent from './MyComponent';

   const App = () =&gt; {
      return &lt;MyComponent name={3}&gt;리액트&lt;/MyComponent&gt;;
   };

   export default App;</code></pre>
<h4 id="🖥️-출력-화면---console">🖥️ 출력 화면 - Console</h4>
</li>
<li><p><del>기존에는 Console에 경고문 출력</del></p>
</li>
</ul>
<blockquote>
<h3 id="리액트-19-이후로는-typescript또는-수동-검사를-통해-타입을-검사하는게-권장---proptypes-관련-경고-로직-미작동">리액트 19 이후로는 TypeScript또는 수동 검사를 통해 타입을 검사하는게 권장 - PropTypes 관련 경고 로직 미작동</h3>
</blockquote>
<h4 id="✍️-1-check-proptypes를-활용한-수동-검사">✍️ 1. check-PropTypes를 활용한 수동 검사</h4>
<pre><code class="language-javascript">  import PropTypes from 'prop-types';
  import checkPropTypes from 'prop-types/checkPropTypes';
&gt;
  const MyComponent = ({ name, children }) =&gt; {
      if (process.env.NODE_ENV !== 'production') {
          checkPropTypes(MyComponent.propTypes, { name }, 'prop', 'MyComponent');
      }
      return (
          &lt;div&gt;
              안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
              children 값은 {children}
          &lt;/div&gt;
      );
  };
&gt;
  MyComponent.propTypes = {
      name: PropTypes.string,
  };
&gt;
  export default MyComponent;</code></pre>
<h4 id="🖥️-출력-화면-5">🖥️ 출력 화면</h4>
<blockquote>
</blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/b31220e6-8a6c-42e6-9c76-efe73ddf2696/image.png" /></p>
<blockquote>
</blockquote>
<hr />
<h4 id="✍️-2-vite에서-typescript를-활용하여-type-검사하기">✍️ 2. Vite에서 TypeScript를 활용하여 Type 검사하기</h4>
<p><strong>1. <code>TypeScript</code> 설치하기</strong></p>
<ul>
<li><code>yarn add -D typescript @types/react@19 @types/react-dom@19</code></li>
<li>리액트 버전과 <code>types/react</code>및 <code>types/react-dom</code> 버전 맞추기
<strong>2. 파일 확장자 변경 (js -&gt; tsx)</strong></li>
<li>index.js -&gt; index.tsx</li>
<li>App.js -&gt; App.tsx</li>
<li>MyComponent.js -&gt; MyComponent.tsx
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/6bef60bc-ec98-4dd7-8c2f-a6ef2562effd/image.png" />
<strong>3. 프로젝트 루트에 tsconfig.json 파일 작성</strong><pre><code class="language-json">{
  &quot;compilerOptions&quot;: {
   &quot;target&quot;: &quot;ES2020&quot;,
   &quot;lib&quot;: [&quot;DOM&quot;, &quot;ES2021&quot;],
   &quot;jsx&quot;: &quot;react-jsx&quot;, // typescript가 jsx파일을 컴파일하도록 설정
   &quot;module&quot;: &quot;ESNext&quot;,
   &quot;moduleResolution&quot;: &quot;Bundler&quot;,
   &quot;resolveJsonModule&quot;: true,
   &quot;isolatedModules&quot;: true,
   &quot;noEmit&quot;: true,
   &quot;strict&quot;: true,
   &quot;skipLibCheck&quot;: true,
   &quot;esModuleInterop&quot;: true
  },
  &quot;include&quot;: [&quot;src&quot;]
}</code></pre>
<strong>4. ✍️ MyComponent.tsx 수정</strong><pre><code class="language-typescript">type MyComponentProps = {
 name?: string; 
 children?: React.ReactNode;         
};
&gt;
const MyComponent = ({ name, children } : MyComponentProps) =&gt; {
 return (
     &lt;div&gt;
         안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
         children 값은 {children}
     &lt;/div&gt;
 );
};
&gt;
export default MyComponent;</code></pre>
<ul>
<li>MyComponentProps에 PropType을 미리 지정</li>
<li>컴포넌트 매개 변수에 같이 넘겨주기</li>
<li><em>5. ✍️ index.tsx 에러 수정*</em>
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/2ce7864b-7ea9-44e2-bc08-4381f0122291/image.png" /><blockquote>
<blockquote>
<ul>
<li><code>document.getElementById()</code>의 반환 타입은 <code>HTMLElement</code> 또는 <code>null</code></li>
<li>TS가 반환 타입이 <code>root</code>가 없으면 <code>null</code>일 수도 있지 않아? 경고중</li>
<li><code>ReactDom.createRoot()</code>는 <code>null</code>을 허용하지 않음<h4 id="ts가-root-요소가-항상-존재한다는-사실을-모름">TS가 'root' 요소가 항상 존재한다는 사실을 모름</h4>
<h4 id="✍️--문법-활용">✍️ ! 문법 활용</h4>
<pre><code class="language-typescript">const root = ReactDOM.createRoot(document.getElementById(&quot;root&quot;)!);</code></pre>
</li>
</ul>
</blockquote>
</blockquote>
<pre><code>&gt;&gt; * `!` : 해당 값이 절대 null이 아니라고 TS에게 보장해주는 문법 
&gt;
&gt; **🖥️ 출력 화면 - 타입 에러 발생(props 검증 성공)** 
![](https://velog.velcdn.com/images/junhyeok020630/post/0c785d44-5001-4bad-b8a8-d8bda440be8f/image.png)
</code></pre></li>
</ul>
</li>
</ul>
<hr />
<h4 id="🖥️-name-값을-string으로-수정해서-오류경고-해결---name-react">🖥️ name 값을 String으로 수정해서 오류(경고) 해결 - name =&quot;React&quot;</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/2db151b5-cd5e-459b-b3b0-72f424b630e2/image.png" /></p>
<hr />
<h3 id="3361-isrequired를-사용하여-필수-proptypes-설정">3.3.6.1 isRequired를 사용하여 필수 propTypes 설정</h3>
<h4 id="✍️-favoritenumber를-필수-props로-지정---mycomponent-수정">✍️ favoriteNumber를 필수 props로 지정 - MyComponent 수정</h4>
<pre><code class="language-javascript">  import PropTypes from 'prop-types';
  import { checkPropTypes } from 'prop-types';

  const MyComponent = ({ name = &quot;기본 이름&quot;, favoriteNumber, children }) =&gt; {
      if (process.env.NODE_ENV !== 'production') {
          checkPropTypes(
              MyComponent.propTypes,            // 정의한 propTypes
              { name, favoriteNumber},               // 실제 전달된 props
              'prop',                           // location
              'MyComponent'                     // component name for message
          );
      };
      return (
          &lt;div&gt;
              안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
              children 값은 {children}
              입니다.
              &lt;br /&gt;
              제가 좋아하는 숫자는 {favoriteNumber}입니다.
          &lt;/div&gt;
      );
  };

  MyComponent.propTypes = {
      name: PropTypes.string,
      favoriteNumber: PropTypes.number.isRequired,
  };

  export default MyComponent;</code></pre>
<h4 id="🖥️-출력-화면-6">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/ba8c73e4-079e-4aec-879b-d7ae75d48177/image.png" /></p>
<h4 id="🖥️-출력-화면---favoritenumber에-값-전달하기">🖥️ 출력 화면 - favoriteNumber에 값 전달하기</h4>
<ul>
<li>App.js 수정
<code>&lt;MyComponent name=&quot;React&quot; favoriteNumber={1}&gt; 리액트 &lt;/MyComponent&gt;</code></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/1bdc5030-536f-49de-b650-fe1ce10fc290/image.png" /></p>
<hr />
<h3 id="❗-vite에서-ts를-이용하여-isrequired-구현하기">❗ Vite에서 TS를 이용하여 isRequired 구현하기</h3>
<ul>
<li><p>type 선언 시 prop 변수에 <code>?</code> 여부로 <code>isRequired</code> 판단</p>
<ul>
<li><code>?</code>가 있다면 필수 X</li>
<li><code>?</code>가 없다면 필수 prop<h4 id="✍️-mycomponenttsx-수정">✍️ MyComponent.tsx 수정</h4>
<pre><code class="language-typescript">type MyComponentProps = {
  name?: string; 
  children?: React.ReactNode;
  favoriteNumber: number;
};
</code></pre>
</li>
</ul>
<p>const MyComponent = ({ name, favoriteNumber, children } : MyComponentProps) =&gt; {</p>
<pre><code>return (
    &lt;div&gt;
        안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
        children 값은 {children}
        입니다.
        &lt;br /&gt;
        제가 좋아하는 숫자는 {favoriteNumber}입니다.
    &lt;/div&gt;
);</code></pre><p>};</p>
<p>export default MyComponent;</p>
<pre><code>#### 🖥️ 문제 화면
</code></pre></li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/7c9ec58b-23fb-4aed-9564-4710ffb4eb89/image.png" /></p>
<hr />
<blockquote>
<h3 id="❓-터미널에서-타입-오류-확인하기">❓ 터미널에서 타입 오류 확인하기</h3>
</blockquote>
<h4 id="❗-vite-plugin-checker활용">❗ Vite-plugin-checker활용</h4>
<p><strong>1. Vite-plugin-checker 다운로드 **
<code>npm i -D vite-plugin-checker</code>
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/dd388e30-84bb-4ea8-af93-e760f4378f48/image.png" />
**2. ✍️ vite.config.ts 수정</strong></p>
<pre><code class="language-typescript">  import { defineConfig } from 'vite'
  import react from '@vitejs/plugin-react'
  import checker from 'vite-plugin-checker'
&gt;
  // https://vite.dev/config/
  export default defineConfig({
    plugins: [
      react(), 
      checker({
        typescript: { tsconfigPath: './tsconfig.app.json' }, // tsc 타입체크 - tsconfig.app.json에서 src 경로를 포함
        // eslint: { lintCommand: 'eslint &quot;src/**/*.{ts,tsx}&quot;' }, // 원하면 ESLint도 함께
      }),
    ],
  })</code></pre>
<h4 id="🖥️-출력-화면-7">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/60c3697b-dfa5-45f7-980c-565300194d4e/image.png" /></p>
<hr />
<h3 id="3362-더-많은-proptypes-종류">3.3.6.2 더 많은 PropTypes 종류</h3>
<table>
<thead>
<tr>
<th align="center">PropTypes</th>
<th align="center">의미</th>
</tr>
</thead>
<tbody><tr>
<td align="center">array</td>
<td align="center">배열</td>
</tr>
<tr>
<td align="center">arrayOf</td>
<td align="center">특정 PropType으로 이루어진 배열</td>
</tr>
<tr>
<td align="center">bool</td>
<td align="center">T/F</td>
</tr>
<tr>
<td align="center">func</td>
<td align="center">함수</td>
</tr>
<tr>
<td align="center">number</td>
<td align="center">숫자</td>
</tr>
<tr>
<td align="center">object</td>
<td align="center">객체</td>
</tr>
<tr>
<td align="center">string</td>
<td align="center">문자열</td>
</tr>
<tr>
<td align="center">symbol</td>
<td align="center">ES6의 Symbol</td>
</tr>
<tr>
<td align="center">node</td>
<td align="center">렌더링 가능한 모든 것(children)</td>
</tr>
<tr>
<td align="center">instanceOf(클래스)</td>
<td align="center">특정 클래스의 인스턴스</td>
</tr>
<tr>
<td align="center">oneOf([?, ?, ...])</td>
<td align="center">주어진 배열 요소 중 값 하나</td>
</tr>
<tr>
<td align="center">oneOfType([React.PropTypes.?, ...])</td>
<td align="center">주어진 배열 안의 Type 중 하나</td>
</tr>
<tr>
<td align="center">objectOf(React.PropTypes.?, ...)</td>
<td align="center">객체의 모든 키 값이 인자로 주어진 PropType인 객체</td>
</tr>
<tr>
<td align="center">shape({?:??, ?:??})</td>
<td align="center">주어진 스키마를 가진 객체</td>
</tr>
<tr>
<td align="center">any</td>
<td align="center">아무 종류</td>
</tr>
</tbody></table>
<hr />
<h2 id="337-클래스형-컴포넌트에서-props-사용하기">3.3.7 클래스형 컴포넌트에서 props 사용하기</h2>
<ul>
<li><p>render 함수에서 this.props를 조회</p>
<ul>
<li>defaultProps와 propTypes는 똑같은 방식으로 설정 가능<h4 id="✍️-클래스형-컴포넌트로-변환---mycomponentjs-수정">✍️ 클래스형 컴포넌트로 변환 - MyComponent.js 수정</h4>
<pre><code class="language-javascript">import React, {Component} from 'react';
</code></pre>
</li>
</ul>
<p>import PropTypes from 'prop-types';
import { checkPropTypes } from 'prop-types';</p>
<p>class MyComponent extends Component {</p>
<pre><code>render() {
    const { name = &quot;기본 이름&quot;, favoriteNumber, children } = this.props;
    if (process.env.NODE_ENV !== 'production') {
        checkPropTypes(
            MyComponent.propTypes,            // 정의한 propTypes
            { name, favoriteNumber},               // 실제 전달된 props
            'prop',                           // location
            'MyComponent'                     // component name for message
        );
    };
    return (
          &lt;div&gt;
            안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
            children 값은 {children}
            입니다.
            &lt;br /&gt;
            제가 좋아하는 숫자는 {favoriteNumber}입니다.
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>MyComponent.propTypes = {</p>
<pre><code>name: PropTypes.string,
favoriteNumber: PropTypes.number.isRequired</code></pre><p>};</p>
<p>export default MyComponent;</p>
<pre><code>#### 🖥️ 출력 화면
![](https://velog.velcdn.com/images/junhyeok020630/post/80c34cb5-2541-4c22-b76d-2e6b4135bb31/image.png)
</code></pre></li>
</ul>
<blockquote>
<h3 id="❗-클래스형-컴포넌트-내부에-defaultprops와-proptypes-설정">❗ 클래스형 컴포넌트 내부에 defaultProps와 propTypes 설정</h3>
</blockquote>
<pre><code class="language-javascript">  import React, {Component} from 'react';
  import PropTypes from 'prop-types';
  import { checkPropTypes } from 'prop-types';
&gt;
  class MyComponent extends Component {
      static defaultProps = {
          name: &quot;기본 이름&quot;
      };
      static propTypes = {
          name: PropTypes.string,
          favoriteNumber: PropTypes.number.isRequired
      };
      render() {
          const { name, favoriteNumber, children } = this.props;
          if (process.env.NODE_ENV !== 'production') {
              checkPropTypes(
                  MyComponent.propTypes,            // 정의한 propTypes
                  { name, favoriteNumber},               // 실제 전달된 props
                  'prop',                           // location
                  'MyComponent'                     // component name for message
              );
          };
          return (
              &lt;div&gt;
                  안녕하세요, 제 이름은 {name}입니다. &lt;br /&gt;
                  children 값은 {children}
                  입니다.
                  &lt;br /&gt;
                  제가 좋아하는 숫자는 {favoriteNumber}입니다.
              &lt;/div&gt;
          );
      }
  }
&gt;
  export default MyComponent;</code></pre>