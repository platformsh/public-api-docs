# Introduction

This book is documenting the Platform.sh Provisioning API.

# Generate the JSON output

The ``output-subscriptions.json`` file can be used to compare with the live API and update the documentation with the possible changes.

It's been generated using the following command:

```bash
curl -H "Authorization: Bearer TOKEN" https://marketplace.commerceguys.com/api/platform/subscriptions -X OPTIONS | python -mjson.tool
``