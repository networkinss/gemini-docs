# Gemini as Dependency

The best way to fully use Gemini features is to integrate it in your project as a dependency. In this way you can register to Gemini events and callback to customize and improve default Gemini API behaviors. For example you can:

* have some calculated fields in your APIs
* perform complex validation
* register completely custom APIs and controllers and use core Gemini features such as the Entity Manager

### Include Gemini

{% hint style="warning" %}
Gemini is made of a set of modules: CORE, AUTH, GUI, PERSISTENCE and so on.

PERSISTENCE module is responsible of storing data and manage storage.  Currently Gemini supports Postgresql and to fully setup a working environment you need to include **gemini-postgresql** dependency \(that loads all the others one\) 
{% endhint %}

{% hint style="danger" %}
You need the jcenter repository 
{% endhint %}

{% tabs %}
{% tab title="Maven" %}
```text
<dependency>
    <groupId>it.at7.gemini</groupId>
    <artifactId>gemini-postgresql</artifactId>
    <version>${gemini-version}</version>
</dependency>
```
{% endtab %}

{% tab title="Gradle" %}
```text
compile 'it.at7.gemini:gemini-postgresql:${gemini-version}
```
{% endtab %}
{% endtabs %}

### Custom Module - Main method

Gemini entry point is the `GeminiPostgresql` class. It provides start methods to automatically start Spring and Gemini. 

```java
public class AppMain {
    public static void main(String[] args) {
        GeminiPostgresql.start(args, CustomModuleCore.class, CustomModuleAPI.class);
    }
}
```

**What are `CustomModuleCore` and `CustomModuleAPI` ?**

They are the entry point beans of your custom logic. The first is if you want to define Gemini entities, events and logic and the latter if you want to register some custom Web controllers. Gemini uses a root Spring application context that handles entities and storage, and a child application context that run the WebServer when the root context is fully initialized.

{% tabs %}
{% tab title="CustomModuleCore" %}
The Core Bean class need to implement the Module interface and provide some information with the ModuleDescription. After that you can scan your components inside your package.

```java
@Service
@ModuleDescription(
        name = "CustomModule",
        order = -999)
@ComponentScan("com.yourdomain.yourproject.core")
public class CustomModuleCore implements Module {
}
```
{% endtab %}

{% tab title="CustomModuleAPI" %}
The API Bean can be used to register totally custom Web Controllers, so is better to scan another package. Scanned services are inserted in the web Gemini application context that can use also the CustomModuleCore beans and service \(registered by gemini in the root context\).

```java
@Service
@ComponentScan("com.yourdomain.yourproject.api")
public class CustomModuleAPI {
}
```
{% endtab %}
{% endtabs %}

Now you can crate the CustomModule entity schema called `CUSTOMMODULE.at` You need to put it inside the `resources/schemas` folder. 

You are ready to run Gemini building and running your project as you want. The only things to remember is to specify the `docker/dev/wd/` as the Java working directory if you want to use the already shipped Docker configuration.

 Continue with the following section to describe your entities.

