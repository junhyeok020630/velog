<h1 id="22-jsx란">2.2 JSX란?</h1>
<ul>
<li>자바스크립트의 확장 문법 (XML과 유사)</li>
<li>브라우저에서 실행되기 전에 코드가 번들링되는 과정에서 바벨을 사용하여 일반 JS 형태의 코드로 변환<h2 id="jsx">JSX</h2>
<h4 id="✍️jsx">✍️JSX</h4>
<pre><code class="language-javascript">function APP() {
return (
  &lt;div&gt;
      Hello &lt;b&gt; react &lt;/b&gt;
  &lt;/div&gt;
);
}</code></pre>
<h4 id="🖥️js로-변환된-코드">🖥️JS로 변환된 코드</h4>
<pre><code class="language-javascript">function APP() {
return React.createElement(&quot;div&quot;, null, &quot;Hello&quot;, React.createElement(&quot;b&quot;, null, &quot;react&quot;));
}</code></pre>
</li>
</ul>
<hr />
<blockquote>
<p>JSX를 활용하여 편리하게 UI 렌더링 가능</p>
<blockquote>
<p>JSX는 공식 자바스크립트 문법이 아님. 바벨을 통해 개발자들이 임의로 만든 문법</p>
</blockquote>
</blockquote>