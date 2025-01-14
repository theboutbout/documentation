
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `OAuth audit logs` | Okta System log provides audit logs about Oauth2 requests, grant and revocation |
| `Authentication logs` | Okta System log provides audit logs about authentication sessions |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `authentication`, `iam`, `session` |
| Type | `change`, `start` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "test_auth_via_idp.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"7a353625-99c9-435b-a4b6-b1137a5e6edb\",\n  \"actor\": {\n    \"id\": \"2pHxMaUZr2yoej9R2Lsf4\",\n    \"type\": \"SystemPrincipal\",\n    \"alternateId\": \"system@okta.com\",\n    \"detailEntry\": null,\n    \"displayName\": \"Okta System\"\n  },\n  \"client\": {\n    \"id\": null,\n    \"zone\": \"null\",\n    \"device\": \"Computer\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Windows 10\",\n      \"browser\": \"CHROME\",\n      \"rawUserAgent\": \"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": null,\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"kdYO9RZnIHNhV6vii333b\",\n      \"type\": \"AppInstance\",\n      \"alternateId\": \"Org2org\",\n      \"detailEntry\": null,\n      \"displayName\": \"SAML 2.0 IdP\"\n    },\n    {\n      \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"User\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": null,\n    \"result\": \"SUCCESS\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"user.authentication.auth_via_IDP\",\n  \"published\": \"2022-11-15T08:04:22.213Z\",\n  \"transaction\": {\n    \"id\": \"jI80snAs0ZMym5tvc8Jbp\",\n    \"type\": \"WEB\",\n    \"detail\": {}\n  },\n  \"displayMessage\": \"Authenticate user via IDP\",\n  \"legacyEventType\": \"core.user_auth.idp.saml.login_success\",\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": \"IDP Instance\",\n    \"credentialType\": \"ASSERTION\",\n    \"externalSessionId\": \"kjrgFtXuZnABQV9Vq1A2c\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": null,\n    \"authenticationProvider\": \"FEDERATION\"\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.authentication.auth_via_IDP",
            "reason": "Authenticate user via IDP",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-11-15T08:04:22.213Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "eWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36",
            "name": "Chrome"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "2pHxMaUZr2yoej9R2Lsf4",
                    "type": "SystemPrincipal",
                    "alternate_id": "system@okta.com",
                    "display_name": "Okta System"
                },
                "transaction": {
                    "id": "jI80snAs0ZMym5tvc8Jbp",
                    "type": "WEB"
                },
                "authentication_context": {
                    "interface": "IDP Instance",
                    "authentication": {
                        "provider": "FEDERATION"
                    },
                    "credential": {
                        "type": "ASSERTION"
                    },
                    "external_session_id": "kjrgFtXuZnABQV9Vq1A2c"
                },
                "outcome": {
                    "result": "SUCCESS"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
            ]
        }
    }
    	
	```


=== "test_auth_via_mfa.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"cb9a43c9-a765-49ba-b2d5-7b9a263d4061\",\n  \"actor\": {\n    \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n    \"type\": \"User\",\n    \"alternateId\": \"john.doe@example.org\",\n    \"detailEntry\": null,\n    \"displayName\": \"John Doe\"\n  },\n  \"client\": {\n    \"id\": null,\n    \"zone\": \"null\",\n    \"device\": \"Computer\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Windows 10\",\n      \"browser\": \"CHROME\",\n      \"rawUserAgent\": \"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": \"75000\",\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"User\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    },\n    {\n      \"id\": \"kdYO9RZnIHNhV6vii333b\",\n      \"type\": \"AuthenticatorEnrollment\",\n      \"alternateId\": \"unknown\",\n      \"detailEntry\": {\n        \"methodTypeUsed\": \"Password\",\n        \"methodUsedVerifiedProperties\": \"[USER_PRESENCE]\"\n      },\n      \"displayName\": \"Password\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": null,\n    \"result\": \"SUCCESS\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"user.authentication.auth_via_mfa\",\n  \"published\": \"2022-11-02T12:00:00.000Z\",\n  \"transaction\": {\n    \"id\": \"jI80snAs0ZMym5tvc8Jbp\",\n    \"type\": \"WEB\",\n    \"detail\": {}\n  },\n  \"displayMessage\": \"Authentication of user via MFA\",\n  \"legacyEventType\": \"core.user.factor.attempt_success\",\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": null,\n    \"credentialType\": null,\n    \"externalSessionId\": \"kjrgFtXuZnABQV9Vq1A2c\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": \"OKTA_CREDENTIAL_PROVIDER\",\n    \"authenticationProvider\": \"FACTOR_PROVIDER\"\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.authentication.auth_via_mfa",
            "reason": "Authentication of user via MFA",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-11-02T12:00:00.000Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "postal_code": "75000",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "eWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36",
            "name": "Chrome"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "eWiaLPtSTpjyy1BIwNFXg",
                    "type": "User",
                    "alternate_id": "john.doe@example.org",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "jI80snAs0ZMym5tvc8Jbp",
                    "type": "WEB"
                },
                "authentication_context": {
                    "authentication": {
                        "provider": "FACTOR_PROVIDER"
                    },
                    "credential": {
                        "provider": "OKTA_CREDENTIAL_PROVIDER"
                    },
                    "external_session_id": "kjrgFtXuZnABQV9Vq1A2c"
                },
                "outcome": {
                    "result": "SUCCESS"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
            ]
        }
    }
    	
	```


=== "test_authentication_sso.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"ea4adf13-1469-4059-9d2c-7cfdb464b123\",\n  \"actor\": {\n    \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n    \"type\": \"User\",\n    \"alternateId\": \"john.doe@example.org\",\n    \"detailEntry\": null,\n    \"displayName\": \"John Doe\"\n  },\n  \"client\": {\n    \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n    \"zone\": \"null\",\n    \"device\": \"Unknown\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Unknown\",\n      \"browser\": \"UNKNOWN\",\n      \"rawUserAgent\": \"axios/0.19.2\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": null,\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"kdYO9RZnIHNhV6vii333b\",\n      \"type\": \"AppInstance\",\n      \"alternateId\": \"Architecture Website\",\n      \"detailEntry\": {\n        \"signOnModeType\": \"OPENID_CONNECT\"\n      },\n      \"displayName\": \"OpenID Connect Client\"\n    },\n    {\n      \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"AppUser\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": null,\n    \"result\": \"SUCCESS\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"user.authentication.sso\",\n  \"published\": \"2022-11-15T08:05:07.656Z\",\n  \"transaction\": {\n    \"id\": \"jI80snAs0ZMym5tvc8Jbp\",\n    \"type\": \"WEB\",\n    \"detail\": {}\n  },\n  \"displayMessage\": \"User single sign on to app\",\n  \"legacyEventType\": \"app.auth.sso\",\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": null,\n    \"credentialType\": null,\n    \"externalSessionId\": \"unknown\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": null,\n    \"authenticationProvider\": null\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.authentication.sso",
            "reason": "User single sign on to app",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-11-15T08:05:07.656Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "user": {
                "id": "eWiaLPtSTpjyy1BIwNFXg"
            },
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "eWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "axios/0.19.2"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "eWiaLPtSTpjyy1BIwNFXg",
                    "type": "User",
                    "alternate_id": "john.doe@example.org",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "jI80snAs0ZMym5tvc8Jbp",
                    "type": "WEB"
                },
                "outcome": {
                    "result": "SUCCESS"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
            ]
        }
    }
    	
	```


=== "test_authentication_sso_failure.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"fa4adf13-1469-4059-9d2c-7cfdb464b123\",\n  \"actor\": {\n    \"id\": \"fWiaLPtSTpjyy1BIwNFXg\",\n    \"type\": \"User\",\n    \"alternateId\": \"john.doe@example.org\",\n    \"detailEntry\": null,\n    \"displayName\": \"John Doe\"\n  },\n  \"client\": {\n    \"id\": \"fWiaLPtSTpjyy1BIwNFXg\",\n    \"zone\": \"null\",\n    \"device\": \"Unknown\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Unknown\",\n      \"browser\": \"UNKNOWN\",\n      \"rawUserAgent\": \"axios/0.19.2\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": null,\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"kdYO9RZnIHNhV6vii333b\",\n      \"type\": \"AppInstance\",\n      \"alternateId\": \"Architecture Website\",\n      \"detailEntry\": {\n        \"signOnModeType\": \"OPENID_CONNECT\"\n      },\n      \"displayName\": \"OpenID Connect Client\"\n    },\n    {\n      \"id\": \"fWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"AppUser\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": \"INVALID_CREDENTIALS\",\n    \"result\": \"FAILURE\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"user.authentication.sso\",\n  \"published\": \"2022-12-16T17:05:07.656Z\",\n  \"transaction\": {\n    \"id\": \"jI80snAs0ZMym5tvc8Jbp\",\n    \"type\": \"WEB\",\n    \"detail\": {}\n  },\n  \"displayMessage\": \"User single sign on to app\",\n  \"legacyEventType\": \"app.auth.sso\",\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": null,\n    \"credentialType\": null,\n    \"externalSessionId\": \"unknown\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": null,\n    \"authenticationProvider\": null\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.authentication.sso",
            "reason": "User single sign on to app",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-12-16T17:05:07.656Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "user": {
                "id": "fWiaLPtSTpjyy1BIwNFXg"
            },
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "fWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "axios/0.19.2"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "fWiaLPtSTpjyy1BIwNFXg",
                    "type": "User",
                    "alternate_id": "john.doe@example.org",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "jI80snAs0ZMym5tvc8Jbp",
                    "type": "WEB"
                },
                "outcome": {
                    "reason": "INVALID_CREDENTIALS",
                    "result": "FAILURE"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
            ]
        }
    }
    	
	```


=== "test_login.json"

    ```json
	
    {
        "message": "{\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"client\": {\n    \"zone\": \"OFF_NETWORK\",\n    \"device\": \"Unknown\",\n    \"userAgent\": {\n      \"os\": \"Unknown\",\n      \"browser\": \"UNKNOWN\",\n      \"rawUserAgent\": \"UNKNOWN-DOWNLOAD\"\n    },\n    \"ipAddress\": \"12.97.85.90\"\n  },\n  \"actor\": {\n    \"id\": \"00u1qw1mqitPHM8AJ0g7\",\n    \"type\": \"User\",\n    \"alternateId\": \"admin@example.com\",\n    \"displayName\": \"John Doe\"\n  },\n  \"outcome\": {\n    \"result\": \"SUCCESS\"\n  },\n  \"uuid\": \"f790999f-fe87-467a-9880-6982a583986c\",\n  \"published\": \"2017-09-31T22:23:07.777Z\",\n  \"eventType\": \"user.session.start\",\n  \"displayMessage\": \"User login to Okta\",\n  \"transaction\": {\n    \"type\": \"WEB\",\n    \"id\": \"V04Oy4ubUOc5UuG6s9DyNQAABtc\"\n  },\n  \"debugContext\": {\n    \"debugData\": {\n      \"requestUri\": \"/login/do-login\"\n    }\n  },\n  \"legacyEventType\": \"core.user_auth.login_success\",\n  \"authenticationContext\": {\n    \"authenticationStep\": 0,\n    \"externalSessionId\": \"1013FfF-DKQSvCI4RVXChzX-w\"\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.session.start",
            "reason": "User login to Okta",
            "category": [
                "session"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2017-09-31T22:23:07.777Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "12.97.85.90",
            "address": "12.97.85.90"
        },
        "user": {
            "id": "00u1qw1mqitPHM8AJ0g7",
            "name": "admin@example.com",
            "email": "admin@example.com",
            "full_name": "John Doe"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "00u1qw1mqitPHM8AJ0g7",
                    "type": "User",
                    "alternate_id": "admin@example.com",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "V04Oy4ubUOc5UuG6s9DyNQAABtc",
                    "type": "WEB"
                },
                "outcome": {
                    "result": "SUCCESS"
                },
                "authentication_context": {
                    "external_session_id": "1013FfF-DKQSvCI4RVXChzX-w"
                }
            }
        },
        "related": {
            "ip": [
                "12.97.85.90"
            ],
            "user": [
                "admin@example.com"
            ]
        }
    }
    	
	```


=== "test_send_factor.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"d34ae6a4-b9d1-4885-b7ff-59e96829d5fc\",\n  \"actor\": {\n    \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n    \"type\": \"User\",\n    \"alternateId\": \"john.doe@example.org\",\n    \"detailEntry\": null,\n    \"displayName\": \"John Doe\"\n  },\n  \"client\": {\n    \"id\": null,\n    \"zone\": \"null\",\n    \"device\": \"Computer\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Windows 10\",\n      \"browser\": \"CHROME\",\n      \"rawUserAgent\": \"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": \"75000\",\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"User\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": null,\n    \"result\": \"SUCCESS\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"system.push.send_factor_verify_push\",\n  \"published\": \"2022-11-01T11:04:00.364Z\",\n  \"transaction\": {\n    \"id\": \"Y3NH1qHvAmGouHz6XfAtaQAABNU\",\n    \"type\": \"WEB\",\n    \"detail\": {}\n  },\n  \"displayMessage\": \"A push was sent to a user for verification\",\n  \"legacyEventType\": null,\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": null,\n    \"credentialType\": null,\n    \"externalSessionId\": \"kjrgFtXuZnABQV9Vq1A2c\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": null,\n    \"authenticationProvider\": null\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "system.push.send_factor_verify_push",
            "reason": "A push was sent to a user for verification",
            "category": [
                "authentication"
            ],
            "type": [
                "start"
            ]
        },
        "@timestamp": "2022-11-01T11:04:00.364Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "postal_code": "75000",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "eWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36",
            "name": "Chrome"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "eWiaLPtSTpjyy1BIwNFXg",
                    "type": "User",
                    "alternate_id": "john.doe@example.org",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "Y3NH1qHvAmGouHz6XfAtaQAABNU",
                    "type": "WEB"
                },
                "outcome": {
                    "result": "SUCCESS"
                },
                "authentication_context": {
                    "external_session_id": "kjrgFtXuZnABQV9Vq1A2c"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
            ]
        }
    }
    	
	```


=== "test_update_account.json"

    ```json
	
    {
        "message": "{\n  \"uuid\": \"b8d32533-0b5e-4081-b933-fb4433f25e95\",\n  \"actor\": {\n    \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n    \"type\": \"User\",\n    \"alternateId\": \"john.doe@example.org\",\n    \"detailEntry\": null,\n    \"displayName\": \"John Doe\"\n  },\n  \"client\": {\n    \"id\": null,\n    \"zone\": \"null\",\n    \"device\": \"Unknown\",\n    \"ipAddress\": \"1.2.3.4\",\n    \"userAgent\": {\n      \"os\": \"Unknown\",\n      \"browser\": \"UNKNOWN\",\n      \"rawUserAgent\": \"Okta-Integrations\"\n    },\n    \"geographicalContext\": {\n      \"city\": \"Paris\",\n      \"state\": \"Ile-de-France\",\n      \"country\": \"France\",\n      \"postalCode\": \"75000\",\n      \"geolocation\": {\n        \"lat\": 48.856944,\n        \"lon\": 2.351389\n      }\n    }\n  },\n  \"device\": null,\n  \"target\": [\n    {\n      \"id\": \"eWiaLPtSTpjyy1BIwNFXg\",\n      \"type\": \"User\",\n      \"alternateId\": \"john.doe@example.org\",\n      \"detailEntry\": null,\n      \"displayName\": \"John Doe\"\n    }\n  ],\n  \"outcome\": {\n    \"reason\": null,\n    \"result\": \"SUCCESS\"\n  },\n  \"request\": {\n    \"ipChain\": [\n      {\n        \"ip\": \"1.2.3.4\",\n        \"source\": null,\n        \"version\": \"V4\",\n        \"geographicalContext\": {\n          \"city\": \"Paris\",\n          \"state\": \"Ile-de-France\",\n          \"country\": \"France\",\n          \"postalCode\": null,\n          \"geolocation\": {\n            \"lat\": 48.856944,\n            \"lon\": 2.351389\n          }\n        }\n      }\n    ]\n  },\n  \"version\": \"0\",\n  \"severity\": \"INFO\",\n  \"eventType\": \"user.account.update_password\",\n  \"published\": \"2022-11-15T08:00:41.468Z\",\n  \"transaction\": {\n    \"id\": \"jI80snAs0ZMym5tvc8Jbp\",\n    \"type\": \"WEB\",\n    \"detail\": {\n      \"requestApiTokenId\": \"REDACTED\"\n    }\n  },\n  \"displayMessage\": \"User update password for Okta\",\n  \"legacyEventType\": \"core.user.config.password_update.success\",\n  \"securityContext\": {\n    \"isp\": \"Easttel\",\n    \"asOrg\": \"Easttel\",\n    \"domain\": \"example.org\",\n    \"isProxy\": false,\n    \"asNumber\": 3741\n  },\n  \"authenticationContext\": {\n    \"issuer\": null,\n    \"interface\": null,\n    \"credentialType\": null,\n    \"externalSessionId\": \"kjrgFtXuZnABQV9Vq1A2c\",\n    \"authenticationStep\": 0,\n    \"credentialProvider\": null,\n    \"authenticationProvider\": null\n  }\n}\n",
        "event": {
            "kind": "event",
            "dataset": "system-log",
            "action": "user.account.update_password",
            "reason": "User update password for Okta",
            "category": [
                "iam"
            ],
            "type": [
                "change"
            ]
        },
        "@timestamp": "2022-11-15T08:00:41.468Z",
        "observer": {
            "vendor": "Okta"
        },
        "source": {
            "ip": "1.2.3.4",
            "domain": "example.org",
            "as": {
                "number": 3741,
                "organization": {
                    "name": "Easttel"
                }
            },
            "geo": {
                "city_name": "Paris",
                "region_name": "Ile-de-France",
                "country_name": "France",
                "postal_code": "75000",
                "location": {
                    "lat": 48.856944,
                    "lon": 2.351389
                }
            },
            "address": "example.org",
            "top_level_domain": "org",
            "registered_domain": "example.org"
        },
        "user": {
            "id": "eWiaLPtSTpjyy1BIwNFXg",
            "name": "john.doe@example.org",
            "email": "john.doe@example.org",
            "full_name": "John Doe"
        },
        "user_agent": {
            "original": "Okta-Integrations"
        },
        "okta": {
            "system": {
                "severity": "INFO",
                "actor": {
                    "id": "eWiaLPtSTpjyy1BIwNFXg",
                    "type": "User",
                    "alternate_id": "john.doe@example.org",
                    "display_name": "John Doe"
                },
                "transaction": {
                    "id": "jI80snAs0ZMym5tvc8Jbp",
                    "type": "WEB"
                },
                "outcome": {
                    "result": "SUCCESS"
                },
                "authentication_context": {
                    "external_session_id": "kjrgFtXuZnABQV9Vq1A2c"
                }
            }
        },
        "related": {
            "hosts": [
                "example.org"
            ],
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "john.doe@example.org"
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
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`okta.system.actor.alternate_id` | `keyword` | The human readable identifier of the requester |
|`okta.system.actor.display_name` | `keyword` | The name of the requester |
|`okta.system.actor.id` | `keyword` | The identifier of the requester |
|`okta.system.actor.type` | `keyword` | The type of the requester |
|`okta.system.authentication_context.authentication.provider` | `keyword` | The provider for the authentication |
|`okta.system.authentication_context.credential.provider` | `keyword` | The provider for the credential |
|`okta.system.authentication_context.credential.type` | `keyword` | The technology used for the credential |
|`okta.system.authentication_context.external_session_id` | `keyword` | The external identifier for the authentication session |
|`okta.system.authentication_context.interface` | `keyword` | The third-party user interface that the actor authenticates |
|`okta.system.authentication_context.issuer.id` | `keyword` | The identifier of the issuer |
|`okta.system.authentication_context.issuer.type` | `keyword` | The type of the issuer |
|`okta.system.outcome.reason` | `keyword` | The outcome reason |
|`okta.system.outcome.result` | `keyword` | The outcome result |
|`okta.system.security_context.is_proxy` | `boolean` | Specifies whether the request come from a proxy |
|`okta.system.security_context.isp` | `keyword` | The name of the Internet Service Provider |
|`okta.system.severity` | `keyword` | The label of the severity of the event |
|`okta.system.transaction.id` | `keyword` | The identifier of the transaction |
|`okta.system.transaction.type` | `keyword` | The type of the transaction |
|`source.as.number` | `long` | Unique number allocated to the autonomous system. |
|`source.as.organization.name` | `keyword` | Organization name. |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.geo.city_name` | `keyword` | City name. |
|`source.geo.country_name` | `keyword` | Country name. |
|`source.geo.location` | `geo_point` | Longitude and latitude. |
|`source.geo.postal_code` | `keyword` | Postal code. |
|`source.geo.region_name` | `keyword` | Region name. |
|`source.ip` | `ip` | IP address of the source. |
|`source.user.id` | `keyword` | Unique identifier of the user. |
|`user.email` | `keyword` | User email address. |
|`user.full_name` | `keyword` | User's full name, if available. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user_agent.name` | `keyword` | Name of the user agent. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

