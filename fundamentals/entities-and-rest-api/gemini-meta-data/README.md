# Meta Data

Gemini is Model Driven Framework that automatically calculate and stores a series of **Meta Information** about its entity records.

Each module can store its related information. Currently available meta data are:

| META FIELD | DESCRIPTION | MODULE |
| :--- | :--- | :--- |
| created | creation date | CORE |
| modified | modification date | CORE |
| created\_user | user that create record | AUTH |
| modified\_user | user that modify record | AUTH |
| uuid | [UUID v3](uuid-v3.md) unique for each record | CORE |

Meta information are stored by the **Gemini Entity Manager** \(and can be extended\). If you want to retrieve them from APIs you must provide the header:

```http
Accept: application/json; gemini=api.meta
```

OpenAPI3 generated documentation already provides this kind of media type. Simply use the Swagger UI to try it out.

![](../../../.gitbook/assets/meta_data_example.gif)

