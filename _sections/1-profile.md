---
title: Profile Info
layout: default
permalink: /sections/basics/profile
parent: Get Started
nav_order: 3
---
# Profile

**Available Methods**: `GET`

## get profile information

- **Method**: `GET`
- **URL**: `/api/v1/users/profile`
- **Authorization**: Api-key required
- **Required Headers**: `Authorization`
- **Response Type**: `application/json; charset=utf-8`

{% tabs example-request %}

{% tab example-request curl %}
```bash
curl -X GET "https://api.hamravesh.com/api/v1/users/profile" \
     -H "Authorization: Api-key YOUR_API_KEY"
```
{% endtab %}

{% tab example-request python %}
```python
import requests

url = "https://api.hamravesh.com/api/v1/users/profile"

payload = {}
headers = {
    'Authorization': 'Api-key YOUR_API_KEY'
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

Request Paremeters:

| Field      | Description | Type                | Example      |
|:-----------|:------------|:--------------------|:--------------------|
|||||

Response:

| Field      | Description | Type                | Example Output      |
|:-----------|:------------|:--------------------|:--------------------|
| first_name |             | `string`            | `null`              |
| last_name  |             | `string`            | `null`              |
| full_name  |             | `string`            | `email@example.com` |
| organizations  |             | `list[dict]`        | *                   |
|organization_roles|| `dict{string:list}` ||
|email|| `integer`           ||
|is_email_verified|| `boolean`           ||
|is_verified|| `boolean`           ||
|mobile|| `string`            ||
|national_id|| `string`            ||
|is_national_id_verified|| `boolean`           ||
|is_mobile_verified|| `boolean`           ||
|creation_time|| `datetime`           ||
|profile_settings||                     ||

\* example output of organizations:
```json
 {
  "id": 1598,
  "name": ,
  "creation_time": ,
  "description": "",
  "invitation_emails": [],
  "image": null,
  "owned_domains": [],
  "autogenerate_gitlabci": true,
  "available_clusters": [],
  "available_namespaces":[],
  "charged_budget": 1072283.0,
  "virtual_budget": 0.0,
  "build_method": "webhook",
  "budget": 0.0,
  "balance": 0.0,
  "is_restricted": false,
  "owner": {
    "id": 0,
    "first_name": null,
    "last_name": null,
    "full_name": "email@example.com",
    "email": "email@example.com",
    "is_email_verified": true,
    "is_verified": true,
    "is_staff": false,
    "creation_time":
  },
  "is_acl_enabled": false,
  "is_viper_notification_enabled": true,
  "is_onboarded": true,
  "is_automatically_generated": true,
  "has_cre": false,
  "invoice_settings": {},
  "invoice_settings_status": null,
  "is_network_billing_enabled": true,
  "is_backingham_billing_enabled": false,
  "is_kaas_billing_enabled": true,
  "show_hamartia": true,
  "show_dazzle": true,
  "show_database": false,
  "show_backup_features": false,
  "show_containerregistry": true,
  "show_containerregistry_gc": false,
  "show_loadbalancer": false,
  "seconds_to_negative_balance": null,
  "pending_invitation_emails": [],
  "total_residual_debt": 0.0,
  "residual_debt_percentage": 0.0,
  "apps_custom_base_domain": null,
  "is_balance_limitation_enabled": true,
  "organization_feature_flags": {
    "limited_apps": [
      "wordpress"
    ],
    "limited_clusters": []
  }
}
```

