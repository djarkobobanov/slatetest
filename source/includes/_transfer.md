<h1 id="transfers">Transfers</h1>

<!-- Transactions -->

<h2 id="transactions">Transactions</h2>

<p><api><code>POST api/v1/transactions/create</code></api></p>

<p>Create a new transaction with transfer values specified from a given <a href="#quotation">quotation</a>.</p>

<h4 id="input-17">Input</h4>

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
<td><code>reference_id</code></td>
<td>Yes</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>payer_id</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>source</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>destination</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>

<tr>
<td><code>beneficiars</code></td>
<td>No</td>
<td>Object</td>
<td></td>
</tr>

<tr>
<td><code>compliance</code></td>
<td>No</td>
<td>Integer</td>
<td></td>
</tr>
</tbody>
</table>

<h4 id="output-26">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<p>&ndash;</p>

<p><api><code>POST /v1/money-transfer/quotations/ext-{external_id}/transactions</code></api></p>

<p>Create a new transaction with transfer values specified from a given <a href="#quotation">quotation</a> based on the external ID.</p>

<h4 id="input-18">Input</h4>

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
<td><a href="#credit-party-identifier">Credit party identifier</a></td>
</tr>

<tr>
<td><code>retail_rate</code></td>
<td>No</td>
<td>Number</td>
<td>Retail rate</td>
</tr>

<tr>
<td><code>retail_fee</code></td>
<td>No</td>
<td>Number</td>
<td>Retail fee</td>
</tr>

<tr>
<td><code>retail_fee_currency</code></td>
<td>No</td>
<td>String</td>
<td>Retail fee currency in <a href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</a> format</td>
</tr>

<tr>
<td><code>sender</code></td>
<td>Yes</td>
<td>Object</td>
<td><a href="#sender">Sender information</a></td>
</tr>

<tr>
<td><code>beneficiary</code></td>
<td>Yes</td>
<td>Object</td>
<td><a href="#beneficiary">Beneficiary information</a></td>
</tr>

<tr>
<td><code>external_id</code></td>
<td>Yes</td>
<td>String</td>
<td>External ID</td>
</tr>

<tr>
<td><code>external_code</code></td>
<td>No</td>
<td>String</td>
<td>External reference code</td>
</tr>

<tr>
<td><code>callback_url</code></td>
<td>No</td>
<td>String</td>
<td><a href="#callback">Callback URL</a></td>
</tr>

<tr>
<td><code>purpose_of_remittance</code></td>
<td>No</td>
<td>String</td>
<td><a href="#purpose-of-remittance">Purpose of the remittance</a></td>
</tr>

<tr>
<td><code>additional_information_1</code></td>
<td>No</td>
<td>String</td>
<td>Additional information</td>
</tr>

<tr>
<td><code>additional_information_2</code></td>
<td>No</td>
<td>String</td>
<td>Additional information</td>
</tr>

<tr>
<td><code>additional_information_3</code></td>
<td>No</td>
<td>String</td>
<td>Additional information</td>
</tr>
</tbody>
</table>

<h4 id="output-27">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<p>&ndash;</p>
\
<p><api><code>POST /v1/money-transfer/transactions/{id}/confirm</code></api></p>

<p>Confirm a previously-created <a href="#transaction">transaction</a> to initiate processing.</p>

<h4 id="output-28">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<p>&ndash;</p>

<p><api><code>POST /v1/money-transfer/transactions/ext-{external_id}/confirm</code></api></p>

<p>Confirm a previously-created <a href="#transaction">transaction</a>, through an external ID, to initiate processing.</p>

<h4 id="output-29">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<p>&ndash;</p>

<p><api><code>GET /v1/money-transfer/transactions/{id}</code></api></p>

<p>Retrieve information for a given <a href="#transaction">transaction</a>.</p>

<h4 id="output-30">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<p>&ndash;</p>

<p><api><code>GET /v1/money-transfer/transactions/ext-{external_id}</code></api></p>

<p>Retrieve information for a given <a href="#transaction">transaction</a> from an external ID.</p>

<h4 id="output-31">Output</h4>

<p><a href="#transaction">Transaction</a> object.</p>

<!-- End Transaction -->

<!-- Transaction code -->

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<h3 class="n">Transfer</h3>
<span class="nf">POST</span> <span class="nn">api/v1/transactions/create/ext-1481184321405</span>
<span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">201</span> <span class="l">Created</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
    <span class="p">},</span>
    <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span>
    <span class="p">},</span>
    <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;Jane&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
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
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Sales Executive&#34;</span>
    <span class="p">},</span>
    <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
    <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
    <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
    <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
    <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span>
<span class="p">}</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
     <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">10000</span><span class="p">,</span>
     <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CREATED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CREATED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;creation_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-02T09:19:15&#34;</span><span class="p">,</span>
     <span class="nt">&#34;expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-03T09:07:44&#34;</span><span class="p">,</span>
     <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
     <span class="p">},</span>
     <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">10.69</span>
     <span class="p">},</span>
     <span class="nt">&#34;payer&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
        <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
        <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;msisdn&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;credit_party_information&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_verification&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">],</span>
            <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">}</span>
     <span class="p">},</span>
     <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;bank_account&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;card&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;beneficiary_relationship&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;source_of_funds&#34;</span><span class="p">:</span> <span class="kc">null</span>
     <span class="p">},</span>
     <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
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
     <span class="p">},</span>
     <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span><span class="p">,</span>
     <span class="nt">&#34;sent_amount&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.06891969534071</span><span class="p">,</span>
     <span class="nt">&#34;retail_rate&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
     <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">1.88</span>
     <span class="p">},</span>
     <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_1&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_3&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">POST</span> <span class="nn">/v1/money-transfer/transactions/1/confirm</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
     <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">20000</span><span class="p">,</span>
     <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CONFIRMED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
     <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CONFIRMED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;creation_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-02T09:19:15&#34;</span><span class="p">,</span>
     <span class="nt">&#34;expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-03T09:07:44&#34;</span><span class="p">,</span>
     <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
     <span class="p">},</span>
     <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">10.69</span>
     <span class="p">},</span>
     <span class="nt">&#34;payer&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
        <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
        <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;msisdn&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;credit_party_information&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_verification&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">],</span>
            <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">}</span>
     <span class="p">},</span>
     <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;bank_account&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;card&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;beneficiary_relationship&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;source_of_funds&#34;</span><span class="p">:</span> <span class="kc">null</span>
     <span class="p">},</span>
     <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
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
     <span class="p">},</span>
     <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span><span class="p">,</span>
     <span class="nt">&#34;sent_amount&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.06891969534071</span><span class="p">,</span>
     <span class="nt">&#34;retail_rate&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
     <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">1.88</span>
     <span class="p">},</span>
     <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_1&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_3&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">POST</span> <span class="nn">/v1/money-transfer/transactions/ext-1478078339357/confirm</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
     <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">20000</span><span class="p">,</span>
     <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CONFIRMED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
     <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;CONFIRMED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;creation_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-02T09:19:15&#34;</span><span class="p">,</span>
     <span class="nt">&#34;expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-03T09:07:44&#34;</span><span class="p">,</span>
     <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
     <span class="p">},</span>
     <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">10.69</span>
     <span class="p">},</span>
     <span class="nt">&#34;payer&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
        <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
        <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;msisdn&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;credit_party_information&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_verification&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">],</span>
            <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">}</span>
     <span class="p">},</span>
     <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;bank_account&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;card&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;beneficiary_relationship&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;source_of_funds&#34;</span><span class="p">:</span> <span class="kc">null</span>
     <span class="p">},</span>
     <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
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
     <span class="p">},</span>
     <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span><span class="p">,</span>
     <span class="nt">&#34;sent_amount&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.06891969534071</span><span class="p">,</span>
     <span class="nt">&#34;retail_rate&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
     <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">1.88</span>
     <span class="p">},</span>
     <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_1&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_3&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/transactions/1</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
     <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">50000</span><span class="p">,</span>
     <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;SUBMITTED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
     <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;SUBMITTED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;creation_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-02T09:19:15&#34;</span><span class="p">,</span>
     <span class="nt">&#34;expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-03T09:07:44&#34;</span><span class="p">,</span>
     <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
     <span class="p">},</span>
     <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">10.69</span>
     <span class="p">},</span>
     <span class="nt">&#34;payer&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
        <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
        <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;msisdn&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;credit_party_information&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_verification&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">],</span>
            <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">}</span>
     <span class="p">},</span>
     <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;bank_account&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;card&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;beneficiary_relationship&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;source_of_funds&#34;</span><span class="p">:</span> <span class="kc">null</span>
     <span class="p">},</span>
     <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
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
     <span class="p">},</span>
     <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span><span class="p">,</span>
     <span class="nt">&#34;sent_amount&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.06891969534071</span><span class="p">,</span>
     <span class="nt">&#34;retail_rate&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
     <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">1.88</span>
     <span class="p">},</span>
     <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_1&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_3&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/transactions/ext-1478078339357</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
     <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">50000</span><span class="p">,</span>
     <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;SUBMITTED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
     <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;SUBMITTED&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
     <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;creation_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-02T09:19:15&#34;</span><span class="p">,</span>
     <span class="nt">&#34;expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-11-03T09:07:44&#34;</span><span class="p">,</span>
     <span class="nt">&#34;credit_party_identifier&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;+263775892100&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_account_number&#34;</span><span class="p">:</span> <span class="s2">&#34;0123456789&#34;</span><span class="p">,</span>
        <span class="nt">&#34;swift_bic_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ABCDEFGH&#34;</span>
     <span class="p">},</span>
     <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">10.69</span>
     <span class="p">},</span>
     <span class="nt">&#34;payer&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
        <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
        <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;USD&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;ZWE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;msisdn&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_sender_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
            <span class="p">[</span>
                <span class="s2">&#34;lastname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;firstname&#34;</span>
            <span class="p">]</span>
        <span class="p">],</span>
        <span class="nt">&#34;credit_party_information&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">},</span>
        <span class="nt">&#34;credit_party_verification&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">],</span>
            <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
                <span class="p">[]</span>
            <span class="p">]</span>
        <span class="p">}</span>
     <span class="p">},</span>
     <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
        <span class="nt">&#34;lastname2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;middlename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;John&#34;</span><span class="p">,</span>
        <span class="nt">&#34;nativename&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;nationality_country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;date_of_birth&#34;</span><span class="p">:</span> <span class="s2">&#34;1970-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_of_birth_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;gender&#34;</span><span class="p">:</span> <span class="s2">&#34;MALE&#34;</span><span class="p">,</span>
        <span class="nt">&#34;address&#34;</span><span class="p">:</span> <span class="s2">&#34;42 Rue des fleurs&#34;</span><span class="p">,</span>
        <span class="nt">&#34;postal_code&#34;</span><span class="p">:</span> <span class="s2">&#34;75000&#34;</span><span class="p">,</span>
        <span class="nt">&#34;city&#34;</span><span class="p">:</span> <span class="s2">&#34;Paris&#34;</span><span class="p">,</span>
        <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="nt">&#34;msisdn&#34;</span><span class="p">:</span> <span class="s2">&#34;33712345678&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;john.doe@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_type&#34;</span><span class="p">:</span> <span class="s2">&#34;SOCIAL_SECURITY&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_country_iso_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;id_number&#34;</span><span class="p">:</span> <span class="s2">&#34;502-42-0158&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_delivery_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2016-01-01&#34;</span><span class="p">,</span>
        <span class="nt">&#34;id_expiration_date&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;occupation&#34;</span><span class="p">:</span> <span class="s2">&#34;Residential Advisor&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;bank_account&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;card&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;province_state&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;beneficiary_relationship&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
        <span class="nt">&#34;source_of_funds&#34;</span><span class="p">:</span> <span class="kc">null</span>
     <span class="p">},</span>
     <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
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
     <span class="p">},</span>
     <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;{URL_PLACEHOLDER}&#34;</span><span class="p">,</span>
     <span class="nt">&#34;sent_amount&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">10</span>
     <span class="p">},</span>
     <span class="nt">&#34;wholesale_fx_rate&#34;</span><span class="p">:</span> <span class="mf">1.06891969534071</span><span class="p">,</span>
     <span class="nt">&#34;retail_rate&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
     <span class="nt">&#34;retail_fee_currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
     <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="p">{</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mf">1.88</span>
     <span class="p">},</span>
     <span class="nt">&#34;purpose_of_remittance&#34;</span><span class="p">:</span> <span class="s2">&#34;FAMILY_SUPPORT&#34;</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_1&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_2&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
     <span class="nt">&#34;additional_information_3&#34;</span><span class="p">:</span> <span class="kc">null</span>
<span class="p">}</span></code></pre></div>

<!-- End Transaction code -->
