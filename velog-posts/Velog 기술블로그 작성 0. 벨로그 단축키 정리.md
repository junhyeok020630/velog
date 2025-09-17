<h1 id="마크다운이란">마크다운이란?</h1>
<blockquote>
<p>마크다운(markdown)은 일반 텍스트 기반의 경량 마크업 언어다. 일반 텍스트로 서식이 있는 문서를 작성하는 데 사용되며, 일반 마크업 언어에 비해 문법이 쉽고 간단한 것이 특징이다. HTML과 리치 텍스트(RTF) 등 서식 문서로 쉽게 변환되기 때문에 응용 소프트웨어와 함께 배포되는 README 파일이나 온라인 게시물 등에 많이 사용된다.</p>
</blockquote>
<ul>
<li><p>쉽게 읽을 수 있고, 쉽게 작성할 수 있게 만들어짐</p>
</li>
<li><p>가독성이 제일 중요</p>
</li>
<li><p>웹상에서 사용할 수 있는 글쓰기 도구</p>
</li>
<li><p>html을 완전하게 대체하지는 못함</p>
<h1 id="📌-block-elements">📌 Block Elements</h1>
<h2 id="📖-제목headers-넣어보기">📖 제목(headers) 넣어보기</h2>
</li>
<li><p>h1부터 h6을 이용해서 제목을 표현할 수 있다</p>
</li>
<li><p>참고: 회색 박스로 감싸진 부분은 백틱(backtick)(`)으로 감싸서 작성하면 된다.</p>
</li>
</ul>
<hr />
<p>✍ 입력</p>
<p># 첫 번째 수준 제목 (h1)
## 두 번째 수준 제목 (h2)
### 세 번째 수준 제목 (h3)
#### 네 번째 수준 제목 (h4)
##### 다섯 번째 수준 제목 (h5)
###### 여섯 번째 수준 제목 (h6)
💻 출력</p>
<h1 id="첫-번째-수준-제목-h1">첫 번째 수준 제목 (h1)</h1>
<h2 id="두-번째-수준-제목-h2">두 번째 수준 제목 (h2)</h2>
<h3 id="세-번째-수준-제목-h3">세 번째 수준 제목 (h3)</h3>
<h4 id="네-번째-수준-제목-h4">네 번째 수준 제목 (h4)</h4>
<h5 id="다섯-번째-수준-제목-h5">다섯 번째 수준 제목 (h5)</h5>
<h6 id="여섯-번째-수준-제목-h6">여섯 번째 수준 제목 (h6)</h6>
<hr />
<h2 id="📖-인용blockquotes">📖 인용(Blockquotes)</h2>
<p>본문 안에서 인용된 내용을 표시하고자 한다면 &gt; 기호를 사용한다.
✍ 입력</p>
<p>&gt; # 1단
인용문 첫 번째 줄
인용문 두 번째 줄
인용문 세 번째 줄
&gt;&gt; ## 2단
중복해서 사용하면
&gt;&gt;&gt; ### 3단
중첩 인용문을 표현할 수 있다
&gt;&gt;&gt;&gt; #### 4단
계속 중첩할 수 있다</p>
<p>참고: 인용문 안에서 제목 수준을 표현할 수도 있다.
💻 출력</p>
<blockquote>
<h1 id="1단">1단</h1>
<p>인용문 첫 번째 줄
인용문 두 번째 줄
인용문 세 번째 줄</p>
<blockquote>
<h2 id="2단">2단</h2>
<p>중복해서 사용하면</p>
<blockquote>
<h3 id="3단">3단</h3>
<p>중첩 인용문을 표현할 수 있다</p>
<blockquote>
<h4 id="4단">4단</h4>
<p>계속 중첩할 수 있다</p>
</blockquote>
</blockquote>
</blockquote>
</blockquote>
<hr />
<h2 id="📖-리스트">📖 리스트</h2>
<h4 id="일반적인-불릿-리스트는-----중-아무-기호나-이용하면-된다">일반적인 불릿 리스트는 * + - 중 아무 기호나 이용하면 된다.</h4>
<p>✍ 입력</p>
<p>  * 별도
  + 플러스도
  - 마이너스도 똑같이 나온다
💻 출력</p>
<ul>
<li>별도</li>
<li>플러스도</li>
<li>마이너스도 똑같이 나온다</li>
</ul>
<hr />
<h4 id="숫자-리스트는-숫자--마침표를-이용하면-된다">숫자 리스트는 숫자 + 마침표를 이용하면 된다.</h4>
<p>✍ 입력</p>
<pre><code>1. 1번
2. 2번
6. 3번
3. 4번
4. 5번</code></pre><p>💻 출력</p>
<ol>
<li>1번</li>
<li>2번</li>
<li>3번</li>
<li>4번</li>
<li>5번</li>
</ol>
<blockquote>
<p>참고: 숫자 리스트는 순서가 맞지 않아도 자동으로 순서가 맞춰진다.</p>
</blockquote>
<hr />
<h4 id="리스트-안에서-이어지는-문단을-추가할-때는-스페이스바만-입력해줘도-된다">리스트 안에서 이어지는 문단을 추가할 때는 스페이스바만 입력해줘도 된다.</h4>
<p>✍ 입력</p>
<p>- 첫 번째 리스트</p>
<p> 이어지는 두 번째 문단</p>
<p>- 두 번째 리스트</p>
<p> 이어지는 두 번째 문단
💻 출력</p>
<ul>
<li><p>첫 번째 리스트</p>
<p>이어지는 두 번째 문단</p>
</li>
<li><p>두 번째 리스트</p>
<p>이어지는 두 번째 문단</p>
</li>
</ul>
<h2 id="📖-코드블럭code-blocks-만들어보기">📖 코드블럭(Code Blocks) 만들어보기</h2>
<h4 id="한-줄짜리-코드블럭은-tab을-이용해서-작성할-수-있다">한 줄짜리 코드블럭은 Tab을 이용해서 작성할 수 있다.</h4>
<ul>
<li>다만, 이전 문장으로부터 엔터를 두 번 입력해야만 가능하다.<h4 id="여러-줄의-코드-블럭은-백틱-3개로-감싸서-작성한다">여러 줄의 코드 블럭은 백틱(`) 3개로 감싸서 작성한다.</h4>
<pre><code>여러 줄의 코드 블럭은
3개의 백틱으로
감싸서 만들 수 있다</code></pre>✍ 입력</li>
</ul>
<p>```c
#include &lt;stdio.h&gt;</p>
<p>int main()
{
    printf(&quot;Hello, world!\n&quot;);</p>
<pre><code>return 0;</code></pre><p>}
```
💻 출력</p>
<pre><code class="language-c">#include &lt;stdio.h&gt;

int main()
{
    printf(&quot;Hello, world!\n&quot;);

    return 0;
}</code></pre>
<hr />
<p>✍ 입력</p>
<p>```python
print(&quot;hello world&quot;)
```
💻 출력</p>
<pre><code class="language-python">print(&quot;hello world&quot;)</code></pre>
<hr />
<p>✍ 입력</p>
<p>```java
public class helloWorld{
    public void main(String[] args) {
        System.out.println(&quot;Hello World&quot;);
    }
}
```
💻 출력</p>
<pre><code class="language-java">public class helloWorld{
    public void main(String[] args) {
        System.out.println(&quot;Hello World&quot;);
    }
}</code></pre>
<hr />
<h4 id="코드블럭-시작점에-사용하는-언어를-선언하면-syntax-highlighting이-가능하다">코드블럭 시작점에 사용하는 언어를 선언하면 Syntax Highlighting이 가능하다.</h4>
<p>언어 이름 |    작성 방식
|:---    |:---
Bash     | bash
C         | c
C#         | cs
C++         | cpp
CSS         | css
Diff     | diff
HTML, XML|    html
HTTP     | http
Ini         | ini
JSON     | json
Java     | java
JavaScript|    javascript
PHP         | php
Perl     | perl
Python     | python
Ruby     | ruby
SQL         | sql</p>
<hr />
<h2 id="📖-가로선-넣기">📖 가로선 넣기</h2>
<p>가로선을 넣기 위한 다양한 방법이 있는데, 아래의 입력 방식은 모두 동일한 가로선을 만들어준다.
✍ 입력</p>
<pre><code>* * *
***
*****
- - -
---
-----
_ _ _
___
_____</code></pre><p>💻 출력</p>
<hr />
<hr />
<hr />
<hr />
<hr />
<hr />
<hr />
<hr />
<hr />
<h1 id="📌-span-elements">📌 Span Elements</h1>
<h2 id="📖-링크-서식links">📖 링크 서식(Links)</h2>
<h4 id="아래-3가지-방식으로-링크를-나타낼-수-있다">아래 3가지 방식으로 링크를 나타낼 수 있다.</h4>
<ul>
<li>인라인 링크</li>
<li>url 링크</li>
<li>참조 링크
✍ 입력
인라인 링크<pre><code>[인라인 링크](https://velog.io/)
</code></pre></li>
</ul>
<p>url 링크
<a href="https://velog.io/">https://velog.io/</a></p>
<p>참조 링크
[velog]:<a href="https://velog.io/">https://velog.io/</a></p>
<p>[velog]</p>
<pre><code>💻 출력

[인라인 링크](https://velog.io/)

&lt;https://velog.io/&gt;

[velog]:https://velog.io/

[velog] &lt;- 키워드 참조 방식
* * *
## 📖 강조하기(Emphasis)
#### 볼드, 이탤릭, 취소선을 사용할 수 있다.
✍ 입력</code></pre><p><em>이탤릭</em>
<em>이탤릭</em>
<strong>볼드</strong>
<strong>볼드</strong>
<del>취소선</del></p>
<pre><code>💻 출력
*이탤릭*
_이탤릭_
**볼드**
__볼드__
~~취소선~~
* * *
## 📖 이미지 삽입(Images)
#### 링크 삽입 방식과 유사하나, 맨 앞에 !를 붙인다.
✍ 입력</code></pre><ol>
<li><p>일반 이미지 삽입하기: ![대체 텍스트](이미지 링크)
예시: <img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" /></p>
</li>
<li><p>이미지에 설명 삽입하기: ![대체 텍스트](이미지 링크 &quot;이미지 설명 문구&quot;)
예시: <img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" title="Cloudy Sky" /></p>
</li>
</ol>
<p>** 참고: 이미지에 마우스를 올렸을 때 나타나는 설명을 의미함</p>
<ol start="3">
<li>이미지에 링크 걸기: [![대체 텍스트](이미지 링크)](연결할 url &quot;url 설명 문구&quot;)
예시: <a href="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" title="Pixabay Image"><img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" /></a>
```
💻 출력</li>
<li>일반 이미지 삽입 예시 :<img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" /></li>
<li>이미지에 설명 삽입 예시 :<img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" title="Cloudy Sky" /></li>
<li>이미지에 링크 걸기 예시 :<a href="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" title="Pixabay Image"><img alt="CloudScape" src="https://cdn.pixabay.com/photo/2015/03/26/09/47/sky-690293_1280.jpg" /></a></li>
</ol>
<hr />
<h1 id="📌-miscellaneous">📌 MISCELLANEOUS</h1>
<h2 id="📖-기호-표시backslash-escapes">📖 기호 표시(Backslash Escapes)</h2>
<h4 id="마크다운-문법에-있는-기호를-그대로-출력하고-싶다면-역방향-슬래시를-앞에-붙여주면-된다">마크다운 문법에 있는 기호를 그대로 출력하고 싶다면, 역방향 슬래시를 앞에 붙여주면 된다.</h4>
<p>✍ 입력</p>
<pre><code>\*
\_
\()
\{}
\[]
\#
\+
\-
\.
\!
\\</code></pre><p>💻 출력
*
_
()
{}
[]
#
+
-
.
!
\</p>
<hr />
<h2 id="📖-테이블table">📖 테이블(Table)</h2>
<ul>
<li>수직선 기호(|)로 열을 구분할 수 있다</li>
<li>하이픈 기호(-)를 여러 개 붙여서 th와 tr을 구분할 수 있다.</li>
<li>콜론 기호(:)로 정렬을 표현할 수 있다.
✍ 입력<pre><code>|    |left |center|right
|----|:----|:----:|----:
|row1|l1   |  c1  |   r1
|row2|l2   |  c2  |   r2
|row3|l3   |  c3  |   r3</code></pre>💻 출력</li>
</ul>
<table>
<thead>
<tr>
<th></th>
<th align="left">left</th>
<th align="center">center</th>
<th align="right">right</th>
</tr>
</thead>
<tbody><tr>
<td>row1</td>
<td align="left">l1</td>
<td align="center">c1</td>
<td align="right">r1</td>
</tr>
<tr>
<td>row2</td>
<td align="left">l2</td>
<td align="center">c2</td>
<td align="right">r2</td>
</tr>
<tr>
<td>row3</td>
<td align="left">l3</td>
<td align="center">c3</td>
<td align="right">r3</td>
</tr>
<tr>
<td>***</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>## 📖 이모지(Emoji)</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>#### 링크에서 복사+붙여넣기: <a href="https://kr.piliapp.com/twitter-symbols/">https://kr.piliapp.com/twitter-symbols/</a></td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>#### 단축키 이용:</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>* windows: 윈도우 키 + 마침표(.)</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>* mac: Command + Control + Space Bar</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>***</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>## 📖 체크박스(Check Box)</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>#### *, +, - 기호 뒤에 띄어쓰기 이후 대괄호[]를 넣어 작성한다.</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>* 띄어쓰기를 하면 체크되지 않은 상태이고,</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
<tr>
<td>x를 입력해주면 체크된 상태가 된다.</td>
<td align="left"></td>
<td align="center"></td>
<td align="right"></td>
</tr>
</tbody></table>
<p>✍ 입력</p>
<pre><code>- [ ] 체크되지 않은 박스
- [x] 체크된 박스</code></pre><p>💻 출력</p>
<ul>
<li><input disabled="" type="checkbox" /> 체크되지 않은 박스</li>
<li><input checked="" disabled="" type="checkbox" /> 체크된 박스</li>
</ul>
<hr />
<h1 id="끝">끝</h1>
<ul>
<li>앞으로 벨로그에 기술 블로그를 정리할 때 사용하기 위해 직접 정리해보았다. 나와 같은 사람이 있다면 유용하게 활용하길 바란다.</li>
</ul>
<blockquote>
<p>출처 : <a href="https://velog.io/@ybkim3603/Velog%EB%B2%A8%EB%A1%9C%EA%B7%B8-%EC%82%AC%EC%9A%A9%EB%B2%95-%ED%8A%9C%ED%86%A0%EB%A6%AC%EC%96%BC">ybkim님의 velog</a></p>
</blockquote>