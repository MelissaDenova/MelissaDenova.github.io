---
layout: default
---

[back](./)

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q2-04 </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Research </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> Fidel Selva </td>
  </tr>
    <tr>
    <td> Requester area </td>
    <td> Research </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Smart Markowitz </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> June 07, 2024 </td>
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
    <td> A method needs to be implemented to estimate expected values for future asset or strategy returns based on current Momentum and Volatility scenarios. </td>
    <td> Since it is required to implement a method for estimating expected values for future returns, when the user enters the parameters to be used, then the system should display the daily predictions per strategy and the realized performance of the strategy that shows statistically significant predictive power for monthly returns. </td>
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
    <td> The universe to be used will be a variable input </td>
  </tr>
  <tr> 
    <td> PC2 </td>
    <td> The vector of weights may not contain negative values to avoid short sales. </td>
  </tr>
  <tr> 
    <td> PC3 </td>
    <td> <p> The variables analyzed will be:</p> <p> &#160; &#160; &#160; *Daily returns time series </p> <p> &#160; &#160; &#160; *Closing price of each stock </p> <p> &#160; &#160; &#160; *MA (21)</p> <p> &#160; &#160; &#160; *MA (63) </p> <p> &#160; &#160; &#160; * MA(252) </p> <p> &#160; &#160; &#160; * Std (21)</p> <p> &#160; &#160; &#160; *Std (63) </p> <p> &#160; &#160; &#160; *Std (252) </p> <p> &#160; &#160; &#160; *Expected holding period </p> </td>
  </tr>
   <tr> 
    <td> PC4 </td>
    <td> All inputs must be calculated with Log. </td>
  </tr>
   <tr> 
    <td> PC5 </td>
    <td> One year should be considered for initial training. </td>
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
    <td> Each strategy TRR should be transformed into log returns by applying log (TRR / lag (TRR)). </td>
  </tr>
    <tr>
     <td> BR2 </td>
     <td> The sample mean and variance should be calculated at 21, 63 and 152 days.  </td>
  </tr>
  <tr>
     <td> BR3 </td>
     <td> The square root of the variance shall be calculated. </td>
  </tr>
  <tr>
     <td> BR4 </td> 
     <td> <p> For each strategy a sklearn SNN object with dense layer sizes 36 and 2, activation of ReLU should be made, ie, sklearn.neural_network. MLPRegressor ((36,2)). </p> <p> Note: In addition to ReLu, activation functions should be considered:  <p>  &#160; &#160; &#160; *Hyperbolic tangent </p> <p>  &#160; &#160; &#160; *Logistic </p></td>
  </tr>
  <tr>
    <td> BR5 </td>
    <td> For each strategy the SNN should be adjusted with one year of initialization data using X = Shift21 (MA21, MA63, MA252, Std21, Std63, Std252) and y = MA21. </td>
  </tr>
  <tr>
    <td> BR6 </td>
    <td> For each trading day, base data shall be received and transformed up to today's date. </td>
  </tr>
  <tr>
    <td> BR7 </td>
    <td> For each trading day, a partial adjustment shall be made to the TRR object for each strategy using the new data, i.e. SNN.partial_fit(X,y). </td>
  </tr>
   <tr>
    <td> BR8 </td>
    <td> For each trading day the TRR object shall be evaluated for the current day's data with SNN.predict(X).  </td>
  </tr>
   <tr>
    <td> BR9 </td>
    <td> For each trading day, a vector of expected logarithmic returns should be filled in. </td>
  </tr>
   <tr>
    <td> BR10 </td>
    <td> <p> Markowitz optimization should be applied for the allocation of allocations, using the newly calculated expected returns. </p> <p> Note: The Markowitz model will be applied on strategies and ETFs and the following restriction must be considered: </p> <p> Strategies = Maximum of 20% allocation. </p> <p> ETFs = 100% allocation </p> </td>
  </tr>
   <tr>
    <td> BR11 </td>
    <td> <p> Node parameters shall be equipped with lbfgs in case the trigger is ReLu.</p> <p> Note: Any optimizer can be considered when using the hyperbolic and logistic tangent activator. </p> </td>
  </tr>
   <tr>
    <td> BR12 </td>
    <td> <p> Net weights shall be equipped with lbfgs in case the trigger is ReLu. </p> <p> Note: Any optimizer can be considered when using the hyperbolic and logistic tangent activator. </p>  </td>
  </tr>
   <tr>
    <td> BR13 </td>
    <td> The network architecture shall have a 1 e-4 L2 regularization. </td>
  </tr>
</table>

### 5. LIST OF NON - FUNCTIONAL REQUIREMENTS
<table>
  <tr>
    <td> NFR ID </td>
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
    <td> <p> José Ángel Reyes </p> <p> Area: Management </p> <p> Role: Director </p></td>
  </tr>
</table>

