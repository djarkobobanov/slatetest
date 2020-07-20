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

<!-- <h2 id="api-error-codes">API Error Codes</h2>

<table>
<thead>
<tr>
<th>Code</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>1000401</code></td>
<td>Unauthorized</td>
</tr>

<tr>
<td><code>1000404</code></td>
<td>Resource not found</td>
</tr>

<tr>
<td><code>1000999</code></td>
<td>Invalid parameter</td>
</tr>

<tr>
<td><code>1000998</code></td>
<td>Source country not authorized</td>
</tr>

<tr>
<td><code>1003001</code></td>
<td>Payer is inactive in your account</td>
</tr>

<tr>
<td><code>1003002</code></td>
<td>Invalid payer</td>
</tr>

<tr>
<td><code>1003007</code></td>
<td>Payer is currently unavailable</td>
</tr>

<tr>
<td><code>1003008</code></td>
<td>Destination amount is invalid</td>
</tr>

<tr>
<td><code>1003009</code></td>
<td>Parameter page is outside of the page range</td>
</tr>

<tr>
<td><code>1003010</code></td>
<td>Destination currency not provided by payer</td>
</tr>

<tr>
<td><code>1003011</code></td>
<td>Transaction amount below minimum of the selected payer</td>
</tr>

<tr>
<td><code>1003012</code></td>
<td>Transaction amount over maximum of the selected payer</td>
</tr>

<tr>
<td><code>1005001</code></td>
<td>Account is invalid</td>
</tr>

<tr>
<td><code>1007001</code></td>
<td>External ID has already been used</td>
</tr>

<tr>
<td><code>1007002</code></td>
<td>Transaction has already been confirmed</td>
</tr>

<tr>
<td><code>1007003</code></td>
<td>Transaction can not be confirmed</td>
</tr>

<tr>
<td><code>1007004</code></td>
<td>Transaction can no longer be confirmed, quotation has expired</td>
</tr>

<tr>
<td><code>1007100</code></td>
<td>Method is not supported by this payer</td>
</tr>

<tr>
<td><code>1007101</code></td>
<td>Method is currently unavailable</td>
</tr>

<tr>
<td><code>1008002</code></td>
<td>Quotation not found</td>
</tr>

<tr>
<td><code>1008003</code></td>
<td>Quotation has expired</td>
</tr>

<tr>
<td><code>1008004</code></td>
<td>Transaction not found</td>
</tr>

<tr>
<td><code>1009001</code></td>
<td>Unexpected error, please contact our support team</td>
</tr>
</tbody>
</table> -->

<!-- End API Error codes -->
