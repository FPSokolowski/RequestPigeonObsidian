## Description  
Extends table [[Document]]s. It's one of document's types.

## Columns  
| Name                   | Type .NET                                     | Type DB                    | Nullable | Description                                                                                               | Notes                                                                                                                                              |
| ---------------------- | --------------------------------------------- | -------------------------- | :------: | :-------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| DocumentId             | *This class implements abstract [[Document]]* | uniqueIdentifier           |    ❌     | For SQL DB it's a separate table. At .NET side it's a class inherits from an abstract [[Document]] class. | *Relationship with Document (core entity).* **TPT**                                                                                                |
| PlannedPurchaseDueDate | DateOnly                                      | date                       |    ✔     | Planned due date of a purchase                                                                            |                                                                                                                                                    |
| PlannedEstimatedCost   | decimal                                       | decimal(12,2)              |    ❌     | Estimated cost                                                                                            |                                                                                                                                                    |
| RealPurchaseDate       | DateOnly                                      | date                       |    ✔     | Final date of a purchase event                                                                            | Allow assign after positive acceptance                                                                                                             |
| RealCost               | decimal                                       | decimal(12,2)              |    ✔     | Final real cost                                                                                           | Allow assign after positive acceptance                                                                                                             |
| AccountantsRecorded    | bool                                          | bit                        |    ❌     | Marked as closed by accountants. It blocks modify/add attachments.                                        | Default: FALSE. Change is possible after positive acceptance (and it starts to be visible for accountants). It can be changed only by accountants. |
| ExpensesType           | [[ExpensesType]]                              | `=[[ExpensesType]].dbType` |    ❌     | Expenses category                                                                                         |                                                                                                                                                    |

## Relationships  
- One-to-one with [[Document]]
## Indexes  
- IX_Document_ExpensesType
  
## Notes  
* Allow assign attachments after positive acceptance
* AccountantsRecorded locks any modifications (also adding attachments)
* Future: add currency and exchange rate to base currency
* Future: Budgets