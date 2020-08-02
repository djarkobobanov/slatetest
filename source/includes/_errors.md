<!-- Errors -->

# Errors

<!-- HTTP Response -->

<h2 id="http-response">HTTP Response</h2>

<!-- <div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span> <span class="m">401</span> <span class="ne">Unauthorized</span><span class="p">{</span>
    <span class="nt">&#34;errors&#34;</span><span class="p">:</span> <span class="p">[</span>
        <span class="p">{</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;1000401&#34;</span><span class="p">,</span>
            <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">&#34;Unauthorized&#34;</span>
        <span class="p">}</span>
    <span class="p">]</span>
<span class="p">}</span>

<span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span> <span class="m">401</span> <span class="ne">Unauthorized</span><span class="p">{</span>
    <span class="nt">&#34;errors&#34;</span><span class="p">:</span> <span class="p">[</span>
        <span class="p">{</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;1000401&#34;</span><span class="p">,</span>
            <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">&#34;Unauthorized&#34;</span>
        <span class="p">}</span>
    <span class="p">]</span>
<span class="p">}</span></code></pre></div> -->
<p>Uses standard HTTP response codes to indicate whether an API request is successful or not.</p>

<table>
<thead>
<tr>
<th>Status</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>200</code></td>
<td>OK</td>
</tr>

<tr>
<td><code>400</code></td>
<td>Bad Request:<br/>Request was malformed</td>
</tr>

<tr>
<td><code>401</code></td>
<td>Unauthorized:<br/>Credentials missing or invalid</td>
</tr>

<tr>
<td><code>422</code></td>
<td>Unprocessable Entity</td>
</tr>

<tr>
<td><code>404</code></td>
<td>Not Found:<br/>Resource doesn&rsquo;t exist</td>
</tr>

<tr>
<td><code>500</code></td>
<td>Server Error:<br/>Error occurred</td>
</tr>
</tbody>
</table>

<p>Details will always be contained within the HTTP body.</p>
<!-- End HTTP Response -->

<!-- API Error Codes -->

<h2 id="api-error-codes">API Error Code</h2>
<p>In case a transaction is declined, we will send an error_code and error_message on payload callback, explaning what went wrong. Here is a list of codes/messages.</p>
<table>
<thead>
<tr>
<th>Code</th>
<th>Error Message</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>001</code></td>
<td>Invalid beneficiary name</td>
</tr>

<tr>
<td><code>002</code></td>
<td>Invalid destination account number</td>
</tr>

<tr>
<td><code>003</code></td>
<td>Invalid destination account or beneficiary name</td>
</tr>

<tr>
<td><code>004</code></td>
<td>General error</td>
</tr>

<tr>
<td><code>005</code></td>
<td>Timeout error by bank</td>
</tr>

<tr>
<td><code>006</code></td>
<td>Unique reference number violation</td>
</tr>

<tr>
<td><code>007</code></td>
<td>Identical request already processed before</td>
</tr>

<tr>
<td><code>008</code></td>
<td>Bank cannot authenticated request</td>
</tr>

<tr>
<td><code>009</code></td>
<td>Bank balance disbursement validation failed</td>
</tr>

<tr>
<td><code>010</code></td>
<td>Payload validation failed</td>
</tr>

<tr>
<td><code>011</code></td>
<td>Otp code expired / blocked</td>
</tr>

<tr>
<td><code>012</code></td>
<td>Beneficiary account is blocked</td>
</tr>

<tr>
<td><code>013</code></td>
<td>Sender and receiver account are the same</td>
</tr>

<tr>
<td><code>014</code></td>
<td>Monthly account balance limit exceeded</td>
</tr>

<tr>
<td><code>015</code></td>
<td>Account balance limit exceeded</td>
</tr>


</tbody>
</table>

<!-- End API Error codes -->


<h2 id="api-error-codes">Validation Error Message</h2>
<p>If transaction failed to be create or confirm, we will return an message on response. Here is a list of validation messages.</p>
<table>
<thead>
<tr>
<th>Method</th>
<th>Error Message</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>Create Transaction</code></td>
<td>reference_id must be uniq</td>
</tr>

<tr>
<td><code>Create Transaction</code></td>
<td>Validations for all required fields (sender, beneficiary, source, destination object)</td>
</tr>

<tr>
<td><code>Create Transaction</code></td>
<td>Beneficiary account must be in integer</td>
</tr>

<tr>
<td><code>Confirm Transaction</code></td>
<td>Insufficient amount Balance</td>
</tr>


</tbody>
</table>