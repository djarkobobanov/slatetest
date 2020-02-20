<h1 id="account">Account</h1>

<h2 id="balances">Balances</h2>

<p><api><code>GET /v1/money-transfer/balances</code></api></p>

<p>Retrieve information for all account balances per currency.</p>

<h4 id="input-13">Input</h4>

<table>
<thead>
<tr>
<th>Field</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>page</code></td>
<td>No</td>
<td>Integer</td>
<td>Page number</td>
</tr>

<tr>
<td><code>per_page</code></td>
<td>No</td>
<td>Integer</td>
<td>Number of results per page (default 50, max 100)</td>
</tr>
</tbody>
</table>

<h4 id="output-20">Output</h4>

<p>Array of <a href="#balance">balance</a> objects.</p>

<!-- Balances code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Balances</h3>
<span class="nf">GET</span> <span class="nn">/v1/money-transfer/balances</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
    <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;balance&#34;</span><span class="p">:</span> <span class="mi">10000000</span><span class="p">,</span>
        <span class="nt">&#34;available_balance&#34;</span><span class="p">:</span> <span class="mi">10000000</span><span class="p">,</span>
        <span class="nt">&#34;credit_facility&#34;</span><span class="p">:</span> <span class="mi">0</span>
    <span class="p">}</span>
<span class="p">]</span></code></pre></div>

<!-- End Balances code -->