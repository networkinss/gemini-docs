# Enjoy with DSL and REST

{% hint style="success" %}
If you followed the [Start Gemini ](start-gemini/)section Gemini has already configured its internal structures and has created the _**schema/RUNTIME.at**_ abstract type file in the working directory. 
{% endhint %}

### DSL

Now you can customize this file with all your entities by using the Gemini DSL. Then restart the application to see your APIs in action. Gemini automatically recognize what you have added/modified. For example:

![](../.gitbook/assets/quic_start_dsl.png)

### SWAGGER

If you want to easily navigate APIs you can use the Swagger openapi tools. Gemini automatically generate the **openapi** json file `openapi/schema/runtime.json`. For example you can navigate the _Book_ and _Author_ sections.

![](../.gitbook/assets/swagger_quick_start.png)

{% hint style="info" %}
Note that entity can be consumed both by their _**logical key**_ and by the _**unique UUID**_ generated when you create a resource with POST
{% endhint %}

{% hint style="warning" %}
f you want customize openapi info you can change default properties of _**./service/info.yml**_ and restart Gemini.
{% endhint %}

