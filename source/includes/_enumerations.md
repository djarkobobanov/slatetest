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
<td><code>7</code></td>
<td>COMPLETED</td>
</tr>

<tr>
<td><code>8</code></td>
<td>REFUNDED</td>
</tr>

<tr>
<td><code>9</code></td>
<td>DECLINED</td>
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

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<p class="n">Get Beneficiary Relationship</p>
<span class="nf">GET</span> <span class="nn">{URL}/beneficiary_relationships</span> 
<span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

<span class="p">{</>
      <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
      <span class="err">data</span> <span class="p">:</span> <span class="p">{</span>
        <span class="err">beneficiary_relationships</span> <span class="p">:</span> <span class="p">[</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Other not listed&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;OTHER&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
            <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Wife&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;WIFE&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Uncle&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;UNCLE&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Son&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SON&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sister-in-law&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SISTER_IN_LAW&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Sister&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SISTER&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">}</span>
    <span class="p">]</span>
<span class="p">},</span>
 <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">Succesfully get my Beneficiary Relationship</span>
<span class="p">}</span>
    </code></pre></div>


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

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<p class="n">Get Source of Funds</p>
<span class="nf">GET</span> <span class="nn">{URL}/source_of_funds
</span> 
<span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

<span class="p">{</>
      <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
      <span class="err">data</span> <span class="p">:</span> <span class="p">{</span>
        <span class="err">total</span> <span class="p">:</span> <span class="p"></span><span class="p">,</span>
        <span class="err">source_of_funds</span> <span class="p">:</span> <span class="p">[</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Other not listed&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;OTHER&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
            <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Savings&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SAVINGS&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Lottery&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;LOTTERY&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Salary&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SALARY&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Gift&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;GIFT&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Salary&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SALARY&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Business&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;BUSINESS&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Cash&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;CASH&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">}</span>
    <span class="p">]</span>
<span class="p">},</span>
 <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">Succesfully get my Source of Funds</span>
<span class="p">}</span>
    </code></pre></div>

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

<div class="highlight"><pre class="chroma"><code class="language-http" data-lang="http">
<p class="n">Get Purpose of Remittance</p>
<span class="nf">GET</span> <span class="nn">{URL}/purpose_of_remittances
</span> 
<span class="kr">HTTP</span><span class="o">/</span><span class="m">1.1</span>
<span class="s2">--header</span> <span class="nf">Authorization</span> <span class="s2">{{API KEY}}</span> 

<span class="p">{</>
      <span class="err">status</span> <span class="err">200</span><span class="p">,</span>
      <span class="err">data</span> <span class="p">:</span> <span class="p">{</span>
        <span class="err">total</span> <span class="p">:</span> <span class="p"></span><span class="p">,</span>
        <span class="err">source_of_funds</span> <span class="p">:</span> <span class="p">[</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Other purposes&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;OTHER&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
            <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Broker, commitment, guarantee and other fees&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;OTHER_FEES&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Payment of salary&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;SALARY_PAYMENT&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Personal transfer&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;PERSONAL_TRANSFER&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Utility bills&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;UTILITY_BILLS&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Transportation fees&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;TRANSPORTATION_FEES&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Tax payment&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;TAX_PAYMENT&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">},</span>
          <span class="p">{</span>
            <span class="nt">&#34;id&#34;</span><span class="p">:</span> <span class="mi">{ID}</span><span class="p">,</span>
            <span class="nt">&#34;name&#34;</span><span class="p">:</span> <span class="s2">&#34;Fund investment&#34;</span><span class="p">,</span>
            <span class="nt">&#34;description&#34;</span><span class="p">:</span> <span class="kc">null</span><span class="p">,</span>
            <span class="nt">&#34;code&#34;</span><span class="p">:</span> <span class="s2">&#34;FUND_INVESTMENT&#34;</span><span class="p">,</span>
            <span class="nt">&#34;created_at&#34;</span><span class="p">:</span> <span class="mi">&#34;2020-04-09T12:13:39.818Z&#34;</span><span class="p">,</span>
            <span class="nt">&#34;updated_at&#34;</span><span class="p">:</span> <span class="mi">2020-04-09T12:13:39.818Z</span>
          <span class="p">}</span>
    <span class="p">]</span>
<span class="p">},</span>
 <span class="nt">&#34;message&#34;</span><span class="p">:</span> <span class="s2">Succesfully get my Purpose of Remittance</span>
<span class="p">}</span>
    </code></pre></div>
</tbody>
</table>
