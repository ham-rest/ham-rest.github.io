---
title: Name Spaces
layout: default
permalink: /sections/namespaces
nav_order: 2
---
# Namespace Management

**Available Methods**: `POST`, `DELETE`

## create new Namespace

- **Method**: `POST`
- **URL**: `/api/v1/darkube/namespaces/`
- **Authorization**: Api-key required
- **Required Headers**: `Authorization`, `x-organization`
- **Payload Type**: `application/json`
- **Response Type**: `application/json; charset=utf-8`

{% tabs create-namespace %}

{% tab create-namespace curl %}
```bash
curl --location 'https://api.hamravesh.com/api/v1/darkube/namespaces/' \
--header 'x-organization: YOUR_ORGANIZATION_NAME' \
--header 'Content-Type: application/json' \
--header 'Authorization: Api-key YOUR_API_KEY' \
--data '{
    "name": "YOUR_ORGANIZATION_NAME-namespace name",
    "cluster_id": 53
}
'
```
{% endtab %}

{% tab create-namespace python %}
```python
import requests
import json

url = "https://api.hamravesh.com/api/v1/darkube/namespaces/"

payload = json.dumps({
  "name": YOUR_ORGANIZATION_NAME+"-"+"namespace name",
  "cluster_id": 53
})
headers = {
  'x-organization': 'YOUR_ORGANIZATION_NAME',
  'Content-Type': 'application/json',
  'Authorization': 'Api-key YOUR_API_KEY',
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```
{% endtab %}

{% endtabs %}

Header Parameters:

| Field      | Example      |
|:-----------|:--------------------|
|Authorization|'Api-key YOUR_API_KEY'|
|x-organization|'organization name'|

Payload:

| Field  | Description                           | Type      | Example                               |
|:-------|:--------------------------------------|:----------|:--------------------------------------|
| name   | should contain your organization name | `string`  | YOUR_ORGANIZATION_NAME-namespace-name |
| cluster_id |                                       | `integer` | 53                                    |

Response:

| Field   | Description             | Type         | Example Output |
|:--------|:------------------------|:-------------|:---------------|
| name    | your new namespace name | `string`     |                |
| cluster | Cluster Information     | `dict`       |                |
| id      | new namespace id        | `integer`    |                |


## delete Namespace

- **Method**: `DELETE`
- **URL**: `/api/v1/darkube/namespaces/{namespace_id}/`
- **Authorization**: Api-key required
- **Required Headers**: `Authorization`, `x-organization`
- **Response Type**: `application/json; charset=utf-8`

* put the id of the namespace you want to delete in the url


{% tabs delete-namespace %}

{% tab delete-namespace curl %}
```bash
curl --location --request DELETE 'https://api.hamravesh.com/api/v1/darkube/namespaces/{namespace_id}/' \
--header 'x-organization: YOUR_ORGANIZATION_NAME' \
--header 'Authorization: Api-key YOUR_API_KEY'
```
{% endtab %}

{% tab delete-namespace python %}
```python
import requests
namespace_id= <int>
url = f"https://api.hamravesh.com/api/v1/darkube/namespaces/{namespace_id}/"

headers = {
  'x-organization': 'YOUR_ORGANIZATION_NAME',
  'Authorization': 'Api-key YOUR_API_KEY'
}

response = requests.request("DELETE", url, headers=headers)

print(response.text)
```
{% endtab %}

{% endtabs %}