# Provisioning API

## List your subscriptions

> GET /api/platform/subscriptions

### Response

```http
Status: 200 OK
```
```json
{
    "count": 3,
    "subscriptions": [
        // ...
    ],
    "_links": {
        "self": {
            "title": "Self",
            "href": "https:\/\/marketplace.commerceguys.com\/api\/platform\/subscriptions"
        },
        "next": {
            "title": "Next",
            "href": "https:\/\/marketplace.commerceguys.com\/api\/platform\/subscriptions?page=2"
        }
    }
}
```

## Get a single subscription

> GET /api/platform/subscriptions/:id

### Response

```http
Status: 200 OK
```
```json
{
    "id": "1234",
    "status": "active",
    "owner": "6e369812-ef06-46f8-8f88-83ff820ef6ac",
    "plan": "standard",
    "environments": 3,
    "storage": 5120,
    "user_licenses": 1,
    "project_id": "azertyuiop",
    "project_title": "Example Project",
    "project_region":"eu_west",
    "project_region_label": "EU (West)",
    "project_ui": "https://eu.platform.sh/#/projects/azertyuiop",
    "_links": {
        "project": {
            "href": "https://eu.platform.sh/api/projects/azertyuiop"
        },
        "self": {
            "href": "https:\/\/marketplace.commerceguys.com\/api\/platform\/subscriptions\/1234"
        }
    }
}
```

## Create a new subscription

> POST /api/platform/subscriptions

### Parameters

Name|Type|Required|Default|Description
:---|:---|:-------|:------|:----------
project_region|String|Yes||The machine name of the region where this Platform.sh project is located.
project_title|String|No|Untitled Project|The initial title of the project.
plan|String|No|development|The pricing plan for the project ('development', 'standard', 'medium', or 'large').
activation_callback|Object|No||A callback URL to notify when the subscription has been activated.
environments|Integer|No|3|The number of environments the project can contain.
storage|Integer|No|5120|The disk space for each environment on the project, in MiB.


```json
{
  "project_region": "eu_west",
  "plan": "standard",
  "project_title": "Example Project"
}
```

### Response

```http
Status: 200 OK
```

```json
{
    "id": "1234",
    "status": "requested",
    "owner": "6e369812-ef06-46f8-8f88-83ff820ef6ac",
    "plan": "standard",
    "environments": 3,
    "storage": 5120,
    "user_licenses": 1,
    "project_id": null,
    "project_title": "Example Project",
    "project_region":"eu_west",
    "project_region_label": "EU (West)",
    "project_ui": null,
    "_links": {
        "self": {
            "href": "https:\/\/marketplace.commerceguys.com\/api\/platform\/subscriptions\/1234"
        }
    }
}
```

## Update an existing subscription

> PATCH /api/platform/subscriptions/:id

### Parameters

Name|Type|Description
:---|:---|:----------
plan|String|Change the plan for the project.
environments|Integer|Change the number of environments for the project.
storage|Integer|Change the disk space for the project (in MiB). The disk space can only be increased, not decreased.


```json
{
  "plan": "medium"
}
```

### Response

```http
Status: 200 OK
```
```json
{
    "id": "1234",
    "status": "active",
    "owner": "6e369812-ef06-46f8-8f88-83ff820ef6ac",
    "plan": "medium",
    "environments": 3,
    "storage": 5120,
    "user_licenses": 1,
    "project_id": "azertyuiop",
    "project_title": "Example Project",
    "project_region":"eu_west",
    "project_region_label": "EU (West)",
    "project_ui": "https://eu.platform.sh/#/projects/azertyuiop",
    "_links": {
        "project": {
            "href": "https://eu.platform.sh/api/projects/azertyuiop"
        },
        "self": {
            "href": "https:\/\/marketplace.commerceguys.com\/api\/platform\/subscriptions\/1234"
        }
    }
}
```

## Delete a subscription

> DELETE /api/platform/subscriptions/:id

### Response

```http
Status: 200 OK
```

