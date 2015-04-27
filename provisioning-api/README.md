# Provisioning API

## List your subscriptions

> GET /subscriptions

### Response

```http
Status: 200 OK
```
```json
{
    "_links": {
        "project": {
            "href": "https://eu.platform.sh/api/projects/azertyuiop"
        },
        "self": {
            "href": "https://marketplace.commerceguys.com/api/platform/subscriptions/123"
        }
    },
    "environments": "3",
    "id": "123",
    "owner": "abcd0123-abcd0123-abcd0123-abcd0123-abcd0123",
    "plan": "medium",
    "project_id": "azertyuiop",
    "project_region": "eu_west",
    "project_region_label": "Europe",
    "project_title": "My Platform project",
    "project_ui": "https://eu.platform.sh/#/projects/azertyuiop",
    "status": "active",
    "storage": 5120,
    "user_licenses": "1"
}
```

## Get a single subscription

> GET /subscriptions/:id

### Response

```http
Status: 200 OK
```
```json
{
    "_links": {
        "project": {
            "href": "https://eu.platform.sh/api/projects/azertyuiop"
        },
        "self": {
            "href": "https://marketplace.commerceguys.com/api/platform/subscriptions/123"
        }
    },
    "environments": "3",
    "id": "123",
    "owner": "abcd0123-abcd0123-abcd0123-abcd0123-abcd0123",
    "plan": "medium",
    "project_id": "azertyuiop",
    "project_region": "eu_west",
    "project_region_label": "Europe",
    "project_title": "My Platform project",
    "project_ui": "https://eu.platform.sh/#/projects/azertyuiop",
    "status": "active",
    "storage": 5120,
    "user_licenses": "1"
}
```

## Create a new subscription

> POST /subscriptions

### Parameters

Name|Type|Required|Description
:---|:---|:-------|:----------
project_region|String|True|The machine name of the region where this Platform.sh project is located.

```json
{
  "project_region": eu_west
}
```

### Response

@TODO

## Update an existing subscription

> PATCH /subscriptions/:id

### Parameters

Name|Type|Required|Description
:---|:---|:-------|:----------
project_region|String|True|The machine name of the region where this Platform.sh project is located.

```json
{
  "project_region": eu_west
}
```

### Response

```http
Status: 200 OK
```
```json
{
    @TODO
}
```

## Delete a subscription

> DELETE /subscriptions/:id

### Response

```http
Status: 204 No Content
```