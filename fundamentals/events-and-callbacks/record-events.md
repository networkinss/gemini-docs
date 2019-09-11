# Record Events

Fields Events can be registered to add business logic during the life-cycle of an entity record. 

| Event | Description |
| :--- | :--- |
| OnRecordInserted | Executed after a record is stored by the current transaction. For example it can be useful to create or modify other entity records that are related to the one that triggered the event. |

