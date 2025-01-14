
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `File monitoring` | Monitor files and devices activities |
| `Process monitoring` | Monitor process activities |
| `Process use of network` | Monitor network activities |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `file`, `iam`, `network`, `process` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "event_application_blocked.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::Application::Blocked\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"Controlled application blocked: Google Software Reporter Tool (Security tool)\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"APPLICATION_CONTROL\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "Controlled application blocked: Google Software Reporter Tool (Security tool)",
            "code": "Event::Endpoint::Application::Blocked",
            "category": [
                "file"
            ],
            "type": [
                "denied"
            ]
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "process": {
            "title": "Google Software Reporter Tool (Security tool)"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "APPLICATION_CONTROL"
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_disk_non_encrypted.json"

    ```json
	
    {
        "message": "{\"severity\":\"medium\",\"type\":\"Event::Endpoint::Enc::DiskNotEncryptedEvent\",\"name\":\"Device is not encrypted.\",\"id\":\"f7c7e65a-a452-429c-9e0a-cdc16c5b50e9\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"DENC\",\"datastream\":\"event\",\"end\":\"2022-04-27T13:23:07.981Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T13:24:08.662Z\",\"duid\":\"574fcff42ead810f5e43b0fc\",\"suser\":\"Elon Musk\"}",
        "event": {
            "end": "2022-04-27T13:23:07.981Z",
            "kind": "event",
            "reason": "Device is not encrypted.",
            "code": "Event::Endpoint::Enc::DiskNotEncryptedEvent",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T13:24:08.662000Z",
        "user": {
            "id": "574fcff42ead810f5e43b0fc",
            "name": "Elon Musk"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "medium"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DENC"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "Elon Musk"
            ]
        }
    }
    	
	```


=== "event_dlp_allowed.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::DataLossPreventionAutomaticallyAllowed\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"An \u2033allow file transfer\u2033 action was taken.  Username: DDDDD\\\\XXXXXXXXXX  Rule names: \u2032Multimedia file\u2032  User action: File open  Application Name: Firefox (V7 and higher)  Data Control action: Allow  File type: Media Container (TFT\u2215MPEG-4)  File size: 559316722  Source path: C:\\\\Users\\\\XXXXXXXX\\\\Downloads\\\\YYYYYYYYYYYYYYYYY.mp4\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"DATA_LOSS_PREVENTION\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "An \u2033allow file transfer\u2033 action was taken.  Username: DDDDD\\XXXXXXXXXX  Rule names: \u2032Multimedia file\u2032  User action: File open  Application Name: Firefox (V7 and higher)  Data Control action: Allow  File type: Media Container (TFT\u2215MPEG-4)  File size: 559316722  Source path: C:\\Users\\XXXXXXXX\\Downloads\\YYYYYYYYYYYYYYYYY.mp4",
            "code": "Event::Endpoint::DataLossPreventionAutomaticallyAllowed",
            "category": [
                "file"
            ],
            "type": [
                "allowed"
            ],
            "action": "allow file transfer"
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "file": {
            "path": "C:\\Users\\XXXXXXXX\\Downloads\\YYYYYYYYYYYYYYYYY.mp4",
            "size": 559316722
        },
        "rule": {
            "name": "Multimedia file"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DATA_LOSS_PREVENTION"
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_dlp_allowed_remote_storage.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::DataLossPreventionAutomaticallyAllowed\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"An \u2033allow file transfer\u2033 action was taken.  Username: DDDDD\\\\XXXXXXXXXX  Rule names: \u2032Multimedia file\u2032  User action: File open  Application Name: Firefox (V7 and higher)  Data Control action: Allow  File type: Media Container (TFT\u2215MPEG-4)  File size: 559316722  Source path: C:\\\\Users\\\\XXXXXXXX\\\\Downloads\\\\YYYYYYYYYYYYYYYYY.mp4  Destination path: D:\\\\XXXXXXXXXXXXXXX\\\\Documents\\\\Videos\\\\YYYYY.mp4  Destination type: Removable storage\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"DATA_LOSS_PREVENTION\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "An \u2033allow file transfer\u2033 action was taken.  Username: DDDDD\\XXXXXXXXXX  Rule names: \u2032Multimedia file\u2032  User action: File open  Application Name: Firefox (V7 and higher)  Data Control action: Allow  File type: Media Container (TFT\u2215MPEG-4)  File size: 559316722  Source path: C:\\Users\\XXXXXXXX\\Downloads\\YYYYYYYYYYYYYYYYY.mp4  Destination path: D:\\XXXXXXXXXXXXXXX\\Documents\\Videos\\YYYYY.mp4  Destination type: Removable storage",
            "code": "Event::Endpoint::DataLossPreventionAutomaticallyAllowed",
            "category": [
                "file"
            ],
            "type": [
                "allowed"
            ],
            "action": "allow file transfer"
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "file": {
            "path": "C:\\Users\\XXXXXXXX\\Downloads\\YYYYYYYYYYYYYYYYY.mp4",
            "size": 559316722
        },
        "rule": {
            "name": "Multimedia file"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DATA_LOSS_PREVENTION"
            },
            "destination": {
                "type": "Removable storage",
                "file": {
                    "path": "D:\\XXXXXXXXXXXXXXX\\Documents\\Videos\\YYYYY.mp4"
                }
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_encryption_information.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::Enc::DiskEncryptionInformation\",\"name\":\"Device Encryption information for volume with id: 63E6153A-3663-44E1-A200-F1CD4CB9EBCE. Message: Encryption has been postponed.\",\"id\":\"55726d81-213b-43b6-be18-48dee3add6f8\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"c0e1e239-8912-4cc9-a6ed-245a964dec10\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"DENC\",\"datastream\":\"event\",\"end\":\"2022-04-27T08:48:48.808Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T08:48:48.809Z\",\"duid\":\"62690353b62561118508746f\",\"suser\":\"TESLA\\\\user\"}",
        "event": {
            "end": "2022-04-27T08:48:48.808Z",
            "kind": "event",
            "reason": "Device Encryption information for volume with id: 63E6153A-3663-44E1-A200-F1CD4CB9EBCE. Message: Encryption has been postponed.",
            "code": "Event::Endpoint::Enc::DiskEncryptionInformation",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T08:48:48.809000Z",
        "user": {
            "id": "62690353b62561118508746f",
            "name": "user",
            "domain": "TESLA"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "c0e1e239-8912-4cc9-a6ed-245a964dec10"
            },
            "event": {
                "group": "DENC"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "user"
            ]
        }
    }
    	
	```


=== "event_encryption_suspended.json"

    ```json
	
    {
        "message": "{\"severity\":\"medium\",\"type\":\"Event::Endpoint::Denc::EncryptionSuspendedEvent\",\"name\":\"Device Encryption is suspended\",\"id\":\"80130549-e09e-46d3-ab98-919fbd625884\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"DENC\",\"datastream\":\"event\",\"end\":\"2022-04-27T08:47:16.490Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T08:48:19.320Z\",\"duid\":\"624aabf253f2e60fda590556\",\"suser\":\"TESLA\\\\admin\"}",
        "event": {
            "end": "2022-04-27T08:47:16.490Z",
            "kind": "event",
            "reason": "Device Encryption is suspended",
            "code": "Event::Endpoint::Denc::EncryptionSuspendedEvent",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T08:48:19.320000Z",
        "user": {
            "id": "624aabf253f2e60fda590556",
            "name": "admin",
            "domain": "TESLA"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "medium"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DENC"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "admin"
            ]
        }
    }
    	
	```


=== "event_exploit_prevention.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::HmpaExploitPrevented\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"'CodeCave' exploit prevented in Essential Objects Worker Process\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"RUNTIME_DETECTIONS\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "'CodeCave' exploit prevented in Essential Objects Worker Process",
            "code": "Event::Endpoint::HmpaExploitPrevented",
            "category": [
                "file"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "RUNTIME_DETECTIONS"
            },
            "threat": {
                "name": "CodeCave"
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_key_received.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::Enc::Recovery::KeyReceived\",\"name\":\"A BitLocker recovery key has been received from: DESKTOP-1234.\",\"id\":\"c8e0b5c9-69d0-4885-8964-5cefaa8ef13e\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"DENC\",\"datastream\":\"event\",\"end\":\"2022-04-27T13:22:08.749Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T13:22:13.565Z\",\"duid\":\"574fcff42ead810f5e43b0fc\",\"suser\":\"admin tech\"}",
        "event": {
            "end": "2022-04-27T13:22:08.749Z",
            "kind": "event",
            "reason": "A BitLocker recovery key has been received from: DESKTOP-1234.",
            "code": "Event::Endpoint::Enc::Recovery::KeyReceived",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T13:22:13.565000Z",
        "user": {
            "id": "574fcff42ead810f5e43b0fc",
            "name": "admin tech"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DENC"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "admin tech"
            ]
        }
    }
    	
	```


=== "event_outlook_plugin.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::Denc::OutlookPluginEnabledEvent\",\"name\":\"Outlook add-in is enabled\",\"id\":\"37d8c083-2342-4e88-9da6-4f47e3143c9d\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"DENC\",\"datastream\":\"event\",\"end\":\"2022-04-27T13:22:06.909Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T13:22:13.226Z\",\"duid\":\"574fcff42ead810f5e43b0fc\",\"suser\":\"admin tech\"}",
        "event": {
            "end": "2022-04-27T13:22:06.909Z",
            "kind": "event",
            "reason": "Outlook add-in is enabled",
            "code": "Event::Endpoint::Denc::OutlookPluginEnabledEvent",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T13:22:13.226000Z",
        "user": {
            "id": "574fcff42ead810f5e43b0fc",
            "name": "admin tech"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "DENC"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "admin tech"
            ]
        }
    }
    	
	```


=== "event_pua_detected.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::CorePuaDetection\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"PUA detected: 'Rule Generic PUA' at 'C:\\\\Users\\\\XXXXXXXXXX\\\\AppData\\\\Local\\\\Microsoft\\\\SquirrelTemp\\\\tempc'\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"PUA\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "PUA detected: 'Rule Generic PUA' at 'C:\\Users\\XXXXXXXXXX\\AppData\\Local\\Microsoft\\SquirrelTemp\\tempc'",
            "code": "Event::Endpoint::CorePuaDetection",
            "category": [
                "file"
            ],
            "type": [
                "info"
            ],
            "action": "detected"
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "file": {
            "path": "C:\\Users\\XXXXXXXXXX\\AppData\\Local\\Microsoft\\SquirrelTemp\\tempc"
        },
        "rule": {
            "name": "Rule Generic PUA"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "PUA"
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_registered.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::Registered\",\"name\":\"New computer registered: DESKTOP-1234\",\"id\":\"b3c9c053-6037-469d-9bee-49d39f7932d0\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"PROTECTION\",\"datastream\":\"event\",\"end\":\"2022-04-27T13:17:10.188Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T13:17:10.197Z\",\"duid\":\"574fcff42ead810f5e43b0fc\",\"suser\":\"admin tech\"}",
        "event": {
            "end": "2022-04-27T13:17:10.188Z",
            "kind": "event",
            "reason": "New computer registered: DESKTOP-1234",
            "code": "Event::Endpoint::Registered",
            "category": [
                "iam"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T13:17:10.197000Z",
        "user": {
            "id": "574fcff42ead810f5e43b0fc",
            "name": "admin tech"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "PROTECTION"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "admin tech"
            ]
        }
    }
    	
	```


=== "event_scan_complete.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::SavScanComplete\",\"name\":\"Scan 'Sophos Cloud Scheduled Scan' completed\",\"id\":\"fca84bd1-44df-4c30-ab79-103b971e714a\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"92d4ef41-9c13-4041-bbed-952011796812\",\"endpoint_type\":\"computer\",\"group\":\"PROTECTION\",\"datastream\":\"event\",\"end\":\"2022-04-27T08:59:59.000Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T09:00:03.548Z\",\"duid\":\"611cda48cf87290e90dfc1d1\",\"suser\":\"Elon Musk\"}",
        "event": {
            "end": "2022-04-27T08:59:59.000Z",
            "kind": "event",
            "reason": "Scan 'Sophos Cloud Scheduled Scan' completed",
            "code": "Event::Endpoint::SavScanComplete",
            "category": [
                "iam"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-27T09:00:03.548000Z",
        "user": {
            "id": "611cda48cf87290e90dfc1d1",
            "name": "Elon Musk"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "92d4ef41-9c13-4041-bbed-952011796812"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "PROTECTION"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "Elon Musk"
            ]
        }
    }
    	
	```


=== "event_update_failure.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::UpdateFailure\",\"endpoint_type\":\"server\",\"endpoint_id\":\"350e274b-777f-4b67-b34b-10d17a6c6193\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"Download of WindowsCloudServer failed from server http:\u2215\u2215dci.sophosupd.com.\",\"id\":\"f68abcb6-c87f-46ae-a82a-7919bf313a66\",\"group\":\"UPDATING\",\"datastream\":\"event\",\"end\":\"2022-04-25T07:41:03.101Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T07:41:03.118Z\",\"dhost\":\"DESKTOP-1234\"}",
        "event": {
            "end": "2022-04-25T07:41:03.101Z",
            "kind": "event",
            "reason": "Download of WindowsCloudServer failed from server http:\u2215\u2215dci.sophosupd.com.",
            "code": "Event::Endpoint::UpdateFailure",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-25T07:41:03.118000Z",
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "server",
                "id": "350e274b-777f-4b67-b34b-10d17a6c6193"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "UPDATING"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_update_reboot_required.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::UpdateRebootRequired\",\"endpoint_type\":\"server\",\"endpoint_id\":\"5da7691b-cc01-4330-bb8b-358362c3a5f1\",\"source_info\":{\"ip\":\"1.2.3.4\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"Reboot to complete update; computer stays protected in the meantime\",\"id\":\"bc60c18b-dc21-43a3-bfd5-f28963f288e2\",\"group\":\"UPDATING\",\"datastream\":\"event\",\"end\":\"2022-04-25T03:15:31.760Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T03:15:31.777Z\",\"dhost\":\"DOMAIN-1234\"}",
        "event": {
            "end": "2022-04-25T03:15:31.760Z",
            "kind": "event",
            "reason": "Reboot to complete update; computer stays protected in the meantime",
            "code": "Event::Endpoint::UpdateRebootRequired",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-25T03:15:31.777000Z",
        "host": {
            "hostname": "DOMAIN-1234",
            "name": "DOMAIN-1234"
        },
        "observer": {
            "ip": "1.2.3.4"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "server",
                "id": "5da7691b-cc01-4330-bb8b-358362c3a5f1"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "UPDATING"
            }
        },
        "related": {
            "hosts": [
                "DOMAIN-1234"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_update_success.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::UpdateSuccess\",\"endpoint_type\":\"server\",\"endpoint_id\":\"2ddff78e-27a1-40ff-8478-6c9be62e3b29\",\"source_info\":{\"ip\":\"4.5.6.7\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"Update succeeded\",\"id\":\"a4c6776e-2f47-4bea-b5b3-7f1914c03a70\",\"group\":\"UPDATING\",\"datastream\":\"event\",\"end\":\"2022-04-25T04:57:09.886Z\",\"suser\":\"n/a\",\"rt\":\"2022-04-25T04:57:09.900Z\",\"dhost\":\"ACLOUD-2K22\"}",
        "event": {
            "end": "2022-04-25T04:57:09.886Z",
            "kind": "event",
            "reason": "Update succeeded",
            "code": "Event::Endpoint::UpdateSuccess",
            "category": [
                "file",
                "process"
            ],
            "type": [
                "info"
            ]
        },
        "@timestamp": "2022-04-25T04:57:09.900000Z",
        "host": {
            "hostname": "ACLOUD-2K22",
            "name": "ACLOUD-2K22"
        },
        "observer": {
            "ip": "4.5.6.7"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "server",
                "id": "2ddff78e-27a1-40ff-8478-6c9be62e3b29"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "UPDATING"
            }
        },
        "related": {
            "hosts": [
                "ACLOUD-2K22"
            ],
            "ip": [
                "4.5.6.7"
            ]
        }
    }
    	
	```


=== "event_user_auto_created.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::UserAutoCreated\",\"name\":\"New user added automatically: TESLA\\\\e.musk\",\"id\":\"1498e255-e9c1-4835-b0b9-8ae7b44ae6f7\",\"source_info\":{\"ip\":\"1.3.3.7\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"endpoint_type\":\"computer\",\"group\":\"PROTECTION\",\"datastream\":\"event\",\"end\":\"2022-04-27T08:48:19.449Z\",\"dhost\":\"DESKTOP-1234\",\"rt\":\"2022-04-27T08:48:19.456Z\",\"duid\":\"62690353b62561118508746f\",\"suser\":\"TESLA\\\\e.musk\"}",
        "event": {
            "end": "2022-04-27T08:48:19.449Z",
            "kind": "event",
            "reason": "New user added automatically: TESLA\\e.musk",
            "code": "Event::Endpoint::UserAutoCreated",
            "category": [
                "iam"
            ],
            "type": [
                "creation"
            ]
        },
        "@timestamp": "2022-04-27T08:48:19.456000Z",
        "user": {
            "id": "62690353b62561118508746f",
            "name": "e.musk",
            "domain": "TESLA"
        },
        "host": {
            "hostname": "DESKTOP-1234",
            "name": "DESKTOP-1234"
        },
        "observer": {
            "ip": "1.3.3.7"
        },
        "log": {
            "level": "low"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "PROTECTION"
            }
        },
        "related": {
            "hosts": [
                "DESKTOP-1234"
            ],
            "ip": [
                "1.3.3.7"
            ],
            "user": [
                "e.musk"
            ]
        }
    }
    	
	```


=== "event_webfiltering.json"

    ```json
	
    {
        "message": "{\"severity\":\"low\",\"type\":\"Event::Endpoint::WebFilteringBlocked\",\"endpoint_type\":\"computer\",\"endpoint_id\":\"3205420f-f05c-4f03-bb10-3ff6bf97b6ab\",\"source_info\":{\"ip\":\"1.3.3.7\"},\"customer_id\":\"36d5cd97-169e-490b-a2c4-bcd9d5d2a54b\",\"name\":\"Access was blocked to \\\"www.malicious-site.com\\\" because of \\\"Rulename\\\".\",\"id\":\"a91e11e2-1739-4f01-bf33-2dfd165e5ca3\",\"group\":\"WEB\",\"datastream\":\"event\",\"end\":\"2022-04-25T09:35:54.000Z\",\"suser\":\"Elon Musk\",\"rt\":\"2022-04-25T09:35:55.764Z\",\"duid\":\"615ff633eae9110e824c07b7\",\"dhost\":\"TESLA-SUPPORT\"}",
        "event": {
            "end": "2022-04-25T09:35:54.000Z",
            "kind": "event",
            "reason": "Access was blocked to \"www.malicious-site.com\" because of \"Rulename\".",
            "code": "Event::Endpoint::WebFilteringBlocked",
            "category": [
                "network"
            ],
            "type": [
                "denied"
            ]
        },
        "@timestamp": "2022-04-25T09:35:55.764000Z",
        "user": {
            "id": "615ff633eae9110e824c07b7",
            "name": "Elon Musk"
        },
        "host": {
            "hostname": "TESLA-SUPPORT",
            "name": "TESLA-SUPPORT"
        },
        "observer": {
            "ip": "1.3.3.7"
        },
        "log": {
            "level": "low"
        },
        "rule": {
            "name": "Rulename"
        },
        "url": {
            "original": "www.malicious-site.com",
            "path": "www.malicious-site.com"
        },
        "sophos": {
            "endpoint": {
                "type": "computer",
                "id": "3205420f-f05c-4f03-bb10-3ff6bf97b6ab"
            },
            "customer": {
                "id": "36d5cd97-169e-490b-a2c4-bcd9d5d2a54b"
            },
            "event": {
                "group": "WEB"
            }
        },
        "related": {
            "hosts": [
                "TESLA-SUPPORT"
            ],
            "ip": [
                "1.3.3.7"
            ],
            "user": [
                "Elon Musk"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.end` | `date` | event.end contains the date when the event ended or when the activity was last observed. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`file.size` | `long` | File size in bytes. |
|`host.hostname` | `keyword` | Hostname of the host. |
|`host.name` | `keyword` | Name of the host. |
|`log.level` | `keyword` | Log level of the log event. |
|`observer.ip` | `ip` | IP addresses of the observer. |
|`process.title` | `keyword` | Process title. |
|`rule.name` | `keyword` | Rule name |
|`sophos.customer.id` | `keyword` | The identifier of the customer |
|`sophos.destination.file.path` | `keyword` | The path of a destination transfert |
|`sophos.destination.type` | `keyword` | The type of a destination transfert |
|`sophos.endpoint.id` | `keyword` | The identifier of the endpoint |
|`sophos.endpoint.type` | `keyword` | The type of the endpoint |
|`sophos.event.group` | `keyword` | The family of the event |
|`sophos.threat.name` | `keyword` | The name of the detected threat |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user.domain` | `keyword` | Name of the directory the user is a member of. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |

