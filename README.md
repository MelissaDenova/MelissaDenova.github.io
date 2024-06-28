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
    <td> Alternative data Dashboard </td>
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
    <td> It is required to implement a dashboard focused on alternative data in order to be able to compare different sectors with respect to Market Cap and Equal Weight. </td>
    <td> <p> Given that visibility is required for certain sectors with respect to Market Cap and Equal weight, when the user enters the eligible universe to be used, the dashboard should display the following data: </p> <p> 1. Table showing the summary of how much companies paid at certain periods, by Market Cap and by Equal Weight in each sector. </p> <p> 2. The difference between the percentage obtained in Market Cap minus Equal weight. </p> <p> 3. A graph showing the difference obtained in point 2. </p> </td>
    <td> BR1, BR2, BR3, BR4, BR5, BR6, BR7, BR8 </td>
  </tr>
  <tr>
    <td> FR2 </td>
    <td> A dashboard needs to be implemented in order to measure, on any given date, certain statistical values for a list of tickers or ETFs. </td>
    <td> <p> Since it is required to display statistical information of tickers over a certain period of time, when the user enters the eligible universe of tickers or ETFs and the date from which the statistics are required to be reviewed, the following data should be displayed: </p> <p> 1. Historical Percentile - Momentum (3M, 6M) over SPY.  </p> <p> 2. Average </p> <p> 3. Deviation </p> <p> 4. Relative (Index) vs Absolute Momentum. </p> </td>
    <td> BR9, BR10, BR11, BR12, BR13 </td>
  </tr>
  <tr>
    <td> FR3 </td>
    <td> A dashboard needs to be developed in order to measure at any given date, certain statistical values for a list of strategies. </td>
    <td> <p> Since it is required to visualise statistical information of strategies in a certain period of time, when the user enters the universe of strategies and the date from which the statistics are required to be reviewed, the following data should be displayed: </p> <p> 1.Historical Percentile - Momentum (3M, 6M) over Index.  </p> <p> 2.Average </p> <p> 3.Deviation </p> <p> 4.YTD </p> <p> 5.Absolute Momentum </p></td>
    <td> BR14, BR15, BR16, BR17, BR18, BR19  </td>
  </tr>
  <tr>
    <td> FR4 </td>
    <td> A dashboard needs to be developed in order to be able to visualize the returns to N days that industries have had. </td>
    <td> <p> Since it is required to visualize the returns that the industries have had, when the user enters the number of days for which the information is required, the system should display the following data: </p> <p> 1. A table with the returns on the requested days and the average value of these values. </p> <p> 2. A graph showing each industry vs. its TRR at n days. </p> </td>
    <td> BR20, BR21, BR22 </td>
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
    <td> <p> The input data for the dashboard views shall be as follows: </p> <p> 1. Eligible universe of tickers, ETFs or strategies.</p><p> 2.Periods to be considered for the calculation.</p> <p> 3.For RF2 and RF3, the variable input will be the index to be used (considering that the daily composition of the chosen index must be taken into account). </p> </td>
  </tr>
  <tr> 
    <td> PC2 </td>
    <td> <p> The input data for the dashboard view in the Industries section will be as follows: </p> <p> 1.Number of days over which the TRR calculation is required. </p> </td>
  </tr>
</table>

### 4. BUSINESS RULES
<table>
  <tr>
    <td> ID BR </td>
    <td> Business rule </td>
  </tr>
  <tr> 
    <td colspan="2"> Market Cap and Equal Weight </td>
  </tr>
  <tr>
    <td> BR1 </td>
    <td> With an eligible universe of tickers as input, the classification of tickers by sector and industry should be performed. </td>
  </tr>
  <tr>
     <td> BR2 </td>
     <td> The n-day returns should be calculated (the number of days will be a variable input). </td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> <p> A calculation should be made of how much the companies weigh in their sector by Market Cap and Equal Weight. </p> <p> Example:</p> <p> For Market Cap </p> <p>The sum of the Market Cap value of all the companies belonging to the same sector is added up, and once this sum is obtained, the Market Cap value of each company is divided by the sum of the sum. </p> <table> <tr> <td> ID </td> <td> Market Cap </td> <td> Sector </td> <td> Sector Weight Mkt Cap </td> <td> Sector Equal Weight </td></tr> <tr> <td>MSFT US Equity</td> <td>3,096,001</td> <td>Information Technology</td> <td>23% </td> <td> 1.54% </td></tr> <tr> <td>AAPL US Equity</td> <td> 2,874,067</td> <td> Information Technology </td> <td> 21% </td> <td> 1.54% </td></tr> <tr> <td>NVDA US Equity</td> <td> 2,247,206 </td> <td> Information Technology </td> <td> 17% </td> <td>1.54% </td></tr> <tr> <td> ... </td> <td> N </td> <td> Information Technology </td> <td> ... </td> <td> ... </td></tr> </table> <p> Total Market Cap = $13,477,568 </p> <p>MSFT US Equity = 3,096,001 / 13, 477,568 = 0.23 </p> <p> AAPL US Equity = 2,874,067 / 13, 477,568 = 0.21 </p> <p>NVDA US Equity = 2,247,206 / 13, 477,568 = 0.17</p> <p> For Equal weight: </p> <p> Weights are divided proportionally among all tickers in the sector. </p></td> 
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p>The calculation of how much the companies weigh in their industry by Market Cap and Equal Weight should be done.</p> <p> Example </p> <p>For Mkt Cap:</p> <p> The sum of the Market Cap value of all the companies belonging to the same industry is added up. Once this sum is obtained, the Market Cap value of each company is divided by the sum value.</p> <table> <tr> <td> ID </td> <td> Market Cap </td> <td> Industry </td> <td>Industry Weight Mkt Cap</td> <td> Industry weight EW </td></tr> <tr> <td> MSFT US Equity </td> <td>3,096,001</td> <td> Software </td> <td> 65% </td> <td> 5.88% </td></tr> <tr> <td>CRM US Equity</td> <td> 268,496 </td> <td> Software </td> <td> 6%</td> <td> 5.88% </td></tr> <tr> <td> ADBE US Equity </td> <td> 213,226 </td> <td> Software </td><td> 4% </td> <td> 5.88% </td></tr> <tr> <td> ... </td> <td> N </td> <td> Software </td> <td> ... </td> <td> ... </td></tr></table> <p> Total Marker Cap = $4,763,318</p> <p>MSFT US Equity = 3,096,001 / 4,763,318 = 0.65 </p> <p> AAPL US Equity = 268,496 / 4,763,318 = 0.06 </p> <p> NVDA US Equity = 213,226 / 4,763,318 = 0.04 </p> <p> For Equal weight: </p> <p> Weights are divided proportionally among all tickers in the industry. </p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> <p> Statistics should be calculated for different time periods to find out how much each of the companies paid, multiplied by how much they weigh in the sector. </p> <p> Note: Each deadline will be a variable input, associated to the RN2 of this document. </p> <p> Example: </p> <table> <tr> <td> Company </td> <td> TRR 30D </td> <td>Sector Weight Mkt Cap </td> <td> Sector Weight EW </td></tr> <tr> <td>MSFT US Equity </td> <td> -1.27%</td> <td> 23% </td> <td> 1.54% </td></tr> <tr> <td> AAPL US Equity </td> <td> 6.31% </td> <td> 21% </td> <td> 1.54% </td></tr> <tr> <td>NVDA US Equity </td> <td> 3.59% </td> <td> 17% </td> <td> 1.54% </td></tr> </table> <p>The TRR at the required term is multiplied by the weight obtained for each company in the sector to which it belongs. </p> <p>For Market Cap:</p> <p>MSFT US Equity = -1.27% * 23% = -0.29% </p> <p>AAPL US Equity = 6.31% * 21% = 1.35%</p> <p> NVDA US Equity = 3.59% * 17% = 0.60%</p> <p>For Equal Weight:</p> <p> MSFT US Equity = -1.27% * 1.54% = -0.02% </p> <p> AAPL US Equity = 6.31% * 1.54% = 0.10% </p> <p> NVDA US Equity = 3.59% * 1.54% = 0.06% </p> <table> <tr> <td> </td> <td> Information Technology </td> <td> Information technology </td></tr> <tr> <td> </td> <td> Market Cap </td> <td> Equal Weight </td></tr> <tr> <td> </td> <td> Contr to Sector </td> <td> Contor to Sector</td></tr> <tr> <td>MSFT US Equity</td> <td> -0.29% </td> <td> -0.02% </td> </tr> <tr> <td> AAPL US Equity </td> <td> 1.35% </td> <td> 0.10% </td></tr> <tr> <td> NVDA US Equity</td> <td>0.60%</td> <td>0.06%</td></tr> </table> </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> <p> Once the values of the RN5 have been obtained, the summary of each of the sectors for the different time periods considered, both Mark Cap and Equal Weight, must be visualised in a table.</p> <p>Example</p> <p>All the values obtained in the RN5 are added up by sector and the results are presented in a summary table.</p> </td>
  </tr>
  <tr>
    <td> BR7 </td>
    <td> <p>A table showing the difference between the values obtained by Market Cap and those obtained by Equal Weight should be displayed.</p> <p> Example: </p> <p>The value obtained by Market Cap is subtracted from that obtained by Equal Weight for each sector for each TRR period considered.</p> <p> Information Technology </p> <p> TRR 30D = 2.13% - 1.14% = 0.99% </p> <p>TRR 60D = 3.01% - 0.96% = 2.05% </p> <p>TRR 90D = 5.69% - 1.91% = 3.78% </p> <p> TRR 180D = 25.19% - 20.65% = 4.54% </p> <p>TRR 360D = 59.71% - 38.31% = 21.40% </p> </td>
  </tr>
  <tr>
    <td> BR8 </td>
    <td> <p> A graph should be generated showing how much companies have paid for Market Cap on Equal Weight. </p> <p> Example: </p> <p> The result obtained in BR7 are graphed. </p> </td>
  </tr>
  <tr> 
    <td colspan="2"> Ticker or ETF statistics </td>
  </tr>
  <tr>
    <td> BR9 </td>
    <td>  </td>
  </tr>
  <tr>
    <td> BR10 </td>
    <td> <p>The average historical percentile value shall be calculated for each ticker.</p> <p> Example: </p> <p> For the calculation of the average, it is considered from 01/07/2013 to the present. </p> </td>
  </tr>
  <tr> 
    <td> BR11 </td>
    <td> <p> The difference between the value obtained in the percentile minus the value obtained in the average shall be calculated. </p> <p> Example: </p> <table> <tr> <td> Ticker </td> <td> Historical Percentil</td> <td> Average </td> <td> Deviation </td></tr> <tr> <td>Healthcare EW </td> <td> 14.80% </td> <td> 40.13% </td> <td> -25.33% </td></tr> <tr> <td> Financials EW </td> <td> 21.90% </td> <td> 42.72% </td> <td> -20.82% </td></tr> <tr> <td> Cons Disc EW </td> <td> 0.40% </td> <td> 39.25% </td> <td> -38.85% </td></tr> </table> <p>Healthcare EW = 14.80% – 40.13% = -25.33%</p> <p>Financials EW = 21.90% - 42.72% = -20.82% </p> <p>Cons Disc EW = 0.40% - 39.25% = -38.85%</p> </td>
  </tr>
  <tr>
    <td> BR12 </td>
    <td> x </td>
  </tr>
  <tr>
    <td> BR13 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR14 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR15 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR16 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR17 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR18 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR19 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR20 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR21 </td>
    <td> x </td>
  </tr>
   <tr>
    <td> BR22 </td>
    <td> x </td>
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

### 7.2 BACKTESTING ASSUMPTIONS
* <p> x </p>
* <p> x </p>

### 8. RESTRICTIONS TO BE CONSIDERED
<p align="justify"> The needs and requirement requests for the development area are defined in the ‘Software Requirements Specification (SRS)’ document that corresponds to the scope requested by the business areas, in case of an adjustment, a change control and redefinition of the work schedule will be carried out. </p>

### 8.1 BACKTESTING RESTRICTIONS
* <p> x </p>
* <p> x </p>
* <p> x </p>
* <p> x </p>

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
    <td> <p> Fidel Selva </p> <p> Area: Research </p> <p> Role: Quant </p></td>
  </tr>
</table>
