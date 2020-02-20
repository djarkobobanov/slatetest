# Callback

<p>As the transfer order is being processed, changes in status will be notified in realtime if a callback URL was provided.</p>

<p>This endpoint must be implemented by the sending partner, which should expect an HTTP <code>POST</code> request containing a <a href="#transaction">transaction</a> object represented in JSON.</p>

<p>The same sets of credentials used to access the Money Transfer API will be used in authenticating to the callback endpoint, via <a href="#digest-auth">digest auth</a>.</p>

<p>Upon sucessful receipt of data, the callback endpoint should respond with an HTTP <code>2XX</code>. In the event that the Money Transfer platform did not receive this response, callback notifications will be retried several times, beyond which, the transaction status will have to be queried by the sending partner.</p>

<div class="highlight">
<pre class="chroma">
<code class="language-http" data-lang="http">
<h3 class="n">Callback</h3>
<span class="nf">POST</span> <span class="nn">/callback</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
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
