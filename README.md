# BabySitter-Requester-App

## NextGen final project BabySitter Requester Application

3/21/2024 by *@ShuLiu*

Used **App Engine Studio** (Studio, both are transferable) tp develop our final project BabySitter Requester.

**Data**- BabySitter Requster table extends from **Task** table. Added new fields: 

  | Label  | Type        |  
  |:----------|:----------|  
  |Requester| Reference(sys_user)|  
  |Start Date/Time| Date/Time |  
  |End Date/Time | Date/TIme |  
  |Children Number| Integer|  
  |Children Age | String|
  |...|...|

**Roles**
- babysitter, 
- manager
- requester

**Group**
- BabySitter Group
- BabySitters
- BabySitter Managers
- BabySitter Requesters
  
**Best practice, always add roles to the group, then and user to the group to inherit roles**

**Flows**-

- **New request created** - requester uses *Self Service > Service Catalog >Can we help you>BabySitter Requester* or Application Menu *BabySitter Requester > New Request* to create new babysitting request through record producer.requester receives confirmation email.
- **Assign babysitter** - manager receives notification and assign a babysitter to the request. The assigned babysitter gets email notification for the new assignment.
- **Service fullfilled**- After request being fulfilled, babysitter set the request to *completed*. requester gets email asking for feedback.
- **Cancellation**-The manager can cancel the request upon requester's request. 

**UI policy/action** and **Client Scripts**, **Business Rules** was created to validate data and keep data consisdence. e.g. *Start Date/Time* must after submission time and before *End Date/Time*. When insert, update records business rules will take place.

**Flows**,**Scripts** and **Business rules** helped keep improve bussiness process efficiency and automation, prevents data inconsistency.

**View**
This application provides different list view and form view based on different roles, which helps keep data security. 

**Follow/DIscuss**
Requesters, manager, and babysitter can follow/discuss the request during the whole process, which provides convenent and direct communication to keep the process clear and transparent. 
