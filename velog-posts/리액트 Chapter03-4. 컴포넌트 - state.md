<h1 id="34-state">3.4 state</h1>
<ul>
<li><code>state</code> : <strong>컴포넌트 내부에서 바뀔 수 있는 값</strong></li>
<li><code>props</code> : 컴포넌트가 사용되는 과정에서 <strong>부모 컴포넌트가 설정하는 값</strong><ul>
<li>컴포넌트 자신 - <code>props</code>를 <strong>읽기 전용</strong>으로만 사용 가능</li>
<li><code>App</code> 컴포넌트에서 <code>MyComponent</code>를 사용할 때 <code>props</code>를 변경하여 값 변경<ul>
<li><code>MyComponent</code>에서는 전달받은 값 변경 불가<h3 id="❗두-가지-종류의-state">❗두 가지 종류의 state</h3>
</li>
</ul>
</li>
</ul>
</li>
</ul>
<ol>
<li><strong>클래스형 컴포넌트</strong>가 지니고 있는 <code>state</code></li>
<li><strong>함수 컴포넌트</strong>에서 <code>useState</code> 함수를 통해 사용하는 <code>state</code></li>
</ol>
<hr />
<h2 id="341-클래스형-컴포넌트의-state">3.4.1 클래스형 컴포넌트의 state</h2>
<h4 id="✍️-새로운-컴포넌트-생성---counterjs">✍️ 새로운 컴포넌트 생성 - Counter.js</h4>
<pre><code class="language-javascript">  import React, { Component } from 'react';

  class Counter extends Component {
        constructor(props) {
          super(props);
          // state 초기 값 설정
          this.state = {
              number: 0,
          };
      }
      render() {
          const { number } = this.state; // state는 this.state로 조회
          return (
              &lt;div&gt;
                  &lt;h1&gt;{number}&lt;/h1&gt;
                  &lt;button
                      //onClick을 통해 버튼이 클릭되었을 때 호출 함수 지정
                      onClick={() =&gt; {
                          //this.setState를 사용해 state에 새로운 값 삽입 가능
                          this.setState({ number: number + 1 });
                      }}
                  &gt;
                      +1
                  &lt;/button&gt;
              &lt;/div&gt;
          );
      }
  }

  export default Counter;</code></pre>
<h3 id="📖-각-코드의-역할">📖 각 코드의 역할</h3>
<ul>
<li>컴포넌트에 <code>state</code>를 설정할 때는 <code>constructor</code> 메서드를 작성하여 설정<pre><code class="language-javascript">constructor(props) {
  super(props);
  // state의 초깃값 설정
  this.state = {
    number: 0
  };
}</code></pre>
</li>
<li>컴포넌트의 <strong>생성자 메서드</strong><ul>
<li>클래스형 컴포넌트에서 <code>constructor</code>를 작성할 때 반드시 <code>super(props)</code> 호출<ul>
<li><code>super(props)</code> : 리액트의 <code>Component</code> 클래스(상속받고 있는 클래스)의 생성자 함수 호출</li>
</ul>
</li>
</ul>
</li>
<li><code>this.state</code>에 초기값 설정<ul>
<li>컴포넌트의 state는 객체 형식 <code>{ }</code></li>
</ul>
</li>
</ul>
<hr />
<ul>
<li><code>render</code> 함수<pre><code class="language-javascript">render() {
  const { number } = this.state; // state는 this.state로 조회
  return (
      &lt;div&gt;
          &lt;h1&gt;{number}&lt;/h1&gt;
          &lt;button
              //onClick을 통해 버튼이 클릭되었을 때 호출 함수 지정
              onClick={() =&gt; {
                  //this.setState를 사용해 state에 새로운 값 삽입 가능
                  this.setState({ number: number + 1 });
              }}
          &gt;
              +1
          &lt;/button&gt;
      &lt;/div&gt;
  );
}</code></pre>
</li>
<li><code>render</code> 함수에서 현재 <code>state</code>를 조회할 때는 <code>this.state</code> 조회</li>
<li><code>button</code>의 <code>props</code> : <code>onClick</code><ul>
<li>버튼이 클릭될 때 호출시킬 함수 설정 가능 - <strong>이벤트 설정</strong></li>
</ul>
</li>
<li>이벤트로 설정할 함수는 <strong>화살표 함수</strong>를 사용해 삽입</li>
<li>함수 내부의 <code>this.setState</code> : 함수가 state 값을 변경할 수 있게 해줌</li>
</ul>
<h4 id="✍️-counter-컴포넌트를-app에서-렌더링">✍️ Counter 컴포넌트를 App에서 렌더링</h4>
<pre><code class="language-javascript">  import Counter from './Counter';

  const App = () =&gt; {
      return &lt;Counter /&gt;;
  };

  export default App;</code></pre>
<h4 id="🖥️-출력-화면">🖥️ 출력 화면</h4>
<ul>
<li>버튼 클릭 시 값 1씩 증가
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/0d5d46a2-29db-4449-ac78-bca3e6b48d36/image.png" /></li>
</ul>
<hr />
<h3 id="3411-state-객체-안에-여러-값이-있을-때">3.4.1.1 state 객체 안에 여러 값이 있을 때</h3>
<h4 id="✍️-state-객체에-여러-값-넣기---counterjs-수정">✍️ state 객체에 여러 값 넣기 - Counter.js 수정</h4>
<pre><code class="language-javascript">import React, { Component } from 'react';

class Counter extends Component {
    constructor(props) {
        super(props);
        // state 초기 값 설정
        this.state = {
            number: 0,
            fixedNumber: 0,
        };
    }
    render() {
        const { number, fixedNumber } = this.state; // state는 this.state로 조회
        return (
            &lt;div&gt;
                &lt;h1&gt;{number}&lt;/h1&gt;
                &lt;h2&gt;바뀌지 않는 값: {fixedNumber}&lt;/h2&gt;
                &lt;button
                    //onClick을 통해 버튼이 클릭되었을 때 호출 함수 지정
                    onClick={() =&gt; {
                        //this.setState를 사용해 state에 새로운 값 삽입 가능
                        this.setState({ number: number + 1 });
                    }}
                &gt;
                    +1
                &lt;/button&gt;
            &lt;/div&gt;
        );
    }
}

export default Counter;</code></pre>
<ul>
<li>버튼이 클릭될 때 <code>number</code>만 변경 - <code>fixedNumber</code>는 고정<ul>
<li><code>this.setState</code> 는 인자로 전달된 객체 안에 들어있는 값만 변경<h4 id="🖥️-출력화면">🖥️ 출력화면</h4>
</li>
</ul>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/239bfe8e-a62e-4c17-ad4e-dceb65c666ae/image.png" /></p>
<hr />
<h3 id="3412-state를-constructor에서-꺼내기">3.4.1.2 state를 constructor에서 꺼내기</h3>
<h4 id="✍️-state의-초깃값을-지정하는-다른-방법">✍️ state의 초깃값을 지정하는 다른 방법</h4>
<pre><code class="language-javascript">import React, { Component } from 'react';

class Counter extends Component {
    state = {
        number: 0,
        fixedNumber: 0,
    }; // state의 초깃값 설정
    render() {
        const { number, fixedNumber } = this.state; // state는 this.state로 조회
        return (...);
    }
}

export default Counter;</code></pre>
<hr />
<h3 id="3413-thissetstate에-객체-대신-함수-인자-전달하기">3.4.1.3 this.setState에 객체 대신 함수 인자 전달하기</h3>
<ul>
<li><code>this.setState</code>는 <code>state</code>를 업데이트할 때 상태가 비동기적 업데이트<h4 id="❓-✍️-onclick에서-thisstate가-두-번-호출-되면">❓ ✍️ onClick에서 this.state가 두 번 호출 되면?</h4>
<pre><code class="language-javascript">onClick={() =&gt; {
  //this.setState를 사용해 state에 새로운 값 삽입 가능
  this.setState({ number: number + 1 });
  this.setState({number: this.state.number + 1})
}}</code></pre>
<h4 id="🖥️-출력-화면-1">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/1006857b-2d5f-442a-8a6d-893b22055dd0/image.png" /></p>
<ul>
<li><code>this.setState</code>를 두번 사용해도 버튼 클릭 시 1만 증가<ul>
<li><code>this.setState</code>를 사용한다 해도 <code>state</code>값이 바로 변경 X</li>
</ul>
</li>
</ul>
<hr />
<h4 id="❗-thissetstate를-사용할-때-객체-대신-함수를-인자로-넣어-해결">❗ this.setState를 사용할 때 객체 대신 함수를 인자로 넣어 해결</h4>
<h4 id="✍️-작성-방법">✍️ 작성 방법</h4>
<pre><code class="language-javascript">this.setState((prevState, props) =&gt; {
  return {
    // 업데이트 하고 싶은 내용
  }
})</code></pre>
<ul>
<li><code>prevState</code> : 기존 상태</li>
<li><code>props</code> : 현재 지니고 있는 <code>props</code> - 업데이트 과정에서 <code>props</code>가 필요 없다면 생략 가능<h4 id="✍️-counterjs---onclick-수정">✍️ Counter.js - onClick 수정</h4>
<pre><code class="language-javascript">&lt;button
  //onClick을 통해 버튼이 클릭되었을 때 호출 함수 지정
  onClick={() =&gt; {
      this.setState(prevState =&gt; {
        return {
          number: prevState.number + 1
        }
      });
      // 위 코드와 동일한 기능
      // 함수에서 바로 객체를 반환한다는 의미
      this.setState(prevState =&gt; ({
        number: prevState.number + 1
      }));
  }}
&gt;
  +1
&lt;/button&gt;</code></pre>
</li>
<li>화살표 함수에서 값을 반환받고 싶다면 코드 블록 <code>{ }</code> 생략<pre><code class="language-javascript">const sum = (a,b) =&gt; a + b;</code></pre>
</li>
<li><code>onClick</code>의 두번째 <code>this.setState</code> : <strong>화살표 함수에서 바로 객체 반환</strong>
<code>prevState =&gt; ({객체})</code> : 바로 객체를 반환하는 코드<h4 id="🖥️-출력-화면-2">🖥️ 출력 화면</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/8487ebe1-2340-4260-9b5c-45e30dde20ab/image.png" /></p>
<ul>
<li><code>onClick</code> 이벤트에서 <code>console.log(&quot;클릭!&quot;)</code> 함수를 넣어 클릭할 때 마다 텍스트 출력</li>
<li><strong>한 번 클릭으로 값 2 증가</strong></li>
</ul>
<hr />
<h3 id="3414-thissetstate가-끝난-후-특정-작업-실행하기">3.4.1.4 this.setState가 끝난 후 특정 작업 실행하기</h3>
<h4 id="❓-setstate를-사용하여-값을-업데이트하고-난-다음에-특정-작업을-하고-싶다면">❓ setState를 사용하여 값을 업데이트하고 난 다음에 특정 작업을 하고 싶다면?</h4>
<h4 id="❗-setstate의-두-번째-파라미터로-콜백함수를-등록하여-작업-처리">❗ setState의 두 번째 파라미터로 콜백함수를 등록하여 작업 처리!</h4>
<h4 id="✍️-onclick-함수-수정">✍️ onClick 함수 수정</h4>
<pre><code class="language-javascript">&lt;button
    //onClick을 통해 버튼이 클릭되었을 때 호출 함수 지정
    onClick={() =&gt; {
        this.setState(
            {
                number: number + 1,
            },
            () =&gt; {
                console.log('방금 setState가 호출되었습니다.');
                console.log(this.state);
            }
        );
    }}
&gt;
    +1
&lt;/button&gt;</code></pre>
<h4 id="🖥️-출력-화면-3">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/6fe14314-52fd-4201-ac97-5ccd578fbef4/image.png" /></p>
<hr />
<h2 id="342-함수-컴포넌트에서-usestate-사용하기">3.4.2 함수 컴포넌트에서 useState 사용하기</h2>
<ul>
<li><p><code>Hooks</code> 중 <code>useState</code>를 통해 함수 컴포넌트에서 <code>state</code> 사용</p>
<h3 id="3421-배열-비구조화-할당">3.4.2.1 배열 비구조화 할당</h3>
</li>
<li><p><strong>배열 비구조화 할당</strong> : 배열 안에 들어 있는 값을 쉽게 추출하는 문법</p>
<h4 id="👎-기존-배열-값-추출-방법">👎 기존 배열 값 추출 방법</h4>
<pre><code class="language-javascript">const array = [1, 2];
const one = array[0];
const two = array[1];</code></pre>
<h4 id="👍-배열-비구조화-할당-사용">👍 배열 비구조화 할당 사용</h4>
<pre><code class="language-jsx">const array = [1, 2];
const [one, two] = array;</code></pre>
</li>
</ul>
<hr />
<h3 id="3422-usestate-사용하기">3.4.2.2 useState 사용하기</h3>
<h4 id="✍️-새로운-컴포넌트-sayjs-생성">✍️ 새로운 컴포넌트 Say.js 생성</h4>
<pre><code class="language-javascript">import React, { useState } from 'react';

const Say = () =&gt; {
    const [message, setMessage] = useState('');
    const onClickEnter = () =&gt; setMessage('안녕하세요!');
    const onClickLeave = () =&gt; setMessage('안녕히 가세요!');
    return (
        &lt;div&gt;
            &lt;button onClick={onClickEnter}&gt;입장&lt;/button&gt;
            &lt;button onClick={onClickLeave}&gt;퇴장&lt;/button&gt;
            &lt;h1&gt;{message}&lt;/h1&gt;
        &lt;/div&gt;
    );
};

export default Say;</code></pre>
<ul>
<li><p><code>useState</code>의 인자 : <strong>상태의 초깃값</strong></p>
<ul>
<li><strong>클래스형 컴포넌트의 <code>state</code>  초깃값 : 객체 형태</strong></li>
<li><strong><code>useState</code> : 자유로운 값의 형태 (숫자, 문자열, 객체, 배열)</strong></li>
</ul>
</li>
<li><p>함수 호출 시 배열 반환 - <strong>세터(setter) 함수</strong></p>
<ul>
<li>배열의 첫 번째 원소 : <strong>현재 상태</strong></li>
<li>배열의 두 번째 원소 : <strong>상태 변환 함수</strong></li>
</ul>
</li>
<li><p>배열 비구조화 할당으로 이름 지정</p>
<ul>
<li>현재 상태 : <code>Message</code></li>
<li>상태 변환 함수 : <code>setMessage</code></li>
</ul>
</li>
</ul>
<h4 id="🖥️-출력-화면---app에-렌더링-코드-생략">🖥️ 출력 화면 - App에 렌더링 코드 생략</h4>
<p><img alt="업로드중.." src="blob:https://velog.io/c7ba4401-03cc-4849-b2a1-75931dab8671" />
<img alt="업로드중.." src="blob:https://velog.io/7fee038c-53ec-4719-9803-4a3f4a124c4f" /></p>
<hr />
<h3 id="3423-한-컴포넌트에서-usestate-여러-번-사용하기">3.4.2.3 한 컴포넌트에서 useState 여러 번 사용하기</h3>
<ul>
<li><code>useState</code>는 한 컴포넌트에서 여러 번 사용 가능<ul>
<li>또 다른 상태를 <code>useState</code>로 관리<h4 id="✍️-color-상태-관리하기---sayjs-수정">✍️ color 상태 관리하기 - Say.js 수정</h4>
<pre><code class="language-jsx">import React, { useState } from 'react';
</code></pre>
</li>
</ul>
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
        &lt;h1 style = {{ color }}&gt;{message}&lt;/h1&gt;
        &lt;button style={{ color: 'red' }} onClick={() =&gt; setColor('red')}&gt;
            빨간색
        &lt;/button&gt;
        &lt;button style={{ color: 'green' }} onClick={() =&gt; setColor('green')}&gt;
            초록색
        &lt;/button&gt;
        &lt;button style={{ color: 'blue' }} onClick={() =&gt; setColor('blue')}&gt;
            파란색
        &lt;/button&gt;
    &lt;/div&gt;
);</code></pre><p>};</p>
<p>export default Say;</p>
<pre><code>#### 🖥️ 출력 화면
![업로드중..](blob:https://velog.io/301493e7-10d1-4230-964c-5c87a12551dc)</code></pre>