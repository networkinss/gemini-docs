---
description: >-
  Gemini is a Model Driven REST framework that automatically generate CRUD APIs 
  with zero code generation.
---

# Gemini Overview

{% hint style="info" %}
Gemini is an under development framework that need support from the community \(feedback, improvements and criticism\). If you like the idea and the project approach please try it and put a star on Github. With [Docker](quickstart-and-setup/environment-setup.md) you can setup a full environment it in minutes.

**Github Repository:** [**https://github.com/gemini-projects/gemini**](https://github.com/gemini-projects/gemini)\*\*\*\*
{% endhint %}

Gemini is Model Driven REST framework that automatically create CRUD REST APIs from scratch starting from a simple Schema definition called Gemini DSL. Briefly with Gemini you only need to define your Model Structure and let the framework to handle for you \(_**without**_ _generating code_\):

* **Data Storage**: creating all persistence stuff \(tables, relations and so on\)
* **API controllers**: creating common REST CRUD controllers for each DSL Entity
* **Swagger API documentation**: creating the openapi language-agnostic interface to RESTful APIs
* **Authentication**: by using Spring OAuth2 and JWT tokens

{% hint style="warning" %}
**GEMINI doesn't generate code**

This is the main difference versus other framework
{% endhint %}

And if you want custom logic or change default CRUD behaviors you can register:

* **API events and callback**: to add business logic with ease
* **Completely custom code**
  * REST Controllers 
  * You can use Spring as you want

![](.gitbook/assets/gemini_hiw.gif)

