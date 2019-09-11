# Entity Reference

Each defined Entity \(with a logical key\) is itself a Gemini Type that you can use in other entities to create a relation between entities.

{% hint style="success" %}
**Entity References validation is provided by Gemini out of the box**

In the following example: if you create a **Post** entity record Gemini automatically check if the provided **Tag** exists. 
{% endhint %}

```text
ENTITY Tag {
    TEXT    name    *
    TEXT    description
}

# Tag is a type that we can use in the Post Entity

ENTITY Post {
    LONG postId *
    TEXT message
    Tag  tag
}
```

## API Examples

First of all we need at least one tag.

```bash
$ curl -H "Content-Type: application/json" -X POST http://127.0.0.1:8090/api/tag -i -d '{"name":"italy","description":"We ❤️ Italy"}'

#    HTTP/1.1 200
#    Content-Type: application/json;charset=UTF-8
#
#    {"name":"italy","description":"We ❤️ Italy"}
```

To insert the POST only the logical key of Tag is required.

```bash
$ curl -H "Content-Type: application/json" -X POST http://127.0.0.1:8090/api/post -i -d '{"postid":1,"message":"Rome", "tag": "italy"}'

#    HTTP/1.1 200
#    Content-Type: application/json;charset=UTF-8
#
#    {"tag":"italy","postId":1,"message":"Rome"}
```

**API Example - Post with unknown Tag**

{% hint style="danger" %}
What if we try to insert a Post with an unknown tag?

404  Not found error!!!
{% endhint %}

```bash
$ curl -H "Content-Type: application/json" -X POST http://127.0.0.1:8090/api/post -i -d '{"postid":2,"message":"Rome", "tag": "unknown"}'

# HTTP/1.1 404
```

