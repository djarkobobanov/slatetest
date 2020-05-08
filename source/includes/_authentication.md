<!-- Authentication -->

<h1 id="authentication">Authentication</h1>

<p><api><code>POST {URL}/authenticate
</code></api></p>

<p>Access to all endpoints of the API requires authentication, through one of the following means:</p>

<ol>
<li><a href="https://en.wikipedia.org/wiki/Basic_access_authentication">HTTP Basic Auth</a></li>
</ol>

<div class="highlight"><pre class="chroma"><code class="language-shell" data-lang="shell">
<p>Success</p>
<span class="nf">POST</span> <span class="nn">{URL}/authenticate/</span><span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
</code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
   <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
   <span class="err">data</span> <span class="p">:</span> <span class="p">{</span>
         <span class="err">auth_token</span> <span class="p">:</span>
            <span class="s2">&#34;{auth_token}&#34;</span>
         <span class="err">api_key</span> <span class="p">:</span>
            <span class="s2">&#34;{api_key}&#34;</span>
<span class="p">}</span>


<p>Unsuccess</p>
<span class="nf">POST</span> <span class="nn">{URL}/authenticate/</span><span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
</code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
   <span class="err">status</span> <span class="err">500</span><span class="p">,</span>
   <span class="err">error</span> <span class="p">:</span> <span class="s2">&#34;internal server error&#34;</span>
<span class="p">}</span>
</code></pre></div>

<!-- End Authentication -->

<!-- Basic Auth -->

<h2 id="basic-auth">Basic Auth</h2>
<div class="highlight"><pre class="chroma"><code class="language-shell" data-lang="shell"><span class="s2">curl --location</span> <span class="s2">--request POST '{URL}/authenticate'</span>
<span class="s2">--header 'Content-Type: application/json' \
<span class="s2">--data-raw '{
	<span class="mi">"email": "{email}"</span>, 
	<span class="mi">"password": "{password}"</span>
}'</code></pre></div>
<table>
<thead>
<tr>
<th>URL Part</th>
<th>Value</th>
</tr>
</thead>

<tbody>
<tr>
<td>Email</td>
<td>API key</td>
</tr>

<tr>
<td>Password</td>
<td>API secret</td>
</tr>
</tbody>
</table>

<!-- End Basic Auth -->
