## Get List of created VA
<p><api><code>GET {{URL}}/va_numbers</code></api></p>
<p>Get list of created VA objects in a <a href="#pagination">paginated</a> fashion.</p>
<div class="highlight"><pre class="highlight"><code>
  <span class="nf">GET</span> <span class="nn">{{URL}}/va_numbers</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
  <span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

  <br>
  <p class="n">Response</p>
  <span class="p">{</span>
    <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">200</span><span class="p">,</span>
    <span class="nt">&#34;page&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
    <span class="nt">&#34;per_page&#34;</span><span class="p">:</span> <span class="mi">2</span><span class="p">,</span>
    <span class="nt">&#34;total_page&#34;</span><span class="p">:</span> <span class="mi">20</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">[</span>
      <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">40</span><span class="p">,</span>
        <span class="nt">&#34;va_status&#34;</span><span class="p">:</span> <span class="s2">&#34;WAITING_PAYMENT&#34;</span><span class="p">,</span>
        <span class="nt">&#34;va_number&#34;</span><span class="p">:</span> <span class="s2">&#34;103406000000004729&#34;</span><span class="p">,</span>
        <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span> <span class="s2">&#34;boby999&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">100000</span><span class="p">,</span>
        <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nt">&#34;is_single_use&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
        <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;va name&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
        <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX0001&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_counter&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;partner_id&#34;</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
        <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T11:44:46.295+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-21T11:44:46.295+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;counter_incoming_payment&#34;</span><span class="p">:</span> <span class="kc">1</span><span class="p">,</span>
        <span class="nt">&#34;va_id&#34;</span><span class="p">:</span> <span class="s2">&#34;5d46ba5b-9af3-4960-a3fe-5bce1da7cebb&#34;</span><span class="p">,</span>
        <span class="nt">&#34;balance_id&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
        <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">{{CALLBACK_URL}}</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">39</span><span class="p">,</span>
        <span class="nt">&#34;va_status&#34;</span><span class="p">:</span> <span class="s2">&#34;WAITING_PAYMENT&#34;</span><span class="p">,</span>
        <span class="nt">&#34;va_number&#34;</span><span class="p">:</span> <span class="s2">&#34;103406000000004723&#34;</span><span class="p">,</span>
        <span class="nt">&#34;partner_user_id&#34;</span><span class="p">:</span> <span class="s2">&#34;boby900&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
        <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">100000</span><span class="p">,</span>
        <span class="nt">&#34;is_open&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nt">&#34;is_single_use&#34;</span><span class="p">:</span> <span class="kc">true</span><span class="p">,</span>
        <span class="nt">&#34;expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
        <span class="nt">&#34;is_lifetime&#34;</span><span class="p">:</span> <span class="kc">false</span><span class="p">,</span>
        <span class="nt">&#34;username_display&#34;</span><span class="p">:</span> <span class="s2">&#34;va name&#34;</span><span class="p">,</span>
        <span class="nt">&#34;email&#34;</span><span class="p">:</span> <span class="s2">&#34;email@mail.com&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_expiration_time&#34;</span><span class="p">:</span> <span class="mi">5</span><span class="p">,</span>
        <span class="nt">&#34;partner_trx_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX0001&#34;</span><span class="p">,</span>
        <span class="nt">&#34;trx_counter&#34;</span><span class="p">:</span> <span class="mi">1</span><span class="p">,</span>
        <span class="nt">&#34;partner_id&#34;</span><span class="p">:</span> <span class="mi">6</span><span class="p">,</span>
        <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-20T22:03:44.397+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="s2">&#34;2021-09-20T22:03:49.719+07:00&#34;</span><span class="p">,</span>
        <span class="nt">&#34;counter_incoming_payment&#34;</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span>
        <span class="nt">&#34;va_id&#34;</span><span class="p">:</span> <span class="s2">&#34;d33e726f-44f6-41d4-9946-2702e78ee7cf&#34;</span><span class="p">,</span>
        <span class="nt">&#34;balance_id&#34;</span><span class="p">:</span> <span class="mi">7</span><span class="p">,</span>
        <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="s2">{{CALLBACK_URL}}</span>
      <span class="p">}</span>
    <span class="p">]</span>
  <span class="p">}</span>
</span></code></pre></div>

<h3 id="response-parameters-get-list-of-created-va" type="normal">Response Parameters</h3>
<table><thead>
<tr>
<th>Parameter</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td><api><code>page</code></api></td>
<td>Integer</td>
<td>current page</td>
</tr>
<tr>
<td><api><code>per_page</code></api></td>
<td>Integer</td>
<td>amount of data per page</td>
</tr>
<tr>
<td><api><code>total_page</code></api></td>
<td>Integer</td>
<td>total page</td>
</tr>
<tr>
<td><api><code>data</code></api></td>
<td>Array of object</td>
<td>List of Object <code>{id: &lt;va_id&gt;, amount: &lt;amount&gt;, va_number: &lt;va_number&gt;, bank_code: &lt;bank_code&gt;, bank_name: &lt;bank_name&gt;, is_open: &lt;is_open&gt;, is_single_user: &lt;is_single_user&gt;, expiration_time: &lt;expiration_time&gt;, va_status: &lt;va_status&gt;, username_display: &lt;username_display&gt;, amount_detected: &lt;amount_detected&gt;, partner_user_id: &lt;partner_user_id&gt;, created: &lt;created&gt;, counter_incoming_payment: &lt;counter_incoming_payment&gt;, trx_counter: &lt;trx_counter&gt;}</code></td>
</tr>
<tr>
<td><api><code>status</code></api></td>
<td>Object</td>
<td>Status of response</code></td>
</tr>
</tbody></table>
