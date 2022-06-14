## Create Virtual Accounts
<p><api><code>POST {URL}/va_numbers</code></api></p>

<div class="highlight"><pre class="highlight"><code>
  <span class="nf">POST</span> <span class="nn">{{URL}}/va_numbers</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
  <span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 
  <p class="n">Request</p>
  <span class="p">{</span>
    <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span><span class="s2">&#34;1234&#34;</span><span class="p">,</span>
    <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
    <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">100000</span><span class="p">,</span>
    <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
    <span class="nt">&#34;is_single_use&#34;</span> <span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
    <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
    <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
    <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;your va name&#34;</span><span class="p">,</span>
    <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
    <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX0001&#34;</span><span class="p">,</span>
    <span class="nt">&#34;trx_counter&#34;</span> <span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
    <span class="nt">&#34;callback_url&#34;</span> <span class="p">:</span> <span class="p"></span><span class="err">&#34;https://staging.api.disbursement.transfez.com/api/v1/callback/va/test_callback&#34;</span><span class="p"></span>
  <span class="p">}</span>

  <br>
  <p class="n">Response</p>
  <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">200</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">{</span>
      <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">40</span><span class="p">,</span>
      <span class="nt">&#34;va_status&#34;</span><span class="p">:</span> <span class="s2">&#34;WAITING_PAYMENT&#34;</span><span class="p">,</span>
      <span class="nt">&#34;va_number&#34;</span><span class="p">:</span> <span class="s2">&#34;103406000000004729&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span> <span class="s2">&#34;1234&#34;</span><span class="p">,</span>
      <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
      <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">100000</span><span class="p">,</span>
      <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
      <span class="nt">&#34;is_single_use&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
      <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
      <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
      <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;va name&#34;</span><span class="p">,</span>
      <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
      <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX0001&#34;</span><span class="p">,</span>
      <span class="nt">&#34;trx_counter&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
      <span class="nt">&#34;partner_id&#34;</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
      <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T11:44:46.295+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T11:44:46.295+07:00&#34;</span><span class="p">,</span>
      <span class="nt">&#34;counter_incoming_payment&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
      <span class="nt">&#34;va_id&#34;</span><span class="p">:</span> <span class="s2">&#34;5d46ba5b-9af3-4960-a3fe-5bce1da7cebb&#34;</span><span class="p">,</span>
      <span class="nt">&#34;balance_id&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
      <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">&#34;https://staging.api.disbursement.transfez.com/api/v1/callback/va/test_callback&#34;</span>
    <span class="p">}</span>
<span class="p">}</span><span class="w">
</span></code></pre></div>



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
<td><api><code>partner_user_id</code></api></td>
<td>String(255)</td>
<td>TRUE</td>
<td>-</td>
<td>Partner unique ID for specific user</td>
</tr>
<tr>
<td><api><code>bank_code</code></api></td>
<td>String(3)</td>
<td>TRUE</td>
<td>-</td>
<td>Bank code which the VA number will be generated</td>
</tr>
<tr>
<td><api><code>amount</code></api></td>
<td>BigDecimal</td>
<td>FALSE</td>
<td>0</td>
<td>Amount your user must paid to complete the transaction, if <code>is_open</code> is false, amount is required.</td>
</tr>
<tr>
<td><api><code>is_open</code></api></td>
<td>Boolean</td>
<td>FALSE</td>
<td>true</td>
<td>If set true means VA number can accept any amount, field <code>amount</code> can be optional, if set false means VA number only accept the specified amount in the field amount. When you set <code>is_open</code> to false, you must specify amount field.</td>
</tr>
<tr>
<td><api><code>is_single_use</code></api></td>
<td>Boolean</td>
<td>FALSE</td>
<td>false</td>
<td>True means that this VA should be <b>closed</b> once there is a successful payment that is being made to this VA.</td>
</tr>
<tr>
<td><api><code>expiration_time</code></api></td>
<td>Long</td>
<td>FALSE</td>
<td>-</td>
<td>Expiration time of the VA in <b>minutes</b>, e.g If VA want to be expired after 5 minutes, you just have to set expiration_time to 5. If empty VA will be expired in 24 hour</td>
</tr>
<tr>
<td><api><code>is_lifetime</code></api></td>
<td>Boolean</td>
<td>FALSE</td>
<td>FALSE</td>
<td>If it is set to FALSE (default) then VA will expire based on the expiration time. Otherwise, it will remain active with <b>no expiration time</b>.</td>
</tr>
<!-- <tr>
<td><api><code>username_display</code></api></td>
<td>String(255)</td>
<td>FALSE</td>
<td>username</td>
<td>Customizable VA display name that will be seen by user, If empty willl be using partner username</td>
</tr> -->
<!-- <tr>
<td><api><code>email</code></api></td>
<td>String(50)</td>
<td>FALSE</td>
<td>-</td>
<td>Email of user, using email standard format</td>
</tr> -->
<tr>
<td><api><code>partner_trx_id</code></api></td>
<td>String(255)</td>
<td>FALSE</td>
<td>-</td>
<td>Partner unique Transaction ID of a VA</td>
</tr>
<tr>
<td><api><code>trx_counter</code></api></td>
<td>Int</td>
<td>FALSE</td>
<td>-1/1</td>
<td>Transaction counter to limit number of transaction that can be receive by va number, if empty will be use default value -1 for multiple use va, and 1 for single use va. If counter reach zero, <b>va cannot be used for inquiry or accept payment.</b></td>
</tr>
<tr>
<td><api><code>callback_url</code></api></td>
<td>String(255)</td>
<td>TRUE</td>
<td>-</td>
<td>Once user successfully do the payment, our system will make a callback to your system. You can do this by registering your callback URL for each VA Number</td>
</tr>
</tbody></table>

<h3 id="response-parameters-create-va" type="normal">Response Parameters</h3>

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
<td><api><code>va_id</code></api></td>
<td>String(36)</td>
<td>Unique VA ID</td>
</tr>
<tr>
<td><api><code>partner_user_id</code></api></td>
<td>String(255)</td>
<td>Your unique ID for specific user</td>
</tr>
<tr>
<td><api><code>bank_code</code></api></td>
<td>String(3)</td>
<td>Bank code for VA, see <a href="#available-bank-for-va-aggregator-va-aggregator-bank-code">VA Bank Code</a></td>
</tr>
<tr>
<td><api><code>is_open</code></api></td>
<td>Boolean</td>
<td>True means VA number can accept any amount, False means VA number only accept the specified amount in the field amount</td>
</tr>
<tr>
<td><api><code>is_single_use</code></api></td>
<td>Boolean</td>
<td>True means that this VA should be closed/complete once there is a successful payment that is being made to this VA.</td>
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
<td>Customizable VA display name that will be seen by user, If empty willl be using partner username</td>
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
<tr>
<td><api><code>counter_incoming_payment</code></api></td>
<td>Integer</td>
<td>Count total incoming payment of VA</td>
</tr>
</tbody></table>
