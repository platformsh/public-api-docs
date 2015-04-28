# Introduction

This book is documenting the Platform.sh Provisioning API. This API allows a user which has a proper access token, to programmatically subscribe to Platform.sh and manage his subscriptions via a REST API.

# Current version

The current version is not yet stable.

# Generate the JSON output

The ``output-subscriptions.json`` file can be used to compare with the live API and update the documentation with the possible changes.

It's been generated using the following command:

```bash
curl -H "Authorization: Bearer TOKEN" https://marketplace.commerceguys.com/api/platform/subscriptions -X OPTIONS | python -mjson.tool
```
