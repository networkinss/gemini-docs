# Date And Time

Dates and Times are Strings \(in JSON notation\). Gemini uses the **ISO 8601** Data elements and interchange formats standard.

```text
ENTITY DatesEntity {
    TEXT        code *
    DATE        aDate
    TIME        aTime
    DATETIME    aDateTime
}
```

### **Date**

**DATE** is the type you can use for a simple local date \(no need of timezone\). Out of the box supported JSON API format is `yyyy-MM-dd`.

### **Time**

**TIME** is the type you can use for ISO-8601 standard time. ISO-TIME is the out of the box supported format. So for example the JSON String `09:41:43.973Z` is a valid time.

### **Datetime**

**DATETIME** can be used for a date time field. It is a full ISO-8601 standard ISO-DATE-TIME. So for example `2019-05-19T09:41:30.000Z` is a valid value.

## Api Example

```bash
$ curl -H "Content-Type: application/json" -X POST http://127.0.0.1:8090/api/datestypes -i -d '{"aTime":"11:11:05.759Z","code":"lkdate","aDate":"2019-05-19","aDateTime":"2019-05-19T11:09:58Z"}'
    
#    HTTP/1.1 200
#    Content-Type: application/json;charset=UTF-8
#
#    {"aTime":"11:11:05.759Z","code":"lkdate","aDate":"2019-05-19","aDateTime":"2019-05-19T11:09:58Z"}
```

