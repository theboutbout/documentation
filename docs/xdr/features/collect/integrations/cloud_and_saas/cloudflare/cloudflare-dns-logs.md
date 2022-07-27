uuid: bd9d0f51-114e-499a-bb7a-4f2d0a518b04
name: Cloudflare DNS logs
type: intake

## Overview

Cloudflare is a global network designed to make everything you connect to the Internet secure, private, fast, and reliable.

In this documentation, you will learn how to collect and send Cloudflare DNS logs to SEKOIA.IO.

{!_shared_content/operations_center/integrations/generated/cloudflare-dns-logs_do_not_edit_manually.md!}

## Configure

### Create the intake

Go to the [intake page](https://app.sekoia.io/operations/intakes) and create a new intake from the format Cloudflare.

### Forward the events

First, you will have to retrieve configuration information.
To do so, connect to [Cloudflare Console](https://dash.cloudflare.com/) to collect:

- `Cloudflare authentication key`
- `Cloudflare Zone ID`
- `Cloudflare account email`

#### with Logpush

Configure a [Logpush job](https://developers.cloudflare.com/logs/reference/logpush-api-configuration/) with the following destination:

`https://intake.sekoia.io/plain/batch?header_X-SEKOIAIO-INTAKE-KEY=<your intake key>`


##### Manage Logpush with cURL

```bash
$ curl -X POST https://api.cloudflare.com/client/v4/zones/<Cloudflare Zone ID>/logpush/jobs \
-h "x-auth-email: <Cloudflare account email>" \
-H "X-Auth-Key: <Cloudflare authentication key>" \
-H "Content-Type: application/json" \
--data '{
    "dataset": "dns_logs",
    "enabled": true,
    "max_upload_bytes": 5000000,
    "max_upload_records": 1000,
    "logpull_options":"fields=ColoCode,EDNSSubnet,EDNSSubnetLength,QueryName,QueryType,ResponseCached,ResponseCode,SourceIP,Timestamp&timestamps=rfc3339",
    "destination_conf": "https://intake.sekoia.io/plain/batch?header_X-SEKOIAIO-INTAKE-KEY=<INTAKE KEY>"
}' # (1)
```

1. will return
```json
{
  "errors": [],
  "messages": [],
  "result": {
    "id": 148,
    "dataset": "dns_log",
    "enabled": false,
    "name": "<DOMAIN_NAME>",
    "logpull_options": "fields=ColoCode,EDNSSubnet,EDNSSubnetLength,QueryName,QueryType,ResponseCached,ResponseCode,SourceIP,Timestamp&timestamps=rfc3339",
    "destination_conf": "https://intake.sekoia.io/plain/batch?header_X-SEKOIAIO-INTAKE-KEY=<INTAKE KEY>",
    "last_complete": null,
    "last_error": null,
    "error_message": null
  },
  "success": true
}
```