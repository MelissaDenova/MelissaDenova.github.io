---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-03 </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Business </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> Luis de Villa </td>
  </tr>
    <tr>
    <td> Requester area </td>
    <td> Business </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Strategy Dashboard </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> May 14, 2024 </td>
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
    <td> A strategy-focused dashboard needs to be developed in order to be able to compare how things perform under different metrics in Backtest, Out-of Sample and Real life performance. </td>
    <td> <p> Given the need to be able to make comparisons under certain metrics, when the user enters the eligible universe of strategies and the time period to be analyzed, the dashboard should display the following data: </p> <p> 1. Three tables, where the metrics of different items on the selected strategies are shown.</p> <p> 2. Three tables showing the relative value for each strategy with respect to the value contained in the benchmark index.</p> <p> 3.A summary table for each metric with its corresponding graph.</p> </td>
    <td> BR1, BR2, BR3, BR4, BR5, BR6, BR7, BR8, BR9,BR10 </td>
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
    <td> <p>The input data for the dashboard view shall be the following:</p> <p> 1. Eligible universe of strategies.</p> <p> 2.Period to be considered as the basis for the calculation.</p> <p> 3.Index on which the comparison will be made.</p> </td>
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
    <td> <p> CAGR calculation should be performed for all strategies and benchmark in Backtester, Out-of Sample and Real life Performance. </p> <p>Example:</p> <p> *The calculation is based on the following formula:</p> <p>Formula:</p> <p>CAGR = Product (1+ Yields for the period) ^ (365 / (End date - Start date)) -1 </p> </td>
  </tr>
  <tr>
     <td> BR2 </td>
     <td> <p> The standard deviation shall be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance on the basis of the returns pertaining to a strategy in the stated period. The result shall be annualized. </p> <p>Example:</p> <p>The standard deviation formula is applied to the returns and multiplied by the root of 252 to annualize the result.</p> <p>Formula:</p> <p>St. Deviation = DESVEST.M (Strategy returns over the period) * sqrt (252). </p> </td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> <p>The Daily Historical VaR value (95%) should be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance.</p> <p>Example:</p> <p>A 5% percentile calculation is performed on the daily returns that the strategy has had in the set period.</p> </td>
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p>The Rolling 12M Return Average value shall be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance. </p> <p>Example:</p> <p>*The first calculation is made with the period of one year as a base. The price on day 252 is divided by the price on day 1 of the period. Subtract 1 from the result.</p> <p>*Once the result of the previous point is obtained, the average is calculated for each strategy of the values obtained (Consider the period).</p> <p> For LowFCF_MctCap, T40, in Backtest a period from 1997 to 2006 is considered, so the average will be calculated on the data of that period for that strategy; the same applies for Out-of Sample and Real life Performance.</p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> <p>The value of the Rolling 12M Return Median should be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance. </p> <p>Example:</p> <p>*The first calculation is made with the period of one year as a base. The price on day 252 is divided by the price on day 1 of the period. Subtract 1 from the result. </p> <p>*Once the result of the previous point is obtained, the median is calculated for each strategy of the values obtained (Consider the period). </p> <p> For LowFCF_MctCap, T40, in Backtest a period from 1997 to 2006 is considered, so the median will be calculated on the data of that period for that strategy; the same applies for Out-of Sample and Real life Performance.</p> </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> <p>The Worst Drawdown value shall be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance.</p> <p>Example:</p> <p> *Calculates the maximum value between the price of the current date and the price of the previous days in the set period. </p> <p> *Divides the price of the current date by the maximum value obtained in the previous step. </p> <p> *Subtracts 1 from the result of the division. </p> <p>*Searches for the minimum value between 0 and the value obtained in step 3. </p> <p>Formula:</p> <p>Min (0, Current date / Max (Current date: Previous dates in the period) -1)</p> <p> *Once the result of the previous point is obtained, calculate the minimum value in the strategy for the established period.</p></td>
  </tr>
  <tr>
    <td> BR7 </td>
    <td> <p>The Sharpe Ratio value shall be calculated for all strategies and the benchmark in Backtester, Out-of Sample and Real life Performance.</p> <p> Example:</p> <p>Perform the division of the value obtained in the CAGR by the value obtained in the standard deviation.</p> <p>Example of the required view:</p></td>
  </tr>
  <tr>
    <td> BR8 </td>
    <td> <p>Once you have the metrics for each strategy in Backtest, Out-of Sample and Real life Performance you should generate a table with the relative values with respect to the SPY in the established period of time.</p> <p>Example:</p> <table> <tr> <td colspan="3">Backtester</td></tr> <tr><td> </td> <td>[LowFCF_MktCap, T40]</td><td>SPY</td></tr> <tr> <td>CAGR</td> <td>33.04%</td> <td>8.16%</td></tr> <tr> <td> St. Deviation</td> <td>19.24%</td> <td>19%</td></tr> <tr><td> Daily Historical VaR (95%)</td> <td> -1.84</td> <td>-1.95 </td></tr> <tr> <td>Rolling 12M Return Average</td> <td> 36.59% </td> <td> 7.62%</td></tr> <tr> <td> Rolling 12M Return Median</td> <td> 31.06</td> <td> 10.28%</td></tr> <tr> <td> Worst Drawdown </td> <td> -33.66%</td> <td> -47.50% </td></tr> <tr> <td> Sharpe Ratio </td> <td> 1.72</td> <td> 0.43</td></tr> </table> </td> <p>For the summary table, the value obtained in the strategy is divided by the value obtained in the SPY.</p> <p>CAGR=33.04% / 8.16% = 4.05</p> <p>St. Deviation = 19.24% / 19 = 1.01</p><p>Daily Historical VaR (95%) = -1.84% / -1.95% = 0.94</p> <p>Example of the required view:</p>
  </tr>
  <tr>
    <td> BR9 </td>
    <td> <p>Finally, once you have the SPY tables for Backtest, Out-of Sample and Real life performance, you should generate summary tables for each statistical value including all strategies.</p> <p>It should be possible to add a Threshold to each metric (Input variable).</p> <p>Example of the required view:</p> </td>
  </tr>
  <tr>
    <td> BR10 </td>
    <td><p>The values displayed in the RN9 tables shall be shown in graphs.</p> <p>Example of a graph:</p> </td>
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
    <td> Augusto González </td>
    <td> Front end team leader </td>
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
* <p> NA </p>

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
    <td> Mock - up </td>
    <td><A HREF="https://tequilacapital.sharepoint.com/:w:/s/TequilaCapital/ETszHqTNRLtMjWv7WDKZidgBwlJQ9ldT3CI9Grj15fx2GA?e=wb4euC"> Mock-up </A></td>
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
    <td> <p> Luis de Villa </p> <p> Area: Business </p> <p> Role: Portfolio Manager </p></td>
  </tr>
</table>
