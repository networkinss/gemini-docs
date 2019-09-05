---
description: >-
  Automatically generate backend REST API. Build modern web/mobile application,
  microservice and MVP faster than ever.
---

# Zero-Code REST framework

{% hint style="info" %}
Gemini is an under development framework that need support from the community \(feedback, improvements and criticism\). If you like the idea and the project approach please try it and put a star on Github. With [Docker](quickstart-and-setup/environment-setup.md) you can setup a full environment it in minutes.

**Github Repository:** [**https://github.com/gemini-projects/gemini**](https://github.com/gemini-projects/gemini)\*\*\*\*
{% endhint %}

Gemini is a backend REST framework to automatically create CRUD REST APIs from scratch starting from a simple Schema definition called Gemini DSL. Briefly Gemini automatically handles for you \(_**without**_ _generating code_\):

* **Data Storage**: creating all persistence stuff \(tables, relations and so on\)
* **API controllers**: creating common REST CRUD controllers for each DSL Entity
* **Swagger API documentation**: creating the openapi language-agnostic interface to RESTful APIs
* **Authentication**: by using Spring OAuth2 and JWT tokens
* **API events and callback**: to add business logic with ease

{% hint style="warning" %}
**GEMINI doesn't generate code**

This is the main difference versus other framework
{% endhint %}

![](.gitbook/assets/gemini_hiw.gif)

