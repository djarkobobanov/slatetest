## Get VA Info

<div class="card">
  <a class="badge get">GET</a> /va_numbers/:va_id
</div>
<br>

|Path parameter|Description|
|----|----|
|`:va_id`|Index number of the virtual account|

<p>Get VA info using Unique VA id.</p>

<div class="highlight"><pre class="highlight"><code>
  <span class="nf">GET</span> <span class="nn">{{URL}}/va_numbers/{{VA_ID}}</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
  <span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

  <p class="n">Response</p>
  <span class="p">{</span>
    <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">200</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
      <span class="nt">&#34;va_status&#34;</span><span class="p">:</span> <span class="s2">&#34;WAITING_PAYMENT&#34;</span><span class="p">,</span>
      <span class="nt">&#34;va_number&#34;</span><span class="p">:</span> <span class="s2">&#34;100536000000004513&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span> <span class="s2">&#34;alcantaros&#34;</span><span class="p">,</span>
      <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
      <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="nt">&#34;is_single_use&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
      <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
      <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
      <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;va name&#34;</span><span class="p">,</span>
      <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX0001&#34;</span><span class="p">,</span>
      <span class="nt">&#34;trx_counter&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
      <span class="nt">&#34;partner_id&#34;</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
      <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-14T18:20:59.925+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-14T18:20:59.925+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;counter_incoming_payment&#34;</span><span class="p">:</span> <span class="kc">0</span><span class="p">,</span>
      <span class="nt">&#34;va_id&#34;</span><span class="p">:</span> <span class="s2">&#34;071b288c-01c8-495b-8669-4fbe6ea0b036&#34;</span><span class="p">,</span>
      <span class="nt">&#34;balance_id&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
      <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="kc">&#34;https://staging.api.disbursement.transfez.com/api/v1/callback/va/test_callback&#34;</span>
    <span class="p">}</span>
  <span class="p">}</span>
</span></code></pre></div>
<h3 id="url-parameters-get-va-info" type="normal">URL Parameters</h3>
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
<td>String(255)</td>
<td>TRUE</td>
<td>-</td>
<td>Unique VA id, you can get this once you success created VA</td>
</tr>
</tbody></table>
<h3 id="response-parameters-get-va-info" type="normal">Response Parameters</h3>
<table><thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><api><code>va_id</code></api></td>
<td>String</td>
<td>Unique VA id</td>
</tr>
<tr>
<td><api><code>status</code></api></td>
<td>Object</td>
<td>Status of response</code></td>
</tr>
<tr>
<td><api><code>amount</code></api></td>
<td>BigDecimal</td>
<td>Amount of VA transaction</td>
</tr>
<tr>
<td><api><code>va_number</code></api></td>
<td>String(20)</td>
<td>Generated VA number</td>
</tr>
<tr>
<td><api><code>bank_code</code></api></td>
<td>String(3)</td>
<td>Bank code for VA</td>
</tr>
<!-- <tr>
<td><api><code>bank_name</code></api></td>
<td>String(10)</td>
<td>Bank name of the VA</td>
</tr> -->
<tr>
<td><api><code>is_open</code></api></td>
<td>Boolean</td>
<td>True means VA number can accept any amount, False means VA number only accept the specified amount in the field amount</td>
</tr>
<tr>
<td><api><code>is_single_use</code></api></td>
<td>Boolean</td>
<td>True means that this VA should be closed once there is a successful payment that is being made to this VA.</td>
</tr>
<tr>
<td><api><code>expiration_time</code></api></td>
<td>Long</td>
<td>Expiration time of VA on Unix timestamp in milliseconds, -1 means no expiration time.</td>
</tr>
<tr>
<td><api><code>va_status</code></api></td>
<td>String(16)</td>
<td>Status of VA, see <a href="#available-status-for-va-aggregator-va-aggregator-status">VA Status</a></td>
</tr>
<tr>
<td><api><code>username_display</code></api></td>
<td>String(255)</td>
<td>Customizable VA display name that will be seen by user, If empty will be using partner username</td>
</tr>
<tr>
<td><api><code>partner_user_id</code></api></td>
<td>String(255)</td>
<td>Partner unique ID for specific user</td>
</tr>
<!-- <tr>
<td><api><code>created</code></api></td>
<td>Long</td>
<td>Unix timestamp in milliseconds when VA created</td>
</tr> -->
<tr>
<td><api><code>counter_incoming_payment</code></api></td>
<td>Integer</td>
<td>Count total incoming payment of VA</td>
</tr>
<tr>
<td><api><code>partner_trx_id</code></api></td>
<td>String(255)</td>
<td>Partner unique Transaction ID of a VA</td>
</tr>
<tr>
<td><api><code>trx_counter</code></api></td>
<td>Int</td>
<td>Transaction counter to limit number of transaction that can be receive by va number, if empty will be use default value -1 for multiple use va, and 1 for single use va. If counter reach zero, <b>va cannot be used for inquiry or accept payment.</b></td>
</tr>
</tbody></table>
