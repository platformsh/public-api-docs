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

### Get plan records for a specifiv product SKU

Used to get plan records for a single product sku. Available options are:
* `PLATFORM-ENVIRONMENT-DEVELOPMENT`
* `PLATFORM-ENVIRONMENT-SMALL`
* `PLATFORM-ENVIRONMENT-STANDARD`
* `PLATFORM-ENVIRONMENT-LARGE`

> GET /api/platform/records/plan?filter[slu]=:sku

*Response*

```http
{
    "_links": {
        "next": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan?filter[sku]=PLATFORM-ENVIRONMENT-MEDIUM&page=2",
            "title": "Next"
        },
        "self": {
            "href": "https://records-api-ime4zei-p43m25zns6k2c.eu.platform.sh/api/platform/records/plan",
            "title": "Self"
        }
    },
    "count": 541,
    "plan": [
        {
            "end": "2014-05-31T13:05:32+02:00",
            "id": "5670",
            "plan": "medium",
            "sku": "PLATFORM-ENVIRONMENT-MEDIUM",
            "start": "2014-05-31T01:44:32+02:00",
            "status": "provisioning",
            "subscription_id": "4506"
        },
        ...
    }
}
```

You can also filter per sku matching:

> GET /api/platform/records/plan?filter[sku][value]=STAND&filter[sku][operator]=CONTAINS

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

?filter[start]=2015-01-01T00:00:00 - Gets any records that overlap with the time period 2015 or later
?filter[end]=2016-01-01T00:00:00 - Gets any records that overlap with the time period before 2016
?filter[start]=2015-01-01T00:00:00&filter[end]=2016-01-01T00:00:00 - Gets any record which overlaps with the year 2015 in some way

?filter[usage_group][value][0]=storage&filter[usage_group][value][1]=environments&filter[usage_group][operator]=IN - Get all usage records of both types