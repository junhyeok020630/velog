<h1 id="13-작업-환경-설정">1.3 작업 환경 설정</h1>
<ul>
<li>리액트 프로젝트 환경설정 과정<ol>
<li>NOde.js / npm, yarn 설치하기</li>
<li>코드 에디터 설치하기</li>
<li>Git 설치하기</li>
<li>create-react-app으로 프로젝트 생성하기<h2 id="131-nodejs와-npm">1.3.1 Node.js와 npm</h2>
</li>
</ol>
</li>
<li>리액트 프로젝트 생성을 위해서는 Node.js 설치 필수</li>
<li>Node.js : 크롬 V8 js 엔진으로 빌드한 js 런타임<ul>
<li>웹 브라우저 환경이 아닌 곳에서도 js를 사용하여 연산 가능</li>
<li>리액트 : 웹브라우저에서 실행되어 Node와 직접적 연관 X<ul>
<li>개발에 필요한 주요 도구들이 Node.js 사용<ul>
<li>바벨 : ECMAScript 6 호환</li>
<li>웹팩 : 코드 수정 시 웹 브라우저 리로딩</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li>npm : Node.js 패키지 매니저 도구<ul>
<li>패키지 설치 및 버전 관리<h3 id="1312-설치--windows">1.3.1.2 설치 : Windows</h3>
</li>
</ul>
</li>
<li><a href="https://nodejs.org/ko/download/">Node.js 공식 다운로드 페이지</a></li>
</ul>
<ol>
<li>Windows Installer로 설치
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/bdfd8c5e-e3c9-402c-a8ad-d5542a61e21e/image.png" /></li>
<li>CMD로 설치 여부 확인
<code>$ node -v</code><h2 id="132-yarn">1.3.2 yarn</h2>
</li>
</ol>
<ul>
<li>yarn : npm 대체 도구 ; npm보다 더 빠르고 효율적인 캐시 시스템과 부가 기능 제공<h3 id="1321-yarn-설치">1.3.2.1 yarn 설치</h3>
<code>$ npm install --global yarn</code><h3 id="1322-설치-확인">1.3.2.2 설치 확인</h3>
<code>$ yarn --version</code><h2 id="133-에디터-설치">1.3.3 에디터 설치</h2>
</li>
<li>VS Code 사용</li>
<li><a href="https://code.visualstudio.com/Download">VS Code 설치 링크</a><blockquote>
<p>유용한 확장 프로그램</p>
<ul>
<li>ESLint : JS 문법 및 코드 스타일 검사 도구</li>
<li>Reactjs Code Snippets : 리액트 컴포넌트 및 라이프사이클 함수를 작성할 때 단축키를 사용하여 코드 생성(charalampos karypidis)</li>
<li>Prettier-Code formatter : 코드 스타일을 자동으로 정리해주는 도구</li>
</ul>
</blockquote>
<h2 id="134-git-설치">1.3.4 Git 설치</h2>
</li>
<li>Git : 형상 관리 도구 - 프로젝트 버전을 관리하고 협업할 때 매우 핵심적인 역할</li>
<li><a href="https://git-scm.com/download">git 설치 링크</a></li>
<li>bash 에뮬레이터도 함께 설치 - 터미널 명령어를 리눅스 명령어와 통일하기 위해 사용<h2 id="135-create-react-app으로-프로젝트-생성하기">1.3.5 create-react-app으로 프로젝트 생성하기</h2>
</li>
<li><code>create-react-app</code> : 리액트 프로젝트를 생성할 때 필요한 웹팩, 바벨의 설치 및 설정 과정을 생략하고 바로 프로젝트 작업 환경을 구축해주는 도구</li>
<li>도구를 사용하기 위한 명령어<ul>
<li>yarn create react-app &lt;프로젝트 이름&gt;
<code>$ yarn create react-app hello-react</code><ul>
<li>실행 화면
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/a5a0a24e-a448-4e78-8c08-96bcfaffef3e/image.png" /></li>
</ul>
</li>
<li>개발 전용 서버 구동
<code>$ cd hello-react</code>
<code>$ yarn start</code><ul>
<li>실행 화면
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/ebd65d9d-ee84-4151-933e-eaaaa1d5c4b3/image.png" />
<img alt="" src="https://velog.velcdn.com/images/junhyeok020630/post/216f5b06-49df-417e-8f14-10771a630b4f/image.png" /><blockquote>
<p>리액트 서버 구동 완료 - 프로젝트 폴더 내 리액트 프로젝트 생성 완료</p>
</blockquote>
</li>
</ul>
</li>
</ul>
</li>
</ul>