# Primitive Types

Primitive types are numbers, strings booleans and their aliases.

```yaml
ENTITY PrimitiveTypes {
    TEXT            code *          // TEXT is the single type for Strings  
    DOUBLE          double
    DECIMAL         anotherDouble
    NUMBER          anyNumber       // any number (int or foating point)
    LONG            long
    QUANTITY        anotherLong
    BOOL            isOk
}
```

### **Numbers**

In Json notation _Number_ is a single type. In Gemini it is the same, but it adds some semantic to each field \(useful for validation\)

* **DOUBLE** or **DECIMAL**: floating point numbers
* **LONG** or **QUANTITY**: integer numbers
* **NUMBER**: any number no matter if it has decimals or not

{% hint style="warning" %}
_they may be extended in next releases \(for example adding only naturals numbers and so on\)_
{% endhint %}

### **Strings and Text**

Any string field can be defined with the **TEXT** type. No matter its size, it is a JSON string.

### **Boolean**

Boolean is _true_ or _false_ and can be defined with the **BOOL** type

## API Example

```http
$ curl -H "Content-Type: application/json" -X POST http://127.0.0.1:8090/api/primitivetypes -i -d '{"code":"logicalKey","anotherDouble":7.77,"double":7.77,"isOk":true,"anotherLong":7,"anyNumber":70,"long":7}'
  
HTTP/1.1 200
Content-Type: application/json;charset=UTF-8
   
{"code":"logicalKey","anotherDouble":7.77,"double":7.77,"isOk":true,"anotherLong":7,"anyNumber":70,"long":7}
```

