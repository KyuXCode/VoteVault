# Domain Model
![DomainModelDiagram](../AuxiliaryFiles/Documents/DomainModelDiagram.png)
## Domain Model Explanation
- User
  - User is an abstract class that is the super class for Admin because Admin shares all properties. User also has access to edit parts of the database through CRUD function calls. 
- Admin
  - Admin inherits the User class and also has the ability to manage other users.
- Database Entity
  - County
  - Contract
  - Certification
  -  Vendor
  -  Inventory Unit
  -  Expense
  -  Component
  -  Storage Location
  -  Disposition
