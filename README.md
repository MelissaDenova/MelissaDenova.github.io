---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-07 </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Research </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> Jaime Vidal </td>
  </tr>
    <tr>
    <td> Requester area </td>
    <td> Research </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Fractal 1 Rule Based </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> June 18, 2024 </td>
  </tr>
  <tr>
    <td> Receptor </td>
    <td> Eddy Zavaleta </td>
  </tr>
  </table>
  
### 2. LIST OF FUNCTIONAL REQUIREMENTS
<table>
  <tr>
    <td> Request ID </td>
    <td> Request </td>
    <td> Acceptance criteria </td>
    <td> Associated BR </td>
  </tr>
  <tr>
    <td> FR1 </td>
    <td> It is required to implement a method based on the variable Uptrend that selects in which portfolio to invest, within two possible options. </td>
    <td> Since a portfolio selection method needs to be implemented, when the user enters the variables to be analyzed, the system will select between portfolio A and B as the best option. </td>
    <td> BR1, BR2, BR3, BR4, BR5, BR6 </td>
  </tr>
</table>

### 3. PRECONDITIONS
<table>
  <tr>
    <td> ID PC </td>
    <td> Preconditions </td>
  </tr>
  <tr> 
    <td> PC1 </td>
    <td> <p> As a basis for the requirement there are two time series (Portfolio A and Portfolio B).</p> <p>The time series can be of any asset type.</p> <p> Example:</p> <p>Blend 1, Blend 2, Blend 3, ETFs, Stocks, etc. can be considered.</p> </td>
  </tr>
  </table>

### 4. BUSINESS RULES
<table>
  <tr>
    <td> ID BR </td>
    <td> Business rule </td>
  </tr>
  <tr>
    <td> BR1 </td>
    <td> The calculation of the uptrend variable shall be performed only for portfolio "A". </td>
  </tr>
  <tr>
     <td> BR2 </td>
     <td> <p>Initially, the calculation of Momentum should be performed using the following formula:</p> <p>MTUM = Price_TRR / MA(N)</p> <p>Where N is the number of days to be considered.</p> <p>For the first user test case, the periods to be considered for the Momentum calculation will be the following:</p> <p>MTUM_13D</p> <p>MTUM_30D</p> <p>MTUM_50D</p> <p>MTUM_100D</p> <p>MTUM_150D</p> <p>MTUM_200D</p> <p>Note: For subsequent tests, the periods considered for the Momentum calculation shall be flexible.</p></td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> <p>Once the Momentum calculation for the different periods selected has been made, the arithmetic mean of these values must be calculated to form the uptrend variable. </p> <p>Expressed in formula we would have:</p> <p>Uptrend = ((MTUM (N1) + MTUM (N2) + MTUM (N3) + MTUM (Nm)) / X </p> <p>Where N1, N2, N3, Nm... will be the periods (in days) that will be used for each MTUM, and X will be the number of MTUMs to be used.</p> </td>
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p>Once the uptrend value is available, an optimal threshold should be set in order to have the criteria under which the switch between portfolio A and portfolio B will be made. </p> <p>For the first user test case, the value considered for the Threshold will be 0.98; for subsequent tests, the value of the Threshold should be flexible.</p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> <p>For the selection of the portfolio, the following rule must be considered: </p> <p>If the uptrend value obtained for portfolio "A" is greater than or equal to the value set as Threshold, then invest in portfolio "A", otherwise invest in portfolio B. </p> <p>Note: For the selection of the portfolio, a Delay T2 must be considered.</p> </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> <p>Once the portfolio is selected, the selection is respected until the "n" days set for rebalancing have elapsed. </p> <p>Note: For the first user test case, 21 days shall be considered; for subsequent tests, the number of days considered for rebalancing shall be flexible.</p> </td>
  </tr>
   </table>

### 5. LIST OF NON - FUNCTIONAL REQUIREMENTS
<table>
  <tr>
    <td> NFR ID </td>
    <td> Non - Functional requirements </td>
    <td> Module / System </td>
  </tr>
  <tr>
    <td> NFR1 </td>
    <td> NA </td>
    <td> NA </td>
  </tr>
</table>

### 6. DEVELOPMENT OFFICERS
<table>
  <tr>
    <td> Name </td>
    <td> Role </td>
  </tr>
  <tr>
    <td> Eddy Zavaleta </td>
    <td> Manager </td>
  </tr>
  <tr>
    <td> Sebastián Carreón </td>
    <td> Developer </td>
  </tr>
  <tr>
    <td> Luis Fábregas </td>
    <td> QA team leader </td>
  </tr>
</table>

### 7. PRODUCT ASSUMPTIONS
<p align="justify"> 1. The documents must be reviewed and approved by the user area.</p>
<p align="justify"> 2. To have the availability of the people involved in the user area for doubts, clarifications, revisions and acceptance of the deliverables of the product. </p>
<p align="justify"> 3. The delivery, review and validation times for the deliverables committed in the product will be defined in the work schedule, however, the times for the fulfilment of each activity may be affected considering the following: </p>

   * <p align="justify"> Availability of stakeholders in the user area for the definition, review, clarification and validation of product requirements. </p> 
   * <p align="justify"> Validation and sign-off of deliverables according to the stages of the product. </p>

### 7.2 BACKTESTING ASSUMPTIONS
* <p>Benchmark (Buy and hold portfolio A and portfolio B)</p>
* <p>Broker Fees are not considered to be</p>
* <p>Scalability was not assumed, i.e. the capacity of the strategy was not considered.</p>

### 8. RESTRICTIONS TO BE CONSIDERED
<p align="justify"> The needs and requirement requests for the development area are defined in the ‘Software Requirements Specification (SRS)’ document that corresponds to the scope requested by the business areas, in case of an adjustment, a change control and redefinition of the work schedule will be carried out. </p>

### 8.1 BACKTESTING RESTRICTIONS
* <p> NA </p>

### 9. EXCLUSIONS
<p align="justify"> The exclusions considered in the requirement are presented below, in order not to generate false expectations in the product that will be delivered to the business area. </p>

   * <p align="justify"> No improvements or changes are envisaged after acceptance of the requirements document at the beginning, during and at the end of the product development; where appropriate, the feasibility of a change control shall be stated. </p> 

### 10. GLOSSARY OF TERMS
<table>
  <tr>
    <td> Term </td>
    <td> Definition </td>
  </tr>
  <tr> 
    <td> FR </td>
    <td> Functional Requirement. </td>
  </tr>
  <tr>
    <td> BR </td>
    <td> Regla de negocio. </td>
  </tr>
  <tr>
    <td> PC </td>
    <td> Precondiciones. </td>
  </tr>
  <tr>
    <td> NFR </td>
    <td> Non - Functional Requirement. </td>
  </tr>
</table>

### 11. APPENDICES
<table>
  <tr>
    <td> Name of document </td>
    <td> Document path </td>
  </tr>
  <tr>
    <td> Framework </td>
    <td> <A HREF="https://tequilacapital.sharepoint.com/:w:/s/TequilaCapital/EbhIH9DsmVxLtjZEKS02vZkBANtCoiNHiGs8asUUHwk70w?e=O7G38o"> Framework Fractal 1 </A> </td>
  </tr>
</table>

### 12. AUTHORISATIONS 
<table>
  <tr>
    <td> Elaborated </td>
    <td> Authorised </td>
  </tr>
  <tr>
    <td> <p> Melissa González </p> <p> Area: Development </p> <p> Role: Analyst </p></td>
    <td> <p> Jaime Vidal </p> <p> Area: Research </p> <p> Role: Quant </p></td>
  </tr>
</table>
