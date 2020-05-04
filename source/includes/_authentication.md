<!-- Authentication -->

<h1 id="authentication">Authentication</h1>

<p><api><code>POST videl.rubyh.co/api/v1/authenticate
</code></api></p>

<p>Access to all endpoints of the API requires authentication, through one of the following means:</p>

<ol>
<li><a href="https://en.wikipedia.org/wiki/Basic_access_authentication">HTTP Basic Auth</a></li>
</ol>

<!-- End Authentication -->

<!-- Basic Auth -->

<h2 id="basic-auth">Basic Auth</h2>
<div class="highlight"><pre class="chroma"><code class="language-shell" data-lang="shell"><span class="s2">curl --location</span> <span class="s2">--request POST 'api/v1/authenticate'</span>
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
