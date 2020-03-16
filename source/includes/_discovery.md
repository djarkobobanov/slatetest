<h1 id="discovery">Discovery</h1>

<!-- Services -->

<h2 href="#service">Services</h2>

<p><api><code>GET api/v1/services</code></api></p>

<p>Retrieve list of all available services.</p>

<h4 id="input">Input</h4>

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
<td><code>name</code></td>
<td>No</td>
<td>String</td>
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

<h4 id="output-1">Output</h4>

<p>Array of <a href="service">service</a> objects in a <a href="#pagination">paginated</a> fashion.</p>

<!-- End Services -->

<!-- Payers -->

<h2 id="payers">Payers</h2>

<p><api><code>GET api/v1/payers</code></api></p>

<p>Retrieve information for all payers available for a given account, optionally filtered based on specified parameters.</p>

<h4 id="input-1">Input</h4>

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
<td><code>name</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>precision</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>service_id</code></td>
<td>No</td>
<td>Integer</td>
<td><a href="#service">Service ID</a></td>
</tr>

<tr>
<td><code>country_iso_code</code></td>
<td>No</td>
<td>String</td>
<td>Country code in <a href="https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3">ISO 3166-1 alpha-3</a> format</td>
</tr>

<tr>
<td><code>currency</code></td>
<td>No</td>
<td>String</td>
<td>Currency in <a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a> format</td>
</tr>

<tr>
<td><code>minimum_amount</code></td>
<td>No</td>
<td>Float</td>
<td></td>
</tr>

<tr>
<td><code>maximum_amount</code></td>
<td>No</td>
<td>Float</td>
<td></td>
</tr>

<tr>
<td><code>required_sender_fields</code></td>
<td>No</td>
<td>Array</td>
<td></td>
</tr>

<tr>
<td><code>required_beneficiary_fields</code></td>
<td>No</td>
<td>Array</td>
<td></td>
</tr>

<tr>
<td><code>destination_info</code></td>
<td>No</td>
<td>Array</td>
<td></td>
</tr>
</tbody>
</table>

<h4 id="output-2">Output</h4>

<p>Array of <a href="#payer">payer</a> objects in a <a href="#pagination">paginated</a> fashion.</p>

<p>&ndash;</p>

<p><api><code>GET api/v1/payers/{id}</code></api></p>

<p>Retrieve information for a given <a href="#payer">payer</a>.</p>

<h4 id="output-3">Output</h4>

<p><a href="#payer">Payer</a> object.</p>

<!-- End Payers -->

<!-- Payes Rates -->

<h2 id="payer-rates">Rates</h2>

<p><api><code>GET api/v1/rates/{source}/{destination}</code></api></p>

<p>Retrieve <a href="#rates">rates</a> under a given <a href="#payer">payer</a>.</p>

<h4 id="output-4">Output</h4>

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
<td><code>destination_currency</code></td>
<td>String</td>
<td>Currency in <a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a> format</td>
</tr>

<tr>
<td><code>source_currency</code></td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>rates</code></td>
<td>Array</td>
<td><a href="#rates">Rates</a> information</td>
</tr>
</tbody>
</table>

<!-- End Payers Rates -->

<!-- Countries-->

<h2 id="countries">Countries</h2>

<p><api><code>GET api/v1/countries</code></api></p>

<p>Retrieve list of <a href="#country">countries</a> for all money transfer <a href="#services">services</a> available for a given account.</p>

<h4 id="input-2">Input</h4>

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
<td><code>iso</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>name</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>iso_3</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>iso_name</code></td>
<td>No</td>
<td>String</td>
<td></td>
</tr>

<tr>
<td><code>numcode</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>currency</code></td>
<td>No</td>
<td>String</td>
<td>Currency in <a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a> format</td>
</tr>
</tbody>
</table>

<h4 id="output-5">Output</h4>

<p>Array of <a href="#country">country</a> objects in a paginated fashion.</p>

<!-- Code Services -->
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Services</h3>
<span class="nf">GET</span> <span class="nn">api/v1/services</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
   <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
   <span class="p">},</span>
   <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;BankAccount&#34;</span>
   <span class="p">},</span>
   <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;CashPickup&#34;</span>
   <span class="p">}</span>
<span class="p">]</span></code></pre></div>

<!-- End code Services -->

<!-- Payers code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Payers</h3>
<span class="nf">GET</span> <span class="nn">api/v1/payers</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
   <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet Payer&#34;</span><span class="p">,</span>
      <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
      <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
      <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;USA&#34;</span><span class="p">,</span>
      <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
      <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
         <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
         <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
      <span class="p">},</span>
      <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;date_of_birth&#34;</span>
         <span class="p">]</span>
      <span class="p">],</span>
      <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;lastname&#34;</span>
         <span class="p">]</span>
      <span class="nt">&#34;destination_info&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
      <span class="p">],</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#3#34;CashPickup Payer&#34;</span><span class="p">,</span>
      <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
      <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;PHP&#34;</span><span class="p">,</span>
      <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;PHL&#34;</span><span class="p">,</span>
      <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
       <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
         <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
         <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
      <span class="p">},</span>
      <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;date_of_birth&#34;</span>
         <span class="p">]</span>
      <span class="p">],</span>
      <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
            <span class="s2">&#34;lastname&#34;</span>
         <span class="p">]</span>
      <span class="p">],</span>
      <span class="nt">&#34;destination_info&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>

<span class="p">]</span></code></pre></div>

<!-- End Pyaers code -->

<!-- Payers rate code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Rates</h3>
<span class="nf">GET</span> <span class="nn">api/v1/rates</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;destination_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;CUC&#34;</span><span class="p">,</span>
    <span class="nt">&#34;rates&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;EUR&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">{</span>
                <span class="nt">&#34;source_amount_min&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
                <span class="nt">&#34;source_amount_max&#34;</span><span class="p">:</span> <span class="mi">88</span><span class="p">,</span>
                <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.10847692409526</span>
            <span class="p">},</span>
            <span class="p">{</span>
                <span class="nt">&#34;source_amount_min&#34;</span><span class="p">:</span> <span class="mi">88</span><span class="p">,</span>
                <span class="nt">&#34;source_amount_max&#34;</span><span class="p">:</span> <span class="mi">8800</span><span class="p">,</span>
                <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.10847692409526</span>
            <span class="p">}</span>
        <span class="p">]</span>
    <span class="p">}</span>
<span class="p">}</span></code></pre></div>

<!-- End Payers rate code -->

<!-- Countries code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Countries</h3>
<span class="nf">GET</span> <span class="nn">api/v1/countries</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
    <span class="p">{</span>
        <span class="nt">&#34;iso&#34;</span><span class="p">:</span> <span class="s2">&#34;KEN&#34;</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Kenya&#34;</span>
        <span class="nt">&#34;iso_3&#34;</span><span class="p">:</span> <span class="s2"></span>
        <span class="nt">&#34;iso_name&#34;</span><span class="p">:</span> <span class="s2"></span>
        <span class="nt">&#34;numcode&#34;</span><span class="p">:</span> <span class="s2"></span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2"></span>
    <span class="p">}</span>
<span class="p">]</span></code></pre></div>

<!-- End Countries code -->

<!-- End Countries -->
