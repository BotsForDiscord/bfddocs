# Receiving Votes

{% api-method method="post" host="​" path="​" %}
{% api-method-summary %}
Receive Vote
{% endapi-method-summary %}

{% api-method-description %}
Response only
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
vote made and response successfully POSTed
{% endapi-method-response-example-description %}

```javascript
{
    "user": "000000000000000000",
    "bot": "123456789012345678",
    "votes": {
        "totalVotes": 5,
        "votes24": 5,
        "votesMonth": 3,
        // only visible if webhook secret key is not NULL or EMPTY
        "hasVoted": [
            "000000000000000000",
            "111111111111111111",
            "222222222222222222"
        ],
        // only visible if webhook secret key is not NULL or EMPTY
        "hasVoted24": [
            "000000000000000000",
            "111111111111111111",
            "222222222222222222",
            "333333333333333333",
            "444444444444444444"
        ]
    },
    // will be "test" when using testing button
    // you can test on your bots edit page
    "type": "vote"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



