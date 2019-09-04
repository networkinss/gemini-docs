# Overview

{% hint style="info" %}
**Github Repository:** [**https://github.com/gemini-projects/gemini**](https://github.com/gemini-projects/gemini)\*\*\*\*
{% endhint %}

Gemini is a backend REST framework to automatically create CRUD REST APIs from scratch starting from a simple Schema definition called Gemini DSL. Briefly Gemini automatically handles for you \(_**without**_ _generating code_\):

* **Data Storage**: creating all persistence stuff \(tables, relations and so on\)
* **API controllers**: creating common REST CRUD controllers for each DSL Entity
* **Swagger API documentation**: creating the openapi language-agnostic interface to RESTful APIs
* **Authentication**: by using Spring OAuth2 and JWT tokens
* **API events and callback**: to add business logic with ease

![](.gitbook/assets/gemini_hiw.gif)

