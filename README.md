## SOFTWARE REQUIREMENTS SPECIFICATIONS (SRS)
<ul>
<li><a href="https://github.com/MelissaDenova/MelissaDenova.github.io/blob/main/READ2.md">Home</a></li>
<li><a href="#">About</a></li>
<li><a href="#">Services</a></li>
<li><a href="#">Partners</a></li>
<li><a href="#">Contacts</a></li>
</ul>

### 1. GENERAL DETAILS OF THE REQUEST
<table>
  <tr>
    <td> Need Id </td>
    <td> REQ-2024Q1-06 Audit Log </td>
  </tr>
  <tr>
    <td> Classification </td>
    <td> Business </td>
  </tr>
  <tr>
    <td> Requester </td>
    <td> José Ángel Reyes </td>
  </tr>
    <tr>
    <td> Requesting area </td>
    <td> Dirección </td>
  </tr>
    <tr>
    <td> Name of the requirement </td>
    <td> Audit Log </td>
  </tr>
    <tr>
    <td> Date of request </td>
    <td> May 07, 2024 </td>
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
    <td> Create a service that registers the actions that each user performs within the Titania application. </td>
    <td> Since it is required to have a log of the activities that users perform within Titania, when the system administrator profile enters to query 
         information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, 
         User, Action, Data/info, Applicative. </td>
    <td> BR1, BR2 </td>
  </tr>
</table>

### 3. PRECONDITIONS
<table>
  <tr>
    <td> ID PC </td>
    <td> Preconditions </td>
  </tr>
  <tr> 
    <td> NA </td>
    <td> NA </td>
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
    <td> <p> For auditing purposes, the following data must be saved for each action performed by a given user within the applications used in Tequila 
     Capital:</p> <p> &#160; &#160; &#160; * ID event: Event number indicator. </p> <p> &#160; &#160; &#160; * Date time: Date - time at which the event 
     occurs. </p> <p> &#160; &#160; &#160; * IP: IP of the device the user is logging in from.</p> <p> &#160; &#160; &#160; * User: User logging in. </p> 
     <p> &#160; &#160; &#160; * Action: It states the activity that the user performs. </p> <p> &#160; &#160; &#160; * Data/ info: Describes the changes 
     that the user makes within the application, showing the previous value and the new value. </p> <p> &#160; &#160; &#160; * Applicative: Within Tequila 
     Capital, the following applications are available: Titania, Data, Builder, Account Manager, Excel AddIn y APIs, it shall be recorded in which of them 
     the event carried out by a user generates impact. </p> </td>
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

