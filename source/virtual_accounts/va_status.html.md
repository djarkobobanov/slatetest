## VA Status
<h3 id="available-status-for-va-aggregator-va-aggregator-status" type="normal">Available Status for VA aggregator</h3>
<table><thead>
<tr>
<th>Status</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>WAITING_PAYMENT</td>
<td>This status means that VA is active and can receive a payment</td>
</tr>
<tr>
<td>PAYMENT_DETECTED</td>
<td>This status means that there are incoming payment to VA Number</td>
</tr>
<tr>
<td>EXPIRED</td>
<td>This status means that VA is expired. You cannot accept or make update to VA Number with this status.</td>
</tr>
<tr>
<td>STATIC_TRX_EXPIRED</td>
<td>This status means that Transaction is expired. If VA have a unlimited lifetime, you can create a new transaction using update va info.</td>
</tr>
<tr>
<td>COMPLETE</td>
<td>This status means that VA is closed/complete after get incoming payment. You cannot accept or make update to VA Number with this status. Only Static VA with attribute <code>is_single_use</code> true can have this status.</td>
</tr>
</tbody></table>
