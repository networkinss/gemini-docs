# Interfaces

Interfaces are used to describe common entity fields and of course an Entity can implement one or more interfaces.

For example the CORE module automatically create the DOMAIN Interface \(take a look at Core.at in the repository\) that is a simple entity composed by a code and a description. A lot of core entities implements this interface.

```text
INTERFACE Domain {
    TEXT            code  *
    TEXT		    description
}

ENTITY SettingsType IMPLEMENTS Domain
```

SettingsType implements Domain so it is an entity that has all the Domain fields and logical key.

{% hint style="danger" %}
**TIP:** INTERFACE CoreMeta  
****is a special interface inherited by all entities.
{% endhint %}



