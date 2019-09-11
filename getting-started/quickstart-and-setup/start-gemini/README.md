# Start Gemini

Once all services are up \(only **postgresql** is required, but using docker is suggested to consume API with swagger\) you can use Gemini as a normal Spring Boot project or application. This means that you have two way.

Run Gemini as a standalone application and use its **zero-code** **REST** API development.

{% page-ref page="zero-code-platform.md" %}

Or add Gemini as a classic **dependency** of your project \(with Spring already included\) and use it as **zero-code** platform but with the possibility to interact with the framework: changing APIs life-cycle by using **Gemini Events** and **Callbacks.** You can also use Spring as you always do, developing completely custom controllers and code.

{% page-ref page="gemini-as-dependency.md" %}

