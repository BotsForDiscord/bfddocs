---
description: Methods used retrieve info about users.
---

# Users

## Base Url

```text
https://botsfordiscord.com/api
```

{% api-method method="get" host="https://botsfordiscord.com" path="/api/user/:id" %}
{% api-method-summary %}
GET /user/:id
{% endapi-method-summary %}

{% api-method-description %}
Obtain JSON encoded information about a specific user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the user you are requesting information on.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The server has located the users information and displayed it.
{% endapi-method-response-example-description %}

```text
The content of this response varies.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
The user you are requesting does not exist on the website.
{% endapi-method-response-example-description %}

```text
{ message: 'User not found.' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://botsfordiscord.com" path="/api/user/:id/bots" %}
{% api-method-summary %}
GET /user/:id/bots
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the user you are requesting information on.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The server has located information about the user's bots and displayed it.
{% endapi-method-response-example-description %}

```text
The content of this response varies.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
You may receive of the following 404 errors depending on your situation.
{% endapi-method-response-example-description %}

```text
The user you are requesting does not exist on the website:
{ message: 'User not found.' }

The user you are requesting does not own any bots on the website:
{ bots: 'User has no bots.' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

