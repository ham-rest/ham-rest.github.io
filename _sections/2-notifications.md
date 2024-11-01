---
title: Notifications
layout: default
permalink: /sections/basics/notifications
parent: Get Started
nav_order: 3
---
# Notifications

**Available Methods**: `GET`

## get profile information

- **Method**: `GET`
- **URL**: `/api/v1/notifications/all_list/`
- **Authorization**: Api-key required
- **Required Headers**: `Authorization`, `x-organization`
- **Response Type**: `application/json; charset=utf-8`

{% tabs example-request %}

{% tab example-request curl %}
```bash
curl --location 'https://api.hamravesh.com/api/v1/notifications/all_list/?limit=5&offset=0' \
--header 'x-organization: YOUR_ORGANIZATION_NAME' \
--header 'Authorization: Api-key YOUR_API_KEY'
```
{% endtab %}

{% tab example-request python %}
```python
import requests

url = "https://api.hamravesh.com/api/v1/notifications/all_list/?limit=5&offset=0"

payload = {}
headers = {
  'x-organization': 'YOUR_ORGANIZATION_NAME',
  'Authorization': 'Api-key YOUR_API_KEY',
}

response = requests.request("GET", url, headers=headers, data=payload)

print(response.text)

```
{% endtab %}

{% endtabs %}

Header Parameters:
| Field      | Example      |
|:-----------|:--------------------|
|Authorization|'Api-key YOUR_API_KEY'|
|x-organization|'organization name'|

Request Parameters:

| Field      | Description | Type     | Example |
|:-----------|:------------|:---------|:--------|
|limit|| `integer` | 50      |
|offset||   `integer`       | 0       |

Response:

| Field      | Description         | Type         | Example Output |
|:-----------|:--------------------|:-------------|:---------------|
| count | total notifications | `integer`    | 10             |
| next | next page           | `url`        |                |
| previous | previous page       | `url`        |                |
| results | notifications       | `list[dict]` |                |

\* example notification:
```json
{
            "unread": false,
            "public": false,
            "timestamp": ,
            "title": ,
            "slug": 000,
            "description": ,
            "target_type": "general"
        }
```