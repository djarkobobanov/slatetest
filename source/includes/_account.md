<h1 id="account">Account</h1>

<h2 id="balances">Balances</h2>

<p><api><code>GET api/v1/balances</code></api></p>

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

<tr>
<td><code>currency</code></td>
<td>No</td>
<td>String</td>
<td>Currency in <a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a> format</td>
</tr>

<tr>
<td><code>balance</code></td>
<td>No</td>
<td>Decimal</td>
<td></td>
</tr>

<tr>
<td><code>available_balance</code></td>
<td>No</td>
<td>Decimal</td>
<td></td>
</tr>

<tr>
<td><code>is_active</code></td>
<td>No</td>
<td>Boolean</td>
<td></td>
</tr>
</tbody>
</table>

<h4 id="output-20">Output</h4>

<p>Array of <a href="#balance">balance</a> objects.</p>

<h2 id="balances">Balance History</h2>

<p><api><code>GET api/v1/balances</code></api></p>

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

<tr>
<td><code>credit</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>debit</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>originator</code></td>
<td>No</td>
<td>Polymorph</td>
<td></td>
</tr>

<tr>
<td><code>notes</code></td>
<td>No</td>
<td>Text</td>
<td></td>
</tr>

<tr>
<td><code>description</code></td>
<td>No</td>
<td>Text</td>
<td></td>
</tr>

<tr>
<td><code>balance_id</code></td>
<td>No</td>
<td>Integer</td>
<td> <a href="#balance">Balance</a> information </td>
</tr>
</tbody>
</table>

<h4 id="output-20">Output</h4>

<p>Array of <a href="#balance">balance</a> objects.</p>

<!-- Balances code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Balances</h3>
<span class="nf">GET</span> <span class="nn">api/v1/my_balances</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

<span class="p">{</span>
    <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;total&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;balances&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">{</span>
                <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
                <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;IDR&#34;</span><span class="p">,</span>
                <span class="nt">&#34;balance&#34;</span><span class="p">:</span> <span class="mi">69900000</span><span class="p">,</span>
                <span class="nt">&#34;available_balance&#34;</span><span class="p">:</span> <span class="s2">null</span><span class="p">,</span>
                <span class="nt">&#34;is_active&#34;</span><span class="p">:</span> <span class="s2">true</span><span class="p">,</span>
                <span class="nt">&#34;user_id&#34;</span><span class="p">:</span> <span class="mi">1</
                span><span class="p">,</span>
                <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T09:36:45.277Z</span><span class="p">,</span>
                <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T11:27:45.691Z</span>
            <span class="p">}</span>
        <span class="p">]</span>
    <span class="p">}</span><span class="p">,</span>
    <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">Succesfully get my balances</span>
<span class="p">}
    </code></pre></div>

<!-- End Balances code -->
 