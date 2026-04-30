## Description  
Document's attachments.
## Columns  
| Name        | Type .NET | Type DB          | Nullable | Description           | Notes                        |
| ----------- | --------- | ---------------- | :------: | :-------------------- | ---------------------------- |
| DocumentId  | Guid      | uniqueIdentifier |    ❌     |                       | FK                           |
| Name        | string    | nvarchar(128)    |    ❌     | Name                  |                              |
| Description | string    | nvarchar(1024)   |    ✔     | Optional description  |                              |
| Content     | byte[]    | varbinary(max)   |    ❌     | Content (image / pdf) | *MaxLength(5 * 1024 * 1024)* |

## Relationships  
- One-to-many with [[Document]]
## Indexes  

## Notes  
