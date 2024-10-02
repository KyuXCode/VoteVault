# Sample Data / Data Model

## Entities
1. Certification
2. Component
3. Contract
4. County
5. Disposition
6. Expense
7. Inventory Unit
8. Storage Location
9. User
10. Vendor

## Entity Properties

### Certification
| Property Name                | Data Type | Optional | Potential Values                                             |
|------------------------------|-----------|----------|--------------------------------------------------------------|
| Model Number                 | string    |          |                                                              |
| Description                  | string    |          |                                                              |
| Application Date             | Date      |          |                                                              |
| Certification Date           | Date      |          |                                                              |
| Expiration Date              | Date      |          |                                                              |
| Federal Certification Number | string    | yes      |                                                              |
| Federal Certification Date   | Date      | yes      |                                                              |
| Type                         | string    |          | Certification, Reevaluation, Renewal, Recertification, Other |
| Action                       | string    |          | Approved, Pending, Denied, Other                             |
| System Type                  | string    |          | VS, EPB                                                      |
| System Base                  | string    |          | DRE, OpScan, PC/Laptop, Tablet, Custom Hardware, Other       |

### Component
| Property Name | Data Type | Potential Values                                                     |
|---------------|-----------|----------------------------------------------------------------------|
| Name          | string    |                                                                      |
| Description   | string    |                                                                      |
| Type          | string    | DRE, OpScan, BMD, VVPAT, COTS, Other, Hardware, Software, Peripheral |

### Contract
| Property Name | Data Type | Potential Values                |
|---------------|-----------|---------------------------------|
| Begin Date    | Date      |                                 |
| End Date      | Date      |                                 |
| Type          | string    | Purchase, Lease, Service, Other |

### County
| Property Name | Data Type | Potential Values |
|---------------|-----------|------------------|
| Name          | string    |                  |

### Disposition
| Property Name | Data Type | Potential Values |
|---------------|-----------|------------------|
| Date          | Date      |                  |
| Method        | string    |                  |
| Entity        | string    |                  |
| Amount        | float     |                  |

### Expense
| Property Name | Data Type | Potential Values |
|---------------|-----------|------------------|
| Name          | string    |                  |
| Amount        | float     |                  |
| Fund          | string    |                  |
| Owner         | string    |                  |

### Inventory Unit
| Property Name    | Data Type | Potential Values                              |
|------------------|-----------|-----------------------------------------------|
| Serial Number    | string    |                                               |
| Acquisition Date | Date      |                                               |
| Condition        | string    | New, Excellent, Good, Worn, Damaged, Unusable |
| Usage            | string    | Active, Spare, Display, Other, Inactive       |

### Storage Location
| Property Name | Data Type | Potential Values |
|---------------|-----------|------------------|
| Name          | string    |                  |
| Address       | string    |                  |
| City          | string    |                  |
| State         | string    |                  |
| Zip           | string    |                  |

### User
| Property Name    | Data Type | Potential Values     |
|------------------|-----------|----------------------|
| Name             | string    |                      |
| Phone            | string    |                      |
| Email            | string    |                      |
| Username         | string    |                      |
| Supervisor Name  | string    |                      |
| Supervisor Email | string    |                      |
| Organization     | string    | County, State, VSTOP |

### Vendor
| Property Name | Data Type | Optional | Potential Values                  |
|---------------|-----------|----------|-----------------------------------|
| Name          | string    |          |                                   |
| Address       | string    | yes      |                                   |
| City          | string    | yes      |                                   |
| State         | string    | yes      |                                   |
| Zip           | string    | yes      |                                   |
| Contact Name  | string    | yes      |                                   |
| Contact Email | string    | yes      |                                   |
| Contact Phone | string    | yes      |                                   |
| Product       | string    |          | EPB, VS, EPB & VS, Service, Other |