### 1. GENERAL DETAILS OF THE REQUEST
|Need ID                   |REQ-2024Q1-06 Audit Log |
|------------------------- |------------------------|
|Classification            |Business                |
|Requester                 |José Ángel Reyes        |
|Requesting area           |Management              |
|Name of the requirement   |Audit Log               |
|Date of request           |May 08, 2024            |
|Receiver                  |Eddy Zavaleta           |

### 2. LIST OF FUNCTIONAL REQUIREMENTS
| Request ID | Request | Acceptance criteria | Associated BR|
|:----------:|---------|---------------------|:------------:|
|FR1|Create a service that registers the actions that each user performs within the Titania application.|Since it is required to have a log of the activities that users perform within Titania, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|
|FR2| Create a service that registers the actions that each user performs within the Data application.|Since it is required to have a log of the activities that users perform within Titania, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|
|FR3| Create a service that registers the actions that each user performs within the Builder application.|Since it is required to have a log of the activities that users perform within Builder, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|
|FR4| Create a service that registers the actions that each user performs within the Account Manager application.|Since it is required to have a log of the activities that users perform within Account Manager, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|
|FR5| Create a service that registers the actions that each user performs within the Excel AddIn application.|Since it is required to have a log of the activities that users perform within Excel AddIn, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|
|FR6| Create a service that registers the actions that each user performs within the APIs application.|Since it is required to have a log of the activities that users perform within APIs, when the system administrator profile enters to query information about the logs, then the system shall allow the system administrator profile to view the following data:  ID event, Date time, IP, User, Action, Data/info, Applicative. |BR1, BR2|

### 3. PRECONDITIONS
|ID PC  |Preconditions|
|:-----:|:-----------:|
| NA    | NA          |

### 4. BUSINESS RULES
|BR ID   |Business rule |
|:------:|--------------|
|BR1| <p> For auditing purposes, the following data must be saved for each action performed by a given user within the applications used in Tequila Capital:</p> <p> &#160; &#160; &#160; * ID event: Event number indicator. </p> <p> &#160; &#160; &#160; * Date time: Date - time at which the event occurs. </p> <p> &#160; &#160; &#160; * IP: IP of the device the user is logging in from.</p> <p> &#160; &#160; &#160; * User: User logging in. </p> <p> &#160; &#160; &#160; * Action: It states the activity that the user performs. </p> <p> &#160; &#160; &#160; * Data/ info: Describes the changes that the user makes within the application, showing the previous value and the new value. </p> <p> &#160; &#160; &#160; * Applicative: Within Tequila Capital, the following applications are available: Titania, Data, Builder, Account Manager, Excel AddIn y APIs, it shall be recorded in which of them the event carried out by a user generates impact. </p>|
|BR2| The values resulting from the log must be persisted in a file or table exclusively accessible by the service administrator user.|
|BR3| The records shall be unalterable.|
|BR4| A log shall be kept of the actions that the system automatically performs.| 

### 5. LIST OF NON - FUNCTIONAL REQUIREMENTS
|NFR ID |Non - Functional requirements |Module / System | 
|:-----:|------------------------------|----------------|
|NFR1|The system shall be protected against unauthorised access.|Titania, Data, Builder, Account manager, Excel AddIn, APIs.|                              
|NFR2|The service shall support n number of registrations without compromising performance.|Titania, Data, Builder, Account manager, Excel AddIn, APIs.|
|NFR3|The records generated should be durable, they can be archived but not deleted.|Titania, Data, Builder, Account manager, Excel AddIn, APIs.|

### 6. DEVELOPMENT OFFICERS
|Name |Rol |
|-----|----|
|Eddy Zavaleta| Manager|
|Julio Pérez| Backend Team leader|
|Luis Fábregas| QA team leader|

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
|Term |Definition |
|-----|-----------|
|FR | Functional Requirement.|
|BR | Regla de negocio.|
|PC | Precondiciones.| 
|NFR| Non - Functional Requirement.|

### 11. APPENDICES
|Name of document |Document path | 
|-----------------|--------------|         
|NA |NA |      

