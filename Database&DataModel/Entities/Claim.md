## Description  
List of all available claims. 
  
## Columns  
| Name               | Type .NET          | Type DB          | Nullable | Description                                              | Notes           |
| ------------------ | ------------------ | ---------------- | -------- | -------------------------------------------------------- | ------------- |
| Id                 | Guid               | uniqueidentifier | ❌        | Id                                                                         |
| Name               | string             | nvarchar(64)     | ❌        | Unique claim name                                        |                 |
| ValueType          | [[ClaimValueType]] | nvarchar(16)     | ❌        | Type of claim value. Needed for auto parser        Default: bool bool bool |
| DefaultValue       | string             | nvarchar(128)    | ❌        | Default value when assign the claim to any role o                          |
| ==[[BaseEntity]]== | --                 | --               | --       | Columns inherited from [[BaseEntity]] class.                               |
  
## Relationships  

## Indexes  
* IX_Claims_Name (Unique)
## Notes  
* Later: add automatic seed at app start (with reflection, checking by values of custom attributes)
* Next phase add handling of many types (at first phase it's only bool and entities [[RoleClaim]] and [[UserClaim]] doesn't contain Value property/column)