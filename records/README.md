# Records API

## Plan

### List all plan records

> GET /api/platform/records/plan

*Response*

```http
Status: 200 OK
```
```json
{
    "_links": {
        "next": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan?page=2",
            "title": "Next"
        },
        "self": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan",
            "title": "Self"
        }
    },
    "count": 23600,
    "plan": [
        {
            "end": "2015-09-21T12:01:37+02:00",
            "id": "5590",
            "plan": "development",
            "sku": "PLATFORM-ENVIRONMENT-DEVELOPMENT",
            "start": "2014-05-23T15:51:34+02:00",
            "status": "active",
            "subscription_id": "4435"
        },
        ...
    }    
}
```

## Usage

### List all usage records

> GET /api/platform/records/usage

*Response*

```http
Status: 200 OK
```
```json
{
    "_links": {
        "next": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/usage?page=2",
            "title": "Next"
        },
        "self": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/usage",
            "title": "Self"
        }
    },
    "count": 51815,
    "usage": [
        {
            "_links": {
                "plan": {
                    "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan/5590"
                }
            },
            "end": "2015-09-21T12:01:37+02:00",
            "id": "1409",
            "plan_record": "5590",
            "quantity": "5",
            "start": "2014-05-23T15:51:34+02:00",
            "subscription_id": "4435",
            "usage_group": "storage"
        },
        ...
    }
}
```

### Get usage records for a single subscription

Used to get usage records for a single project.

> GET /api/platform/records/usage?filter[subscription_id]=:id

*Response*

```http
Status: 200 OK
```
```json
{
    "_links": {
        "self": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/usage",
            "title": "Self"
        }
    },
    "count": 3,
    "usage": [
        {
            "_links": {
                "plan": {
                    "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan/6102"
                }
            },
            "end": "2014-10-16T17:22:01+02:00",
            "id": "1755",
            "plan_record": "6102",
            "quantity": "5",
            "start": "2014-06-18T16:35:15+02:00",
            "subscription_id": "4833",
            "usage_group": "storage"
        },
        {
            "_links": {
                "plan": {
                    "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan/6102"
                }
            },
            "end": "2014-10-16T17:22:01+02:00",
            "id": "1756",
            "plan_record": "6102",
            "quantity": "3",
            "start": "2014-06-18T16:35:15+02:00",
            "subscription_id": "4833",
            "usage_group": "environments"
        },
        {
            "_links": {
                "plan": {
                    "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan/6102"
                }
            },
            "end": "2014-10-16T17:22:01+02:00",
            "id": "1761",
            "plan_record": "6102",
            "quantity": "2",
            "start": "2014-06-18T16:40:20+02:00",
            "subscription_id": "4833",
            "usage_group": "user_licenses"
        }
    ]
}
```
