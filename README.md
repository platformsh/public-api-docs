# Platform.sh subscription API

Documentation for the Platform.sh subscription API. This API allows a user which has a proper access token to programmatically subscribe to Platform.sh and manage their subscriptions via a REST API.

## Generate the JSON output

The JSON output file can be used to compare with the live API and update the documentation with the possible changes.

It has been generated using the following command:

```bash
curl -H "Authorization: Bearer $TOKEN" $ENDPOINT -X OPTIONS | python -m json.tool
```
