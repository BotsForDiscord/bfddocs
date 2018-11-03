# Testing

{% api-method method="get" host="https://botsfordiscord.com/api" path="/webhooktest" %}
{% api-method-summary %}
Example Webhook Response
{% endapi-method-summary %}

{% api-method-description %}
Returns an example webhook response
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
    user: "000000000000000000",
    bot: "123456789012345678",
    votes: {
        totalVotes: 5,
        votes24: 5,
        votesMonth: 3,
    hasVoted: [
        "000000000000000000",
        "111111111111111111",
        "222222222222222222"
    ],
    hasVoted24: [
        "000000000000000000",
        "111111111111111111",
        "222222222222222222",
        "333333333333333333",
        "444444444444444444"
    ]
    },
    type: "test"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://botsfordiscord.com/api" path="/webhooktest" %}
{% api-method-summary %}
Test Webhook Posting
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authorization" type="string" required=false %}
Webook Secret
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user" type="string" required=false %}
ID of user that voted
{% endapi-method-parameter %}

{% api-method-parameter name="bot" type="string" required=false %}
ID of bot voted on
{% endapi-method-parameter %}

{% api-method-parameter name="votes" type="object" required=false %}
Object of voting info
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    // boolean
    "authenticated": false,
    // null/string
    "auth": null,
    // null/string/number
    "bot": null,
    // null/string/number
    "user": null,
    // object
    "votes": {},
    // epoch
    "timestamp": 0000000000000
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



