---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-10 </td>
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
    <td> Base Strategies </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> June 25, 2024 </td>
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
    <td> A methodology needs to be developed that systematically classifies stocks by large, medium and small market cap in order to generate investment strategies within these categories. </td>
    <td> *<p>Each of the individual groups will adequately represent each sector according to its weight in a particular segment.</p> *<p>Since all stocks can only belong to a single group at any given time, they must provide a particular exposure to the size factor described by Fama and French.(See reference to Fama and French in the Framework document, section Hypotheses).</p> *<p>Since group 1 (large cap) strategies will have a smaller number of stocks, they should better approximate the distributions found in the market cap indices.</p> </td>
    <td> BR1, BR2, BR3, BR4, BR5, BR6, BR7, BR8, BR9</td>
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
    <td> Common stocks, ADRs, NY Reg Shrs and REITs listed in the United States (US Equity Termination) will be considered as the investable universe. </td>
  </tr>
  <tr> 
    <td> PC2 </td>
    <td> <p>The data that will be needed for the implementation of the model will be: </p> *<p>Market Cap</p> *<p>AOA (traded volume)</p> *<p>Sector and industry data</p> <p>Note: All data for the model layout was taken exactly as downloaded from Excel AddIn.</p> </td>
  </tr>
  <tr>
    <td> PC3 </td>
    <td> All data shall be displayed in USD. </td>
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
    <td> Business rules RN2 to RN8 shall be implemented and tested as soon as history is available. </td>
  </tr>
  <tr>
     <td> BR2 </td>
     <td> For each trading day, tickers ending in US Equity should be filtered out. </td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> For each trading day, tickers should be filtered by Common stocks, ADRs, NY Reg Shrs and REITs. </td>
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p>For each trading day, all shares shall be ranked according to the Market Cap (Ordinary Ranking). </p> <p>Note: The deciles of this Ordinary Ranking shall be used to decide which tickers belong to a given category.</p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> For each trading day the Market Cap must be above USD 300 million and reduced using the total returns of W500 as of 31 December 2023. </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> <p>Stocks should be classified into 3 groups as follows:</p> <table> <tr> <td> Strategy </td> <td>Decil</td> <td>Group (Size Mkt Cap)</td></tr> <tr><td>Top</td> <td>10%</td> <td>1</td></tr> <tr><td>Mid</td> <td>10% - 40%</td> <td> 2</td></tr> <tr><td>Bottom</td> <td> </td> <td>3</td></tr> </table> <p> 1.Group 1 (Large Cap): Number of eligible tickers multiplied by the relevant decile (to be rounded down to the nearest whole number). </p> <p>Example:</p> <p>If you have 1878 eligible tickers, then 1878 * 10% = 187.</p> <p>Therefore, the first 187 tickers in the list will be Group 1.</p> <p>2.Group 2 (Mid Cap): Number of eligible tickers multiplied by the relevant decile (to be rounded down).</p> <p>Example:</p> <p>If you have 1878 eligible tickers, then 1878 * 40% = 751.</p> <p>Therefore, tickers between the range 188 and 751 will be in group 2.</p> <p>3.Group 3 (Small Cap): The remaining tickers will form Group 3. </p> <p>Example:</p> <p>Tickers 752 to 1878 will be group 3.</p> <p>Note: The parameters for determining the deciles and the number of shares included in each strategy for each group (large, medium, small) were based on scalability and traded volume considerations.</p></td>
  </tr>
  <tr>
    <td> BR7 </td>
    <td> <p>For all three groups, the following six strategies should be implemented as a first test case:</p> *<p>High Momentum </p> *<p>High Volatility</p> *<p>•	High YoY Revenue Growth</p> *<p>Low EV/Sales</p> *<p>High Free Cash Flow / Market Cap</p> *<p>•	High EBIT Margin</p> <p>Note: For later cases, the strategies to be implemented will be parameterizable.</p> </td>
  </tr>
  <tr>
    <td> BR8 </td>
    <td> <p>For each of the strategies, the selection will be carried out as follows as a first test case:</p> <p>In group 1 the top 10 will be selected.</p> <p>In group 2 the top 25 will be selected.</p> <p>In group 3 the top 40 will be selected.</p> <p>Example:</p> <p>When executing each chosen strategy, you will have:</p> <p>1.For High Momentum:  </p> <p> &#160; &#160; &#160; 10 stocks for group 1 </p> <p> &#160; &#160; &#160; 25 stocks for group 2 </p> <p> &#160; &#160; &#160; 40 stocks for group 3 </p> <p> 2.High Volatility </p> &#160; &#160; &#160; 10 stocks for group 1</p> &#160; &#160; &#160; 25 stocks for group 2 </p> &#160; &#160; &#160; 40 stocks for group 3 </p> <p>Note: For later cases, the number of top will be a parameterizable value.</p> </td>
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
* <p> Trading volume: Generally speaking, it is true that traded volumes are always higher in large Market Cap stocks. (The higher the Market Cap, on average, there is always a relationship with traded volume, given this there may be smaller tops in the larger group). </p>
* <p> Sector distribution: Ideally, all sectors should be represented in all three groups. Ideally, the minimum number of tickers in each strategy should never exceed a certain percentage of the available number of tickers in each category. This is to ensure that most strategies are fully reversed at any given time. </p>

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
    <td> <A HREF="https://tequilacapital.sharepoint.com/:w:/s/TequilaCapital/EUxMZPi-yuVIpgh2MGMOdzkBI4-uNu0o2NVplg5PFbhqsQ?e=Kna9Dj"> Framework </A> </td>
  </tr>
  <tr>
    <td> Mock-up </td>
    <td> <A HREF="https://tequilacapital.sharepoint.com/:x:/s/TequilaCapital/ESMgBMB9rUJMjh_Ep1nkyBQBj8BQN0aaFRXgYvPEGNQtkQ?e=cSbb9f"> Mock-up </A> </td>
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
