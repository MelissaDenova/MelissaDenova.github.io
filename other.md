---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-01 </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Research </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> Luis Cárdenas </td>
  </tr>
    <tr>
    <td> Requester area </td>
    <td> Research </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Tracking Error </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> May 08, 2024 </td>
  </tr>
  <tr>
    <td> Receiver </td>
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
    <td> It is required to implement an algorithm that minimises the tracking error with respect to the theoretical portfolio subject to scalability constraints, i.e. what it could buy of each stock. </td>
    <td> <p> Since it is required to have an algorithm that minimises tracking error, when performing the actual portfolio optimisation using the proposed methodology, then the following results should be displayed: </p> <p> &#160; &#160; &#160; *Start date of the analysis. </p> <p> &#160; &#160; &#160; *Completion date of the performance calculation. </p> <p> &#160; &#160; &#160; *Dates from which data is run. </p> <p> &#160; &#160; &#160; *Dates of return calculations. </p> <p> &#160; &#160; &#160; *Theoretical yield. </p> <p> &#160; &#160; &#160; *Actual performance already optimised. </p> <p> &#160; &#160; &#160; *A priori and a posteriori error tracking. </p></td>
    <td> BR1, BR2, BR3, BR4, BR5, BR6, BR7, BR8, BR9, BR10, BR11, BR12, BR13 </td>
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
    <td> <p> The input data for the design of the algorithm shall be the following: </p> <p> &#160; &#160; &#160; *Ticker database. </p> <p> &#160; &#160; &#160; *Average volume at n days of the selected tickers (Variable). </p> <p> &#160; &#160; &#160; *Daily return of the tickers. </p> <p> &#160; &#160; &#160; *Daily returns of the theoretical portfolio. </p></td>
  </tr>
</table>

### 4. BUSINESS RULES
<table>
  <tr>
    <td> BR ID </td>
    <td> Business rule </td>
  </tr>
  <tr>
    <td> BR1 </td>
    <td> <p> Having as input a list of tickers, and the average volume at "n" days of those tickers, the calculation of the maximum tradable amount shall be performed, considering the rule of trading only the established percentage of the total value. (The percentage shall be considered as a variable input).</p> <p> Example: </p> <p>  For this example, 30 days and a maximum trading percentage of 8% are considered </p> <table align="center"> <tr> <td> TICKER DATA </td> <td> VOLUMEN AVG 30D </td> <td> 8% DEL AVG VOLUME </td> </tr> <tr> <td> ACCD US Equity </td> <td> $5,074,957.29 </td> <td>$405,996.58 </td> </tr> <tr> <td> ACMR US Equity </td> <td> $59,834,022.85 </td> <td> $4,786,721.83 </td></tr> <tr> <td> ADCT US Equity</td> <td>$   2,801,423.83 </td> <td> $224,113.91</td> </tr></table> <p> ACCD US Equity = 5074957.29 (0.08) = 405996.58 </p> <p> ACMR US Equity = 59834022.85 (0.08) = 4786721.83 </p> <p> ADCT US Equity = 2801423.83 (0.08) = 224113.91 </p> </td> 
  </tr>
  <tr>
     <td> BR2 </td>
     <td> <p> The assignment of weights to the theoretical model for each of the listed tickers must be made according to the value obtained in the strategy used. </p> <p> The sum of the weights must equal 100%.</p> <p> Example: </p> <p> For the example, 100 tickers will be considered, so the weight assigned to each ticker will be 1%.</p> <table align="center"> <tr> <td>TICKER DATA</td> <td> MODEL WEIGHT </td></tr> <tr> <td>ACCD US Equity</td> <td>1% </td> </tr> <tr> <td>ACMR US Equity </td> <td>1% </td> </tr> <tr> <td>ADCT US Equity </td> <td>1% </td> </tr> </table> </td>
  </tr>
  <tr>
     <td> BR3 </td> 
     <td> <p>Based on the total amount to be traded on the day, the notional amount should be calculated with respect to the weights assigned in the model by multiplying the total amount to be traded by the notional weight assigned to each of the tickers.</p> <p> The total amount to be operated will be a variable input. </p> <p> Example </p> <p> Amount to operate: $30,000,000 </p> <table align="center"> <tr> <td> TICKER DATA </td> <td> MODEL WEIGHT </td> <td> THEORICAL AMOUNT</td></tr> <tr> <td> ACCD US Equity </td> <td> 1% </td> <td> $300,000 </td></tr> <tr> <td> ACMR US Equity </td> <td> 1% </td> <td> $300,000 </td></tr> <tr> <td> ADCT US Equity </td> <td> 1% </td> <td> $300,000 </td></tr></table> <p> ACCD US Equity = 30 000 000 (0.01) = 300 000 </p> <p>ACMR US Equity = 30 000 000 (0.01) = 300 000 </p> <p>ADCT US Equity = 30 000 000 (0.01) = 300 000 </p></td>
  </tr>
  <tr>
    <td> BR4 </td>
    <td> <p> Ceilings and floors shall be set for each of the actions. </p> <p>The minimum limit shall be 0% and the maximum limit shall be considered as a variable input. </p> <p> To set the value of the maximum limit in each ticker, the following condition shall be obeyed: </p> <p>If the result of dividing the maximum tradable amount for each ticker by the total amount to be traded on a given day is greater than the maximum limit set, then the value of the maximum limit is assigned. </p> <p> Otherwise, the maximum limit will be the quotient value of the division. </p> <p> Example: </p> <p> Amount to operate: $30,000,000 </p> <table align="center"> <tr> <td>TICKER DATA </td> <td> 8% DEL AVG VOLUME </td> <td> %MIN </td> <td> %MAX </td></tr> <tr> <td> ACCD US Equity </td> <td> $405,996.58 </td> <td> 0% </td> <td> 1.35% </td></tr> <tr> <td> ACMR US Equity </td> <td> $4,786,721.83 </td> <td> 0% </td> <td> 5.0% </td></tr> <tr> <td> ADCT US Equity </td> <td> $224,113.91</td> <td>0% </td> <td> 0.75% </td></tr></table> <p> %MAX ACCD US Equity = 405,996.58 / 30,000,000 = 1.35% </p> <p> %MAX ACMR US Equity = 4,786,721.83 / 30,000,000 = 15.95% (In this case, the value is greater than 0.05 so the maximum limit will be considered to be 5%). </p> <p> %MAX ADCT US Equity = 224,113.91 / 30,000,000 = 0.75% </p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> <p>Before calculating the tracking error, the daily returns for both the theoretical portfolio and the real portfolio shall be calculated.</p> <p>The pivot date shall be considered as the day before trading; from that date, the analysis shall begin and the amount that the portfolio would have paid in the last "n" days shall be calculated by multiplying the weight by the daily yields that the issuer has had in the last "n" days including the pivot date. </p> <p>The calculation should be made considering the theoretical weights and the current weights.</p> </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> The days on which the Tracking Error will be calculated should a priori be considered as a variable input. </td>
  </tr>
  <tr> 
    <td> BR7 </td>
    <td> <p> Once the values of the NR5 are available, the daily differences between the target value and the actual value should be calculated. </p> <table align="center"> <tr> <td> DATE </td> <td> THEORICAL </td> <td> ACTUAL </td> <td> DIFFERENCE </td></tr> <tr> <td> 28/02/2024 </td> <td> -0.252% </td> <td> -0.212% </td> <td> 0.041 </td> </tr> <tr> <td>29/02/2024 </td> <td> 0.229% </td> <td> 0.479</td> <td> 0.249 </td></tr> <tr> <td> 01/02/2024 </td> <td> 1.686% </td> <td> 1.952 </td> <td> 0.267</td></tr></table> </td>
  </tr>
  <tr>
    <td> BR8 </td>
    <td> <p> The a priori tracking error value shall be obtained by calculating the standard deviation of the difference in daily returns between a theoretical portfolio and the actual portfolio as of "n" days prior, including the pivot date. </p> <p>Tracking error = Standard deviation of (P - B) </p> <p> Where P is the portfolio return and B is the benchmark return. </p> <p>To annualize the result, the value obtained for the standard deviation should be multiplied by the root of 252.</p> </td>
  </tr>
  <tr>
    <td> BR9 </td>
    <td> <p>The ex-post tracking error value shall be obtained by calculating the standard deviation of the difference in daily returns between a notional portfolio and the actual portfolio at "n" days from the trading day (day after the pivot date). </p> <p> Tracking error = Standard deviation of (P - B) </p> <p>Where P is the portfolio return and B is the benchmark return. </p> <p> To annualize the result, the value obtained for the standard deviation should be multiplied by the root of 252.</p> </td>
  </tr>
  <tr>
    <td> BR10 </td>
    <td> <p> For the optimisation of the portfolio, the value obtained in Tracking error a priori shall be considered as a target and the following conditions shall be respected: </p> <p> 1.1.	The optimised percentage must be greater than or equal to the minimum established limit (0%). </p> <p> 2.2.	The optimised percentage must be less than or equal to the maximum established limit.</p> <p> 3.3.	The sum of the weights must be equal to 100%. </p> </td>
  </tr>
  <tr>
    <td> BR11 </td>
    <td> <p> For the final analysis of the methodology, the return for the theoretical portfolio and for the actual portfolio should be calculated by multiplying the returns of each ticker by its corresponding weight. </p> <p> Once these values are available, the difference between the theoretical return and the actual return is calculated. </p> </td>
  </tr>
  <tr>
    <td> BR12 </td>
    <td> The amount invested shall not exceed a set value of the total volume traded (Parametric, not to exceed a threshold of the volume traded). </td>
  </tr>
  <tr>
    <td> BR13 </td>
    <td> The only eligible shares are those comprising the theoretical portfolio. </td>
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
    <td> The optimiser that will be used to find the optimal weight will be GRG. </td>
    <td> To be define </td>
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
    <td> Sergio Méndez </td>
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

### 8. RESTRICTIONS TO BE CONSIDERED
<p align="justify"> The needs and requirement requests for the development area are defined in the ‘Software Requirements Specification (SRS)’ document that corresponds to the scope requested by the business areas, in case of an adjustment, a change control and redefinition of the work schedule will be carried out. </p>

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
    <td> NA </td>
    <td> NA </td>
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
    <td> <p> Luis Cardenas </p> <p> Area: Research </p> <p> Role: Portfolio Manager </p></td>
  </tr>
</table>
