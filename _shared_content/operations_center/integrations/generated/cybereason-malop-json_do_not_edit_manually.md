
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Application logs` | Cybereason MalOps platform provides detections on malicious activities |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `alert`, `event` |
| Category | `file`, `host`, `intrusion_detection`, `malware`, `session` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_file_suspect_detail.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\"malopGuid\": \"11.-6654920844431693523\", \"timestamp\": 1668945737625},\n  \"@class\": \".FileSuspectDetailsModel\",\n  \"firstSeen\": 1657923190000,\n  \"lastSeen\": 1667946935000,\n  \"counter\": 2,\n  \"wasEverDetectedInScan\": false,\n  \"wasEverDetectedByAccess\": true,\n  \"detectionDecisionStatus\": \"DDS_PREVENTED\",\n  \"guid\": \"11.7498520112250262440\",\n  \"ownerMachineName\": \"desktop-aaaaaa\",\n  \"ownerMachineGuid\": \"aaaaaaaaaaaaaaaa\",\n  \"sha1String\": \"adc83b19e793491b1c6ea0fd8b46cd9f32e592fc\",\n  \"behaviourIdString\": null,\n  \"correctedPath\": \"c:\\\\System\\\\kprocesshacker.sys\",\n  \"modifiedTime\": null,\n  \"elementDisplayName\": \"kprocesshacker.sys\"\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "file"
            ],
            "type": [
                "info"
            ],
            "code": "file_suspect"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.-6654920844431693523",
                "host": {
                    "id": "aaaaaaaaaaaaaaaa"
                },
                "file": {
                    "id": "11.7498520112250262440",
                    "decision": {
                        "status_code": "DDS_PREVENTED"
                    }
                }
            }
        },
        "file": {
            "path": "c:\\System\\kprocesshacker.sys",
            "hash": {
                "sha1": "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"
            }
        },
        "host": {
            "name": "desktop-aaaaaa"
        },
        "related": {
            "hash": [
                "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"
            ]
        }
    }
    	
	```


=== "test_machine_detail.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\"malopGuid\": \"11.-6654920844431693523\", \"timestamp\": 1668945737625},\n  \"@class\": \".MachineDetailsModel\",\n  \"guid\": \"-576002811.1198775089551518743\",\n  \"displayName\": \"desktop-aaaaaa\",\n  \"osType\": \"WINDOWS\",\n  \"connected\": false,\n  \"isolated\": false,\n  \"lastConnected\": 1668439428578,\n  \"adOU\": null,\n  \"adOrganization\": null,\n  \"adDisplayName\": \"DESKTOP-AAAAAA\",\n  \"adDNSHostName\": \"desktop-aaaaaa.example.org\",\n  \"adDepartment\": null,\n  \"adCompany\": null,\n  \"adLocation\": null,\n  \"adMachineRole\": null,\n  \"pylumId\": \"MARVELCLIENT_INTEGRATION_DESKTOP-AAAAAA_000000000000\",\n  \"empty\": true\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "host"
            ],
            "type": [
                "info"
            ],
            "code": "machine"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.-6654920844431693523",
                "host": {
                    "id": "-576002811.1198775089551518743",
                    "is_online": false,
                    "is_isolated": false
                }
            }
        },
        "host": {
            "name": "desktop-aaaaaa",
            "domain": "desktop-aaaaaa.example.org",
            "os": {
                "type": "windows"
            }
        }
    }
    	
	```


=== "test_machine_inbox.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\"malopGuid\": \"11.-6654920844431693523\", \"timestamp\": 1668945737625},\n  \"@class\": \".MachineInboxModel\",\n  \"guid\": \"11.7498520112250262440\",\n  \"displayName\": \"desktop-aaaaaa\",\n  \"osType\": \"WINDOWS\",\n  \"connected\": false,\n  \"isolated\": false,\n  \"lastConnected\": 1668439428578,\n  \"empty\": true\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "host"
            ],
            "type": [
                "info"
            ],
            "code": "machine"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.-6654920844431693523",
                "host": {
                    "id": "11.7498520112250262440",
                    "is_online": false,
                    "is_isolated": false
                }
            }
        },
        "host": {
            "name": "desktop-aaaaaa",
            "os": {
                "type": "windows"
            }
        }
    }
    	
	```


=== "test_malop.json"

    ```json
	
    {
        "message": "{\n  \"@class\": \".MalopInboxModel\",\n  \"guid\": \"11.-6654920844431693523\",\n  \"displayName\": \"cymulateagent.exe\",\n  \"rootCauseElementType\": \"Process\",\n  \"primaryRootCauseName\": \"cymulateagent.exe\",\n  \"rootCauseElementNamesCount\": 1,\n  \"detectionEngines\": [\n    \"EDR\"\n  ],\n  \"detectionTypes\": [\n    \"Custom Malware\"\n  ],\n  \"malopDetectionType\": \"CUSTOM_RULE\",\n  \"creationTime\": 1668333388300,\n  \"lastUpdateTime\": 1668945737625,\n  \"iconBase64\": \"iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAADsMAAA7DAcdvqGQAAAIISURBVFhHxdS/K8RxHMfxQxaKbrnBjwXjWW3UTSZlEMk/oAxs/gQZRdkoUmYGGSyXhVXM6m5RiiLDxZ3n+9P7XZ++vQnfj+5Vj7rh+3m9vnffuyvkTd/cpehEBSd4RhMP2Mc4wnXJo8UdWEIdLccNppD2JqwQE6jBGzfXGIKeThApg7z7HXijMXkkKwjnkkTL+nEFbzTrCPJd0YackSKUcAtvMOsU3dCGnJEi9OAC3mDWLsK5JLEyrMMbjL1hFuluQKKFg6jCGzYH6IWeTBQpVGWcoYF4+BV7GEC49sd5Kg+bIiaxgBmMoQvhOitGEfPYwiE2MQ35nvxpXEZksIoXfKCBe2yghHCtxYYg/w+/G7VYKRbxiJajiWPIp6MnE0UKMYI7eOPmHWsIZ5LEyrAMeZfecOwSfdCGnJEitQ1vMKuOUWhDzkiR+ukN1PAvN9CeRyCRMrTnSyixQrTnZyiRUvz6j2i1cm467PWfY+X49q84Gi1iHls4xCam0YN8N/NVrBhlnKGBVuQVexhA+pvQ0kFUEQ9nHaAXejJBpEytwxuNvWEW4UySaJk83wt4o1m7SH4DJdzCG8w6RTe0IWekCP24gjeYdYROaEPOSBHk974DbzDWxArCuSSxMkygBm/YXGMIejpRpBDyKSyhDm/8BlMI1yePFsuzreAEz5CP/AH7GMcX44XCJ3XZVwZHImRNAAAAAElFTkSuQmCC\",\n  \"priority\": \"HIGH\",\n  \"group\": \"\",\n  \"rootCauseElementHashes\": \"\",\n  \"status\": \"Active\",\n  \"severity\": \"High\",\n  \"machines\": [\n    {\n      \"@class\": \".MachineInboxModel\",\n      \"guid\": \"-576002811.1198775089551518743\",\n      \"displayName\": \"win-cybereason\",\n      \"osType\": \"WINDOWS\",\n      \"connected\": true,\n      \"isolated\": false,\n      \"lastConnected\": 1669369715023,\n      \"empty\": true\n    }\n  ],\n  \"users\": [\n    {\n      \"guid\": \"0.2548072792133848559\",\n      \"displayName\": \"win-cybereason\\\\administrator\",\n      \"admin\": true,\n      \"localSystem\": false,\n      \"domainUser\": false\n    }\n  ],\n  \"containers\": [],\n  \"labels\": [],\n  \"decisionStatuses\": [],\n  \"malopCloseTime\": null,\n  \"closerName\": null,\n  \"malopType\": \"CUSTOM_RULE\",\n  \"escalated\": false,\n  \"malopPriority\": \"HIGH\",\n  \"edr\": true,\n  \"malopStatus\": \"Active\",\n  \"malopSeverity\": \"High\",\n  \"closed\": false,\n  \"empty\": true\n}\n",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ],
            "code": "malop"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "process": {
            "name": "cymulateagent.exe"
        },
        "cybereason": {
            "malop": {
                "id": "11.-6654920844431693523",
                "status": "Active",
                "priority": "HIGH",
                "severity": "High",
                "detection": {
                    "type": "CUSTOM_RULE",
                    "engines": [
                        "EDR"
                    ]
                },
                "root_cause": {
                    "type": "Process",
                    "name": "cymulateagent.exe"
                },
                "is_edr": "true",
                "created_at": "2022-11-13T09:56:28.300000Z",
                "modified_at": "2022-11-20T12:02:17.625000Z"
            }
        }
    }
    	
	```


=== "test_malop_detail.json"

    ```json
	
    {
        "message": "{\n  \"@class\": \".DetectionMalopDetailsModel\",\n  \"guid\": \"11.7498520112250262440\",\n  \"displayName\": \"kprocesshacker.sys\",\n  \"rootCauseElementType\": \"File\",\n  \"primaryRootCauseName\": \"kprocesshacker.sys\",\n  \"rootCauseElementNamesCount\": 1,\n  \"detectionEngines\": [\n    \"AntiVirus\"\n  ],\n  \"detectionTypes\": [\n    \"Known malware detected by Cybereason Anti-Malware\"\n  ],\n  \"malopDetectionType\": \"KNOWN_MALWARE\",\n  \"creationTime\": 1668357472339,\n  \"lastUpdateTime\": 1668392385000,\n  \"iconBase64\": \"\",\n  \"priority\": \"HIGH\",\n  \"group\": \"\",\n  \"rootCauseElementHashes\": \"adc83b19e793491b1c6ea0fd8b46cd9f32e592fc\",\n  \"status\": \"Active\",\n  \"severity\": \"High\",\n  \"machines\": [\n    {\n      \"@class\": \".MachineDetailsModel\",\n      \"guid\": \"-576002811.1198775089551518743\",\n      \"displayName\": \"desktop-aaaaaa\",\n      \"osType\": \"WINDOWS\",\n      \"connected\": false,\n      \"isolated\": false,\n      \"lastConnected\": 1668439428578,\n      \"adOU\": null,\n      \"adOrganization\": null,\n      \"adDisplayName\": \"DESKTOP-AAAAAA\",\n      \"adDNSHostName\": \"desktop-aaaaaa.example.org\",\n      \"adDepartment\": null,\n      \"adCompany\": null,\n      \"adLocation\": null,\n      \"adMachineRole\": null,\n      \"pylumId\": \"MARVELCLIENT_INTEGRATION_DESKTOP-AAAAAA_000000000000\",\n      \"empty\": true\n    }\n  ],\n  \"users\": [\n    {\n      \"guid\": \"0.2548072792133848559\",\n      \"displayName\": \"desktop-aaaaa\\\\system\",\n      \"admin\": false,\n      \"localSystem\": false,\n      \"domainUser\": false\n    }\n  ],\n  \"containers\": [],\n  \"labels\": [],\n  \"decisionStatuses\": [\n    \"Detected\"\n  ],\n  \"malopCloseTime\": null,\n  \"closerName\": null,\n  \"signer\": null,\n  \"fileClassificationType\": \"av_detected\",\n  \"filePaths\": [\n    \"c:\\\\System\\\\kprocesshacker.sys\"\n  ],\n  \"commandLines\": [],\n  \"decodedCommandLines\": [],\n  \"detectionValues\": [\n    \"Generic.ASP.WebShell.AH.B7A2B560\"\n  ],\n  \"detectionValueTypes\": [\n    \"DVT_FILE\"\n  ],\n  \"fileHash\": \"adc83b19e793491b1c6ea0fd8b46cd9f32e592fc\",\n  \"scriptDetectionTypes\": [],\n  \"exploitDetectionTypes\": [],\n  \"descriptions\": [\n    \"Known malware with file name kprocesshacker.sys was detected\"\n  ],\n  \"hasAnyScanEvent\": false,\n  \"activeProcessesCount\": 0,\n  \"totalProcessesCount\": 0,\n  \"fileSuspects\": [\n    {\n      \"@class\": \".FileSuspectDetailsModel\",\n      \"firstSeen\": 1657923190000,\n      \"lastSeen\": 1667946935000,\n      \"counter\": 2,\n      \"wasEverDetectedInScan\": false,\n      \"wasEverDetectedByAccess\": true,\n      \"detectionDecisionStatus\": \"DDS_PREVENTED\",\n      \"guid\": \"11.7498520112250262440\",\n      \"ownerMachineName\": \"desktop-aaaaaa\",\n      \"ownerMachineGuid\": \"aaaaaaaaaaaaaaaa\",\n      \"sha1String\": \"adc83b19e793491b1c6ea0fd8b46cd9f32e592fc\",\n      \"behaviourIdString\": null,\n      \"correctedPath\": \"c:\\\\System\\\\kprocesshacker.sys\",\n      \"modifiedTime\": null,\n      \"elementDisplayName\": \"kprocesshacker.sys\"\n    }\n  ],\n  \"processSuspects\": null,\n  \"processes\": null,\n  \"files\": [\n    {\n      \"@class\": \".FileDetailsModel\",\n      \"lastDetectionDecisionStatus\": \"DDS_UNKNOWN\",\n      \"guid\": \"11.7498520112250262440\",\n      \"ownerMachineName\": \"desktop-aaaaaa\",\n      \"ownerMachineGuid\": \"aaaaaaaaaaaaaaaa\",\n      \"sha1String\": \"adc83b19e793491b1c6ea0fd8b46cd9f32e592fc\",\n      \"correctedPath\": \"c:\\\\System\\\\kprocesshacker.sys\",\n      \"modifiedTime\": null,\n      \"elementDisplayName\": \"kprocesshacker.sys\",\n      \"behaviourIdString\": null,\n      \"quarantined\": false\n    }\n  ],\n  \"connections\": null,\n  \"timelineEvents\": [\n    {\n      \"@class\": \".MalopStartTimelineEventModel\",\n      \"timestamp\": 1657923190000,\n      \"data\": {\n        \"detectionTypes\": [\n          \"Known malware detected by Cybereason Anti-Malware\"\n        ],\n        \"detectionEngines\": [\n          \"AntiVirus\"\n        ]\n      },\n      \"type\": \"malopStart\"\n    },\n    {\n      \"@class\": \".DetectionEventFirstSeenTimelineEventModel\",\n      \"timestamp\": 1657923190000,\n      \"data\": {\n        \"machineName\": \"sthq-mimikatz\",\n        \"osType\": \"WINDOWS\",\n        \"connected\": true,\n        \"detectionsCount\": 2,\n        \"prevented\": false\n      },\n      \"type\": \"detectionEventFirstSeen\"\n    },\n    {\n      \"@class\": \".SuspicionTimelineEventModel\",\n      \"timestamp\": 1657923198032,\n      \"data\": {\n        \"suspicion\": \"Malicious by Anti-Malware\",\n        \"activityType\": \"MALICIOUS_INFECTION\"\n      },\n      \"type\": \"suspicion\"\n    }\n  ],\n  \"payloads\": [],\n  \"escalated\": false,\n  \"edr\": false,\n  \"malopStatus\": \"Closed\",\n  \"malopSeverity\": \"Low\",\n  \"malopType\": \"KNOWN_MALWARE\",\n  \"malopPriority\": \"HIGH\",\n  \"closed\": false,\n  \"empty\": true\n}\n",
        "event": {
            "kind": "alert",
            "category": [
                "malware"
            ],
            "type": [
                "info"
            ],
            "code": "malop"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-14T02:19:45.000000Z",
        "file": {
            "name": "kprocesshacker.sys",
            "hash": {
                "sha1": "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"
            }
        },
        "cybereason": {
            "malop": {
                "id": "11.7498520112250262440",
                "status": "Closed",
                "priority": "HIGH",
                "severity": "Low",
                "detection": {
                    "type": "KNOWN_MALWARE",
                    "engines": [
                        "AntiVirus"
                    ]
                },
                "root_cause": {
                    "type": "File",
                    "name": "kprocesshacker.sys"
                },
                "is_edr": "false",
                "created_at": "2022-11-13T16:37:52.339000Z",
                "modified_at": "2022-11-14T02:19:45.000000Z"
            }
        },
        "related": {
            "hash": [
                "adc83b19e793491b1c6ea0fd8b46cd9f32e592fc"
            ]
        }
    }
    	
	```


=== "test_suspicions.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\n    \"malopGuid\": \"11.7498520112250262440\",\n    \"timestamp\": \"1668945737625\"},\n  \"@class\": \".SuspicionModel\",\n  \"guid\": 1495442710604,\n  \"name\": \"shellOfNonShellRunnerSuspicion\",\n  \"firstTimestamp\": 1447276254985,\n  \"evidences\": [\n    \"detectedInjectedEvidence\",\n    \"highUnresolvedToResolvedRateEvidence\",\n    \"hostingInjectedThreadEvidence\",\n    \"manyUnresolvedRecordNotExistsEvidence\"\n  ]\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "code": "suspicion"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.7498520112250262440",
                "suspicion": {
                    "id": "1495442710604",
                    "name": "shellOfNonShellRunnerSuspicion",
                    "evidences": [
                        "detectedInjectedEvidence",
                        "highUnresolvedToResolvedRateEvidence",
                        "hostingInjectedThreadEvidence",
                        "manyUnresolvedRecordNotExistsEvidence"
                    ]
                }
            }
        }
    }
    	
	```


=== "test_suspicions2.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\n    \"malopGuid\": \"11.7498520112250262440\",\n    \"timestamp\": \"1668945737625\"},\n  \"@class\": \".SuspicionModel\",\n  \"guid\": 1495442710604,\n  \"name\": \"T1060 - Registry Run Keys / Startup Folder : Autorun JavaScript Value\",\n  \"firstTimestamp\": 1447276254985,\n  \"evidences\": [\n    \"detectedInjectedEvidence\",\n    \"highUnresolvedToResolvedRateEvidence\",\n    \"hostingInjectedThreadEvidence\",\n    \"manyUnresolvedRecordNotExistsEvidence\"\n  ]\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "intrusion_detection"
            ],
            "type": [
                "info"
            ],
            "code": "suspicion"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.7498520112250262440",
                "suspicion": {
                    "id": "1495442710604",
                    "name": "T1060 - Registry Run Keys / Startup Folder : Autorun JavaScript Value",
                    "evidences": [
                        "detectedInjectedEvidence",
                        "highUnresolvedToResolvedRateEvidence",
                        "hostingInjectedThreadEvidence",
                        "manyUnresolvedRecordNotExistsEvidence"
                    ]
                }
            }
        },
        "threat": {
            "technique": {
                "id": "T1060",
                "name": "Registry Run Keys / Startup Folder"
            }
        }
    }
    	
	```


=== "test_user_inbox.json"

    ```json
	
    {
        "message": "{\n  \"metadata\": {\"malopGuid\": \"11.-6654920844431693523\", \"timestamp\": 1668945737625},\n  \"@class\": \".UserInboxModel\",\n  \"guid\": \"0.2548072792133848559\",\n  \"displayName\": \"desktop-aaaaa\\\\system\",\n  \"admin\": false,\n  \"localSystem\": false,\n  \"domainUser\": false\n}\n",
        "event": {
            "kind": "event",
            "category": [
                "session"
            ],
            "type": [
                "info"
            ],
            "code": "user"
        },
        "observer": {
            "vendor": "Cybereason",
            "product": "Cybereason"
        },
        "@timestamp": "2022-11-20T12:02:17.625000Z",
        "cybereason": {
            "malop": {
                "id": "11.-6654920844431693523",
                "user": {
                    "id": "0.2548072792133848559",
                    "is_admin": false
                }
            }
        },
        "user": {
            "name": "system",
            "domain": "desktop-aaaaa"
        },
        "related": {
            "user": [
                "system"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`cybereason.malop.closed_at` | `text` | The closing date of the MalOp |
|`cybereason.malop.created_at` | `text` | The creation date of the MalOp |
|`cybereason.malop.detection.engines` | `keyword` | The list of detection engines |
|`cybereason.malop.detection.type` | `keyword` | The type of the detection used for the MalOp |
|`cybereason.malop.file.decision.status_code` | `keyword` | The status code of the decision about the file |
|`cybereason.malop.file.id` | `keyword` | The identifier of the file in the Cybereason platform |
|`cybereason.malop.host.id` | `keyword` | The identifier of the machine in the Cybereason platform |
|`cybereason.malop.host.is_isolated` | `boolean` | Indicates whether the host is isolated from the network |
|`cybereason.malop.host.is_online` | `boolean` | Indicates whether the host is connected to the Cybereason platform |
|`cybereason.malop.id` | `keyword` | The identifier of the MalOp |
|`cybereason.malop.is_edr` | `text` | Indicates whether the MalOp originated from an EDR detection |
|`cybereason.malop.modified_at` | `text` | The modification date of the MalOp |
|`cybereason.malop.priority` | `text` | The priority of the MalOp |
|`cybereason.malop.root_cause.name` | `keyword` | The name of the root cause of the MalOp |
|`cybereason.malop.root_cause.type` | `keyword` | The type of the root cause of the MalOp |
|`cybereason.malop.severity` | `text` | The severity of the MalOp |
|`cybereason.malop.status` | `keyword` | The status of the MalOp |
|`cybereason.malop.suspicion.evidences` | `keyword` | The list of evidences associated to the suspicion |
|`cybereason.malop.suspicion.id` | `keyword` | The identifier of the suspicion |
|`cybereason.malop.suspicion.name` | `keyword` | The name of the suspicion |
|`cybereason.malop.user.id` | `keyword` | The identifier of the user in the Cybereason platform |
|`cybereason.malop.user.is_admin` | `boolean` | Indicates whether the user has admin role |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.sha1` | `keyword` | SHA1 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`host.domain` | `keyword` | Name of the directory the group is a member of. |
|`host.name` | `keyword` | Name of the host. |
|`host.os.type` | `keyword` | Which commercial OS family (one of: linux, macos, unix or windows). |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`process.hash.sha1` | `keyword` | SHA1 hash. |
|`process.name` | `keyword` | Process name. |
|`threat.technique.id` | `keyword` | Threat technique id. |
|`threat.technique.name` | `keyword` | Threat technique name. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.name` | `keyword` | Short name or login of the user. |

