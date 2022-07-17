## VA Bank Codes

<div class="card">
  <a class="badge get">GET</a> /va_numbers/available_banks
</div>
<br>

<p>Get list of VA Bank Codes.</p>
<div class="highlight"><pre class="highlight"><code>
  <span class="nf">GET</span> <span class="nn">{{URL}}/va_numbers/available_banks</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
  <span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

  <p class="n">Response</p>
  <span class="p">{</span>
    <span class="nt">&#34;status&#34;</span><span class="p">:</span> <span class="mi">200</span><span class="p">,</span>
    <span class="nt">&#34;data&#34;</span><span class="p">:</span> <span class="p">[</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;002&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank BRI&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;013&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank Permata&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;022&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank CIMB Niaga&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;008&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank Mandiri&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;009&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank BNI&#34;</span>
      <span class="p">},</span>
      <span class="p">{</span>
        <span class="nt">&#34;bank_code&#34;</span><span class="p">:</span> <span class="s2">&#34;213&#34;</span><span class="p">,</span>
        <span class="nt">&#34;bank_name&#34;</span><span class="p">:</span> <span class="s2">&#34;Bank BTPN&#34;</span>
      <span class="p">}</span>
    <span class="p">]</span>
  <span class="p">}</span>
</span></code></pre></div>
<h3 id="available-bank-for-va-aggregator-va-aggregator-bank-code" type="normal">Available Bank for VA aggregator</h3>
<table><thead>
<tr>
<th>Bank Code</th>
<th>Bank Name</th>
</tr>
</thead><tbody>
<tr>
<td>002</td>
<td>Bank BRI</td>
</tr>
<tr>
<td>013</td>
<td>Bank Permata</td>
</tr>
<tr>
<td>022</td>
<td>Bank CIMB Niaga</td>
</tr>
<tr>
<td>008</td>
<td>Bank Mandiri</td>
</tr>
<tr>
<td>009</td>
<td>Bank BNI</td>
</tr>
<tr>
<td>213</td>
<td>Bank BTPN</td>
</tr>
</tbody></table>
