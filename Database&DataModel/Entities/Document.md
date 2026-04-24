## Description  
Represents a core of any request document. 
Approach TPT. This table represents common part of any document type. Each document consist of data from tables Document and Document{Type}. 
First phase there will be few types handle: Leave, Refund, Purchase, BusinessTrip, Credentials.
  
## Columns  
| Name               | Type .NET            | Type DB                                              | Nullable | Description                                                                                                           | Notes                                           |
| ------------------ | -------------------- | ---------------------------------------------------- | :------: | :-------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| Id                 | Guid                 | uniqueidentifier                                     |    ❌     | Primary key                                                                                                           | PK                                              |
| DateTime           | DateTime             | datetime2(0)                                         |    ❌     | Date time issued (official, visible at the document)                                                                  |                                                 |
| Type               | [[DocumentTypeInfo]] | `= [[Database&DataModel/Enums/DocumentType]].dbType` |    ❌     | At .NET side it's a class which contains DocumentType DocumentType, string Header and string Description              | Needs conversion based on enum [[DocumentType]] |
| Status             | [[DocumentStatus]]   | `= [[DocumentStatus]].dbType`                        |    ❌     | Status of the document                                                                                                |                                                 |
| Priority           | [[DocumentPriority]] | `= [[DocumentPriority]].dbType`                      |    ❌     | Priority of the document                                                                                              |                                                 |
| TextContent        | string               | nvarchar(2048)                                       |    ✔     | Optional text (specification / explaination / reason / purpose / additional notes)                                    |                                                 |
| TextMessage        | string               | nvarchar(1024)                                       |    ✔     | It's just a note. Not visible at document but sent with it as a sticky note additional informal message to acceptors. |                                                 |
| RequestorId        | [[User]]             | uniqueidentifier                                     |    ❌     | User-requestor                                                                                                        | FK                                              |
| Acceptances        | List<[[Acceptance]]> | --                                                   |    ❌     | Assigned decision-makers with decision data.                                                                          | *relationship (separate table with FKs)*        |
| ==[[BaseEntity]]== | --                   | --                                                   |    --    | Columns inherited from [[BaseEntity]] class.                                                                          | --                                              |
  
## Relationships  
- Many-to-one with [[User]] (as Requestor)
- Many-to-many with [[Acceptance]] (separate [[DocumentAcceptance]] FK's table)
## Indexes  
- IX_Document_Type 
- IX_Document_DateTime
- IX_Document_Type_Status
  
## Notes  
* Settings for document Types are located in table [[DocumentSettings]]. Setting data should be cached.