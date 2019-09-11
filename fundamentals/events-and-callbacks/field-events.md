# Field Events

Fields Events can be registered to add business logic during the life-cycle of a single entity record field.  

| Event | Description |
| :--- | :--- |
| BeforeInsertField | To add business logic before an Entity Record field is inserted the first time \(CRUD POST methods\) |
| OnUpdateField | Executed each time a field change \(CRUD PUT methods\) |

For example META DATA consists of always available fields that each entity has out of the box. To compute the insertion and modification date the following Events are added to the CORE\_META Entity \(that is a special Gemini Core Interface\).

```java
@Events(entityName = Entity.CORE_META, order = -100)
public class CoreMetaEvents {

    @BeforeInsertField(field = "created")
    @BeforeInsertField(field = "modified")
    @OnUpdateField(field = "modified")
    public LocalDateTime transactionDate(EventContext context) {
        if (context.getTransaction().isPresent()) {
            return context.getTransaction().get().getOpenTime();
        }
        return LocalDateTime.now(ZoneOffset.UTC);
    }

}
```

