<!-- Authentication -->

<h1 id="authentication">Authentication</h1>

<p>Access to all endpoints of the API requires authentication, through one of the following means:</p>

<ol>
<li><a href="https://en.wikipedia.org/wiki/Basic_access_authentication">HTTP Basic Auth</a></li>
<li><a href="https://en.wikipedia.org/wiki/Digest_access_authentication">Digest Auth</a> (<a href="https://en.wikipedia.org/wiki/Hash-based_message_authentication_code">HMAC</a>)</li>
</ol>

<!-- End Authentication -->

<!-- Basic Auth -->

<h2 id="basic-auth">Basic Auth</h2>
<div class="highlight"><pre class="chroma"><code class="language-shell" data-lang="shell">curl https://api.mm.thunes.com/ping <span class="se">\
</span><span class="se"></span>  -u <span class="s2">&#34;</span><span class="si">${</span><span class="nv">API_KEY</span><span class="si">}</span><span class="s2">:</span><span class="si">${</span><span class="nv">API_SECRET</span><span class="si">}</span><span class="s2">&#34;</span></code></pre></div>
<table>
<thead>
<tr>
<th>URL Part</th>
<th>Value</th>
</tr>
</thead>

<tbody>
<tr>
<td>username</td>
<td>API key</td>
</tr>

<tr>
<td>password</td>
<td>API secret</td>
</tr>
</tbody>
</table>

<!-- End Basic Auth -->
