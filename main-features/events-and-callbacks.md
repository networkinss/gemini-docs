# Gemini Events

{% hint style="warning" %}
**Under Development.**  
Event types will be added as needed accordingly to the features roadmap.
{% endhint %}

Events are a way to change default behaviors that can be registered with suitable Gemini annotations. Currently Gemini support the following events.

| Event | Description |
| :--- | :--- |
| BeforeInsertField | To add business logic before an Entity Record field is inserted the first time \(CRUD POST methods\) |
| OnUpdateField | Executed each time a field change \(CRUD PUT methods\) |

For example META DATA consists of always available fields that each entity has out of the box. So to compute the insertion and modification date the following Events are added to the META Entity \(that is a special Gemini Core Interface\).

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



