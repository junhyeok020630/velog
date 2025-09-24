<h1 id="43-함수-컴포넌트로-구현해-보기">4.3 함수 컴포넌트로 구현해 보기</h1>
<h4 id="✍️-eventpracticejs-함수-컴포넌트로-구현">✍️ EventPractice.js 함수 컴포넌트로 구현</h4>
<pre><code class="language-jsx">import React, { useState } from 'react';

const EventPractice = () =&gt; {
    const [username, setUsername] = useState('');
    const [message, setMessage] = useState('');
    const onChangeUsername = (e) =&gt; setUsername(e.target.value);
    const onChangeMessage = (e) =&gt; setMessage(e.target.value);
    const onClick = () =&gt; {
        alert(`${username} : ${message}`);
        setUsername('');
        setMessage('');
    };
    const onKeyPress = (e) =&gt; {
        if (e.key === 'Enter') {
            onClick();
        }
    };
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;username&quot;
                placeholder=&quot;사용자명&quot;
                value={username}
                onChange={onChangeUsername}
            /&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                value={message}
                onChange={onChangeMessage}
                onKeyPress={onKeyPress}
            /&gt;
            &lt;button onClick={onClick}&gt;확인&lt;/button&gt;
        &lt;/div&gt;
    );
};

export default EventPractice;</code></pre>
<h4 id="🖥️-출력-화면">🖥️ 출력 화면</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/19922994-3b9c-4fed-a976-4c1df1707455/image.png" /></p>
<ul>
<li><code>e.targetname</code>을 사용하지 않고 <code>onChane</code>관련 함수 두 개 생성<ul>
<li>인풋 개수가 늘어날 수록 <code>e.target.name</code>을 사용하는 것이 더 좋다</li>
</ul>
</li>
</ul>
<hr />
<h4 id="✍️-usestate를-통해-상태에-문자열-대신-객체-삽입">✍️ useState를 통해 상태에 문자열 대신 객체 삽입</h4>
<pre><code class="language-jsx">import React, { useState } from 'react';

const EventPractice = () =&gt; {
    const [form, setForm] = useState({
        username: '',
        message: '',
    });
    const { username, message } = form;
    const onChange = (e) =&gt; {
        const nextForm = {
            ...form, // 기존의 form 내용을 이 자리에 복사
            [e.target.name]: e.target.value, // 원하는 값 덮어 씌우기
        };
        setForm(nextForm);
    };
    const onClick = () =&gt; {
        alert(`${username} : ${message}`);
        setForm({
            username: '',
            message: '',
        });
    };
    const onKeyPress = (e) =&gt; {
        if (e.key === 'Enter') {
            onClick();
        }
    };
    return (
        &lt;div&gt;
            &lt;h1&gt;이벤트 연습&lt;/h1&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;username&quot;
                placeholder=&quot;사용자명&quot;
                value={username}
                onChange={onChange}
            /&gt;
            &lt;input
                type=&quot;text&quot;
                name=&quot;message&quot;
                placeholder=&quot;아무거나 입력해 보세요&quot;
                value={message}
                onChange={onChange}
                onKeyPress={onKeyPress}
            /&gt;
            &lt;button onClick={onClick}&gt;확인&lt;/button&gt;
        &lt;/div&gt;
    );
};

export default EventPractice;</code></pre>
<h4 id="🖥️-출력-화면---동일한-기능-제공">🖥️ 출력 화면 - 동일한 기능 제공</h4>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/b70365f1-4b89-4504-b4a6-ebc4f1f604b7/image.png" /></p>
<ul>
<li><code>e.target.name</code> 값을 활용하려면, <code>useState</code>를 쓸 때 인풋이 들어있는 <code>form</code> 객체를 생성 후 사용</li>
</ul>
<hr />
<blockquote>
<h1 id="44-정리">4.4 정리</h1>
</blockquote>
<ul>
<li>리액트의 이벤트 핸들링은 <strong>순수 JS 또는 jQuery를 사용한 웹 애플리케이션의 이벤트 핸들링과 유사</strong></li>
<li>리액트의 장점 : JS에 익숙하면 쉽게 활용 가능하다</li>
<li>기존 HTML DOM Event를 알고 있다면 리액트의 컴포넌트 이벤트도 쉽게 사용 가능<blockquote>
<ul>
<li>함수 컴포넌트로 *<em>여러 개의 인풋을 관리하기 위해 <code>useState</code>에서 <code>form</code>객체 *</em>사용<ul>
<li><code>useReducer</code>와 커스텀 Hooks를 사용해 작업 간편화 가능 - 추후 8장 등장 예정 </li>
</ul>
</li>
</ul>
</blockquote>
</li>
</ul>