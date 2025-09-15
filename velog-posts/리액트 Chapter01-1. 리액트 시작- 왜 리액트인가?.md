<h1 id="11-왜-리액트인가">1.1 왜 리액트인가?</h1>
<ul>
<li><p>대규모 애플리케이션 중 프론트엔드 사이드로 돌아가는 애플리케이션 구조를 관리</p>
<ul>
<li><p>프레임 워크를 활용하여 애플리케이션 관리 (순수 JS 만으로는 한계)</p>
<ul>
<li><p><strong>MVC : Model-View-Controller</strong>
  <img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/d2ffa55b-31a0-4ec9-a7e2-ffa6eed8d488/image.png" /></p>
</li>
<li><p>MVVM : Model-View-View-Model</p>
</li>
<li><p>MVW : Model-View-Whatever</p>
<blockquote>
<p>공통점 : Model과 View 존재</p>
</blockquote>
</li>
</ul>
</li>
<li><p><strong>Model</strong> : 애플리케이션에서 사용하는 <strong>데이터</strong>를 관리하는 영역</p>
</li>
<li><p><strong>View</strong> : 사용자에게 <strong>보이는</strong> 부분 </p>
</li>
<li><p><strong>Controller</strong> : 사용자가 프로그램에게 작업 요청 시 <strong>컨트롤러</strong>가 모델 <strong>데이터를 조회하거나 수정, 변경된 사항을 뷰에 반영</strong></p>
</li>
</ul>
</li>
<li><p>뷰의 변형(mutate)</p>
<ul>
<li>아래의 json을 활용하는 뷰가 있다 가정<pre><code>{
  &quot;title : &quot;Hello&quot;        
  &quot;contents&quot; : &quot;Hello World&quot;,
  &quot;author&quot; : &quot;velopert&quot;,
  &quot;likes&quot; : 1
}</code></pre></li>
</ul>
<pre><code>&lt;div id=&quot;post-1&quot;&gt;
    &lt;div class=&quot;title&quot;&gt;Hello&lt;/div&gt;
    &lt;div class=&quot;contents&quot;&gt;Hello World&lt;/div&gt;
    &lt;div class=&quot;author&quot;&gt;velopert&lt;/div&gt;
    &lt;div class=&quot;likes&quot;&gt;1&lt;/div&gt;
&lt;/div&gt;</code></pre><ul>
<li>likes를 2로 변경하면 애플리케이션에서 post-1의 likes 요소를 찾아 내부 수정</li>
<li>애플리케이션 규모가 클 수록 복잡성 향상 및 성능 저하<ul>
<li>페이스북 개발 팀 : 데이터의 변화에 따라 화면의 변화를 고민하지 말고 기존 뷰를 날려버리고 새롭게 렌더링?<ul>
<li>장점 : 매우 간단한 애플리케이션 구조, 코드 작성량 저하</li>
<li>단점 : CPU 점유율 증가 및 메모리 과사용, 사용자가 인풋 박스에 텍스트 입력 시 기존 렌더링된 것은 사라지고, 새로 렌더링하면 끊김현상 발생<blockquote>
<p><strong>React : 최대한 성능을 아끼고(데이터가 변할 때 마다 리렌더링) 편안한 UX 제공을 위해 개발한 언어</strong></p>
</blockquote>
<h2 id="111-리액트-이해">1.1.1 리액트 이해</h2>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li><p>UI를 만드는 데 사용하는 JS 라이브러리</p>
<ul>
<li>오직 V(View)만 신경 쓰는 라이브러리</li>
</ul>
</li>
<li><p><strong>컴포넌트</strong> : 리액트 프로젝트에서 특정 부분이 어떻게 생길지 정하는 선언체</p>
<blockquote>
<p><strong>컴포넌트와 템플릿의 차이점</strong></p>
<p>템플릿 : 데이터셋이 주어지면 HTML 태그 형식을 문자열로 반환
컴포넌트 : 좀 더 복합적인 개념, 재사용이 가능한 API, 컴포넌트 하나에서 해당 컴포넌트의 생김새와 작동 방식 정의</p>
</blockquote>
</li>
<li><p>렌더링 : 사용자 화면에 뷰를 보여 주는 것</p>
<ul>
<li>초기 렌더링 : 리액트 컴포넌트가 최초로 실행</li>
<li>리렌더링 : 컴포넌트의 데이터 변경으로 다시 실행<h3 id="1111-초기-렌더링">1.1.1.1 초기 렌더링</h3>
</li>
</ul>
</li>
<li><p>리액트의 초기 렌더링 함수 : <code>render() {...}</code></p>
<ul>
<li>컴포넌트가 어떻게 생겼는지 정의</li>
</ul>
<ol>
<li>html 형식의 문자열 반환 X -&gt; <strong>뷰가 어떻게 생겼고, 어떻게 작동하는지에 대한 정보를 지닌 객체</strong> 반환</li>
<li>컴포넌트 내부에는 또 다른 컴포넌트 존재 가능<ul>
<li>render 함수 실행 시 내부의 컴포넌트도 재귀적 렌더링</li>
</ul>
</li>
<li>최상위 컴포넌트의 렌더링 작업이 끝나면 지니고 있는 정보를 사용해 HTML 마크업 생성 -&gt; 실제 페이지의 DOM 요소 안에 주입
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/688e0446-0813-4155-91b9-4e1f362464e1/image.png" /><blockquote>
<p><strong>컴포넌트를 렌더링하는 분리된 두가지 절차</strong></p>
<ol>
<li>문자열 형태의 HTML 코드 생성</li>
<li>특정 DOM에 해당 내용을 주입하여 이벤트 적용 </li>
</ol>
</blockquote>
<h3 id="1112-조화-과정">1.1.1.2 조화 과정</h3>
</li>
</ol>
</li>
<li><p>리액트의 업데이트 과정(조화과정)</p>
<ul>
<li>조화과정(reconciliation) : 리액트의 뷰 업데이트</li>
<li>컴포넌트의 데이터 변화<ul>
<li>사용자 시점 : 뷰의 변형</li>
<li>내부적 시점 : 새로운 요소로 데이터 갈아 끼우기</li>
</ul>
</li>
<li><code>render()</code>로 동작<ol>
<li>데이터 업데이트 시 새로운 데이터로 <code>render()</code>함수 재호출</li>
<li>결과를 바로 DOM에 반영하지 않고, 초기 render 함수로 생성한 컴포넌트 정보와 비교
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/2fb3e3ec-fcf2-4026-b9dc-8a3706fc227f/image.png" /></li>
<li>최소한의 연산(변경사항만)으로 DOM 트리 업데이트<blockquote>
<p>루트 노드부터 전체 컴포넌트를 리렌더링하는 것처럼 보이지만 최적의 자원만을 사용하여 리렌더링 수행</p>
</blockquote>
</li>
</ol>
</li>
</ul>
</li>
</ul>