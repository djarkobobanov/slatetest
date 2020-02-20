<!-- Paginations -->

<h1 id="pagination">Pagination</h1>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/{resource}?page=1&amp;per_page=50</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span></code></pre></div>
<p>API resources supporting bulk fetches via &ldquo;list&rdquo; API methods will be returned in a paginated fashion.</p>

<!-- End Paginations -->

<!-- Input Parameters -->
<h2 id="input-parameters">Input Parameters</h2>

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

<!-- End Input Parameters -->
