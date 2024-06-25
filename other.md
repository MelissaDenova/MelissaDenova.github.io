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
    <td> <p> Having as input a list of tickers, and the average volume at "n" days of those tickers, the calculation of the maximum tradable amount shall be performed, considering the rule of trading only the established percentage of the total value. (The percentage shall be considered as a variable input).</p> <p> &#160; &#160; &#160; Example. </p> <p> &#160; &#160; &#160; For this example, 30 days and a maximum trading percentage of 8% are considered </p> <table> <tr> <td> TICKER DATA </td> <td> VOLUMEN AVG 30D </td> <td> 8% DEL AVG VOLUME </td> </tr> <tr> <td> ACCD US Equity </td> <td> $5,074,957.29 </td> <td>$405,996.58 </td> </tr> <tr> <td> ACMR US Equity </td> <td> $59,834,022.85 </td> <td> $4,786,721.83 </td></tr> <tr> <td> ADCT US Equity</td> <td>$   2,801,423.83 </td> <td> $224,113.91</td> </tr></table> <p>  &#160; &#160; &#160; ACCD US Equity = 5074957.29 (0.08) = 405996.58 </p> <p>  &#160; &#160; &#160; ACMR US Equity = 59834022.85 (0.08) = 4786721.83 </p> <p>  &#160; &#160; &#160; ADCT US Equity = 2801423.83 (0.08) = 224113.91 </p> </td> 
  </tr>
  <tr>
     <td> BR2 </td>
     <td> The values resulting from the log must be persisted in a file or table exclusively accessible by the service administrator user. </td>
  </tr>
  <tr>
     <td> BR3 </td> 
     <td> The records shall be unalterable. </td>
  </tr>
  <tr>
    <td> BR4 </td>
    <td> A log shall be kept of the actions that the system automatically performs. </td>
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
    <td> The system shall be protected against unauthorised access. </td>
    <td> Titania, Data, Builder, Account manager, Excel AddIn, APIs. </td>
  </tr>
  <tr>
    <td> NFR2 </td>
    <td> The service shall support n number of registrations without compromising performance. </td>
    <td> Titania, Data, Builder, Account manager, Excel AddIn, APIs. </td>
  </tr>
  <tr>
    <td> NFR3 </td>
    <td> The records generated should be durable, they can be archived but not deleted. </td>
    <td> Titania, Data, Builder, Account manager, Excel AddIn, APIs. </td>
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
    <td> Julio Pérez </td>
    <td> Backend Team leader </td>
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