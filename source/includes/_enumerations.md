<h1 id="enumerations">Enumerations</h1>

<p>A number of resource fields will only accept a list of known values, as outlined in this section.</p>

<h2 id="quotation-mode">Quotation Mode</h2>

<table>
<thead>
<tr>
<th>Mode</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>SOURCE_AMOUNT</code></td>
<td><a href="#quotation">Quotation</a> created by specifying desired <a href="#source">source</a></td>
</tr>

<tr>
<td><code>DESTINATION_AMOUNT</code></td>
<td><a href="#quotation">Quotation</a> created by specifying desired <a href="#destination">destination</a></td>
</tr>
</tbody>
</table>

<h2 id="gender">Gender</h2>

<table>
<thead>
<tr>
<th>Gender</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>MALE</code></td>
<td>Male</td>
</tr>

<tr>
<td><code>FEMALE</code></td>
<td>Female</td>
</tr>
</tbody>
</table>

<h2 id="transaction-status-class">Transaction Status Class</h2>

<table>
<thead>
<tr>
<th>Status Class</th>
<th>Message</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>1</code></td>
<td>CREATED</td>
</tr>

<tr>
<td><code>2</code></td>
<td>CONFIRMED</td>
</tr>

<tr>
<td><code>3</code></td>
<td>REJECTED</td>
</tr>

<tr>
<td><code>4</code></td>
<td>CANCELLED</td>
</tr>

<tr>
<td><code>5</code></td>
<td>SUBMITTED</td>
</tr>

<tr>
<td><code>6</code></td>
<td>AVAILABLE</td>
</tr>

<tr>
<td><code>7</code></td>
<td>COMPLETED</td>
</tr>

<tr>
<td><code>8</code></td>
<td>REVERSED</td>
</tr>

<tr>
<td><code>9</code></td>
<td>DECLINED</td>
</tr>
</tbody>
</table>

<h2 id="transaction-status">Transaction Status</h2>

<table>
<thead>
<tr>
<th>Status</th>
<th>Message</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>10000</code></td>
<td>CREATED</td>
</tr>

<tr>
<td><code>20000</code></td>
<td>CONFIRMED</td>
</tr>

<tr>
<td><code>20110</code></td>
<td>CONFIRMED-UNDER-REVIEW-SLS</td>
</tr>

<tr>
<td><code>20150</code></td>
<td>CONFIRMED-WAITING-FOR-PICKUP</td>
</tr>

<tr>
<td><code>30000</code></td>
<td>REJECTED</td>
</tr>

<tr>
<td><code>30110</code></td>
<td>REJECTED-SLS-SENDER</td>
</tr>

<tr>
<td><code>30120</code></td>
<td>REJECTED-SLS-BENEFICIARY</td>
</tr>

<tr>
<td><code>30200</code></td>
<td>REJECTED-INVALID-BENEFICIARY</td>
</tr>

<tr>
<td><code>30201</code></td>
<td>REJECTED-BARRED-BENEFICIARY</td>
</tr>

<tr>
<td><code>30202</code></td>
<td>REJECTED-BARRED-SENDER</td>
</tr>

<tr>
<td><code>30210</code></td>
<td>REJECTED-INVALID-BENEFICIARY-DETAILS</td>
</tr>

<tr>
<td><code>30305</code></td>
<td>REJECTED-LIMITATIONS-ON-TRANSACTION-VALUE</td>
</tr>

<tr>
<td><code>30310</code></td>
<td>REJECTED-LIMITATIONS-ON-SENDER-VALUE</td>
</tr>

<tr>
<td><code>30320</code></td>
<td>REJECTED-LIMITATIONS-ON-BENEFICIARY-VALUE</td>
</tr>

<tr>
<td><code>30330</code></td>
<td>REJECTED-LIMITATIONS-ON-ACCOUNT-VALUE</td>
</tr>

<tr>
<td><code>30350</code></td>
<td>REJECTED-LIMITATIONS-ON-SENDER-QUANTITY</td>
</tr>

<tr>
<td><code>30360</code></td>
<td>REJECTED-LIMITATIONS-ON-BENEFICIARY-QUANTITY</td>
</tr>

<tr>
<td><code>30370</code></td>
<td>REJECTED-LIMITATIONS-ON-ACCOUNT-QUANTITY</td>
</tr>

<tr>
<td><code>30400</code></td>
<td>REJECTED-PAYER-CURRENTLY-UNAVAILABLE</td>
</tr>

<tr>
<td><code>30500</code></td>
<td>REJECTED-INSUFFICIENT-BALANCE</td>
</tr>

<tr>
<td><code>40000</code></td>
<td>CANCELLED</td>
</tr>

<tr>
<td><code>50000</code></td>
<td>SUBMITTED</td>
</tr>

<tr>
<td><code>60000</code></td>
<td>AVAILABLE</td>
</tr>

<tr>
<td><code>70000</code></td>
<td>COMPLETED</td>
</tr>

<tr>
<td><code>80000</code></td>
<td>REVERSED</td>
</tr>

<tr>
<td><code>90000</code></td>
<td>DECLINED</td>
</tr>

<tr>
<td><code>90110</code></td>
<td>DECLINED-SLS-SENDER</td>
</tr>

<tr>
<td><code>90120</code></td>
<td>DECLINED-SLS-BENEFICIARY</td>
</tr>

<tr>
<td><code>90200</code></td>
<td>DECLINED-INVALID-BENEFICIARY</td>
</tr>

<tr>
<td><code>90201</code></td>
<td>DECLINED-BARRED-BENEFICIARY</td>
</tr>

<tr>
<td><code>90202</code></td>
<td>DECLINED-UNSUPPORTED-BENEFICIARY</td>
</tr>

<tr>
<td><code>90210</code></td>
<td>DECLINED-INVALID-BENEFICIARY-DETAILS</td>
</tr>

<tr>
<td><code>90305</code></td>
<td>DECLINED-LIMITATIONS-ON-TRANSACTION-VALUE</td>
</tr>

<tr>
<td><code>90310</code></td>
<td>DECLINED-LIMITATIONS-ON-SENDER-VALUE</td>
</tr>

<tr>
<td><code>90320</code></td>
<td>DECLINED-LIMITATIONS-ON-BENEFICIARY-VALUE</td>
</tr>

<tr>
<td><code>90330</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-VALUE</td>
</tr>

<tr>
<td><code>90331</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-VALUE-DAILY</td>
</tr>

<tr>
<td><code>90332</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-VALUE-WEEKLY</td>
</tr>

<tr>
<td><code>90333</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-VALUE-MONTHLY</td>
</tr>

<tr>
<td><code>90334</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-VALUE-YEARLY</td>
</tr>

<tr>
<td><code>90350</code></td>
<td>DECLINED-LIMITATIONS-ON-SENDER-QUANTITY</td>
</tr>

<tr>
<td><code>90360</code></td>
<td>DECLINED-LIMITATIONS-ON-BENEFICIARY-QUANTITY</td>
</tr>

<tr>
<td><code>90370</code></td>
<td>DECLINED-LIMITATIONS-ON-ACCOUNT-QUANTITY</td>
</tr>

<tr>
<td><code>90380</code></td>
<td>DECLINED-DUPLICATED-TRANSACTION</td>
</tr>

<tr>
<td><code>90400</code></td>
<td>DECLINED-PAYER-CURRENTLY-UNAVAILABLE</td>
</tr>
</tbody>
</table>

<h2 id="account-status">Account Status</h2>

<table>
<thead>
<tr>
<th>Status</th>
<th>Message</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>AVAILABLE</code></td>
<td>Credit party account is available and can receive a transfer</td>
</tr>

<tr>
<td><code>UNREGISTERED</code></td>
<td>Credit party account is not registered but can still receive a transfer</td>
</tr>

<tr>
<td><code>UNAVAILABLE</code></td>
<td>Credit party account is not available and will not receive a transfer</td>
</tr>
</tbody>
</table>

<h2 id="beneficiary-relationship">Beneficiary Relationship</h2>

<table>
<thead>
<tr>
<th>Relationship</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>AUNT</code></td>
<td>Aunt</td>
</tr>

<tr>
<td><code>BROTHER</code></td>
<td>Brother</td>
</tr>

<tr>
<td><code>BROTHER_IN_LAW</code></td>
<td>Brother-in-law</td>
</tr>

<tr>
<td><code>COUSIN</code></td>
<td>Cousin</td>
</tr>

<tr>
<td><code>DAUGHTER</code></td>
<td>Daughter</td>
</tr>

<tr>
<td><code>FATHER</code></td>
<td>Father</td>
</tr>

<tr>
<td><code>FATHER_IN_LAW</code></td>
<td>Father-in-law</td>
</tr>

<tr>
<td><code>FRIEND</code></td>
<td>Friend</td>
</tr>

<tr>
<td><code>GRAND_FATHER</code></td>
<td>Grandfather</td>
</tr>

<tr>
<td><code>GRAND_MOTHER</code></td>
<td>Grandmother</td>
</tr>

<tr>
<td><code>HUSBAND</code></td>
<td>Husband</td>
</tr>

<tr>
<td><code>MOTHER</code></td>
<td>Mother</td>
</tr>

<tr>
<td><code>MOTHER_IN_LAW</code></td>
<td>Mother-in-law</td>
</tr>

<tr>
<td><code>NEPHEW</code></td>
<td>Nephew</td>
</tr>

<tr>
<td><code>NIECE</code></td>
<td>Niece</td>
</tr>

<tr>
<td><code>SELF</code></td>
<td>Self (i.e. the <a href="#sender">sender</a>, himself)</td>
</tr>

<tr>
<td><code>SISTER</code></td>
<td>Sister</td>
</tr>

<tr>
<td><code>SISTER_IN_LAW</code></td>
<td>Sister-in-law</td>
</tr>

<tr>
<td><code>SON</code></td>
<td>Son</td>
</tr>

<tr>
<td><code>UNCLE</code></td>
<td>Uncle</td>
</tr>

<tr>
<td><code>WIFE</code></td>
<td>Wife</td>
</tr>

<tr>
<td><code>OTHER</code></td>
<td>Others not listed</td>
</tr>
</tbody>
</table>

<h2 id="source-of-funds">Source of Funds</h2>

<table>
<thead>
<tr>
<th>Source</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>CASH</code></td>
<td>Cash</td>
</tr>

<tr>
<td><code>BUSINESS</code></td>
<td>Business</td>
</tr>

<tr>
<td><code>GIFT</code></td>
<td>Gift</td>
</tr>

<tr>
<td><code>SALARY</code></td>
<td>Salary</td>
</tr>

<tr>
<td><code>LOTTERY</code></td>
<td>Lottery</td>
</tr>

<tr>
<td><code>SAVINGS</code></td>
<td>Savings</td>
</tr>

<tr>
<td><code>OTHER</code></td>
<td>Others not listed</td>
</tr>
</tbody>
</table>

<h2 id="id-type">ID Type</h2>

<table>
<thead>
<tr>
<th>Type</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>PASSPORT</code></td>
<td>Passport</td>
</tr>

<tr>
<td><code>NATIONAL_ID</code></td>
<td>National Identification Card</td>
</tr>

<tr>
<td><code>DRIVING_LICENSE</code></td>
<td>Driving License</td>
</tr>

<tr>
<td><code>SOCIAL_SECURITY</code></td>
<td>Social Security Card/Number</td>
</tr>

<tr>
<td><code>TAX_ID</code></td>
<td>Tax Payer Identification Card/Number</td>
</tr>

<tr>
<td><code>SENIOR_CITIZEN_ID</code></td>
<td>Senior Citizen Identification Card</td>
</tr>

<tr>
<td><code>BIRTH_CERTIFICATE</code></td>
<td>Birth Certificate</td>
</tr>

<tr>
<td><code>VILLAGE_ELDER_ID</code></td>
<td>Village Elder Identification Card</td>
</tr>

<tr>
<td><code>RESIDENT_CARD</code></td>
<td>Permanent Residency Identification Card</td>
</tr>

<tr>
<td><code>ALIEN_REGISTRATION</code></td>
<td>Alien Registration Certificate/Card</td>
</tr>

<tr>
<td><code>PAN_CARD</code></td>
<td>PAN Card</td>
</tr>

<tr>
<td><code>VOTERS_ID</code></td>
<td>Voter’s Identification Card</td>
</tr>

<tr>
<td><code>HEALTH_CARD</code></td>
<td>Health Insurance Card/Number</td>
</tr>

<tr>
<td><code>EMPLOYER_ID</code></td>
<td>Employer Identification Card</td>
</tr>

<tr>
<td><code>OTHER</code></td>
<td>Others not listed</td>
</tr>
</tbody>
</table>

<h2 id="purpose-of-remittance">Purpose of Remittance</h2>

<table>
<thead>
<tr>
<th>Purpose</th>
<th>Description</th>
</tr>
</thead>

<tbody>
<tr>
<td><code>FAMILY_SUPPORT</code></td>
<td>Family support</td>
</tr>

<tr>
<td><code>EDUCATION</code></td>
<td>Education</td>
</tr>

<tr>
<td><code>GIFT_AND_DONATION</code></td>
<td>Gift and other donations</td>
</tr>

<tr>
<td><code>MEDICAL_TREATMENT</code></td>
<td>Medical treatment</td>
</tr>

<tr>
<td><code>MAINTENANCE_EXPENSES</code></td>
<td>Maintenance or other expenses</td>
</tr>

<tr>
<td><code>TRAVEL</code></td>
<td>Travel</td>
</tr>

<tr>
<td><code>SMALL_VALUE_REMITTANCE</code></td>
<td>Small value remittance</td>
</tr>

<tr>
<td><code>LIBERALIZED_REMITTANCE</code></td>
<td>Liberalized remittance</td>
</tr>

<tr>
<td><code>CONSTRUCTION_EXPENSES</code></td>
<td>Construction expenses</td>
</tr>

<tr>
<td><code>HOTEL_ACCOMMODATION</code></td>
<td>Hotel accommodation</td>
</tr>

<tr>
<td><code>ADVERTISING_EXPENSES</code></td>
<td>Advertising and/or public relations related expenses</td>
</tr>

<tr>
<td><code>ADVISORY_FEES</code></td>
<td>Fees for advisory or consulting service</td>
</tr>

<tr>
<td><code>BUSINESS_INSURANCE</code></td>
<td>Business related insurance payment</td>
</tr>

<tr>
<td><code>INSURANCE_CLAIMS</code></td>
<td>Insurance claims payment</td>
</tr>

<tr>
<td><code>DELIVERY_FEES</code></td>
<td>Delivery fees</td>
</tr>

<tr>
<td><code>EXPORTED_GOODS</code></td>
<td>Payments for exported goods</td>
</tr>

<tr>
<td><code>SERVICE_CHARGES</code></td>
<td>Payment for services</td>
</tr>

<tr>
<td><code>LOAN_PAYMENT</code></td>
<td>Payment of loans</td>
</tr>

<tr>
<td><code>OFFICE_EXPENSES</code></td>
<td>Office expenses</td>
</tr>

<tr>
<td><code>PROPERTY_PURCHASE</code></td>
<td>Residential property purchase</td>
</tr>

<tr>
<td><code>PROPERTY_RENTAL</code></td>
<td>Property rental payment</td>
</tr>

<tr>
<td><code>ROYALTY_FEES</code></td>
<td>Royalty, trademark, patent and copyright fees</td>
</tr>

<tr>
<td><code>SHARES_INVESTMENT</code></td>
<td>Investment in shares</td>
</tr>

<tr>
<td><code>FUND_INVESTMENT</code></td>
<td>Fund investment</td>
</tr>

<tr>
<td><code>TAX_PAYMENT</code></td>
<td>Tax payment</td>
</tr>

<tr>
<td><code>TRANSPORTATION_FEES</code></td>
<td>Transportation fees</td>
</tr>

<tr>
<td><code>UTILITY_BILLS</code></td>
<td>Utility bills</td>
</tr>

<tr>
<td><code>PERSONAL_TRANSFER</code></td>
<td>Personal transfer</td>
</tr>

<tr>
<td><code>SALARY_PAYMENT</code></td>
<td>Payment of salary</td>
</tr>

<tr>
<td><code>OTHER_FEES</code></td>
<td>Broker, commitment, guarantee and other fees</td>
</tr>

<tr>
<td><code>OTHER</code></td>
<td>Other purposes</td>
</tr>
</tbody>
</table>