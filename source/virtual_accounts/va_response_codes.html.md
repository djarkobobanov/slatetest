## VA Response Codes
<p>Below is the list of response codes for API VA aggregator:</p>
<table><thead>
<tr>
<th>Response Code</th>
<th>State</th>
<th>Description</th>
</tr>
</thead><tbody>
<tr>
<td>000</td>
<td>Final</td>
<td>Response success without error</td>
</tr>
<tr>
<td>207</td>
<td>Final</td>
<td>Request is Rejected (Request IP Address is not Registered)</td>
</tr>
<tr>
<td>208</td>
<td>Final</td>
<td>Request is Rejected (API Key is not Valid)</td>
</tr>
<tr>
<td>211</td>
<td>Final</td>
<td>Request is Rejected (Bank code is not available for this service)</td>
</tr>
<tr>
<td>212</td>
<td>Final</td>
<td>Request is Rejected (Given amount are lesser than allowed value for static va)</td>
</tr>
<tr>
<td>214</td>
<td>Final</td>
<td>Request is Rejected (Failed to generate static va)</td>
</tr>
<tr>
<td>216</td>
<td>Final</td>
<td>Request is Rejected (VA Id is empty)</td>
</tr>
<tr>
<td>217</td>
<td>Final</td>
<td>Request is Rejected (VA Number is still active for this partner user id)</td>
</tr>
<tr>
<td>219</td>
<td>Final</td>
<td>Request is Rejected (Virtual account is not enabled for this bank)</td>
</tr>
<tr>
<td>226</td>
<td>Final</td>
<td>Request is rejected (Transaction expiry time exceeds VA expiry time)</td>
</tr>
<tr>
<td>245</td>
<td>Final</td>
<td>Request is rejected (Min expiry time is 60 minutes)</td>
</tr>
<tr>
<td>246</td>
<td>Final</td>
<td>Request is rejected (Failed update va)</td>
</tr>
<tr>
<td>999</td>
<td>Non-Final</td>
<td>Internal Server Error</td>
</tr>
</tbody></table>
