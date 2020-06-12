<h1 id='callback'>Callback</h1>
<div class="highlight"><pre><code>
<span class="nf">POST</span> <span class="nn">{URL}/callback</span> <span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>

<span class="p">{</span>
    <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
    <span class="err">data</span> <span class="p">:</span> <span class="p">[</span>
    <span class="p">{</>
        <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{{ID}}</span><span class="p">,</span>
        <span class="nt">&#34;reference_id&#34;</span><span class="p">:</span> <span class="s2">&#34;TRX124&#34;</span><span class="p">,</span>
        <span class="nt">&#34;callback_url&#34;</span><span class="p">:</span> <span class="kc">https://sawtooth.rubyh.co/callback_transfez</span><span class="p">,</span>
        <span class="nt">&#34;payer_id&#34;</span><span class="p">:</span> <span class="mi">&#34;1&#34;</span><span class="p">,</span>
        <span class="nt">&#34;mode&#34;</span><span class="p">:</span> <span class="s2">&#34;DESTINATION&#34;</span><span class="p">,</span>
        <span class="nt">&#34;sender&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;Tiara Italyana&#34;</span><span class="p">,</span>
            <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Pribadi&#34;</span><span class="p">,</span>
            <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="p">},</span>
        <span class="nt">&#34;source&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="kc">&#34;null&#34;</span><span class="p">,</span>
            <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;EUR&#34;</span><span class="p">,</span>
            <span class="nt">&#34;country_iso_code&#34;</span><span class="p">:</span> <span class="s2">&#34;FRA&#34;</span><span class="p">,</span>
        <span class="p">}</span>
        <span class="nt">&#34;destination&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">&#34;1000000&#34;</span><span class="p">,</span>
            <span class="nt">&#34;currency&#34;</span><span class="p">:</span> <span class="s2">&#34;IDR&#34;</span>
        <span class="p">}</span>
        <span class="nt">&#34;beneficiary&#34;</span><span class="p">:</span> <span class="p">{</span>
            <span class="nt">&#34;firstname&#34;</span><span class="p">:</span> <span class="s2">&#34;Jane&#34;</span><span class="p">,</span>
            <span class="nt">&#34;lastname&#34;</span><span class="p">:</span> <span class="s2">&#34;Doe&#34;</span><span class="p">,</span>
            <span class="nt">&#34;bank&#34;</span><span class="p">:</span> <span class="s2">&#34;bni&#34;</span><span class="p">,</span>
            <span class="nt">&#34;account&#34;</span><span class="p">:</span> <span class="mi">&#34;1172993826&#34;</span>
        <span class="p">}</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T10:02:30.150Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T11:14:59.896Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;state&#34;</span><span class="p">:</span> <span class="s2">&#34;refunded&#34;</span><span class="p">,</span>
            <span class="nt">&#34;amount&#34;</span><span class="p">:</span> <span class="mi">&#34;1018000&#34;</span><span class="p">,</span>
            <span class="nt">&#34;paid_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T10:52:37.000Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;rate&#34;</span><span class="p">:</span> <span class="mi">&#34;18000.0&#34;</span><span class="p">,</span>
            <span class="nt">&#34;fee&#34;</span><span class="p">:</span> <span class="mi">&#34;18000.0&#34;</span><span class="p">,</span>
        <span class="p">}
<span class="p">}</span>
</code></pre></div>
<p>As the transfer order is being processed, changes in status will be notified in realtime if a callback URL was provided.</p>

<p>This endpoint must be implemented by the sending partner, which should expect an HTTP <code>POST</code> request containing a <a href="#transaction">transaction</a> object represented in JSON.</p>

<p>The same sets of credentials used to access the Money Transfer API will be used in authenticating to the callback endpoint, via <a href="#digest-auth">digest auth</a>.</p>

<p>Upon sucessful receipt of data, the callback endpoint should respond with an HTTP <code>2XX</code>. In the event that the Money Transfer platform did not receive this response, callback notifications will be retried several times, beyond which, the transaction status will have to be queried by the sending partner.</p>