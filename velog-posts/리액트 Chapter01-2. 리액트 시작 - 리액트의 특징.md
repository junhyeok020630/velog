<h1 id="12-리액트의-특징">1.2 리액트의 특징</h1>
<h2 id="121-virtual-dom">1.2.1 Virtual DOM</h2>
<h3 id="1211-dom이란">1.2.1.1 DOM이란?</h3>
<ul>
<li>** DOM : Document Object Model** - 객체로 문서 구조를 표현하는 방법(XML, HTML)<ul>
<li>웹 브라우저 : DOM을 활용하여 객체에 JS와 CSS 적용</li>
<li><strong>트리 형태</strong>이기 때문에 특정 노드를 찾거나 수정, 제거, 삽입 가능
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/5a9e7264-de44-421d-8921-9f9bcaf09e5e/image.png" /><blockquote>
<h3 id="dom은-과연-느릴까">DOM은 과연 느릴까?</h3>
<p>DOM은 동적 UI에 최적화되어 있지 않음
규모가 큰 웹의 경우 수많은 데이터(element) 로딩 -&gt; DOM에 직접 접근하여 변화를 주면 성능 문제 발생</p>
<p>DOM 자체를 읽고 쓰는 성능은 JS 객체 처리 성능과 유사함
<strong>DOM에 변화가 생기면 CSS를 다시 연산하고, 레이아웃을 구성하고 페이지를 리페인트 해야됨 -&gt; 시간 허비</strong></p>
<h4 id="해결법">해결법</h4>
<p>DOM을 최소한으로 조작하여 작업을 처리하는 방식
<strong>리액트의 Virtual DOM 방식으로 DOM 업데이트를 추상화하여 DOM 처리 횟수를 최소화하고 효율적으로 진행</strong></p>
</blockquote>
</li>
</ul>
</li>
</ul>
<h3 id="1212-virtual-dom">1.2.1.2 Virtual DOM</h3>
<ul>
<li><p>실제 DOM에 접근하여 조작하는 대신, 추상화를 거친 JS 객체를 구성하여 사용</p>
</li>
<li><p><strong>리액트가 DOM을 업데이트하는 3가지 절차</strong></p>
<ol>
<li>데이터를 업데이트하면 전체 UI를 Virtual DOM에 리렌더링</li>
<li>이전 Virtual DOM의 내용과 현재 내용 비교</li>
<li>바뀐 부분만 실제 DOM 적용</li>
</ol>
</li>
<li><p>Virtual DOM - 오른쪽 새로운 DOM 트리
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/9206718d-029d-4448-abec-7975804b47ea/image.png" /></p>
<blockquote>
<p><strong>Virtual DOM은 무조건 성능 향상?</strong></p>
<p>지속적으로 데이터가 변화하는 대규모 애플리케이션에 알맞는 언어
단순 라우팅 정도만 있는 정적인 페이지는 리액트를 사용하지 않는 것이 더 좋은 성능을 보이기도 함
리액트와 Virtual DOM : 업데이트 처리 간결성
| UI를 업데이트하는 과정에서 생기는 복잡함 해소</p>
</blockquote>
<h2 id="122-기타-특징">1.2.2 기타 특징</h2>
</li>
<li><p>리액트는 MVC, MVW의 구조를 지향하는 것이 아닌 View만 담당</p>
</li>
<li><p>리액트는 프레임워크? X -&gt; 라이브러리</p>
</li>
<li><p>타 라이브러리와 함께 사용하여 웹 구현 가능
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/218cdffa-1aca-432e-ab5b-9cd85eac25f0/image.png" /></p>
<ul>
<li>라우팅 기능 : <code>react-router</code></li>
<li>Ajax 처리 : <code>axios</code>나 <code>fetch</code></li>
<li>상태 관리 : <code>redux</code>나 <code>MobX</code></li>
</ul>
</li>
<li><p>다른 웹 프레임워크와 혼용하여 사용</p>
<ul>
<li>Spring 웹 프레임워크와 혼용하여 사용 중</li>
</ul>
</li>
</ul>