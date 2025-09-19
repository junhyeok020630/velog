<h1 id="25-eslint와-prettier-적용하기">2.5 ESLint와 Prettier 적용하기</h1>
<h2 id="251-eslint">2.5.1 ESLint</h2>
<ul>
<li>코드 작성 중 실수하면 에러 혹은 경고 메시지를 VS Code 에디터에서 바로 확인 가능<h4 id="🖥️-사용-예시">🖥️ 사용 예시</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/ddb5ab2f-5c5e-41b2-b84f-645fa785fd73/image.png" /></p>
<hr />
<h2 id="252-prettier">2.5.2 Prettier</h2>
<ul>
<li>코드의 가독성을 위해 들여쓰기 사용<h4 id="✍️-들여쓰기가-이상한-코드">✍️ 들여쓰기가 이상한 코드</h4>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/97bcfecb-2ee2-4cf0-a173-7f933c4c2743/image.png" /></p>
<h4 id="🖥️-prettier로-정리된-코드">🖥️ Prettier로 정리된 코드</h4>
<ul>
<li><code>F1</code>을 눌러 <code>format</code> 입력 후 <code>Enter</code><ul>
<li>다른 포맷 도구를 설치 했다면 Prettier와 충돌 가능</li>
</ul>
</li>
</ul>
<p><img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/5872c49f-3338-4978-95e6-19f297240725/image.png" /></p>
<hr />
<h3 id="prettier-주요-기능">Prettier 주요 기능</h3>
<ul>
<li>코드가 제대로 정렬</li>
<li>세미콜론이 빠진 곳에 자동 추가</li>
<li>작은따옴표는 모두 큰따옴표로 변경</li>
</ul>
<h4 id="prettier는-스타일을-쉽게-커스터마이징-가능">Prettier는 스타일을 쉽게 커스터마이징 가능</h4>
<hr />
<ul>
<li>프로젝트의 루트 디렉터리에 <code>.prettierrc</code>라는 파일 생성<h4 id="✍️-prettier-스타일-커스터마이징">✍️ Prettier 스타일 커스터마이징</h4>
<pre><code class="language-json">{
  &quot;singleQuote&quot;: true,
  &quot;semi&quot;: true,
  &quot;useTabs&quot;: false,
  &quot;tabWidth&quot;: 2
}</code></pre>
</li>
<li>들여쓰기는 탭 사용 X (<code>&quot;useTabs&quot;: false</code>) 대신 공백 두칸 (<code>&quot;tabWidth&quot;: 2</code>)</li>
<li>큰따옴표 대신 작은따옴표 사용(<code>&quot;singleQuote&quot;: true</code>)</li>
<li>세미콜론은 언제나 붙이도록 설정(<code>&quot;semi&quot;: true,</code>)</li>
</ul>
<blockquote>
<h3 id="❗-prettier-사전-설정-명령어-확인">❗ Prettier 사전 설정 명령어 확인</h3>
<ul>
<li><a href="https://prettier.io/docs/en/options.html">프리티어 설정 사이트</a></li>
</ul>
</blockquote>
<hr />
<h3 id="2521-저장할-때-자동으로-코드-정리하기">2.5.2.1 저장할 때 자동으로 코드 정리하기</h3>
<ul>
<li><p>자동 <code>prettier</code> 사용</p>
<ol>
<li><p>VS Code 환경설정 열기</p>
<ul>
<li>파일 &gt; 기본 설정 &gt; 설정
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/c3f28294-736d-4108-9044-6ddfc8842703/image.png" /></li>
</ul>
</li>
<li><p>상단 텍스트 박스에서 <code>format on save</code>를 검색하여 체크박스 체크
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/3e7db81e-c710-43e7-b07d-0f851df62887/image.png" /></p>
</li>
</ol>
</li>
</ul>
<hr />
<blockquote>
<h2 id="단원-정리">단원 정리</h2>
<ul>
<li>JSX는 HTML과 유사하지만 완전히 동일 X</li>
<li>코드 : XML 형식 -&gt; 실제 : JS 객체<ul>
<li>용도와 문법에 차이 발생 </li>
</ul>
</li>
</ul>
</blockquote>