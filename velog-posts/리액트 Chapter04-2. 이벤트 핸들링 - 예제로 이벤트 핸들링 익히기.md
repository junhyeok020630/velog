<h1 id="42-예제로-이벤트-핸들링-익히기">4.2 예제로 이벤트 핸들링 익히기</h1>
<h4 id="실습-단계">실습 단계</h4>
<ol>
<li>컴포넌트 생성 및 불러오기</li>
<li>onChange 이벤트 핸들링하기</li>
<li>임의 메서드 만들기</li>
<li>input 여러 개 다루기</li>
<li>onKeyPress 이벤트 핸들링하기</li>
</ol>
<hr />
<h2 id="421-컴포넌트-생성-및-불러오기">4.2.1 컴포넌트 생성 및 불러오기</h2>
<h3 id="4211-컴포넌트-생성">4.2.1.1 컴포넌트 생성</h3>
<h4 id="✍️-eventpracticejs-파일-생성---클래스형-컴포넌트">✍️ EventPractice.js 파일 생성 - 클래스형 컴포넌트</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';

class EventPractice extends Component {
    render() {
        return (
            &lt;div&gt;
                &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;/div&gt;
        );
    }
}

export default EventPractice;</code></pre>
<h3 id="4212-appjs에서-eventpractice-렌더링">4.2.1.2 App.js에서 EventPractice 렌더링</h3>
<h4 id="✍️-app-컴포넌트에서-eventpractice-컴포넌트-렌더링">✍️ App 컴포넌트에서 EventPractice 컴포넌트 렌더링</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';

class EventPractice extends Component {
    render() {
        return (
            &lt;div&gt;
                &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;/div&gt;
        );
    }
}

export default EventPractice;</code></pre>
<h4 id="🖥️-출력-화면">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/3a02116d-86d0-41d5-bd32-a71dd38d8aa8/image.png" /></p>
<hr />
<h2 id="422-onchange-이벤트-핸들링하기">4.2.2 onChange 이벤트 핸들링하기</h2>
<h3 id="4221-onchange-이벤트-설정">4.2.2.1 onChange 이벤트 설정</h3>
<ul>
<li><code>EventPractice</code> 컴포넌트에 <code>input</code> 요소를 렌더링하는 코드와 <code>onChange</code> 이벤트를 설정하는 코드 작성<h4 id="✍️-렌더링-코드-수정---eventpracticejs">✍️ 렌더링 코드 수정 - EventPractice.js</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
<p>class EventPractice extends Component {
    render() {
        return (
            <div>
                <h1>이벤트 연습</h1>
                &lt;input
                    type=&quot;text&quot;
                    name=&quot;message&quot;
                    placeholder=&quot;아무거나 입력해 보세요&quot;
                    onChange={(e) =&gt; {
                        console.log(e);
                    }}
                /&gt;
            </div>
        );
    }
}</p>
<p>export default EventPractice;</p>
<pre><code>#### 🖥️ 출력 화면

![](https://velog.velcdn.com/images/junhyeok020630/post/e274b1c7-0f0f-4617-baf3-8cf6ba1788b5/image.png)

* 이벤트 객체 콘솔에 출력

&gt; ### `onChange` 설정 부분 다시 보기
&gt;```jsx
 onChange={
   (e) =&gt; {
       console.log(e);
   }
 }</code></pre><blockquote>
<ul>
<li><strong>콘솔에 기론되는 <code>e</code> : <code>SyntheticEvent</code></strong></li>
</ul>
</blockquote>
<ul>
<li>웹 브라우저의 네이티브 이벤트를 감싸는 객체</li>
<li><strong>네이티브 이벤트와 인터페이스가 동일</strong>해 순수 JS에서 HTML 이벤트를 다룰 때와 동일하게 사용<blockquote>
<ul>
<li><code>SyntheticEvent</code>는 네이티브 이벤트와 달리 이벤트 종료 시 이벤트가 초기화되어 정보 참조 불가능</li>
</ul>
</blockquote>
</li>
<li>0.5초 뒤에 <code>e</code> 객체를 참조하면 <code>e</code> 객체 내부의 모든 값이 비워짐</li>
</ul>
<ul>
<li>비동기적으로 이벤트 객체 참조 시 : <code>e.persist()</code> 호출</li>
</ul>
<h4 id="✍️-onchange-이벤트가-발생할-때-앞으로-변할-인풋-값인-etargetvalue를-출력---onchange-코드-수정">✍️ onChange 이벤트가 발생할 때, 앞으로 변할 인풋 값인 e.target.value를 출력 - onChange 코드 수정</h4>
<pre><code class="language-jsx">onChange={(e) =&gt; {
    console.log(e.target.value);
}}</code></pre>
<h4 id="🖥️-출력-화면-1">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/5293c9f3-397c-425b-863d-c86da1ce4646/image.png" /></p>
<hr />
<h3 id="4222-state에-input-값-담기">4.2.2.2 state에 input 값 담기</h3>
<ul>
<li><code>constructor</code>에서 <code>state</code> 초기값을 설정하고, 이벤트 핸들링 함수 내부에서 <code>this.setState</code>를 호출해 <code>state</code> 업데이트<ul>
<li><code>input</code>의 <code>value</code>값을 <code>state</code>에 있는 값으로 설정<h4 id="✍️-eventpractice의-state에-input-값-담기">✍️ EventPractice의 state에 input 값 담기</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
</li>
</ul>
<p>class EventPractice extends Component {
    state = {
        message: '',
    };</p>
<pre><code>render() {
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                onChange={(e) =&gt; {
                    this.setState({
                        message: e.target.value,
                    });
                }}
            /&gt;
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>export default EventPractice;</p>
<pre><code>#### 🖥️ 출력 화면

![](https://velog.velcdn.com/images/junhyeok020630/post/633021d4-0340-4253-9280-55c4095db177/image.png)

---

### ❓ 위에서 처럼 state에 담은 message를 console에 출력해 입력값을 보고 싶다면?
#### ❗ setState의 두 번째 파라미터로 출력 함수를 콜백 함수로 넣자!
#### 👎 콜백 함수로 넣지 않고 그냥 출력 할 때
```jsx
import React, { Component } from 'react';

class EventPractice extends Component {
    state = {
        message: '',
    };

    render() {
        return (
            &lt;div&gt;
                &lt;h1&gt;이벤트 연습&lt;/h1&gt;
                &lt;input
                    type=&quot;text&quot;
                    name=&quot;message&quot;
                    placeholder=&quot;아무거나 입력해 보세요&quot;
                    onChange={(e) =&gt; {
                        this.setState({
                            message: e.target.value,
                        });
                        console.log(this.state.message);
                    }}
                /&gt;
            &lt;/div&gt;
        );
    }
}

export default EventPractice;</code></pre><h4 id="🖥️-출력-화면-2">🖥️ 출력 화면</h4>
<ul>
<li><code>message</code>가 변경과 동시에 출력되지 않고 다음 텍스트 입력 시 출력
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/c46f3d0c-38c8-4a15-9a57-63d679816d71/image.png" /><h4 id="👍-콜백함수로-출력함수-삽입">👍 콜백함수로 출력함수 삽입</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
<p>class EventPractice extends Component {
    state = {
        message: '',
    };</p>
<pre><code>render() {
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                onChange={(e) =&gt; {
                    this.setState(
                        {
                            message: e.target.value,
                        },
                        () =&gt; {
                            console.log(this.state.message);
                        }
                    );
                }}
            /&gt;
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>export default EventPractice;</p>
<pre><code>#### 🖥️ 출력 화면

![](https://velog.velcdn.com/images/junhyeok020630/post/f74b5bee-4279-474a-b90a-c56e2a59e52d/image.png)

---
### 4.2.2.3 버튼을 누를 때 comment 값을 공백으로 설정
* 입력한 값이 `state`에 잘 들어갔는지 인풋에서 값을 제대로 반영하는지 확인
  * `input` 아래 `button`을 만들어 클릭 이벤트 발생 시 현재 `comment` 값을 메시지 박스로 띄운 후 `comment`를 공백으로 설정
#### ✍️ state확인용 버튼 생성 -EventPractice.js 수정
```jsx
import React, { Component } from 'react';

class EventPractice extends Component {
    state = {
        message: '',
    };

    render() {
        return (
            &lt;div&gt;
                &lt;h1&gt;이벤트 연습&lt;/h1&gt;
                &lt;input
                    type=&quot;text&quot;
                    name=&quot;message&quot;
                    placeholder=&quot;아무거나 입력해 보세요&quot;
                    onChange={(e) =&gt; {
                        this.setState(
                            {
                                message: e.target.value,
                            },
                            () =&gt; {
                                console.log(this.state.message);
                            }
                        );
                    }}
                /&gt;
                &lt;button
                    onClick={() =&gt; {
                        alert(this.state.message);
                        this.setState({
                            message: '',
                        });
                    }}
                &gt;
                    확인
                &lt;/button&gt;
            &lt;/div&gt;
        );
    }
}

export default EventPractice;</code></pre><h4 id="🖥️-출력-화면-3">🖥️ 출력 화면</h4>
<ol>
<li><code>state</code> 업데이트 확인</li>
</ol>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/55ac03ea-d6fb-4005-be3f-0828cf9e732a/image.png" />
2. <code>state</code> 초기화 확인</p>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/3a55a073-7c25-48a3-bbd3-cc32217173de/image.png" /></p>
<hr />
<h2 id="423-임의-메서드-만들기">4.2.3 임의 메서드 만들기</h2>
<ul>
<li>리액트에서는 이벤트에 실행할 JS 코드가 아니라 함수 형태의 값 전달<ul>
<li>이벤트 처리 시 렌더링 과 동시에 함수를 만들어 전달</li>
</ul>
</li>
</ul>
<h4 id="❗함수를-미리-만들어-전달도-가능">❗함수를 미리 만들어 전달도 가능</h4>
<ul>
<li>높은 가독성 유지 가능<h3 id="4231-기본-방식">4.2.3.1 기본 방식</h3>
<h4 id="✍️-컴포넌트-임의-메서드를-만들어-사용---eventpracticejs-수정">✍️ 컴포넌트 임의 메서드를 만들어 사용 - EventPractice.js 수정</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
<p>class EventPractice extends Component {
    state = {
        message: '',
    };</p>
<pre><code>constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.handleClick = this.handleClick.bind(this);
}

handleChange(e) {
    this.setState({
        message: e.target.value,
    });
}

handleClick() {
    alert(this.state.message);
    this.setState({
        message: '',
    });
}

render() {
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                value={this.state.message}
                onChange={this.handleChange}
            /&gt;
            &lt;button onClick={this.handleClick}&gt;확인&lt;/button&gt;
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>export default EventPractice;</p>
<pre><code>&gt; ### ❓ 함수가 호출될 때 `this`는 호출부에서 결정
  * 클래스의 임의 메서드가 특정 `HTML` 요소의 이벤트로 등록되는 과정에서 메서드와 `this`의 관계가 끊어짐
  * **임의 메서드가 이벤트로 등록되어도 `this`가 컴포넌트 자신을 가리키기 위해 메서드를 `this`와 바인딩하는 작업 필요**
    * **바인딩 하지 않으면 `this`가 `undefined`를 가리킴**

---
### 4.2.3.2 Property Initializer Syntax를 사용한 메서드 작성
* 메서드 바인딩은 생성자(`constructor`) 메서드에서 하는게 정석
  * 새 메서드를 만들 때마다 생성자를 수정해야 하기 때문에 불편함
* **바벨의 `transform-class-properties`를 사용해 화살표 함수로 메서드 정의하여 작업 간편화 **
#### ✍️ transform-class-properties 활용 - EventPractice.js 수정

```jsx
import React, { Component } from 'react';

class EventPractice extends Component {
    state = {
        message: '',
    };

    handleChange = (e) =&gt; {
        this.setState({
            message: e.target.value,
        });
    };

    handleClick = () =&gt; {
        alert(this.state.message);
        this.setState({
            message: '',
        });
    };

    render() {
        return (
            &lt;div&gt;
                &lt;h1&gt;이벤트 연습&lt;/h1&gt;
                &lt;input
                    type=&quot;text&quot;
                    name=&quot;message&quot;
                    placeholder=&quot;아무거나 입력해 보세요&quot;
                    value={this.state.message}
                    onChange={this.handleChange}
                /&gt;
                &lt;button onClick={this.handleClick}&gt;확인&lt;/button&gt;
            &lt;/div&gt;
        );
    }
}

export default EventPractice;</code></pre><blockquote>
<h3 id="❓-왜-화살표함수는-문제없이-실행될까">❓ 왜 화살표함수는 문제없이 실행될까?</h3>
</blockquote>
<h4 id="❗화살표-함수는-this를-호출이-아닌-선언-시에-바인딩">❗화살표 함수는 this를 호출이 아닌 선언 시에 바인딩</h4>
<ul>
<li>함수가 선언된 컴포넌트에 this를 바인딩해 오류 없이 실행 가능</li>
</ul>
<hr />
<h2 id="424-input-여러-개-다루기">4.2.4 input 여러 개 다루기</h2>
<h3 id="❓input을-여러-개-다루기-위해서는">❓input을 여러 개 다루기 위해서는?</h3>
<ul>
<li>메서드를 여러 개 생성
-&gt; 방법이 될 수 있지만 비효율적</li>
<li><strong><code>event</code> 객체를 활용</strong><ul>
<li><code>e.target.name</code>값 활용</li>
<li>해당 인풋의 name을 가리키는 속성<h4 id="✍️-이벤트-객체를-활용한-여러-input---eventpracticejs-수정">✍️ 이벤트 객체를 활용한 여러 input - EventPractice.js 수정</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
</li>
</ul>
<p>class EventPractice extends Component {
    state = {
        username: '',
        message: '',
    };</p>
<pre><code>handleChange = (e) =&gt; {
    this.setState({
        [e.target.name]: e.target.value,
    });
};

handleClick = () =&gt; {
    alert(this.state.username + ':' + this.state.message);
    this.setState({
        userName: '',
        message: '',
    });
};

render() {
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;username&quot;
                placeholder=&quot;사용자명&quot;
                value={this.state.username}
                onChange={this.handleChange}
            /&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                value={this.state.message}
                onChange={this.handleChange}
            /&gt;
            &lt;button onClick={this.handleClick}&gt;확인&lt;/button&gt;
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>export default EventPractice;</p>
<pre><code>#### 🖥️ 출력 화면

![](https://velog.velcdn.com/images/junhyeok020630/post/9d09dfda-06f0-4544-a056-533b0c26b243/image.png)

#### ❗ 핵심 코드
```jsx
handleChange = e =&gt; {
    this.setState({
        [e.target.name]: e.target.value,
    });
};</code></pre><ul>
<li>객체 안에서 key를 <code>[ ]</code>로 감싸면 그 안의 레퍼런스가 가리키는 실제 값이 key 값으로 사용</li>
<li>예시<pre><code class="language-javascript">const name = 'variantKey';
const object = {</code></pre>
</li>
</ul>
<p>};</p>
<pre><code>* 출력 값
```javascript
{
  'variantKey' = 'value'
}</code></pre><hr />
<h2 id="425-onkeypress-이벤트-핸들링">4.2.5 onKeyPress 이벤트 핸들링</h2>
<ul>
<li>키를 눌렀을 때 발생하는 <code>KeyPress</code>이벤트 처리<h4 id="✍️-인풋에서-enter-입력-시-handleclick-메서드-호출">✍️ 인풋에서 Enter 입력 시 handleClick 메서드 호출</h4>
<pre><code class="language-jsx">import React, { Component } from 'react';
</code></pre>
</li>
</ul>
<p>class EventPractice extends Component {
    state = {
        username: '',
        message: '',
    };</p>
<pre><code>handleChange = (e) =&gt; {
    this.setState({
        [e.target.name]: e.target.value,
    });
};

handleClick = () =&gt; {
    alert(this.state.username + ':' + this.state.message);
    this.setState({
        username: '',
        message: '',
    });
};
handleKeyPress = (e) =&gt; {
    if (e.key === 'Enter') {
        this.handleClick();
    }
};

render() {
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;username&quot;
                placeholder=&quot;사용자명&quot;
                value={this.state.username}
                onChange={this.handleChange}
            /&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                value={this.state.message}
                onChange={this.handleChange}
                onKeyPress={this.handleKeyPress}
            /&gt;
            &lt;button onClick={this.handleClick}&gt;확인&lt;/button&gt;
        &lt;/div&gt;
    );
}</code></pre><p>}</p>
<p>export default EventPractice;</p>
<p>```</p>
<h4 id="🖥️-출력-화면-4">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/e0d4dda2-a827-4cbb-9c78-5f890affded7/image.png" /></p>