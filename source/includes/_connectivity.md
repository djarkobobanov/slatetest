# Connectivity

<!-- Ping -->

<h2 id="ping">Ping</h2>

<p><api><code>GET /ping</code></api></p>

<p>Query API status.</p>

<h4 id="output">Output</h4>

<table>
<thead>
<tr>
<th>Field</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>status</code></td>
<td>String</td>
<td>API status</td>
</tr>
</tbody>
</table>

<p>Expected value of <code>status</code> should be &ldquo;up&rdquo;.</p>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/ping</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
   <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="s2">&#34;up&#34;</span>
<span class="p">}</span></code></pre></div>

<!-- End Ping -->
