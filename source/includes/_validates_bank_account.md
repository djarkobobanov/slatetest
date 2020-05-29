<h1 id="validate_bank_account">Validates Bank Account</h1>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<span class="nf">GET</span> <span class="nn">{{URL}}/validation_bank_account?bank_name={{BANK_NAME}}&account_number={{ACC_NUMBER}}</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

<span class="p">{</span>
    <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;account_no&#34;</span><span class="p">:</span> <span class="mi">000001137298</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;danamon&#34;</span><span class="p">,</span>
        <span class="nt">&#34;account_name&#34;</span><span class="p">:</span> <span class="s2">Danamon Simulator A</span>
    <span class="p">}</span>
<span class="p">}
    </code></pre></div>
<p>Check if an account is valid, if valid return account information</p>
<p><api><code>GET {{URL}}/validation_bank_account?bank_name={{BANK_NAME}}&account_number={{ACC_NUMBER}}</code></api></p>

<h4 id="input-13">Input</h4>

<table>
<thead>
<tr>
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>


<tbody>
<tr>
<td><code>bank_name</code></td>
<td>Bank code</td>
</tr>

<tr>
<td><code>account_number</code></td>
<td>Account number</td>
</tr>
</tbody>
</table>

<h4 id="output-20">Output</h4>

<table>
<thead>
<tr>
<th>Parameter</th>
<th>Description</th>
</tr>
</thead>


<tbody>
<tr>
<td><code>bank_name</code></td>
<td>Bank name of partner's bank account</td>
</tr>

<tr>
<td><code>account_name</code></td>
<td>Account name of partner's bank account</td>
</tr>

<tr>
<td><code>account_no</code></td>
<td>Account number of partner's bank account</td>
</tr>
</tbody>
</table>