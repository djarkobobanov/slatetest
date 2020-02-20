---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

search: true
---

<!-- Start Introduction -->
<h1 id="introduction">Introduction</h1>

<blockquote>
<p><img src="images/money_transfer.png" alt="money transfer" /></p>
</blockquote>

<p>Welcome to the Money Transfer API reference.</p>

<p>This API serves as the primary gateway to facilitate money transfers through Thunes&rsquo; platform.</p>

<p>The Money Transfer API is organized according to <a href="https://en.wikipedia.org/wiki/Representational_state_transfer">REST</a> principles and provides the following functionalities:</p>

<ul>
<li>Process and retrieve transaction details</li>
<li>Account management services</li>
<li>Discovery services</li>
</ul>

<h2 id="environments">Environments</h2>

<p>This API is available in 2 environments: production and pre-production, reachable via IPSec VPN or HTTPS.</p>

<p>Specific details relating to the endpoints will be provided upon account creation.</p>

<!-- End Introduction -->

<h1 id="transaction-states">Transaction states</h1>

<blockquote>
<p><img src="images/transaction_states.png" alt="transaction states" /></p>
</blockquote>

<p>During the course of a transfer, a transaction will undergo various status changes as illustrated.</p>

<p>Conditions marked as &ldquo;Upon request to customer care team&rdquo; pertains to reversal and/or cancellation, which must be requested through and performed by Thunesâ€™ customer care team.</p>

<p>As changes in transaction status occur, updates will be sent in real-time when a callback URL is provided. In conjunction, transaction status can be queried through one of two means: via the returned <code>id</code> or a provided <code>external_id</code>.</p>

<p>The latter serves as a unique reference in the perspective of the sending partner and functions to retrieve transaction details when exceptions occur, such as when the supposed response was not received, as an example.</p>

<p>The numerical values within each of the illustrated states correspond to the <a href="#transaction-status">transaction status</a>, while the labels correspond to that of the <a href="#transaction-status-class">transaction status class message</a>.</p>

<h1 id="example-flow">Example Flow</h1>

<blockquote>
<p><img src="images/transaction_flow.png" alt="transaction flow" /></p>
</blockquote>

<p>As soon as a transaction is confirmed, the transfer order will be sent to the receiving partner for immediate processing.</p>

<p>During this time, the sending partner will receive a <code>CONFIRMED</code> status for the transaction.</p>

<h1 id="callback">Callback</h1>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">POST</span> <span class="nn">/callback</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">Date</span><span class="o">:</span> <span class="l">Wed, 02 Nov 2016 09:17:54 GMT</span>
<span class="n">Content-Type</span><span class="o">:</span> <span class="l">application/json</span>
<span class="n">X-TransferTo-Apikey</span><span class="o">:</span> <span class="l">00000000-0000-0000-0000-000000000000</span>
<span class="n">X-TransferTo-Nonce</span><span class="o">:</span> <span class="l">1478078334</span>
<span class="n">X-TransferTo-Hmac</span><span class="o">:</span> <span class="l">g41AgixMSFMQj0TZgyXIK6+odCVgy76fxfGpAtWwhE8=</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
   <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
   <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">70000</span><span class="p">,</span>
   <span class="nt">&#34;status_message&#34;</span><span class="p">:</span> <span class="s2">&#34;COMPLETED&#34;</span><span class="p">,</span>
   <span class="nt">&#34;status_class&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
   <span class="nt">&#34;status_class_message&#34;</span><span class="p">:</span> <span class="s2">&#34;COMPLETED&#34;</span><span class="p">,</span>
   <span class="nt">&#34;external_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1478078339357&#34;</span><span class="p">,</span>
   <span class="nt">&#34;external_code&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
   <span class="nt">&#34;payer_transaction_reference&#34;</span><span class="p">:</span> <span class="s2">&#34;SP-000-123&#34;</span><span class="p">,</span>
   <span class="nt">&#34;payer_transaction_code&#34;</span><span class="p">:</span> <span class="s2">&#34;SP-ABC-DEF&#34;</span><span class="p">,</span>
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
      <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
         <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
         <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;MobileWallet&#34;</span>
      <span class="p">},</span>
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
<p>As the transfer order is being processed, changes in status will be notified in realtime if a callback URL was provided.</p>

<p>This endpoint must be implemented by the sending partner, which should expect an HTTP <code>POST</code> request containing a <a href="#transaction">transaction</a> object represented in JSON.</p>

<p>The same sets of credentials used to access the Money Transfer API will be used in authenticating to the callback endpoint, via <a href="#digest-auth">digest auth</a>.</p>

<p>Upon sucessful receipt of data, the callback endpoint should respond with an HTTP <code>2XX</code>. In the event that the Money Transfer platform did not receive this response, callback notifications will be retried several times, beyond which, the transaction status will have to be queried by the sending partner.</p>

<br>

<h1 id="authentication">Authentication</h1>

<p>Access to all endpoints of the API requires authentication, through one of the following means:</p>

<ol>
<li><a href="https://en.wikipedia.org/wiki/Basic_access_authentication">HTTP Basic Auth</a></li>
<li><a href="https://en.wikipedia.org/wiki/Digest_access_authentication">Digest Auth</a> (<a href="https://en.wikipedia.org/wiki/Hash-based_message_authentication_code">HMAC</a>)</li>
</ol>

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

> To authorize, use this code:

<h1 id="errors">Errors</h1>

<h2 id="http-response">HTTP Response</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span> <span class="m">401</span> <span class="ne">Unauthorized</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;errors&#34;</span><span class="p">:</span> <span class="p">[</span>
        <span class="p">{</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;1000401&#34;</span><span class="p">,</span>
            <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">&#34;Unauthorized&#34;</span>
        <span class="p">}</span>
    <span class="p">]</span>
<span class="p">}</span></code></pre></div>
<p>Thunes uses standard HTTP response codes to indicate whether an API request is successful or not.</p>

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
<td>Server Error:<br/>Error occurred on Thunes</td>
</tr>
</tbody>
</table>

<p>Details will always be contained within the HTTP body.</p>

<h2 id="api-error-codes">API Error Codes</h2>

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
</table>

<h1 id="pagination">Pagination</h1>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/{resource}?page=1&amp;per_page=50</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span></code></pre></div>
<p>API resources supporting bulk fetches via &ldquo;list&rdquo; API methods will be returned in a paginated fashion.</p>
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

<h1 id="connectivity">Connectivity</h1>

<h2 id="ping">Ping</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/ping</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
   <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="s2">&#34;up&#34;</span>
<span class="p">}</span></code></pre></div>
<p><api><code>GET /ping</code></api></p>

<p>Query API status.</p>

<h4 id="output">Output</h4>

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
<td><code>status</code></td>
<td>String</td>
<td>API status</td>
</tr>
</tbody>
</table>

<p>Expected value of <code>status</code> should be &ldquo;up&rdquo;.</p>

<h1 id="discovery">Discovery</h1>

<h2 id="services">Services</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/services</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
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
<p><api><code>GET /v1/money-transfer/services</code></api></p>

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
<td><code>country_iso_code</code></td>
<td>No</td>
<td>String</td>
<td>Country code in <a href="https://en.wikipedia.org/wiki/ISO_3166-1_alpha-3">ISO 3166-1 alpha-3</a> format</td>
</tr>
</tbody>
</table>

<h4 id="output-1">Output</h4>

<p>Array of <a href="#service">service</a> objects in a <a href="#pagination">paginated</a> fashion.</p>

<h2 id="payers">Payers</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/payers</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
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
      <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;msisdn&#34;</span>
         <span class="p">]</span>
      <span class="p">],</span>
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
   <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#3#34;CashPickup Payer&#34;</span><span class="p">,</span>
      <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
      <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
      <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;PHP&#34;</span><span class="p">,</span>
      <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;PHL&#34;</span><span class="p">,</span>
      <span class="nt">&#34;minimum_transaction_amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;maximum_transaction_amount&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
      <span class="nt">&#34;service&#34;</span><span class="p">:</span> <span class="p">{</span>
         <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;CashPickup&#34;</span><span class="p">,</span>
         <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">3</span>
      <span class="p">},</span>
      <span class="nt">&#34;credit_party_identifiers_accepted&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
            <span class="s2">&#34;msisdn&#34;</span>
         <span class="p">]</span>
      <span class="p">],</span>
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
   <span class="p">}</span>
<span class="p">]</span></code></pre></div>
<p><api><code>GET /v1/money-transfer/payers</code></api></p>

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
</tbody>
</table>

<h4 id="output-2">Output</h4>

<p>Array of <a href="#payer">payer</a> objects in a <a href="#pagination">paginated</a> fashion.</p>

<p>&ndash;</p>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/payers/3</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">{</span>
    <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
    <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sample Payer&#34;</span><span class="p">,</span>
    <span class="nt">&#34;precision&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
    <span class="nt">&#34;increment&#34;</span><span class="p">:</span> <span class="mf">0.01</span><span class="p">,</span>
    <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;IDR&#34;</span><span class="p">,</span>
    <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;IDN&#34;</span><span class="p">,</span>
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
                <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;date_of_birth&#34;</span><span class="p">,</span>
                <span class="s2">&#34;lastname&#34;</span>
         <span class="p">]</span>
    <span class="p">],</span>
    <span class="nt">&#34;required_beneficiary_fields&#34;</span><span class="p">:</span> <span class="p">[</span>
         <span class="p">[</span>
                <span class="s2">&#34;firstname&#34;</span><span class="p">,</span>
                <span class="s2">&#34;lastname&#34;</span>
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
<span class="p">}</span></code></pre></div>
<p><api><code>GET /v1/money-transfer/payers/{id}</code></api></p>

<p>Retrieve information for a given <a href="#payer">payer</a>.</p>

<h4 id="output-3">Output</h4>

<p><a href="#payer">Payer</a> object.</p>

<h2 id="payer-rates">Payer Rates</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/payers/362/rates</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
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
<p><api><code>GET /v1/money-transfer/payers/{id}/rates</code></api></p>

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
<td><code>rates</code></td>
<td>Object</td>
<td><a href="#rates">Rates</a> information</td>
</tr>
</tbody>
</table>

<h2 id="countries">Countries</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/countries</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
    <span class="p">{</span>
        <span class="nt">&#34;iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;KEN&#34;</span><span class="p">,</span>
        <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Kenya&#34;</span>
    <span class="p">}</span>
<span class="p">]</span></code></pre></div>
<p><api><code>GET /v1/money-transfer/countries</code></api></p>

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
</tbody>
</table>

<h4 id="output-5">Output</h4>

<p>Array of <a href="#country">country</a> objects in a paginated fashion.</p>

<h1 id="account">Account</h1>

<h2 id="balances">Balances</h2>
<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http"><span class="nf">GET</span> <span class="nn">/v1/money-transfer/balances</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="n">X-Total</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Total-Pages</span><span class="o">:</span> <span class="l">1</span>
<span class="n">X-Per-Page</span><span class="o">:</span> <span class="l">50</span>
<span class="n">X-Page</span><span class="o">:</span> <span class="l">1</span>
<span class="err">200</span> <span class="l">OK</span></code></pre></div><div class="highlight"><pre class="chroma"><code class="language-json" data-lang="json"><span class="p">[</span>
    <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
        <span class="nt">&#34;balance&#34;</span><span class="p">:</span> <span class="mi">10000000</span><span class="p">,</span>
        <span class="nt">&#34;available_balance&#34;</span><span class="p">:</span> <span class="mi">10000000</span><span class="p">,</span>
        <span class="nt">&#34;credit_facility&#34;</span><span class="p">:</span> <span class="mi">0</span>
    <span class="p">}</span>
<span class="p">]</span></code></pre></div>
<p><api><code>GET /v1/money-transfer/balances</code></api></p>

<p>Retrieve information for all account balances per currency.</p>

<h4 id="input-13">Input</h4>

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

<h4 id="output-20">Output</h4>

<p>Array of <a href="#balance">balance</a> objects.</p>
