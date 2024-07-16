---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-02 </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Research </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> Luis Cárdenas</td>
  </tr>
    <tr>
    <td> Requester area </td>
    <td> Research </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Fractal 0 CAGR Method </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> May 28, 2024 </td>
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
    <td> A CAGR-based model needs to be developed to rank investment strategies by historical performance in order to identify long-term trends and short-term seasonal changes. </td>
    <td> Since it is required to rank investment strategies, the best performing strategies should be obtained when calculating cumulative CAGR and Rolling.</td>
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
    <td> The analyzed data will be open to any time series required. </td>
  </tr>
  <tr> 
    <td> PC2 </td>
    <td> A T2 delay is considered. </td>
  </tr>
  <tr>
    <td> PC3 </td>
    <td> Scalability was not assumed, i.e. the capacity of the strategy was not considered. </td>
  </tr>
 <tr>
  <td> PC4 </td>
  <td> No broker fees were considered.</td>
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
    <td> <p>Starting from the time series to be analyzed, 2 rankings should be made using the CAGR variable:</p> <p> 1.Cumulative CAGR: All data available so far should be considered. </p> <p> 2.CAGR Rolling: Rolling windows shall be considered at a certain variable size (the size of the window shall be considered as input).</p> </td>
  </tr>
  <tr>
     <td> BR2 </td>
     <td> <p> The amount available should be split between the two methods, i.e. X% of the total amount should be allocated to Cumulative CAGR and 1-X% to Rolling CAGR.</p> <p>Note: The percentage to be allocated to each method should be considered as a variable input respecting that the sum of both should give 100% of the amount available. </p> </td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> <p>Once both rankings are available, the selection of the required top should be made, considering that it must have a minimum of one top two in each ranking. </p> <p>The number of top should be considered as a variable input and may be different for Cumulative CAGR and Rolling CAGR.</p> </td>
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p> Having selected the top, the allocation should be assigned with equal weights (EW). </p> <p> Example:</p> <p>If for Cumulative CAGR you have a top 4, then an allocation of 25% will be assigned to each selected strategy.</p> <p>Note: A strategy can be selected by both methods.</p> </td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> The calculation shall be made on a daily basis, considering a T2 delay.  </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> The rebalancing deadline shall be considered as a variable input. </td>
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
    <td> Framework </td>
    <td> <A HREF="https://tequilacapital.sharepoint.com/:w:/s/TequilaCapital/EbppGyyo04pAnoaOm9sDiokBvufkYwpTinIDgmAn3HjHlg?e=59M1Qf"> Framework Fractal 0 </A> </td>
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
    <td> <p> Luis Cárdenas </p> <p> Area: Research </p> <p> Role: Portfolio Manager </p></td>
  </tr>
</table>



 
