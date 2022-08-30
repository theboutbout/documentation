
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Mail server` | Message trace follows email messages as they travel through your Exchange Online organization. |
| `Email gateway` | Message trace follows email messages as they travel through your Exchange Online organization. |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `email` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "messagetrace.json"

    ```json
	
    {
        "message": "{\"__metadata\": {\"id\": \"https://reports.office365.com/ecp/ReportingWebService/Reporting.svc/MessageTrace(0)\", \"uri\": \"https://reports.office365.com/ecp/ReportingWebService/Reporting.svc/MessageTrace(0)\", \"type\": \"TenantReporting.MessageTrace\"}, \"Organization\": \"examplecorp.onmicrosoft.com\", \"MessageId\": \"<3a273efc-cd65-4335-96ec-5f6934f0fb10@az.uksouth.production.microsoft.com>\", \"Received\":\"/Date(1658751973240)/\", \"SenderAddress\": \"azure-noreply@microsoft.com\", \"RecipientAddress\": \"foo.bar@example.corp\", \"Subject\": \"PIM: MessageTrace API service account has the Privileged Role Administrator role\", \"Status\": \"GettingStatus\", \"ToIP\": null, \"FromIP\": \"1.1.1.1\", \"Size\": 87680, \"MessageTraceId\": \"3b4fc661-180d-4c2f-60c9-08da6e38dd10\", \"StartDate\":\"/Date(1658579297628)/\", \"EndDate\":\"/Date(1658752097628)/\", \"Index\": 0}",
        "event": {
            "kind": "event",
            "category": "email",
            "type": "info",
            "action": "GettingStatus"
        },
        "@timestamp": "2022-07-25T12:26:13.240000Z",
        "office365": {
            "message_trace": {
                "MessageTraceId": "3b4fc661-180d-4c2f-60c9-08da6e38dd10",
                "Size": 87680
            }
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "email": {
            "message_id": "<3a273efc-cd65-4335-96ec-5f6934f0fb10@az.uksouth.production.microsoft.com>",
            "from": {
                "address": [
                    "azure-noreply@microsoft.com"
                ]
            },
            "to": {
                "address": [
                    "foo.bar@example.corp"
                ]
            },
            "subject": "PIM: MessageTrace API service account has the Privileged Role Administrator role"
        },
        "organization": {
            "name": "examplecorp.onmicrosoft.com"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "messagetrace2.json"

    ```json
	
    {
        "message": "{\"__metadata\":{\"id\":\"https://reports.office365.com/ecp/ReportingWebService/Reporting.svc/MessageTrace(5)\",\"uri\":\"https://reports.office365.com/ecp/ReportingWebService/Reporting.svc/MessageTrace(5)\",\"type\":\"TenantReporting.MessageTrace\"},\"Organization\":\"abc.onmicrosoft.com\",\"MessageId\":\"<123456@abc-prod2.mcc-soft.com>\",\"Received\":\"/Date(1661344992170)/\",\"SenderAddress\":\"support@abc.com\",\"RecipientAddress\":\"user@abc.fr\",\"Subject\":null,\"Status\":\"Delivered\",\"ToIP\":null,\"FromIP\":null,\"Size\":0,\"MessageTraceId\":\"1203cd7a-18d5-4a92-4343-08da85ce34c9\",\"StartDate\":\"/Date(1661344937835)/\",\"EndDate\":\"/Date(1661344997835)/\",\"Index\":5}\n",
        "event": {
            "kind": "event",
            "category": "email",
            "type": "info",
            "action": "Delivered"
        },
        "@timestamp": "2022-08-24T12:43:12.170000Z",
        "office365": {
            "message_trace": {
                "MessageTraceId": "1203cd7a-18d5-4a92-4343-08da85ce34c9",
                "Size": 0
            }
        },
        "email": {
            "message_id": "<123456@abc-prod2.mcc-soft.com>",
            "from": {
                "address": [
                    "support@abc.com"
                ]
            },
            "to": {
                "address": [
                    "user@abc.fr"
                ]
            }
        },
        "organization": {
            "name": "abc.onmicrosoft.com"
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`email.from.address` | `keyword` | None |
|`email.message_id` | `keyword` | None |
|`email.subject` | `keyword` | None |
|`email.to.address` | `keyword` | None |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`office365.message_trace.MessageTraceId` | `keyword` | None |
|`office365.message_trace.Size` | `number` | None |
|`organization.name` | `keyword` | Organization name. |
|`source.ip` | `ip` | IP address of the source. |
