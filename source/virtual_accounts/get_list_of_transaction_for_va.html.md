## Get List of transaction for VA

<div class="card">
  <a class="badge get">GET</a> /va_numbers/:va_id/va_transactions
</div>
<br>

|Path parameter|Description|
|----|----|
|`:va_id`|Index number of the virtual account|

<p>Get list of incoming transaction for specific va number in a <a href="#pagination">paginated</a> fashion.</p>

<div class="highlight"><pre class="highlight"><code>
  <span class="nf">GET</span> <span class="nn">{{URL}}/va_numbers/{{VA_ID}}/va_transactions</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
  <span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 
  <p class="n">Response</p>
  <span class="p">{</span>
    <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">200</span><span class="p">,</span>
    <span class="nt">&#34;page&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
    <span class="nt">&#34;per_page&#34;</span><span class="p">:</span> <span class="mi">10</span><span class="p">,</span>
    <span class="nt">&#34;total_page&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
    <span class="nt">&#34;va_data&#34;</span><span class="p">:</span> <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">41</span><span class="p">,</span>
      <span class="nt">&#34;va_status&#34;</span><span class="p">:</span> <span class="s2">&#34;PAYMENT_DETECTED&#34;</span><span class="p">,</span>
      <span class="nt">&#34;va_number&#34;</span><span class="p">:</span> <span class="s2">&#34;100536000000004747&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span> <span class="s2">&#34;partnerVA01&#34;</span><span class="p">,</span>
      <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
      <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="nt">&#34;is_single_use&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
      <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
      <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;va name&#34;</span><span class="p">,</span>
      <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRXVA01&#34;</span><span class="p">,</span>
      <span class="nt">&#34;trx_counter&#34;</span><span class="p">:</span> <span class="mi">-1</span><span class="p">,</span>
      <span class="nt">&#34;partner_id&#34;</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
      <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:28:26.891+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:52.535+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;counter_incoming_payment&#34;</span><span class="p">:</span> <span class="mi">3</span><span class="p">,</span>
      <span class="nt">&#34;va_id&#34;</span><span class="p">:</span> <span class="s2">&#34;fb6f3dee-91e5-4a02-9ec0-624a710dff9e&#34;</span><span class="p">,</span>
      <span class="nt">&#34;balance_id&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
      <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;https://staging.api.disbursement.transfez.com/api/v1/callback/va/test_callback&#34;</span><span class="p">,</span>
      <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank BRI&#34;</span>
    <span class="p">},</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">[</span>
      <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">49</span><span class="p">,</span>
        <span class="nt">&#34;va_number_id&#34;</span><span class="p">:</span> <span class="s2">&#34;41&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">22020</span><span class="p">,</span>
        <span class="nt">&#34;success&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nt">&#34;tx_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:52.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:33:26.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;3a8dc9ef-88be-44ec-9805-6edd64d8acaf&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_time&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-22T00:29:52.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_status&#34;</span><span class="p">:</span> <span class="s2">&#34;SUCCESS&#34;</span><span class="p">,</span>
        <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:52.270+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:52.270+07:00&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">48</span><span class="p">,</span>
        <span class="nt">&#34;va_number_id&#34;</span><span class="p">:</span> <span class="s2">&#34;41&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">22020</span><span class="p">,</span>
        <span class="nt">&#34;success&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nt">&#34;tx_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:51.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:33:26.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;ae49cbf0-f0fe-4fab-9fa3-49c578ca2ed8&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_time&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-22T00:29:51.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_status&#34;</span><span class="p">:</span> <span class="s2">&#34;SUCCESS&#34;</span><span class="p">,</span>
        <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:51.223+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:51.223+07:00&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">47</span><span class="p">,</span>
        <span class="nt">&#34;va_number_id&#34;</span><span class="p">:</span> <span class="s2">&#34;41&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">220000</span><span class="p">,</span>
        <span class="nt">&#34;success&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nt">&#34;tx_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:44.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_expiration_date&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:33:26.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;e0504351-b809-47b5-a381-4fbce300a7a3&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_time&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-22T00:29:44.000+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;settlement_status&#34;</span><span class="p">:</span> <span class="s2">&#34;SUCCESS&#34;</span><span class="p">,</span>
        <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:45.133+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T17:29:45.133+07:00&#34;</span>
      <span class="p">}</span>
    <span class="p">]</span>
  <span class="p">}</span>
</span></code></pre></div>
<h3 id="url-parameter-get-list-of-transaction-for-va" type="normal">URL Parameter</h3>
<table><thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Required</th>
<th>Default</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><api><code>VA_ID</code></api></td>
<td>String(36)</td>
<td>TRUE</td>
<td>-</td>
<td>Unique VA ID, you can get this once you success created VA</td>
</tr>
</tbody></table></table>

<h3 id="response-parameters-get-list-of-transaction-for-va" type="normal">Response Parameters</h3>
<table><thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><api><code>status</code></api></td>
<td>Object</td>
<td>Status of response</code></td>
</tr>
<tr>
<td><api><code>va_data</code></api></td>
<td>Array of Object</td>
<td>List of VA <a href="#response-parameters-get-va-info">Objects</a>.</td>
<tr>
<td><api><code>va_number</code></api></td>
<td>String(20)</td>
<td>Generated VA number</td>
</tr>
<tr>
<td><api><code>amount</code></api></td>
<td>BigDecimal</td>
<td>Amount of VA transaction</td>
</tr>
<tr>
<td><api><code>partner_user_id</code></api></td>
<td>String(255)</td>
<td>Your unique ID for specific user</td>
</tr>
<tr>
<td><api><code>success</code></api></td>
<td>boolean</td>
<td>The status of the payment and it is always set to <b>SUCCESS</b></td>
</tr>
<tr>
<td><api><code>tx_date</code></api></td>
<td>Timestamp</td>
<td>Incoming payment transaction date, format <code>dd/MM/yyyy'T'HH:mm:ss.SSSZZZZ</code></td>
</tr>
<tr>
<td><api><code>username_display</code></api></td>
<td>String(255)</td>
<td>Customizable VA display name that will be seen by user, If empty willl be using partner username</td>
</tr>
<tr>
<td><api><code>trx_expiration_date</code></api></td>
<td>Long</td>
<td>Transaction expiration date, format <code>dd/MM/yyyy'T'HH:mm:ss.SSSZZZZ</code></td>
</tr>
<tr>
<td><api><code>trx_id</code></api></td>
<td>String (255)</td>
<td>Unique ID of incoming payment</td>
</tr>
<tr>
<td><api><code>settlement_time</code></api></td>
<td>Timestamp</td>
<td>The timestamp (in UTC+7) indicating when the fund will be settled to partner’s account statement, format <code>dd/MM/yyyy'T'HH:mm:ss.SSSZZZZ</code></td>
</tr>
<tr>
<td><api><code>settlement_status</code></api></td>
<td>String(255)</td>
<td>The status of the settlement</td>
</tr>
</tbody></table>
