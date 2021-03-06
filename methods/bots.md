---
description: Methods used to post or retrieve info about bots.
---

# Bots

## Base Url

```text
https://botsfordiscord.com/api
```

{% api-method method="get" host="https://botsfordiscord.com/api" path="/bot/:id" %}
{% api-method-summary %}
bot info
{% endapi-method-summary %}

{% api-method-description %}
Obtain JSON encoded information about a specific bot.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the bot you are requesting information on.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The website was successfully able to fetch information about the bot.
{% endapi-method-response-example-description %}

```text
The content of this response varies.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
The bot you requested is not listed on the website.
{% endapi-method-response-example-description %}

```javascript
{"message":"Bot not found."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://botsfordiscord.com/api" path="/bot/:id/votes" %}
{% api-method-summary %}
bot votes
{% endapi-method-summary %}

{% api-method-description %}
Obtain JSON encoded voting information about a bot you own, without the necessity of webhooks.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the bot you are requesting voting information on.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=true %}
The bot's API token.
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
This should be set to application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The website was successfully able to fetch information about the bot.
{% endapi-method-response-example-description %}

```
{
    "hasVoted": [],
    "hasVoted24": [],
    "votes": 0,
    "votes24": 0,
    "votesMonth": 0
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
You provided the wrong API token for the bot.
{% endapi-method-response-example-description %}

```
{"message":"Invalid authorization token."}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
The bot you requested is not listed on the website.
{% endapi-method-response-example-description %}

```
{"message":"Bot not found."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://botsfordiscord.com/api" path="/bot/:id/widget" %}
{% api-method-summary %}
bot widget
{% endapi-method-summary %}

{% api-method-description %}
Obtain a widget that can be added to a website through HTML or Markdown.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the bot you are requesting information on.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="theme" type="string" required=false %}
Set this to dark for a dark themed widget
{% endapi-method-parameter %}

{% api-method-parameter name="width" type="number" required=false %}
Set the width of the widget
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
The website was successfully able to fetch and display the bot's widget.
{% endapi-method-response-example-description %}

```text
The content of this response varies.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
The bot you requested is not listed on the website.
{% endapi-method-response-example-description %}

```javascript
{"message":"Bot not found."}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://botsfordiscord.com/api" path="/bot/:id" %}
{% api-method-summary %}
bot stats
{% endapi-method-summary %}

{% api-method-description %}
Update your bot's server count on the website. Authorization is required!
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="id" type="integer" required=true %}
The ID of the bot you are posting information about.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
This should be set to application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Authorization" type="string" required=true %}
The bot's API token.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="server\_count" type="number" required=true %}
The server count for the bot.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Server count was successfully received and updated.
{% endapi-method-response-example-description %}

```javascript
{ message: 'Server count successfully updated.' }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
You may receive one of the following 400 errors depending on your situation.
{% endapi-method-response-example-description %}

```javascript
//You did not provide any bot token:
{ message: 'Authorization is required.' }

//You did not provide any server count:
{ message: 'Server count is required.' }

//The server count you provided was not a valid number:
{ message: 'Server count must be a valid number.' }

//The token you provided does not match the bot's token:
{ message: 'Invalid authorization token.' }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
The bot you are trying to post information on is not listed.
{% endapi-method-response-example-description %}

```javascript
{ message: 'Invalid bot.' }
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

