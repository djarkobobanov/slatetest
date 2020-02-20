<h1 id="credit-parties">Credit Parties</h1>

<h2 id="information">Information</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">POST</span> <span class="nn">/v1/money-transfer/payers/1/credit-party-information</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;263775892364&#34;</span>
    <span class="p">}</span>
<span class="p">}</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
    <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;Jane&#34;</span><span class="p">,</span>
    <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
    <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1971-01-01&#34;</span><span class="p">,</span>
    <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
    <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
    <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;3 Norfolk Road&#34;</span><span class="p">,</span>
    <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;4581&#34;</span><span class="p">,</span>
    <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Harare&#34;</span><span class="p">,</span>
    <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
    <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;263775892364&#34;</span><span class="p">,</span>
    <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;jane.doe@mail.com&#34;</span><span class="p">,</span>
    <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
    <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
    <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;178027317681327&#34;</span><span class="p">,</span>
    <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Sales Executive&#34;</span><span class="p">,</span>
    <span class="nt">&#34;bank_account_holder_name&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
    <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>
<p><api><code>POST /v1/money-transfer/payers/{id}/credit-party-information</code></api></p>

<p>Retrieve <a href="#beneficiary">beneficiary</a> information based on account details under a given <a href="#payer">payer</a>.</p>

<h4 id="input-14">Input</h4>

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
<td><code>credit_party_identifier</code></td>
<td>Yes</td>
<td>Object</td>
<td><a href="#credit-party-identifier">Credit party identifier</a> information</td>
</tr>
</tbody>
</table>

<h4 id="output-21">Output</h4>
<p><a href="#beneficiary">Beneficiary</a> object.</p>
