# highlighter

This is a simple utility I created to crate deployment markers utilizing logz.io [Deployment Markers](https://docs.logz.io/user-guide/logs/exceptions-deployments.html).

#### Requirements

1. Logz.io API TOKEN
1. This utility

## Create a deployment Marker

First you need to create a JSON payload you need to set the tag to 'DEPLOYMENT' or 'OTHER'. You can add as much data as you want in the metadata.

example-payload.json

```
{
  "markers": [
    {
      "description": "marker description",
      "title": "marker title",
      "tag": "DEPLOYMENT",
      "timestamp": 1613311091679,
      "metadata": {
        "region": "us-east-1",
        "deployedBy": "bot"
      }
    }
  ]
}
```

Set the `LOGZ_IO_API_TOKEN` environment variable:

```
export LOGZ_IO_API_TOKEN=00000000-0000000-000000-0000000
echo $LOGZ_IO_API_TOKEN
```

If you utilize the fish shell then you can do:

```
set -x LOGZ_IO_API_TOKEN 00000000-0000000-000000-0000000
echo $LOGZ_IO_API_TOKEN
```

Create a Deployment marker:

```
# We are just creating a deployment marker
highlighter -p deployment-start.json
```
