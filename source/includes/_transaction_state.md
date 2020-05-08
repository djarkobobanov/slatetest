<h1 id="transaction-states">Transaction states</h1>

<blockquote>
<p><img src="images/transaction_states.png" alt="transaction states" /></p>
</blockquote>

<p>During the course of a transfer, a transaction will undergo various status changes as illustrated.</p>

<p>Conditions marked as &ldquo;Upon request to customer care team&rdquo; pertains to reversal and/or cancellation, which must be requested through and performed by customer care team.</p>

<p>As changes in transaction status occur, updates will be sent in real-time when a callback URL is provided. In conjunction, transaction status can be queried through one of two means: via the returned <code>id</code> or a provided <code>external_id</code>.</p>

<p>The latter serves as a unique reference in the perspective of the sending partner and functions to retrieve transaction details when exceptions occur, such as when the supposed response was not received, as an example.</p>

<p>The numerical values within each of the illustrated states correspond to the <a href="#transaction-status">transaction status</a>, while the labels correspond to that of the <a href="#transaction-status-class">transaction status class message</a>.</p>
