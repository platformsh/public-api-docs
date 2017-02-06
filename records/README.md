# Records API

## Plan

### List all plan records

> GET /api/platform/records/plan

### Response

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
