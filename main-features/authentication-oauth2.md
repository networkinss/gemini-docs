# Authentication - OAuth2

### **Login**

{% hint style="success" %}
To enable Gemini Authentication you need to use the following Spring parameter. If you don't specify a value Authentication is enabled out of the box.

 **gemini.auth=true**
{% endhint %}

Gemini authentication is handled by the **gemini-auth** module. Gemini uses Spring OAuth2 framework to provide Authentication and once logged gives a signed **JWT** token.

{% api-method method="post" host="" path="/api/auth/login" %}
{% api-method-summary %}
Login Endpoint
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Password
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
Username
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
  { 
   "access_token":"____the_JWT__token___",
   "refresh_token":"__the_JWT_refresh_token____",
   "token_type":"bearer",
   "expires_in":3600
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
**Admin** user was created automatically by Gemini

username: **Admin**  
password: **Admin**
{% endhint %}

### **Swagger UI**

{% hint style="success" %}
OpenAPI spec created by Gemini already provides Authentication features. Try the API setting up the [Docker Environment](../quickstart-and-setup/environment-setup.md)
{% endhint %}

