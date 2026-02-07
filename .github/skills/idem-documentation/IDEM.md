# IDEM VSC - Documentation Complète

 

IDEM VSC est un IDE Mainframe sur base VSCode packagé et pré paramétré

par l'équipe zDevOps. Un ensemble d'extensions sont ajoutées par défaut

lors de l'installation :

 

- Zowe Explorer: Explorateur de partition Mainframe

 

- Z Open Editor: Éditeur Cobol,JCL,REXX...

 

- DB2 for z/OS Developer: Création/exécution de scripts SQL DB2

 

- Git History : Visualiser aisément l'historique Git d'un dépôt

 

- SonarLint : Analyser vos sources Cobol directement depuis l'IDE

 

- Workbench Explorer : Explorateur de partition Mainframe basé sur la HCI topaz

 

- Workbench Code Debug : Débogueur de programme COBOL BATCH et CICS

 

- Cobol Control Flow : Représentation graphique d'un programme COBOL

 

- Compilation : plugin zDevOps pour compiler depuis l'IDE

 

- Injector : plugin zDevOps pour exécuter des transaction CICS ou IMS

 

Les paramétrages d'usine fournis lors de l'installation permettent une

prise en main facilitée des extensions packagées.

 

---

 

## Lien vers la documentation

 

[Documentation zPortal Docs]()

 

---

 

## Configuration par défaut

 

Vous pouvez accéder aux settings en cliquant sur ce [lien](command:workbench.action.openSettings)

 

### Visual studio code

 

- vscode settings.json content :

 

```json

{

  "update.mode": "none",

  "extensions.autoUpdate": false,

  "telemetry.telemetryLevel": "off",

  "security.workspace.trust.emptyWindow": true,

  "security.workspace.trust.enabled": true,

  "security.workspace.trust.untrustedFiles": "open",

  "files.associations": {

    "**.CBL*": "cobol",

    "**.CBL**": "cobol",

    "**.CBL.**": "cobol",

    "**.COBOL*": "cobol",

    "**.COBOL**": "cobol",

    "**.COBOL.**": "cobol",

    "**.CPY*": "cobol",

    "**.CPY**": "cobol",

    "**.CPY.**": "cobol",

    "**.COPY*": "cobol",

    "**.COPY**": "cobol",

    "**.COPY.**": "cobol",

    "**.COPYBOOK*": "cobol",

    "**.COPYBOOK.**": "cobol",

    "**.COPYLIB*": "cobol",

    "**.COPYLIB**": "cobol",

    "**.COPYLIB.**": "cobol",

    "**.CCO*": "cobol",

    "**.CCO**": "cobol",

    "**.CCO.**": "cobol",

    "**.CCP*": "cobol",

    "**.CCP.**": "cobol",

    "**.SRC*": "cobol",

    "**.SRC**": "cobol",

    "**.SRC.**": "cobol",

    "**.SOURCE*": "cobol",

    "**.SOURCE**": "cobol",

    "**.SOURCE.**": "cobol",

    "**.PBA*": "cobol",

    "**.PBA**": "cobol",

    "**.PBA.**": "cobol",

    "**.SPBA*": "cobol",

    "**.SPBA**": "cobol",

    "**.SPBA.**": "cobol",

    "**.PGM*": "cobol",

    "**.PGM**": "cobol",

    "**.PGM.**": "cobol",

    "**.SPGM*": "cobol",

    "**.SPGM**": "cobol",

    "**.SPGM.**": "cobol",

    "**.PBATP*": "cobol",

    "**.PBATP**": "cobol",

    "**.PBATP.**": "cobol",

    "**.SOURCLIB*": "cobol",

    "**.SOURCLIB.**": "cobol",

    "*.PL1*": "pl1",

    "*.PLI*": "pl1",

    "*.INC*": "pl1",

    "*.INCLUDE*": "pl1",

    "**.JCL*": "jcl",

    "**.JCL**": "jcl",

    "**.JCL.**": "jcl",

    "**.JOB*": "jcl",

    "**.JOB**": "jcl",

    "**.JOB.**": "jcl",

    "**.PROCLIB*": "jcl",

    "**.PROCLIB**": "jcl",

    "**.PROCLIB.**": "jcl",

    "**.MBA*": "jcl",

    "**.MBA**": "jcl",

    "**.MBA.**": "jcl",

    "**.MBE*": "jcl",

    "**.MBE**": "jcl",

    "**.MBE.**": "jcl",

    "**.MB2*": "jcl",

    "**.MB2**": "jcl",

    "**.MB2.**": "jcl",

    "**.CNTL*": "jcl",

    "**.CNTL**": "jcl",

    "**.CNTL.**": "jcl",

    "**.PRO*": "jcl",

    "**.PRO**": "jcl",

    "**.PRO.**": "jcl",

    "*.ASM*": "hlasm",

    "*.ASSEMBLE*": "hlasm",

    "*.HLASM*": "hlasm",

    "*.HLA*": "hlasm",

    "*.MACLIB*": "hlasm",

    "*.EXEC*": "rexx",

    "*.REXX*": "rexx",

    "*.REXXINC*": "rexx",

    "*.rex": "rexx",

    "*.rexx": "rexx"

  }

}

```

 

### IBM Z/Open Editor

 

- vscode settings.json content :

 

```json

{

  "zopeneditor.datasets.cobolDatasets": [

    "*.CBL",

    "*.CBL*",

    "*.CBL.*",

    "*.COBOL",

    "*.COBOL*",

    "*.COBOL.*",

    "*.CPY",

    "*.CPY*",

    "*.CPY.*",

    "*.COPY",

    "*.COPY*",

    "*.COPY.*",

    "*.COPYBOOK",

    "*.COPYBOOK.*",

    "*.COPYLIB",

    "*.COPYLIB*",

    "*.COPYLIB.*",

    "*.CCO",

    "*.CCO*",

    "*.CCO.*",

    "*.CCP",

    "*.CCP.*",

    "*.SRC",

    "*.SRC*",

    "*.SRC.*",

    "*.SOURCE",

    "*.SOURCE*",

    "*.SOURCE.*",

    "*.PBA",

    "*.PBA*",

    "*.PBA.*",

    "*.SPBA",

    "*.SPBA*",

    "*.SPBA.*",

    "*.PGM",

    "*.PGM*",

    "*.PGM.*",

    "*.SPGM",

    "*.SPGM*",

    "*.SPGM.*",

    "*.PBATP",

    "*.PBATP*",

    "*.PBATP.*",

    "*.SOURCLIB",

    "*.SOURCLIB.*"

  ],

  "zopeneditor.datasets.jclDatasets": [

    "*.JCL",

    "*.JCL*",

    "*.JCL.*",

    "*.JOB",

    "*.JOB*",

    "*.JOB.*",

    "*.PROCLIB",

    "*.PROCLIB*",

    "*.PROCLIB.*",

    "*.MBA",

    "*.MBA*",

    "*.MBA.*",

    "*.MBE",

    "*.MBE*",

    "*.MBE.*",

    "*.MB2",

    "*.MB2*",

    "*.MB2.*",

    "*.CNTL",

    "*.CNTL*",

    "*.CNTL.*",

    "*.PRO",

    "*.PRO*",

    "*.PRO.*"

  ],

  "zopeneditor.JAVA_HOME": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1",

  "zopeneditor.welcomePage.show": false,

  "zopeneditor.userbuild.enabled": false,

  "zopeneditor.zapp.generateZappOnDemand": false

}

```

 

### Zowe Explorer

 

- vscode settings.json content :

 

```json

{

  "zowe.ds.history": {

    "persistence": true,

    "favorites": [""],

    "history": [""],

    "sessions": ["HY99", "SDEV"],

    "templates": [],

    "fileHistory": [""],

    "searchHistory": [""]

  },

  "zowe.uss.history": {

    "persistence": true,

    "favorites": [""],

    "history": [""],

    "sessions": ["HY99", "SDEV"],

    "fileHistory": [""],

    "searchHistory": [""],

    "templates": []

  },

  "zowe.jobs.history": {

    "persistence": true,

    "favorites": [""],

    "history": [""],

    "sessions": ["HY99", "SDEV"],

    "fileHistory": [""],

    "searchHistory": [""]

  },

  "zowe.settings.version": 2

}

```

 

- extension specific configuration file :

 

zowe.config.json

 

```json

{

  "$schema": "./zowe.schema.json",

  "profiles": {

    "SDEV": {

      "type": "zosmf",

      "properties": {

        "port": 7554,

        "rejectUnauthorized": false,

        "encoding": "1147",

        "host": "sdev.dns21.socgen",

        "basePath": "ibmzosmf/api/v1"

      },

      "secure": ["user", "password"]

    },

    "HY99": {

      "type": "zosmf",

      "properties": {

        "port": 7554,

        "rejectUnauthorized": false,

        "encoding": "1147",

        "host": "hy99.dns21.socgen",

        "basePath": "ibmzosmf/api/v1"

      },

      "secure": ["user", "password"]

    }

  },

  "defaults": {

    "zosmf": "SDEV"

  },

  "autoStore": true

}

```

 

zowe.schema.json

 

```json

{

  "$schema": https://json-schema.org/draft/2020-12/schema,

  "$version": "1.0",

  "type": "object",

  "description": "Zowe configuration",

  "properties": {

    "profiles": {

      "type": "object",

      "description": "Mapping of profile names to profile configurations",

      "patternProperties": {

        "^\\S*$": {

          "type": "object",

          "description": "Profile configuration object",

          "properties": {

            "type": {

              "description": "Profile type",

              "type": "string",

              "enum": ["zosmf", "tso", "ssh", "rse", "base"]

            },

            "properties": {

              "description": "Profile properties object",

              "type": "object"

            },

            "profiles": {

              "description": "Optional subprofile configurations",

              "type": "object",

              "$ref": "#/properties/profiles"

            },

            "secure": {

              "description": "Secure property names",

              "type": "array",

              "items": {

                "type": "string"

              },

              "uniqueItems": true

            }

          },

          "allOf": [

            {

              "if": {

                "properties": {

                  "type": false

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "title": "Missing profile type"

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "zosmf"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "z/OSMF Profile",

                    "description": "z/OSMF Profile",

                    "properties": {

                      "host": {

                        "type": "string",

                        "description": "The z/OSMF server host name."

                      },

                      "port": {

                        "type": "number",

                        "description": "The z/OSMF server port.",

                        "default": 443

                      },

                      "user": {

                        "type": "string",

                        "description": "Mainframe (z/OSMF) user name, which can be the same as your TSO login."

                      },

                      "password": {

                        "type": "string",

                        "description": "Mainframe (z/OSMF) password, which can be the same as your TSO password."

                      },

                      "rejectUnauthorized": {

                        "type": "boolean",

                        "description": "Reject self-signed certificates.",

                        "default": true

                      },

                      "certFile": {

                        "type": "string",

                        "description": "The file path to a certificate file to use for authentication"

                      },

                      "certKeyFile": {

                        "type": "string",

                        "description": "The file path to a certificate key file to use for authentication"

                      },

                      "basePath": {

                        "type": "string",

                        "description": "The base path for your API mediation layer instance. Specify this option to prepend the base path to all z/OSMF resources when making REST requests. Do not specify this option if you are not using an API mediation layer."

                      },

                      "protocol": {

                        "type": "string",

                        "description": "The protocol used (HTTP or HTTPS)",

                        "default": "https",

                        "enum": ["http", "https"]

                      },

                      "encoding": {

                        "type": "string",

                        "description": "The encoding for download and upload of z/OS data set and USS files. The default encoding if not specified is IBM-1047."

                      },

                      "responseTimeout": {

                        "type": "number",

                        "description": "The maximum amount of time in seconds the z/OSMF Files TSO servlet should run before returning a response. Any request exceeding this amount of time will be terminated and return an error. Allowed values: 5 - 600"

                      }

                    },

                    "required": []

                  },

                  "secure": {

                    "items": {

                      "enum": ["user", "password"]

                    }

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "tso"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "TSO Profile",

                    "description": "z/OS TSO/E User Profile",

                    "properties": {

                      "account": {

                        "type": "string",

                        "description": "Your z/OS TSO/E accounting information."

                      },

                      "characterSet": {

                        "type": "string",

                        "description": "Character set for address space to convert messages and responses from UTF-8 to EBCDIC.",

                        "default": "697"

                      },

                      "codePage": {

                        "type": "string",

                        "description": "Codepage value for TSO/E address space to convert messages and responses from UTF-8 to EBCDIC.",

                        "default": "1047"

                      },

                      "columns": {

                        "type": "number",

                        "description": "The number of columns on a screen.",

                        "default": 80

                      },

                      "logonProcedure": {

                        "type": "string",

                        "description": "The logon procedure to use when creating TSO procedures on your behalf.",

                        "default": "IZUFPROC"

                      },

                      "regionSize": {

                        "type": "number",

                        "description": "Region size for the TSO/E address space.",

                        "default": 4096

                      },

                      "rows": {

                        "type": "number",

                        "description": "The number of rows on a screen.",

                        "default": 24

                      }

                    },

                    "required": []

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "ssh"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "z/OS SSH Profile",

                    "description": "z/OS SSH Profile",

                    "properties": {

                      "host": {

                        "type": "string",

                        "description": "The z/OS SSH server host name."

                      },

                      "port": {

                        "type": "number",

                        "description": "The z/OS SSH server port.",

                        "default": 22

                      },

                      "user": {

                        "type": "string",

                        "description": "Mainframe user name, which can be the same as your TSO login."

                      },

                      "password": {

                        "type": "string",

                        "description": "Mainframe password, which can be the same as your TSO password."

                      },

                      "privateKey": {

                        "type": "string",

                        "description": "Path to a file containing your private key, that must match a public key stored in the server for authentication"

                      },

                      "keyPassphrase": {

                        "type": "string",

                        "description": "Private key passphrase, which unlocks the private key."

                      },

                      "handshakeTimeout": {

                        "type": "number",

                        "description": "How long in milliseconds to wait for the SSH handshake to complete."

                      }

                    },

                    "required": []

                  },

                  "secure": {

                    "items": {

                      "enum": ["user", "password", "keyPassphrase"]

                    }

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "rse"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "IBM RSE API Zowe Profile",

                    "description": "A profile to issue commands to a z/OS system with a working Zowe REST server,Mediation Layer, or IBM RSE (Remote System Explorer) API server installation.",

                    "properties": {

                      "host": {

                        "type": "string",

                        "description": "The z/OS host name running the Zowe REST API."

                      },

                      "port": {

                        "type": "number",

                        "description": "The server port used by the REST API.",

                        "default": 6800

                      },

                      "user": {

                        "type": "string",

                        "description": "The user name for the Zowe REST API operations."

                      },

                      "password": {

                        "type": "string",

                        "description": "The password of the user for the Zowe REST API operations."

                      },

                      "rejectUnauthorized": {

                        "type": "boolean",

                        "description": "Reject self-signed certificates.",

                        "default": true

                      },

                      "basePath": {

                        "type": "string",

                        "description": "The base path of the API for the REST API operations.",

                        "default": "rseapi"

                      },

                      "protocol": {

                        "type": "string",

                        "description": "http or https, depending whether a TLS handshake is required to access REST API.",

                        "default": "https"

                      },

                      "encoding": {

                        "type": "string",

                        "description": "The encoding for download and upload of z/OS data set and USS files. The encoding should be specified in the form of \"IBM-1047\"."

                      },

                      "tokenType": {

                        "type": "string",

                        "description": "JWT token type assigned to profile when \"zowe rse auth login\" is used for authentication."

                      },

                      "tokenValue": {

                        "type": "string",

                        "description": "JWT token value assigned to profile when \"zowe rse auth login\" is used for authentication."

                      }

                    },

                    "required": []

                  },

                  "secure": {

                    "items": {

                      "enum": ["user", "password", "tokenValue"]

                    }

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "ssh"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "z/OS SSH Profile",

                    "description": "z/OS SSH Profile",

                    "properties": {

                      "host": {

                        "type": "string",

                        "description": "The z/OS SSH server host name."

                      },

                      "port": {

                        "type": "number",

                        "description": "The z/OS SSH server port.",

                        "default": 22

                      },

                      "user": {

                        "type": "string",

                        "description": "Mainframe user name, which can be the same as your TSO login."

                      },

                      "password": {

                        "type": "string",

                        "description": "Mainframe password, which can be the same as your TSO password."

                      },

                      "privateKey": {

                        "type": "string",

                        "description": "Path to a file containing your private key, that must match a public key stored in the server for authentication"

                      },

                      "keyPassphrase": {

                        "type": "string",

                        "description": "Private key passphrase, which unlocks the private key."

                      },

                      "handshakeTimeout": {

                        "type": "number",

                        "description": "How long in milliseconds to wait for the SSH handshake to complete."

                      }

                    },

                    "required": []

                  },

                  "secure": {

                    "items": {

                      "enum": ["user", "password", "keyPassphrase"]

                    }

                  }

                }

              }

            },

            {

              "if": {

                "properties": {

                  "type": {

                    "const": "base"

                  }

                }

              },

              "then": {

                "properties": {

                  "properties": {

                    "type": "object",

                    "title": "Base Profile",

                    "description": "Base profile that stores values shared by multiple service profiles",

                    "properties": {

                      "host": {

                        "type": "string",

                        "description": "Host name of service on the mainframe."

                      },

                      "port": {

                        "type": "number",

                        "description": "Port number of service on the mainframe."

                      },

                      "user": {

                        "type": "string",

                        "description": "User name to authenticate to service on the mainframe."

                      },

                      "password": {

                        "type": "string",

                        "description": "Password to authenticate to service on the mainframe."

                      },

                      "rejectUnauthorized": {

                        "type": "boolean",

                        "description": "Reject self-signed certificates.",

                        "default": true

                      },

                      "tokenType": {

                        "type": "string",

                        "description": "The type of token to get and use for the API. Omit this option to use the default token type, which is provided by 'zowe auth login'."

                      },

                      "tokenValue": {

                        "type": "string",

                        "description": "The value of the token to pass to the API."

                      },

                      "certFile": {

                        "type": "string",

                        "description": "The file path to a certificate file to use for authentication"

                      },

                      "certKeyFile": {

                        "type": "string",

                        "description": "The file path to a certificate key file to use for authentication"

                      }

                    },

                    "required": []

                  },

                  "secure": {

                    "items": {

                      "enum": ["user", "password", "tokenValue"]

                    }

                  }

                }

              }

            }

          ]

        }

      }

    },

    "defaults": {

      "type": "object",

      "description": "Mapping of profile types to default profile names",

      "properties": {

        "zosmf": {

          "description": "Default zosmf profile",

          "type": "string"

        },

        "tso": {

          "description": "Default tso profile",

          "type": "string"

        },

        "ssh": {

          "description": "Default ssh profile",

          "type": "string"

        },

        "rse": {

          "description": "Default rse profile",

          "type": "string"

        },

        "base": {

          "description": "Default base profile",

          "type": "string"

        }

      }

    },

    "autoStore": {

      "type": "boolean",

      "description": "If true, values you enter when prompted are stored for future use"

    }

  }

}

```

 

### DB2 for Z/OS developper

 

- vscode settings.json content :

 

```json

{

  "db2forzosdeveloperextension.db2sqlservice.dependencies": "C:/Users/X152543/Compuware/Workbench/workspace/.metadata/.plugins/org.jkiss.dbeaver.core/db2jcc_license_zdevops.jar",

  "db2forzosdeveloperextension.java.home": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1"

}

```

 

- extension specific configuration file :

 

connections.json

 

```json

{

  "BDDFDB2DConnection": {

    "name": "BDDF-DB2D",

    "server": "sdev.dns21.socgen",

    "port": "4446",

    "location": "DB2D",

    "authType": "REGULAR",

    "savePassword": true,

    "traceLevel": 0,

    "traceFileAppend": false,

    "jdbcProperties": {

      "clientApplCompat": "V12R1M500",

      "currentPackageSet": "NULLID_V12R1M500",

      "sslConnection": "true",

      "sslTrustStoreLocation": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1/lib/security/cacerts",

      "sslTrustStorepassword": "changeit"

    }

  },

  "BDDFDB1HConnection": {

    "name": "BDDF-DB1H",

    "server": "hy99.dns21.socgen",

    "port": "5446",

    "location": "DB1H",

    "authType": "REGULAR",

    "savePassword": true,

    "traceLevel": 0,

    "traceFileAppend": false,

    "jdbcProperties": {

      "clientApplCompat": "V12R1M500",

      "currentPackageSet": "NULLID_V12R1M500",

      "sslConnection": "true",

      "sslTrustStoreLocation": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1/lib/security/cacerts",

      "sslTrustStorepassword": "changeit"

    }

  },

  "BDDFDB2EConnection": {

    "name": "BDDF-DB2E",

    "server": "sdev.dns21.socgen",

    "port": "5447",

    "location": "DB2E",

    "authType": "REGULAR",

    "savePassword": true,

    "traceLevel": 0,

    "traceFileAppend": false,

    "jdbcProperties": {

      "clientApplCompat": "V12R1M500",

      "currentPackageSet": "NULLID_V12R1M500",

      "sslConnection": "true",

      "sslTrustStoreLocation": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1/lib/security/cacerts",

      "sslTrustStorepassword": "changeit"

    }

  },

  "BDDFDB7HConnection": {

    "name": "BDDF-DB7H",

    "server": "hy99.dns21.socgen",

    "port": "4446",

    "location": "DB7H",

    "authType": "REGULAR",

    "savePassword": true,

    "traceLevel": 0,

    "traceFileAppend": false,

    "jdbcProperties": {

      "clientApplCompat": "V12R1M500",

      "currentPackageSet": "NULLID_V12R1M500",

      "sslConnection": "true",

      "sslTrustStoreLocation": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1/lib/security/cacerts",

      "sslTrustStorepassword": "changeit"

    }

  },

  "BDDFDB0HConnection": {

    "name": "BDDF-DB0H",

    "server": "splxdbg0.dns21.socgen",

    "port": "4447",

    "location": "DB0H",

    "authType": "REGULAR",

    "savePassword": true,

    "traceLevel": 0,

    "traceFileAppend": false,

    "jdbcProperties": {

      "clientApplCompat": "V12R1M500",

      "currentPackageSet": "NULLID_V12R1M500",

      "sslConnection": "true",

      "sslTrustStoreLocation": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1/lib/security/cacerts",

      "sslTrustStorepassword": "changeit"

    }

  }

}

```

 

### Devx Workbench Explorer

 

- vscode settings.json content :

 

```json

{

  "JobExplorer.Columns": {

    "CPU %": true,

    "CPU Time": true,

    "EXCPs": true,

    "Programmer*": true,

    "Start Time*": true,

    "System*": true

  },

  "devx-workbench-explorer.hciConnections": [

    {

      "name": "HY99",

      "host": "hy99.dns21.socgen",

      "port": 10198,

      "securityType": {

        "secure": true,

        "encryption": "AUTO"

      },

      "codePage": 1147,

      "authType": "credential"

    },

    {

      "name": "SDEV",

      "host": "sdev.dns21.socgen",

      "port": 10198,

      "securityType": {

        "secure": false,

        "encryption": ""

      },

      "codePage": 1147

    }

  ],

  "files.autoSaveDelay": 60000,

  "DevxExplorer.cobolCopybooks": [

    "APP.SOURCLIB.MASTER.COPYEXPL",

    "MQS.SCSQCOBC"

  ]

}

```

 

### Sonarlint

 

- vscode settings.json content :

 

```json

{

  "sonarlint.disableTelemetry": true,

  "sonarlint.ls.javaHome": "C:\\\\Users\\\\X152543\\\\bin\\\\idem-vsc-23.3.0\\\\jdk-11.0.20.1+1",

  "sonarlint.connectedMode.connections.sonarqube": [

    {

      "serverUrl":,

      "connectionId": ""

    }

  ]

}

```

 

### Idem Compilation

 

- vscode settings.json content :

 

```json

{

  "idemCompilation.JAVA_HOME": "C:/Users/X152543/bin/idem-vsc-23.3.0/jdk-11.0.20.1+1",

  "idemCompilation.M2_HOME": "C:/Users/X152543/bin/idem-vsc-23.3.0/apache-maven-3.6.3",

  "idemCompilation.applicationId": "APP",

  "idemCompilation.ddioFile": "DAPPT.APP.DDIO",

  "idemCompilation.loadLibrary": "DAPPT.APP.LOAD",

  "idemCompilation.executionClass": "Q",

  "idemCompilation.targetEnvironment": "DTU(T)",

  "idemCompilation.copyLibrary": ["DAPPT.APP.CPY"]

}

```

 

- Idem compilation pom.xml

 

```xml

<?xml version='1.0' encoding='UTF-8' standalone='yes'?>

<project xsi:schemaLocation=http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd xmlns=http://maven.apache.org/POM/4.0.0 xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance>

<modelVersion>4.0.0</modelVersion>

               <groupId>com.socgen.idem</groupId>

               <artifactId>compile</artifactId>

               <version>0.0.1-SNAPSHOT</version>

               <packaging>zcompiler</packaging>

               <pluginRepositories>

                              <pluginRepository>

                                            <id>top_snapshots_repo</id>

                                            <url></url>

                              </pluginRepository>

                              <pluginRepository>

                                            <id>compuware_repo</id>

                                            <url></url>

                              </pluginRepository>

               </pluginRepositories>

               <properties>

                              <java.version>11</java.version>

                              <maven.compiler.source>${java.version}</maven.compiler.source>

                              <maven.compiler.target>${java.version}</maven.compiler.target>

               </properties>

               <profiles>

                              <profile>

                                            <id>Default</id>

                                            <activation>

                                                           <activeByDefault>true</activeByDefault>

                                            </activation>

                                            <build>

                                                           <plugins>

                                                                          <plugin>

                                                                                         <groupId>com.socgen.zdevops</groupId>

                                                                                         <artifactId>zdevops-maven-plugin</artifactId>

                                                                                         <version>23.3.0-SNAPSHOT</version>

                                                                                         <extensions>true</extensions>

                                                                                         <configuration>

                                                                                                        <hciHost>sdev.dns21.socgen</hciHost>

                                                                                                       <hciPort>10198</hciPort>

                                                                                                        <ApplicationID>APP</ApplicationID>

                                                                                                        <DDIOFile>DAPPT.APP.DDIO</DDIOFile>

                                                                                                        <LoadLibrary>DAPPT.APP.LOAD</LoadLibrary>

                                                                                                        <CopybookLibrary>DAPPT.APP.CPY;</CopybookLibrary>

                                                                                                        <TargetEnvironment>DTU(T)</TargetEnvironment>

                                                                                                        <ExecutionClass>Q</ExecutionClass>

                                                                                                        <DB2Owner>DVLUSER</DB2Owner>

                                                                                         </configuration>

                                                                          </plugin>

                                                           </plugins>

                                            </build>

                              </profile>

               </profiles>

</project>

```

 

---

 

## Auto-dépannage

 

IDEM VSC vous propose quelque outil pour vous auto dépanner ou faciliter vos actions

 

- Remise des paramètres par défauts des extensions

- Lien vers le support zDevOps

- Lien vers la documentation IDEM VSC

- Liens vers des applications externes

 

### Paramètrage par défauts

 

Pour revenir au paramètres par défauts des extensions d'IDEM VSC, il faut utiliser la commande palette (CTRL+MAJ+P) "Idem First Aid Kit: Reset Parameters"

 

Selectionner ensuite l'extension à restaurer puis appuyer sur "ok"

 

 

### Liens utiles

 

IDEM VSC vous proposes une commande palette pour chacun de ses liens :

 

- Documentation zDevops

- Support zDevOps

- Métriques Z

- Host Access

- Zrest Factory

 

 

## Creation et gestion de profils de compilation

 

### Configurer un Profil

 

Pour définir vos paramètres de configuration vous pouvez utiliser le raccourci CTRL+,

et chercher "@ext:zdevops.idem-vsc" dans la barre de recherche.

 

Vous arrivez sur la page ci-dessous

 

 

A partir d'ici il suffit de renseigner vos paramètres de compilations

 

- Application ID : correspond au trigramme de votre application (exemple : "TOP")

- Copy Library : Vous devez renseigner l'ensemble des PDS qui contiennent les COPY utiliser par votre programme (exemple : "DTOPT.TOP.CPY")

- DB2 Owner : Si votre programme fait du DB2 alors il faut choisir entre l'owner DVLUSER (utilisé par les anciens trigrammes) ou DappA (qui correspond à D${ApplicationID}A par exemple DTOPA)

- DDIO File : le fichier DDIO où stocker le source pour le deboguing via Xpeditor (exemple : DPOGT.IDEM.DDIO.COMMUN)

- Execution Clas : la classe d'exécution du job de compilation

- Load library : le PDS où stocker le load module après compilation

- Target Environment : L'environement cible pour la compilation

 

### Créer/Supprimer/Choisir un profil

 

Pour gérer un profil, cliquer sur le bouton des paramètres de vscode puis sur "Profils" et enfin sur "Create profil..."

 

 

Nommer votre profil, choisissez le profil a partir duquel vous voulez créer votre profil (Default par exemple), choisissez une icone pour représenter votre profil et enfin sélectionner les éléments que vous voulez inclure dans le profil. Nous conseillons de n'inclure que les settings pour gagner en performance lors des changements de profils.

 

 

Appuyer ensuite sur le bouton "Create"

 

Pour supprimer un profil la procédure est semblable, cliquer sur le bouton des paramètres de vscode puis sur "Profils" puis sur 'Delete Profil..."

Choississez les profils a supprimer et valider.

 

### Importer des profils depuis IDEM

 

Dans la palette de commande vous trouverez la commande "Idem Compilation: Import Profiles From pom.xml"

Cette commande permet d'importer dans IDEM VSC des profils de compilation présent dans un pom.xml, donc par exemple provenant d'IDEM

 

Appuyez sur CTRL + MAJ + P pour ouvrir la palette de commande.

Exécuter la commande "Idem Compilation: Import Profiles From pom.xml"

 

Par défaut la commande vous propose la pom.xml d'IDEM VSC, vous pouvez cependant renseigner un autre fichier pom.xml provenant d'IDEM, par exemple "C:\Users\Annnnnn\Compuware\Workbench\workspace\.IDEMCompilation\SDEV\pom.xml"

 

### Création d'un fichier DDIO

 

Pour créer un fichier DDIO on peut utiliser le JCL ci-dessous, il suffit de modifier le nom du DDIO à la 7ème ligne

 

```jcl

//DDIOCREA JOB (MMC),'DDIOCREA',CLASS=A,

//  MSGCLASS=X,MSGLEVEL=(1,1),NOTIFY=&SYSUID

//*--------------------------------------------------------------

//* PARAMETRAGE :

//*       - DDIONAME : Nom du DDIO à créer

//*--------------------------------------------------------------

// SET DDIONAME=X152543.DDIO

//*--------------------------------------------------------------

//* PREPARATION SYSIN DELETE

//*--------------------------------------------------------------

//UTSY11A1 EXEC PGM=SY00011,

// PARM=('&DDIONAME')

//DD00011A DD  *

  DELETE &1

  IF MAXCC NE 0 THEN SET MAXCC EQ 0

//*

//DD00011S DD  DISP=(NEW,PASS,DELETE),

//             DSN=&&TEMP01,

//             SPACE=(TRK,1),

//             UNIT=TVIO

//*

//SYSOUT   DD  SYSOUT=*

//CEEDUMP  DD  SYSOUT=E

//*--------------------------------------------------------------

//* SUPPRESSION SI DDIO EXISTANT

//*--------------------------------------------------------------

//DELETE EXEC PGM=IDCAMS

//SYSPRINT DD  SYSOUT=*

//SYSOUT   DD  SYSOUT=*

//SYSIN    DD  DISP=(OLD,PASS),

//             DSN=&&TEMP01

//*--------------------------------------------------------------

//* PREPARATION SYSIN SHRDIR

//*--------------------------------------------------------------

//UTSY11A1 EXEC PGM=SY00011,

// PARM=('&DDIONAME')

//DD00011A DD  *

  CREATE OBJECT=SRCEDIR,

       AM=VSAM,

       CISIZE=18432,

       DIRENTS=005000,

       REALLOCATE=NO,

       AD=DUPS,

       DIRDSN=&1,

       MGMTCLAS=ND0010

//*

//DD00011S DD  DISP=(NEW,PASS,DELETE),

//             DSN=&&TEMP02,

//             SPACE=(TRK,1),

//             UNIT=TVIO

//*

//SYSOUT   DD  SYSOUT=*

//CEEDUMP  DD  SYSOUT=E

//*--------------------------------------------------------------

//* CREATION DU VSAM DDIO

//*--------------------------------------------------------------

//SHRDIR   EXEC PGM=CWDDALLU

//STEPLIB  DD DISP=SHR,DSN=SYS2.COMPWARE.CSS.LOAD

//ABNLREPT DD SYSOUT=*

//ABNLPARM DD DISP=(OLD,PASS),

//             DSN=&&TEMP02

//*--------------------------------------------------------------

//* PREPARATION SYSIN DATABASE

//*--------------------------------------------------------------

//UTSY11A1 EXEC PGM=SY00011,

// PARM=('&DDIONAME')

//DD00011A DD  *

CREATE OBJECT=DATABASE,

       TYPE=SOURCE,

       AM=VSAM,

       CISIZE=18432,

       CYLINDERS=00050,

       REALLOCATE=NO,

       MGMTCLAS=ND0010,

       AD=DUPS,

       RC=00500,

       GC=0003,

       DSN=&1.BASE,

       DIRDD=CWUT0001

//*

//DD00011S DD  DISP=(NEW,PASS,DELETE),

//             DSN=&&TEMP03,

//             SPACE=(TRK,1),

//             UNIT=TVIO

//*

//SYSOUT   DD  SYSOUT=*

//CEEDUMP  DD  SYSOUT=E

//*--------------------------------------------------------------

//* CREATION DE LA DATABASE ASSOCIE AU DDIO

//*--------------------------------------------------------------

//DATABASE   EXEC PGM=CWDDALLU

//STEPLIB  DD DISP=SHR,DSN=SYS2.COMPWARE.CSS.LOAD

//ABNLREPT DD SYSOUT=*

//CWUT0001 DD DISP=SHR,DSN=&DDIONAME

//ABNLPARM DD DISP=(OLD,PASS),

//             DSN=&&TEMP03

```

 

## Compilation

 

Il y a deux méthodes de compilation : la compilation simple que vous

lancez avec la commande palette **Idem Compilation : Compile** et la

compilation unitaire avec un panneau de configuration que vous lancez

avec la commande palette **Idem Compilation : Compile\...**

 

Le profil de compilation par défaut est celui configuré ci-dessus dans

**l'Idem compilation** **configuration**.

 

 

### Panneau de la compilation unitaire

 

 

Dans cet écran le type est calculé

automatiquement, sinon vous pouvez le modifier en cliquant sur le bouton :crayon:

et le calculer manuellement dans l'écran ci-dessous.

 

 

Lors de la compilation, vous pouvez lire le journal du terminal pour

récupérer le job ID.

 

 

Remarque : la compilation ne s'exécutera pas si les identifiants sont

erronés. Sinon, elle s'exécutera automatiquement en présence du fichier

hciid ou après l'authentification (cela pourrait prendre quelques

secondes si vous êtes rapide pour saisir les identifiants).

 

---

 

## GitHub Copilot

 

 

GitHub Copilot est un assistant de codage alimenté par l'IA développé par GitHub. Il est conçu pour aider les développeurs à écrire du code de manière plus efficace. Avec Copilot, vous pouvez obtenir des suggestions de complétion de code, générer des extraits de code et même recevoir une documentation contextuelle.

 

Pour le développement mainframe, y compris COBOL, Assembler, JCL, et plus encore, GitHub Copilot peut être un outil précieux. Il peut vous aider à écrire du code mainframe complexe en fournissant des suggestions pertinentes et en automatisant les tâches répétitives. Que vous ayez besoin d'aide avec la syntaxe, la logique ou les meilleures pratiques, Copilot peut être un compagnon utile dans votre parcours de développement mainframe.

 

Pour en savoir plus sur GitHub Copilot et comment le configurer pour le développement mainframe, vous pouvez consulter la [documentation]().

 

**Documentation écrite avec Copilot**

 

---

 

## DB2

 

 

Pour manipuler vos bases de données DB2 depuis IDEM VSC vous avez deux possibilité :

 

- Utiliser l'extension DB2 for Z/OS developper

 

« IBM Db2 for Z/OS Developer » est une extension Visual Studio Code

fournie avec IDEM VSC. Elle permet de vérifier la syntaxe des requêtes

SQL, de fournir une auto-complétion de code, de pouvoir mettre en forme

vos requêtes, d'exécuter une requête SQL, d'analyser les performances de

vos requêtes et d'explorer le catalogue DB2.

 

La documentation éditeur se trouve ici : [Getting started

(ibm.github.io)]()

 

Cette extension nécessite un fichier de licence. Pour le récupérer :

 

    - Ouvrir la commande palette (CTRL + MAJ + P)

    - Rechercher et exécuter la commande "Idem First Aid Kit: Retrieve JDBC license file"

 

- Utiliser l'extension DevX FileAid

 

« DevX FileAid » est une extension Visual Studio Code fournie avec IDEM VSC. Elle permet d'éditer des dataset mais aussi des tables DB2.

 

La documentation éditeur se trouve ici : [Docs BMC]()

 

### Explorer une Base de donnée

 

Depuis la vue DB2 Developer Extension connectez-vous à votre base de

données avec le bouton « Connect »

 

 

Une fois connecté vous pouvez explorer la base de données. Les éléments

sont rangés en 4 groupes :

 

- Storage groups

 

- Databases

 

- Tables

 

- Schémas

 

Cliquer sur un groupe dans l'arbre pour explorer celui-ci.

 

Pour tous les groupes vous verrez un tableau avec une entête comme

celui-ci :

 

 

La loupe permet d'effectuer une recherche dans toutes les colonnes de la

table.

 

L'entonnoir permet de définir un filtre sur le nom de l'élément affiché.

Le caractère % peut être utilisé dans les filtres comme un Like.

 

En cliquant sur « Max rows » vous pouvez augmenter ou diminuer le nombre

de ligne maximum à afficher.

 

En cliquant sur « Total Rows » vous pouvez voir le nombre de ligne total

du tableau.

 

#### Storage groups

 

Dans l'arbre d'exploration en cliquant sur « Storage groups » vous

obtenez la vue suivante.

 

 

A partir de là vous pouvez cliquer sur le storage group qui vous

intéresse pour avoir plus de détails sur celui-ci.

 

 

#### Databases

 

Dans l'arbre d'exploration en cliquant sur « Databases » vous obtenez la

vue suivante.

 

 

A partir de là vous pouvez cliquer sur la database qui vous intéresse

pour avoir plus de détails sur celle-ci.

 

 

Vous pouvez aussi directement accéder au storage group correspondant.

 

#### Tables

 

En cliquant dans l'arbre sur Tables vous ouvrirez la vue ci-dessous.

 

 

A partir de ce tableau vous pouvez cliquer sur la table qui vous

intéresse pour avoir plus de détails sur celle-ci.

 

Un premier onglet « Properties » résume les propriétés de la table.

 

 

Un deuxième onglet « Columns » permet de voir les propriétés des

colonnes de la table

 

 

Un troisième onglet « Constraints » permet d'afficher les contraintes de

la table.

 

Un quatrième onglet « Indexes » liste les index présents sur la table.

 

 

Un cinquième onglet « Data » permet de visualiser les données de la

table.

 

 

On peut trier par colonne simplement en cliquant sur celle-ci.

 

#### Schemas

 

Pour accéder au Schémas il faut des autorisations spécifiques. A moins

que vous les ayez vous aurez une erreur SQL -551.

 

### Exécuter une requete SQL

 

Commencer par créer dans votre workspace un fichier .sql.

 

Avec CTRL+SPACE vous pouvez profiter de l'auto complémention pour écrire

votre requête :

 

 

La première fois que vous exécutez une requête vous devez d'abord

définir quelques options. Pour cela cliquez droit dans l'éditeur et

choisissez « Run SQL option »

 

 

Définissez ensuite les options SQL qui vous conviennent pour votre

requête.

 

 

Une fois vos requêtes écrites, faite clic droit puis Run All

 

 

Le résultat de votre requête apparaît dans une nouvelle vue. Vous pouvez

exporter les résultats avec le bouton en forme de disquette.

 

### Analyser une requete

 

Après avoir été exécutée votre requête apparaît dans l'historique des

requêtes.

 

 

A partir d'ici vous pouvez accéder à différentes informations concernant

votre requête. En appuyant sur « Execution Summary », vous avez un

résumé de toutes les requêtes exécutées dans votre fichier .sql.

 

 

En cliquant sur une requête de votre fichier vous pouvez accéder à son

résultat mais aussi à son statut

 

 

Il est aussi possible depuis cette arbre « Query History » de réexécuter

une requête déjà exécutée.

 

### Editer une table

 

Pour éditer une table avec FileAid DB2 il faut d'abord créer un filtre de table :

 

 

Il est ensuite possible de consulter vos tables et leurs metadonnées ou de les éditers

 

 

---

 

## Débogage

 

 

« BMC AMI DevX Code Debug » est une extension Visual Studio

Code fournie avec IDEM VSC. Elle permet de déboguer pas à pas les

programmes COBOL BATCH et CICS. Elle fonctionne de pair avec l'extension

« BMC AMI DevX Explorer ».

 

La documentation éditeur se trouve ici : [BMC

Documentation]()

 

### Déboguer un programme BATCH

 

Dans la vue « Exécuter et déboguer » de VSC, cliquer sur Créer un

fichier launch.json.

 

 

Dans le choix du débogueur, choisir « Workbench Batch ».

 

Remplir les différents champs du fichier launch.json. Il est important de compiler son programme

dans un DDIO avant de vouloir le déboguer, sinon le débogueur ne

retrouvera pas le code source.

 

La configuration de débogage apparaît dans la vue « Exécuter et

Déboguer ». Il suffit maintenant d'exécuter le batch (F5 ou le bouton

play).

 

 

- Le job se lance et le source du programme s'affiche à l'écran.

 

 

Il est ensuite possible d'avancer pas à pas dans l'exécution du

programme avec les touches F10 ou F11 ou Maj + F11, ou bien d'exécuter

jusqu'au prochain point d'arrêt avec F5.

 

Pour définir un point d'arrêt, il suffit de cliquer dans la marge du code

source. On peut définir des points d'arrêt conditionnels.

 

Quand on arrive sur une instruction qui met en jeu des variables, on voit

la valeur des variables dans la vue « variables ».

 

 

Il est aussi possible d'ajouter des espions sur les variables pour

suivre leur valeur tout au long de l'exécution.

 

#### Exemple de configuration

 

Voici un exemple de configuration pour déboguer le programme TOP0001 exécuté à la STEP01 du JCL DTOPT.TOP.JCL(TOPJ0001).

 

```json

{

  "configurations": [

    {

      "type": "workbench-batch",

      "request": "launch",

      "name": "TOP00001",

      "hciConnectionName": "SDEV",

      "jclDatasetMember": "DTOPT.TOP.JCL(TOPJ0001)",

      "jobName": "USERID00",

      "steps": [

        {

          "step": "STEP01",

          "program": "TOP00001",

          "DB2": false,

          "IMS": false

        }

      ],

      "ddios": ["DPOGT.IDEM.DDIO.COMMUN"],

      "loadlibs": ["DTOPT.TOP.LOAD"],

      "log": {

        "dsn": "DTOPT.TOP.VSC.LOG",

        "spaceUnit": "TRK",

        "primary": "5",

        "secondry": "5",

        "unit": "",

        "volume": "",

        "dataClass": "",

        "stgClass": "",

        "printSysoutClass": ""

      }

    }

  ]

}

```

 

#### Description des champs

 

- type : type de configuration de débogage (ne pas modifier).

 

- request : type de requête (ne pas modifier).

 

- name : nom de la configuration de débogage.

 

- hciConnectionName : Nom de la connexion HCI sur laquelle lancer le

  job (SDEV est celle par défaut pour le moment).

 

- jclDatasetMember : Nom du JCL à soumettre.

 

- jobName : jobname du JCL à soumettre.

 

- steps : liste des steps à déboguer.

 

  - step : nom de la step.

 

  - program : nom du programme exécuté à cette step.

 

  - DB2 : boolean qui indique si le programme fait du DB2 ou non.

 

  - IMS : boolean qui indique si le programme fait de l'IMS ou non.

 

- ddios : liste des DDIO dans lesquels chercher le code source.

 

- loadlibs : liste de loadlibs dans lesquelles chercher les loads.

 

- log : fichier de log pour la session de débogage.

 

### Déboguer une transaction CICS

 

Si vous avez déjà votre fichier launch.json (voir Déboguer un batch pour

voir comment le créer), vous pouvez y rajouter une configuration de

débogage.

 

Cliquer sur le bouton pour ouvrir la liste des configurations

d'exécution, puis choisir l'option « Ajouter une configuration ». Choisir

« workbench : Launch CICS ».

 

 

Appuyer sur PLAY sur la configuration pour commencer le débogage.

 

 

- Choisir la région sur laquelle on va chercher la transaction.

 

 

Le débogueur s'exécute, le code source est retrouvé automatiquement.

 

 

#### Exemple de configuration

 

Voici un exemple de configuration pour la transaction TOP0 qui exécute

le programme TOP0005P.

 

```json

{

  "configurations": [

    {

      "type": "workbench-cics",

      "request": "launch",

      "name": "CICS TOP0",

      "hciConnectionName": "SDEV",

      "cicsRegion": "${command:AskForCICSRegion}",

      "program": {

        "loadModule": "TOP0005P",

        "csect": "TOP0005P"

      },

      "trap": [

        {

          "users": {

            "loggedInUser": true

          },

          "trapAbends": true

        }

      ]

    }

  ]

}

```

 

#### Description des champs

 

- type : type de configuration de débogage (ne pas modifier).

 

- request : type de requête (ne pas modifier).

 

- name : nom de la configuration de débogage.

 

- hciConnectionName : Nom de la connexion HCI sur laquelle attendre la

  transaction (SDEV est celle par défaut pour le moment).

 

- cicsRegion : nom de la région CICS sur laquelle la transaction va

  s'exécuter. (Par défaut, le débogueur demande à chaque fois la

  transaction, il est aussi possible de mettre la valeur de la

  transaction en dur).

 

- program : description du programme à déboguer.

 

  - loadModule : nom du load module.

 

  - csect : nom de la control section associée au programme.

 

- trap : configuration pour piéger la transaction CICS à déboguer.

 

  - users : liste des utilisateurs à scanner, loggedInUser à true

    permet de reconnaître automatiquement l'utilisateur connecté sur

    la HCI pour piéger sa transaction.

 

  - trapAbends : permet de piéger les ABEND.

 

#### Exécuter la transaction

 

Il faut maintenant exécuter la transaction pour que celle-ci puisse être

piégée par le débogueur. Pour cela, plusieurs solutions :

 

- Utiliser l'[injecteur CICS](./injector.md) disponible dans IDEM VSC.

 

- Créer un fichier FB 80 sur le mainframe avec pour contenu :

 

```jcl

skeletonLibrary='MIG.ISPF.V5.ISPSLIB'

skeletonName='KIXINTRA'

SYSUID='X152543'                                 /* Utilisateur

NOMT='TOP0'                                      /* Nom de la transaction

NOMPROG='TOP0005P'                               /* Nom du programme

LONGCOM='100'                                    /* Longueur de la commarea

NOMCICS='CICSDVT'                                /* Région CICS

NOMFICH1='DTOPT.KIXINTRA.TOP0005P.ENTREE'        /* Fichier entrée commarea

NOMFICH2='DTOPT.KIXINTRA.TOP0005P.SORTIE'        /* fichier sortie commarea

FLAGFICH='O'                                     /* fichier sortie existant ? (O = Old, N = New)

LIGNE='X152543;CICSDVT;TOP0;TOP0005P;100'        /* récapitulatif : USER;regCiCS;Transac;transacName;longueurCommarea

SUP='>'

```

 

Puis exécuter la commande TSO \"EXEC \'DSOC.IDEM.EXEC(STRTCMDF)\'

'nomDuFichierCréé\'\" par exemple à l'aide de zowe explorer (CTRL+MAJ+P)

puis « Zowe Explorer : Issue TSO command » (on pourra utiliser l'account

IZUACCT).

 

Une fois la transaction soumise, l'exécution est piégée par l'extension

et on peut maintenant déboguer :

 

 

On a ici les mêmes possibilités que pour le débogage batch.

 

### Couverture du test

 

À l'aide de l'extension Code Coverage de BMC, il est possible de savoir quelles lignes du programme ont été exécutées lors d'une session de débogage. Cela peut être pratique pour voir si notre cas de test a bien testé la partie de code que l'on voulait.

 

La documentation éditeur est disponible ici [Documentation BMC]().

 

#### Mise en place

 

Pour utiliser Code Coverage, vous avez besoin d'un "coverage repository". Vous pouvez en créer un ou utiliser un existant depuis l'activité "Code Coverage". Dans la section "Code Coverage Repository", cliquer sur le bouton + puis créer votre repository ou sélectionner un repository existant.

 

Une fois que votre repository est prêt, il faut modifier votre configuration de débogage pour y ajouter les données nécessaires à Code Coverage. Pour cela, depuis la palette de commande (F1), exécuter la commande "DevX Code Debug: Edit Batch Debug Configuration". Aller dans l'onglet "Code Coverage" et renseigner les données nécessaires.

 

 

Une fois la configuration à jour, il suffit d'exécuter le débogage du programme.

À la fin de la session de débogage, une fenêtre de rapport de Code Coverage s'ouvre :

 

 

Cliquer sur la ligne correspondant au rapport généré, le programme s'ouvre dans une nouvelle fenêtre avec en vert les lignes par lesquelles le débogage est passé, et en rouge les lignes non couvertes par le test.

 

 

Pour plus d'informations, veuillez consulter la documentation éditeur.

 

---

 

## Développement

 

IDEM VSC est avant tous à atelier de développement pour les langages Cobol, PL/I, Assembler, Rexx et JCL.

 

Plusieurs extensions vont vous faciliter le dévelopement.

 

- IBM Z/Open Editor qui est un éditeur de code spécialiser dans les langages mainframes

- Cobol Control Flow qui permet de représenter les programmes Cobol sous forme de graphiques

 

### Editer du code

 

L'éditeur de code s'appelle IBM Z/Open Editor

La documentation éditeur se trouve ici : [IBM Z Open Editor documentation]()

 

#### Configuration de l'extension

 

Pour trouver les paramètres associés à l'extension IBM Z Open Editor

il faut rechercher « @ext:ibm.zopeneditor » dans les

settings VSC.

 

 

Lors de l'installation d'IDEM VSC, un paramétrage par défaut de IBM Z Open Editor est appliqué permettant de reconnaitre la plupart des fichiers Z/OS.

Il est possible d'éditer la configuration afin de rajouter d'autres règles d'identification de langages si besoin

 

#### Editer un programme

 

Pour utiliser IBM Z Open Editor il suffit d'ouvrir un fichier Cobol, JCL, Hlasm, Rexx, PL/I depuis n'importe quel explorer de Visual Studio Code.

Dans IDEM VSC, il est possible d'utiliser [Zowe Explorer](fr/IDEM-VSC/Guides/hostsExplorer.md#zowe-explorer), [Devx Explorer](fr/IDEM-VSC/Guides/hostsExplorer.md#devx-explorer) ou l'explorer de Visual Studio Code.

 

#### Ajouter l'auto-complétion des COPYBOOK

 

Pour permettre à IBM Z open Editor de récupérer des copybook en local ou directement sur le mainframe depuis Zowe Explorer il faut créer un fichier zapp.yaml dans le workspace.

Si vous n'avez pas de workspace vous pouvez simplement en créer un dossier sur votre poste, puis l'ouvrir depuis "file/open folder".

 

 

Dans ce fichier zapp.yaml le principe est de définir un propertyGroup pour chaque language avec des includes/copy à récupérer.

Dans ces propertyGroups on défini ensuite des librairies où chercher les copies.

 

Les librairies de type local, permettent de chercher les copies dans le workspace.

Les librairies de type mvs, permettent de chercher les copies dans un PDS sur le mainframe à l'aide de Zowe Explorer.

 

_Exemple de fichier zapp.yaml_

 

```yaml

name: TOP_SDEV

description: Application mainframe de test TOP pour SDEV

version: 1.0.0

author:

  name: ITIM/ASR/SMP/SDM

 

propertyGroups:

  - name: cobol-copybooks

    language: cobol

    libraries:

      - name: syslib

        type: local

        locations:

          - "**/Compilation/CPY"

      - name: syslib

        type: mvs

        locations:

          - "DTOPT.TOP.CPY"

          - "APP.SOURCLIB.MASTER.COPYEXPL"

          - "MQS.SCSQCOBC"

          - "PKZIP.V15.INSTLIB"

```

 

#### Les raccourcis utiles

 

| Action                                                             | Combinaison de touche          |

| ------------------------------------------------------------------ | ------------------------------ |

| Atteindre la déclaration                                           | F12                            |

| Atteindre les références                                           | Maj + F12                      |

| Retourner à la position précédente dans l'historique des positions | Alt + ←                        |

| Retourner à la position suivante dans l'historique des positions   | Alt + →                        |

| Renommer une variable                                              | F2                             |

| Mettre le document en forme                                        | Maj + Alt + F                  |

| Selectionner par colonne                                           | Maj + Alt + clic gauche        |

| Copier ; Couper ; Coller                                           | Ctrl + C ; Ctrl + X ; Ctrl + V |

| Ouvrir la palette de commande                                      | Ctrl + Maj + P                 |

| Déclencher l'autocomplétion                                        | Ctrl + Espace                  |

 

### Analyse graphique

 

**COBOL Control Flow** est une extension Visual Studio Code fournie avec

IDEM VSC. Elle permet de représenter un programme COBOL sous forme de

graphique pour mieux visualiser les liens entre les différents

paragraphes du programme.

 

La documentation éditeur se trouve ici : [COBOL Control Flow - Visual

Studio

Marketplace]()

 

#### Générer un graphique sur un programme COBOL

 

Ouvrir un programme COBOL dans l'éditeur VSC

 

Faire un clic droit sur le code source et choisir l'option « Generate

COBOL Control Flow »

 

 

Le diagramme de flux du programme s'ouvre sur la droite

 

 

On peut zoomer sur le graphique avec la molette

 

On peut utiliser les boutons « Collapse Unused » et « Expand All » pour

réduire et augmenter les données affichées

 

 

Si on clique sur un paragraphe dans le graphique, on est redirigé vers

son emplacement dans le code.

 

Si on laisse la souris au-dessus d'un paragraphe un extrait de code

s'affiche

 

 

#### Limitations

 

Sans l'extension « COBOL Language Support » les dépendances aux COPY ne

s'affichent pas sur le graphique

 

 

---

 

## DevX Code Insight

 

« DevX Code Insight » est une extension Visual Studio

Code fournie avec IDEM VSC. Elle permet de réaliser des analyses sur le code source et de faciliter des analyses d'impact ou la compréhension d'un programme.

 

La documentation éditeur se trouve ici : [BMC

Documentation]()

 

### Expliquation du code

 

Code Insight peut expliquer le code Cobol à l'aide d'un LLM. Cette fonctionnalité n'est pas encore disponible à la SG.

 

### Structure d'un programme

 

Code Insight permet d'analyser la structure d'un programme Cobol en identifiant les différentes sections, paragraphes et divisions. Cela facilite la navigation et la compréhension de la logique du programme.

 

### Flux de donnée

 

Cette fonctionnalité identifie les flux de données dans un programme, en mettant en évidence les variables d'entrée, de sortie et les transformations effectuées. Cela aide à comprendre comment les données circulent dans le programme.

 

### Flux logique d'un programme

 

Code Insight peut visualiser le flux logique d'un programme en représentant les chemins d'exécution possibles. Cela inclut les conditions, les boucles et les appels de sous-programmes.

 

### Vue procédurale

 

La vue procédurale offre une représentation hiérarchique des appels de procédures et sous-programmes, permettant de comprendre les relations entre les différentes parties du code.

 

### Résumé d'un programme

 

Cette fonctionnalité génère un résumé concis d'un programme Cobol, incluant les points clés comme les variables principales, les sections critiques et les dépendances externes.

 

### Mise en route

 

Pour utiliser Code Insight il suffit d'ouvrir un programme Cobol puis à l'aide d'un clic droit d'aller dans le sous-menu "Code Insight"

 

 

En cas de non fonctionnement, ou d'erreur, aller dans les settings (CTRL + ,) puis chercher "Licensing" et enfin cliquer sur le text "Validate Url"

 

 

---

 

## DevX File-AID

 

« DevX File-AID » est une extension Visual Studio

Code fournie avec IDEM VSC. Elle permet de visualiser un fichier en y ajoutant un calque, par exemple celui d'une COPY Cobol.

 

La documentation éditeur se trouve ici : [BMC

Documentation]()

 

### Ouvrir un fichier avec un calque

 

Depuis la vue DevX Explorer, cliquer droit sur le fichier à visualiser puis choississez les option "Browse with" (ou "Edit with") puis "Data Editor"

 

 

cocher ensuite "Single Layout" puis appuyer sur le bouton "Find" à coté de "Layout data set(member)" pour trouver votre COPY.

 

Selectionner ensuite le niveau à utiliser pour visualiser votre copy et si vous voulez utiliser le mode Edit ou Browse.

 

Cliquer enfin sur "Run". Une nouvelle vue s'ouvre permettant de visualiser vos données

 

 

En mode Edit vous pouvez supprimer une ligne en cliquant droit dessus puis "delete", modifier des valeurs en double cliquant dessus. Il faut ensuite sauvegarder avec CTRL+S

 

---

 

## Endevor

 

### Présentation Générale

 

« Idem Endevor » est une extension Visual Studio Code développée par l'équipe zDevOps

fournie avec IDEM VSC. Elle permet d'utiliser Endevor depuis Visual Studio Code.

 

### Le panel Endevor

 

Le panel Endevor est une vue disponible dans IDEM VSC qui permet de réaliser des actions sur Endevor depuis IDEM VSC. Par défaut, ce panel est disponible dans la vue des panels (CTRL + J pour l'ouvrir).

 

 

#### L'onglet Explore

 

L'onglet Explore permet de naviguer dans Endevor et de récupérer des informations sur les éléments. Sur la partie de gauche, vous avez la possibilité de renseigner un filtre puis de chercher dans Endevor les éléments qui correspondent à ce filtre en appuyant sur le bouton "Search".

 

 

La liste des éléments se charge dans un tableau.

Chaque ligne correspond à une version d'un élément dans Endevor. Les informations disponibles sont :

 

- Le nom de l'élément

- Le système Endevor

- L'environnement

- Le stage

- Le type de l'élément

- La version

 

Une colonne action permet de réaliser des actions directement sur un élément.

Le premier bouton (la loupe) permet d'utiliser la fonction détail, le deuxième bouton (l'écran avec une flèche vers le bas) permet de récupérer (retrieve) l'élément.

 

#### Fonction détail

 

Cette fonction permet de visualiser un élément dans le cycle de vie d'Endevor.

Elle est accessible depuis le bouton détail (la loupe) du tableau qui liste les éléments sur le panel Endevor.

 

 

On peut notamment y trouver :

 

- Dans chaque stage, la version de l'élément qui est en cours

- Si l'élément est en No Source ou non

- Le processor group utilisé pour l'élément

 

Des données supplémentaires apparaissent au survol de la souris sur le stage.

 

- L'utilisateur et la date avec lesquels l'élément a été modifié

- L'utilisateur et la date avec lesquels l'élément a été généré

 

 

#### Retrieve depuis le panel Endevor

 

Fonction en cours d'implémentation, merci de patienter encore un peu.

 

### Retrieve

 

Pour récupérer des éléments d'Endevor et les mettre dans un PDS, il faut réaliser un RETRIEVE.

Pour cela, vous pouvez utiliser les éléments suivants :

 

- La commande palette : Idem Endevor : Retrieve from Endevor

 

 

Saisissez l'application (Subsystem) depuis laquelle vous voulez récupérer un élément.

 

 

Sélectionnez l'environnement depuis lequel récupérer votre élément.

 

 

Sélectionnez le système depuis lequel vous voulez récupérer vos éléments (cette étape peut ne pas se présenter si un seul environnement existe pour vos critères précédents).

 

 

Choisissez le type des éléments à récupérer (il est possible de saisir une valeur avec "\*" par exemple "COB\*").

 

 

Saisissez un filtre pour le nom des éléments à récupérer.

 

 

Une fois la liste des éléments correspondant à votre filtre générée, vous pouvez sélectionner les éléments à récupérer (cette étape n'est pas nécessaire si un seul élément correspond au filtre).

 

 

Renseignez le PDS dans lequel vous voulez que vos éléments soient stockés :

 

- Le PDS doit exister

- Le PDS doit avoir les caractéristiques nécessaires aux éléments que vous récupérez

 

 

Un job de retrieve est alors soumis sur SDEV. L'Output "Idem Endevor" vous permet de savoir si le job est réussi ou non.

 

 

### Add

 

Pour ajouter un élément stocké dans un PDS dans Endevor, il faut réaliser un Add.

Pour cela, vous pouvez utiliser les éléments suivants sur une source ouverte depuis Zowe Explorer ou DevX Explorer :

 

- La commande palette : "Idem Endevor : Add to Endevor", qui ajoutera l'élément ouvert dans l'éditeur.

 

 

- Le menu contextuel de l'éditeur : la commande "Add to Endevor" disponible dans Idem Endevor, qui ajoutera l'élément ouvert dans l'éditeur.

 

 

- Le menu contextuel de Zowe Explorer : la commande "Add to Endevor", qui ajoutera l'élément sur lequel vous cliquez.

 

 

Une fois la commande lancée, renseignez les champs suivants :

 

- Application name (Subsystem)

 

 

- Le système

 

 

- L'environnement d'entrée cible

 

 

- Le type du composant à monter

 

 

Le job d'ADD est soumis et le résultat est visible dans l'output IDEM Endevor.

 

---

 

## FAQ

 

 

### Général

 

#### Comment installer IDEM VSC ?

 

L'installation s'effectue depuis le portail [Dev Tools | DEVPORTAL](). L'installation dure environ 5 minutes.

 

#### Comment mettre à jour IDEM VSC ?

 

La mise à jour s'effectue depuis le portail [Dev Tools | DEVPORTAL](). Elle effectue une désinstallation de la version en cours suivi d'une installation de la version souhaitée.

 

#### Je viens d'installer IDEM VSC, je ne sais pas par où commencer.

 

Vous pouvez suivre le [Kit de démarrage](fr/IDEM-VSC/Guides/guideDeDemarrage.md)

 

#### Puis-je installer IDEM VSC alors que j'ai déjà VSCode ?

 

Oui, bien sûr. Il n'y a aucun problème à l'installer. IDEM VSC utilise le mode portable de Visual studio code ce qui le rend isolé des autres installation de vscode.

 

#### Puis-je utiliser IDEM VSC et VSCode en même temps ?

 

Oui

 

#### Comment désinstaller IDEM VSC ?

 

La désinstallation s'effectue depuis le portail [Dev Tools | DEVPORTAL]().

 

#### Une fenêtre "Proxy Authentification" me demande un nom d'utilisateur et un mot de passe. Que faire ?

 

Vous pouvez ignorer cette demande en fermant simplement la fenêtre.

 

### Visual Studio Code

 

#### Comment réinitiliser le zoom de l'éditeur ?

 

Pour réinitialiser le zoom de l'éditeur, il faut ouvrir la palette de commande (F1 ou CTRL + MAJ + P), puis chercher la commande "View: Reset Zoom"

 

### Code Debug (Xpeditor)

 

#### Comment éviter les ABEND S0C1 lors du débogage d'un programme DB2 exécuté via IKJEFT01

 

Il faut ajouter dans sa configuration les LOADLIBS suivantes : "SYS2.DB2.SDEV.LOADLIB" et "SYS1.LE370.SCEERUN"

 

### Host Explorers

 

#### Comment faire une recherche dans le contenu des fichiers ?

 

Cette fonctionnalité est disponible dans Zowe Explorer. Pour l'utiliser il faut cliquer droit sur un PDS puis lancer la fonction "Search PDS Members". Enfin, renseigner le mot clé à rechercher puis valider avec "Entrée".

 

---

 

## Guide de démarrage

 

### Présentation Générale

 

IDEM VSC est un IDE Mainframe sur base VSCode packagé et pré paramétré

par l'équipe zDevOps. Un ensemble d'extensions sont ajoutées par défaut

lors de l'installation :

 

- Zowe Explorer: Explorateur de partition Mainframe

 

- Z Open Editor: Éditeur Cobol,JCL,REXX...

 

- DB2 for z/OS Developer: Création/exécution de scripts SQL DB2

 

- Git History : Visualiser aisément l'historique Git d'un dépôt

 

- SonarLint : Analyser vos sources Cobol directement depuis l'IDE

 

- DevX Explorer : Explorateur de partition Mainframe basé sur la HCI topaz

 

- DevX Code Debug : Débogueur de programme COBOL BATCH et CICS

 

- Cobol Control Flow : Représentation graphique d'un programme COBOL

 

- Compilation : plugin zDevOps pour compiler depuis l'IDE

 

- Injecteur : plugin zDevOps permettant l'exécution de transaction CICS ou IMS

 

- zServices : plugin zDevOps pour faciliter le developpement depuis un projet local (git)

 

Les paramétrages d'usine fournis lors de l'installation permettent une

prise en main facilitée des extensions packagées.

 

<iframe src=Icône pptx IDEM_VSC_quèsaco.pptx width="1000px" height="587px" frameborder="0">Ceci est un document <a target="_blank" href=https://office.com>Microsoft Office</a> incorporé, avec <a target="_blank" href=https://office.com/webapps>Office</a>.</iframe>

 

### Installation

 

L'installation s'effectue depuis le portail [Dev Tools | DEVPORTAL](). L'installation dure environ 5 minutes.

 

### Gestion des mots de passe

 

Pour utiliser les différentes extensions d'IDEM VSC, il est nécessaire de renseigner ses identifiants TSO à plusieurs endroits.

 

#### Zowe Explorer

 

Pour pouvoir utiliser l'explorer Zowe Explorer il faut d'abord pour chaque connexion au mainframe renseigner vos identifiants TSO.

Pour cela :

 

1. Cliquer sur la vue Zowe Explorer

2. Cliquer droit sur la connexion au mainframe à mettre à jour

3. Cliquer sur "Manage Profile"

4. Choississez "Add Credentials" ou "Update Credentials"

5. Renseigner votre identifiant TSO

6. Renseigner votre mot de passe TSO

 

 

#### Devx Explorer

 

Pour pouvoir utiliser l'explorer DevX Explorer il faut renseigner vos identifiants TSO

Pour cela :

 

1. Cliquer sur la vue Devx Explorer

2. Cliquer sur la connexion au mainframe à mettre à jour

3. Cliquer sur "Display filters"

4. Renseigner votre identifiant TSO

5. Renseigner votre mot de passe TSO

6. Sauvegarder votre saisie pour les utilisations futur en répondant "Yes" dans la notification

 

 

#### DB2 for z/OS Developer

 

Pour utiliser DB2 for z/OS Developer, il est nécessaire de renseigner son identifiant et mot de passe TSO sur chaque connexion DB2.

Pour cela :

 

1. Cliquer sur la vue DB2 Developer Extension

2. Cliquer droit sur la connexion DB2 à mettre à jour puis sur "Edit Connection"

3. Renseigner le champ "User Id" avec votre identifiant TSO

4. Renseigner le champ "Password" avec votre mot de passe TSO

5. Selectionner la case "Save Password"

6. Cliquer sur "Finish" pour valider votre saisie

 

 

#### Sonarlint

 

Pour utiliser Sonarlint avec le Cobol, il faut renseigner un token de connexion à SonarQube.

Pour cela :

 

1. Cliquer sur la vue Sonarlint

2. Déplier la connexion SonarQube

3. Appuyer sur le crayon pour éditer la connexion à SonarQube Dsp

4. Appuyer sur le bouton "Generate Token"

5. Valider l'ouverture du lien web

6. Se connecter à SonarQube via le bouton "Login with Github"

7. Appuyer sur le bouton "Allow Connection"

8. Retourner dans vscode, vérifier que le token a bien été saisi automatiqement

9. Appuyer sur le bouton "Save Connection"

 

 

---

 

Vous êtes maintenant en mesure d'utiliser IDEM VSC.

Poursuivez la documentation pour plus de détails sur chaque fonctionnalités.

 

---

 

## Explorateurs d'hôtes

 

IDEM VSC vous propose deux explorateurs qui permettent de naviguer dans le catalogue mainframe. Ces deux explorateurs sont **Zowe Explorer** et **DevX Explorer**.

 

### Comparaison des Explorateurs

 

| Fonctionnalités Host Explorer                  | Zowe Explorer                     | DevX Explorer |

| ---------------------------------------------- | --------------------------------- | ------------- |

| Gestion des filtres                            | Non                               | Oui           |

| Gestion des favoris                            | Oui                               | Non           |

| Allouer un dataset                             | Oui                               | Oui           |

| Nouveau membre                                 | Oui                               | Oui           |

| Allouer comme                                  | Oui                               | Oui           |

| Copier un dataset                              | Oui                               | Oui           |

| Supprimer un dataset                           | Oui                               | Oui           |

| Renommer un dataset                            | Oui                               | Oui           |

| Afficher les propriétés d'un dataset           | Oui                               | Oui           |

| Parcourir un membre                            | Oui                               | Oui           |

| Modifier un membre                             | Oui                               | Oui           |

| Copier un membre                               | Oui                               | Oui           |

| Couper un membre                               | Non                               | Oui           |

| Supprimer un membre                            | Oui                               | Oui           |

| Renommer un membre                             | Oui                               | Oui           |

| Voir les attributs d'un membre                 | Oui                               | Non           |

| Soumettre un JCL                               | Oui                               | Oui           |

| Désarchiver un dataset                         | Oui                               | Oui           |

| Soumettre des commandes MVS                    | Oui                               | Non           |

| Soumettre des commandes TSO                    | Oui                               | Non           |

| Filtrer/trier l'affichage des membres d'un PDS | Oui                               | Non           |

| Migrer un dataset                              | Oui (ne fonctionne pas chez nous) | Non           |

| Téléverser un membre                           | Oui                               | Non           |

| Ouvrir un module de chargement                 | Non                               | Oui           |

| Rechercher du texte dans les membres           | Oui                               | Non           |

| Rechercher du texte dans les datasets          | Oui                               | Non           |

 

| Fonctionnalités Unix Explorer | Zowe Explorer | DevX Explorer |

| ----------------------------- | ------------- | ------------- |

| Nouveau fichier               | Oui           | Oui           |

| Nouveau dossier               | Oui           | Oui           |

| Supprimer                     | Oui           | Oui           |

| Renommer                      | Oui           | Oui           |

| Modifier les permissions      | Oui           | Oui           |

| Afficher les propriétés       | Oui           | Oui           |

| Téléverser des fichiers       | Oui           | Non           |

| Copier                        | Oui           | Non           |

| Coller                        | Oui           | Non           |

| Copier le chemin              | Oui           | Non           |

| Parcourir/Modifier un fichier | Oui           | Oui           |

 

Modifier un fichier avec **DevX Explorer** bloque la ressource, tandis que le modifier avec **Zowe Explorer** ne bloque pas la ressource et propose un système de gestion des conflits lors de la sauvegarde.

 

### Zowe Explorer

 

La documentation éditeur se trouve ici : [Zowe Explorer documentation]()

 

#### Configuration de l'extension

 

Pour trouver les paramètres associés à l'extension Zowe Explorer, recherchez « @ext:zowe.vscode-extension-for-zowe » dans les paramètres de VSC.

 

 

Pour une première utilisation, il est nécessaire de saisir vos identifiants TSO pour les connexions au mainframe. Consultez le [Kit de démarrage](./guideDeDemarrage.md#gestion-des-mots-de-passe) pour voir comment gérer vos mots de passe.

 

#### Explorer les DATASETS du mainframe

 

Depuis la vue Zowe Explorer de VSCode, dans le panneau "Zowe Explorer", un onglet « DATA SETS » apparaît.

 

 

Créer un filtre de dataset :

 

- Cliquez sur la loupe à côté de la connexion.

 

 

- Renseignez le filtre à adopter puis appuyez sur Entrée (ou sélectionnez un ancien filtre dans la liste).

 

 

- Les datasets trouvés apparaissent dans l'explorateur.

 

 

Vous pouvez facilement naviguer dans les datasets avec la souris.

 

##### Actions sur la connexion (menu contextuel via clic droit)

 

- Rechercher des datasets

 

- Exécuter une commande MVS

 

- Exécuter une commande TSO

 

- Créer un dataset

 

- Mettre à jour les identifiants de connexion

 

 

##### Actions sur un PDS (menu contextuel via clic droit)

 

- Rafraîchir le dataset

 

- Afficher les attributs d'un dataset

 

- Allouer un dataset avec les mêmes attributs

 

- Créer un membre

 

- Téléverser un membre

 

- Copier/Coller un dataset

 

- Désarchiver un dataset

 

- Renommer un dataset

 

- Supprimer un dataset

 

- Rechercher un texte dans les membres d'un PDS

 

 

##### Actions sur un membre (menu contextuel via clic droit)

 

- Soumettre le job (si le membre est un JCL avec une carte job)

 

- Afficher les attributs du membre

 

- Copier

 

- Modifier

 

- Renommer

 

- Supprimer

 

 

##### Rechercher un texte dans les membres d'un PDS

 

Pour réaliser l'équivalent d'un scan de PDSMAN ou d'un search-for (3.14), utilisez la fonction "Search PDS members" en faisant un clic droit sur un PDS dans Zowe Explorer.

 

 

Puis renseignez le texte recherché :

 

 

Les résultats sont ensuite fournis dans le panneau Zowe ressources.

 

 

Vous pouvez filtrer les résultats ou trier chaque colonne en cliquant sur l'en-tête de la colonne.

 

### DevX Explorer

 

La documentation éditeur se trouve ici : [BMC Documentation]()

 

#### Configuration de l'extension

 

Pour trouver les paramètres associés à l'extension DevX Explorer, recherchez « @ext:BMC.devx-workbench-explorer » dans les paramètres de VSC.

 

 

**DevX Explorer : Show Migrated Data Sets :** Permet de choisir d'afficher ou non les datasets archivés dans l'explorateur.

 

**DevX Explorer : COBOL Copybooks :** Permet de lister les PDS dans lesquels chercher les COPY pour l'autocomplétion du code.

 

**DevX Explorer : Open Mode :** Permet de choisir le mode d'ouverture par défaut des fichiers.

 

**DevX Explorer : PL/I Includes :** Permet de lister les PDS dans lesquels chercher les includes PL/I pour l'autocomplétion du code.

 

Pour une première utilisation, il est nécessaire de saisir vos identifiants TSO pour les connexions au mainframe. Consultez le [Kit de démarrage](./guideDeDemarrage.md#gestion-des-mots-de-passe) pour voir comment gérer vos mots de passe

 

#### Explorer les DATASETS du mainframe

 

Depuis la vue de l'extension DevX Explorer :

 

 

Créer un filtre de dataset :

 

- Cliquez sur la loupe à côté de la connexion.

 

 

- Renseignez le filtre à adopter puis appuyez sur Entrée (ou sélectionnez un ancien filtre dans la liste).

 

 

- Renseignez votre identifiant et mot de passe TSO.

 

 

- Les datasets trouvés apparaissent dans l'explorateur.

 

 

Vous pouvez facilement naviguer dans les datasets avec la souris.

 

##### Actions sur la HCI (menu contextuel via clic droit)

 

- Rechercher un dataset

 

- Allouer un nouveau dataset

 

 

- Déconnexion

 

##### Actions sur un PDS (menu contextuel via clic droit)

 

- Nouveau membre

 

- Allouer comme

 

- Copier

 

- Supprimer

 

- Renommer

 

- Rafraîchir

 

- Propriétés

 

 

##### Actions sur un membre (menu contextuel via clic droit)

 

- Parcourir

 

- Modifier

 

- Copier

 

- Couper

 

- Supprimer

 

- Renommer

 

- Soumettre un JCL (déclenche le JCL puis une notification permet d'accéder directement au job output et/ou de le chercher dans Job Explorer)

 

---

 

## Injector

 

 

### Fonctionnalités

 

L'extension Idem Injector vous permet d'exécuter un transaction CICS ou IMS sans vous connecter au moteur correspondant. Elle est particulièrement utile lorsque vous voulez tester votre programme ou le déboguer. En effet elle vous permet d'exécuter le programme lié à votre transaction directement depuis l'IDE

 

### Configurations

 

#### Scope d'une configuration

 

Idem Injector vous permet de sauvegarder vos configurations d'injection et de les partager.

Pour cela il est important de bien choisir le scope de sa configuration quand on la créé.

 

- **Workspace** : signifie que la configuration est sauvegardé au niveau de votre workspace (à condition d'en avoir ouvert un) et peut donc être partagé dans sGitHub par exemple

- **User**: signifie que la configuration est sauvegardé au niveau de votre poste utilisateur. Et vous la retrouver donc quelque soit le workspace avec lequel vous travaillez.

 

#### Description d'une configuration

 

les données nécessaires pour une injection sont :

 

- Le nom de la configuration

- Le type de transaction

  CICS ou IMS

- Le host mainframe ciblé

  sdev.dns21.socgen

- Le fichier commarea d'entrée de la transaction

 

  C'est le fichier qui contient les données métiers envoyées à votre transaction.

 

- Le fichier commarea de sortie de la transaction

  C'est le fichier qui contient les données renvoyées par votre transaction.

- Le nom de la transaction

  TOP0, ECHO

 

Pour les transactions CICS :

 

- La région CICS sur laquelle exécuter la transaction

  CICSDVT

- Le nom du programme associé à la transaction

  TOP0005P

- La longueur de la commarea

  100

 

Pour les transactions IMS

 

- La région IMS sur laquelle exécuter la transaction

  SIMSD

- Le type de message

  MULTSEG ou SNGLSEG

  Cela indique si le message entrant peut contenir plusieurs segment ou un seul.

- Est-ce qu'on attend une réponse de la transaction ou non

 

#### Création d'une configuration

 

Pour créer une configuration d'injection vous avez deux possibilités :

 

- Via la commande palette "Idem Injector: Create an injector configuration"

 

 

- Directement dans le fichier json accessible depuis l'UI [settings](command:workbench.action.openSettings) (CTRL + ,)

 

 

#### Suppression d'une configuration

 

Pour supprimer une configuration d'injection vous avez deux possibilités :

 

- Via la commande palette "Idem Injector: Delete injectors configurations"

 

 

- Directement dans le fichier json accessible depuis l'UI [settings](command:workbench.action.openSettings) (CTRL + ,)

 

#### Mettre à jour une configuration

 

Pour mettre à jour une configuration d'injection vous pouvez :

 

- Modifier le fichier json accessible depuis l'UI [settings](command:workbench.action.openSettings) (CTRL + ,)

- Une commande palette sera ajoutée dans le futur

 

### Exécuter une transaction

 

Pour exécuter une transaction il suffit d'utiliser la commande palette "Idem Injector: Launch a transaction".

De selectionner la transaction à lancer puis de cliquer sur OK.

 

 

Vous recevrez une notification vous indiquant le JobID du JCL soumis.

Il est nécessaire d'aller voir le compte rendu de ce job pour vérifier sa bonne exécution.

 

---

 

## Issues

 

 

### Idem compilation

 

- Lors d'une compilation le message "'cmd' n’est pas reconnu en tant que commande interne ou externe, un programme exécutable ou un fichier de commandes." apparait. Ce message n'a pas d'incidence et sera enlever lors de la refonte de la compilation prévue pour IDEM VSC 25.2

- Lors de la compilation si mon programme a des modifications non sauvegardées elle ne sont pas prise en compte. Dans les prochaines version un paramètre permettra de forcer la sauvegarde du fichier avant la compilation.

 

### Idem Endevor

 

- La première exécution d'une commande Endevor ne fait rien, les suivantes sont fonctionnelles. Le problème est en cours de correction

- Lors d'un Retrieve, si on écrit son filtre sur l'élément en minuscule, alors on ne retrouve pas ses éléments. Cela est dû au fait qu'Endevor est sensible à la casse pour certain élément UNIX. Lors d'une prochaine version on appliquera automatiquement la saisie en majuscule pour éviter le problème, vu que les éléments en minuscule ne sont pas censés être Retrieve.

- Lors des commandes Endevor, plusieurs choses sont manquantes (modification du CCID, du processor group, de nom de l'élément à Retrieve, ...), ceci sera possible dans le futur.

 

### Zowe Explorer

 

- Il arrive qu'au niveau du Job Explorer de Zowe Explorer, un favori vide apparait, empêchant le job explorer de fonctionner correctement. Il faut supprimer le favoris vide pour enlever le problème. Le problème sera corrigé dans la prochaine version d'IDEM VSC 25.1

 

### Devx Code Debug

 

- Je n'arrive pas à déboguer un programme DB2 soumis via IKJEFT01, le job plante en abend S0C1. Il s'agit ici d'un problème de configuration de la session de débogage. Il faut rajouter les LOADLIB suivantes dans la configuration : "SYS2.DB2.SDEV.LOADLIB", "SYS1.LE370.SCEERUN"

 

### DB2 for Z/OS Developper

 

- Lors de la soumission d'un script SQL sans être au préalable connecté à une base de données, l'extension propose de choisir une base de données sur laquelle soumettre la commande. Lorsque l'on choisit une base de données rien ne se passe

 

---

 

## Jobs Explorer

 

IDEM VSC vous propose deux explorer qui permettent de naviguer dans JES. Ces deux explorer sont **Zowe Explorer** et **DevX Explorer**

 

### Comparaison des Explorers

 

| Fonctionnalités Jobs Explorer        | Zowe Explorer                         | DevX Explorer |

| ------------------------------------ | ------------------------------------- | ------------- |

| filtrer par prefix + owner           | oui                                   | oui           |

| filtrer par status                   | oui                                   | non           |

| Chercher par job id                  | oui                                   | oui           |

| ouvrir la sysout global d'un job     | non                                   | oui           |

| télécharger les sysouts              | oui                                   | non           |

| télécharger l'output en zip          | oui                                   | non           |

| ouvrir un DD spécifique de la sysout | oui                                   | oui           |

| resoumettre un job                   | non                                   | oui           |

| purger un job                        | oui                                   | oui           |

| Extraire le JCL du job               | oui                                   | oui           |

| gestion de jobs favoris              | oui                                   | non           |

| Voir les jobs en cours               | oui                                   | non           |

| issue modify command                 | oui (mais bloqué par des droits zowe) | non           |

| Issue stop command                   | oui (mais bloqué par des droits zowe) | non           |

 

### Zowe Explorer

 

La documentation éditeur se trouve ici : [Zowe Explorer documentation]()

 

#### Configuration de l'extension

 

Pour trouver les paramètres associés à l'extension Zowe Explorer

il faut rechercher « @ext:zowe.vscode-extension-for-zowe » dans les

settings VSC.

 

 

Pour une première utilisation il est nécessaire de saisir ses identifiants TSO sur les connexion aux mainframe. consulter le [Kit de démarrage](./guideDeDemarrage.md#gestion-des-mots-de-passe) pour voir comment gérer vos mots de passe

 

#### Utiliser Job Explorer

 

Depuis la vue Zowe Explorer de VSCode, dans le panneau "Zowe Explorer" apparaît un onglet « JOBS ».

 

 

Pour accéder aux jobs sur SDEV, positionner la souris sur SDEV puis appuyer sur la loupe.

 

 

Une fenêtre apparait permettant de selectionner un filtre de recherche ou d'en créer un.

 

 

Il est possible de chercher un job soit par son job ID soit en créant un filtre. Pour créer un filtre cliquer sur "create job search filter". cliquer ensuite sur "job Owner", "job Prefix" ou "job status" pour ajouter votre filtre sur le champs indiqué. Une fois votre filtre terminé cliquer sur "Sumbit this Job Search Query"

 

 

Les jobs trouvés apparaissent maintenant dans la vue job.

 

 

A partir d'ici avec le clic gauche de la souris il est possible de récupérer le contenu des différentes sysout du jobs et de les consulter depuis visual studio code.

 

Dans la liste des jobs, avec un clic droit sur le job on peut :

 

- Rafraichir le job dans la liste s'il n'était pas terminé

 

- Extraire le JCL

 

- Télécharger le contenu complet du spool

 

- Arreter le job

 

- Ajouter le job aux favoris

 

- Supprimer le job du spool

 

 

Dans la liste des output d'un job, avec un clic droit sur un output on peut :

 

- Télécharger l'ouput en binaire ou non

 

- Itérer la récupération de l'ouput (Start Polling). Permet de requeter à un interval de temps donner le spool pour récupérer le contenu de l'output.

 

 

### DevX Explorer

 

La documentation éditeur se trouve ici : [BMC

Documentation]()

 

#### Configuration de l'extension

 

Pour trouver les paramètres associés à l'extension DevX Explorer

vous pouvez rechercher « @ext:BMC.devx-workbench-explorer » dans les

settings VSC.

 

 

**Job Explorer : Columns :** Permet de choisir les colonnes

à afficher dans l'explorateur de job

 

**Job Explorer : Job Limit :** Fixe la limite de job à

afficher dans l'explorateur de job

 

Pour une première utilisation il est nécessaire de saisir ses identifiants TSO sur les connexion aux mainframe. consulter le [Kit de démarrage](./guideDeDemarrage.md#gestion-des-mots-de-passe) pour voir comment gérer vos mots de passe

 

#### Utiliser Job Explorer

 

Depuis n'importe quelle vue de VSCode, dans le panneau des outputs

(Problèmes, sortie, Terminal, etc) apparaît un onglet « JOB EXPLORER ».

Naviguer vers cet onglet. Dans Search renseigner le prefix du Job à

chercher et l'owner puis appuyer sur search. Si vous n'êtes pas encore

connecté à la HCI renseigner vos identifiants TSO.

 

 

Vous pouvez ensuite sélectionner le job à consulter. Un double clic sur

le job ouvre la sysout complète. Un double clic dans la liste des

outputs du job permet de voir l'output concerné

 

 

Dans la liste des jobs, avec un clic droit sur le job on peut :

 

- Cancel un job executing

 

- Resoumettre un job

 

- Extraire le JCL

 

- Rafraîchir l'affichage

 

- purger un job de SDSF

 

 

---

 

## Développement local

 

 

L'extension Idem zServices disponible dans IDEM VSC permet de travailler avec un projet local. C'est à dire avec des fichiers stockés sur votre ordinateur.

Ceci est particulierement utile lorsque votre code est stocké dans git.

Idem zServices vous propose les fonctionnalités suivante : - téléverser (Upload) des fichiers sources vers une partition mainframe. (Il est possible de téléverser seulement des membres de PDS au format FB 80) - Compiler (Build) vos programmes locaux sur SDEV.

 

### Prérequis

 

Pour pouvoir utiliser cette fonctionnalité il vous faut les autorisations sur la HCI de la partition concernée. Ces droits sont disponibles dans le rôle :

 

R-\*\*\*-TOP-IDEM (\*\*\* = ALL/DVP/DEO/HOF/MOF suivant votre profil)

 

    - ALL : Transverse

    - DVP : Développeur ITIM

    - DEO : Développeur Offshore/TTIS

    - HOF : Homologation

    - MOF : Maîtrise d'ouvrage

 

Ce rôle contient les droits suivants :

 

    - PDSUEBAS pour les accès HCI SDEV

    - PH$TOP22 pour les accès HCI HY99

 

### Configuration

 

L'extension zServices vous permet de créer des profils

 

- Lancer la commande "Idem zServices: Manage profiles" disponible depuis la commande palette, le menu contextuel de l'éditeur ou celui de l'explorer

 

 

Depuis cette vue vous pouvez gérer vos profils zServices (création, suppression, modification)

 

 

Les profils sont organisés en trois quatres blocs :

 

- **Global settings**, les paramètres globaux du profils

 

  - **Configuration Scope** _(Obligatoire)_: défini où est sauvegardé votre profil.

 

    - **_Workspace_** : Le profil est sauvegardé dans votre workspace, vous pouvez donc partager la configuration avec vos collègues à l'aide de git

    - **_User_** : Le profil est sauvegardé sur votre PC. Il est donc utilisable avec n'importe quel workspace

 

  - **Profile name** _(Obligatoire)_: défini le nom du profil

 

- **Upload settings**, les paramètres utiles au téléversements de membres vers une partition mainframe :

 

  - **Destination Hostname** _(Obligatoire)_: Il s'agit de l'hostname de la partition mainframe sur laquelle vous voulez upload un fichier. Par exemple pour SDEV il faut renseigner sdev.dns21.socgen

 

  - **High level qualifier** _(Obligatoire)_: Ici il faut définir la racine des PDS qui contiendrons vos fichiers après upload. Par exemple "DTOPT.TOP"

 

  - **Extension Mapping** : Dans ce tableau vous allez définir pour chaque extension de fichiers vers quel PDS vous aller l'upload. Par exemple si j'ajoute la ligne

    .cbl -> SOURCE, alors mes fichiers \*.cbl seront téléverser dans le PDS HLQ.SOURCE (DTOPT.TOP.SOURCE si HLQ = DTOPT.TOP)

 

  - **Ignore Pattern** : Il faut ici renseigner des pattern de fichiers que l'on veut ignorer pour les actions de zServices (principe similaire au fichier gitignore). Par exemple si mon workspace contient un dossier .vscode à sa racine et que ce dossier contient des fichiers qui ne doivent pas être téléverser sur le mainframe. Alors je peux rajouter la ligne ".vscode/" dans le tableau Ignore Patterns, pour que ce dossier soit ignoré. Les dossiers suivants sont la plupart du temps à ignorer :

    - .vscode/

    - .git/

    - .github/

    - .settings/

 

  Pour plus d'informations sur la synthaxe des patterns, vous pouvez consulter cette page :

 

- **Build settings**, les paramètres nécessaire pour compiler un programme. Il est impératif de renseigner aussi les paramètres d'upload pour pouvoir compiler

 

  - **Application id** _(Obligatoire)_: Trigramme de l'application associé au programme à compiler

 

  - **DB2 Owner** _(Obligatoire)_: Owner DB2 à utiliser pour les compilations DB2

 

    - **_DVLUSER_**

    - **_DappA_** -> Correspond à DTOPA si "Application ID" = "TOP"

 

  - **Target environment** _(Obligatoire)_: L'environnement ciblé nécessaire aux compilations DB2

 

  - **DDIO file**: Fichier de listing de source. Si non renseigner on utilise DPOGT.IDEM.DDIO.COMMUN

 

  - **Load Library** _(Obligatoire)_: La library de load module ou stocké le load module généré

 

  - **Copy libraries**: La liste des PDS de copy nécessaires à la compilation.

 

- **Delivery settings** _(En cours d'implémentation)_

 

### Choix du profil actif

 

Il est possible de choisir le profil à utiliser pour zServices de plusieurs façons :

 

- En lançant une commande alors qu'aucun profil n'a été défini comme actif

- En utilisant la commande "Idem zServices: switch profiles" disponible depuis la commande palette ou les menus contextuels de l'éditeur et de l'explorer.

 

 

- En utilisant la case à cocher "Active Profile" disponible depuis la vue "Manage Profile"

 

 

### Téléverser des fichiers (Upload)

 

Pour téléverser des fichiers vers le mainframe il faut :

 

- Aller dans la vue explorer de vscode

- Selectionner les dossiers et/ou fichiers que vous voulez téléverser

- Faire clic droit, puis choisir "Idem zServices: Upload"

- Choisir le profil zService à utiliser (seulement si aucun profil n'est défini comme actif)

- Renseigner vos identifiants mainframe (seulement la première fois)

- Consultez le résultat dans l'output.

 

 

Il est aussi possible de téléverser directement tous les fichiers de son workspace :

 

- Aller dans la vue explorer de vscode

- Faire clic droit, sur n'importe quel fichier du workspace

- Choisir la commande "Idem zServices: Upload project"

- Choisir le profil zService à utiliser (seulement si aucun profil n'est défini comme actif)

- Renseigner vos identifiants mainframe (seulement la première fois)

- Consultez le résultat dans l'output.

 

 

### Compiler un programme (Build)

 

#### Calcul des dépendances

 

Avant de pouvoir compiler un programme, il faut qu'IDEM VSC calcule plusieurs choses :

 

- Avoir la liste des copy utilisé par le programme

- Calculer le type du programme (BATCH, CICS, IMS, DB2, MQ)

 

Pour cela une commande est disponible : "Idem zServices: Calculate dependencies".

Le résultat de la commande est sauvegarder dans à la racine de votre workspace dans un fichier dependencies.xml.

 

Cette action est lancé automatiquement avant un build si votre programme n'est pas trouvé dans le fichier dependencies.xml.

Si vous ajouter un appel de copy ou un appel DB2 ou MQ à votre programme alors il faut relancer manuellement le calcul de dépendance avant de lancer un Build.

 

```xml

<?xml version="1.0" encoding="utf8"?>

<sources xmlns= >

    <source>

        <localFile>Compilation\SRC\TOP0008P.cbl</localFile>

        <dependencies>

            <sourceRef>Compilation\CPY\TOPC0002.cpy</sourceRef>

            <sourceRef>Compilation\CPY\TOPJOURT.cpy</sourceRef>

        </dependencies>

        <types>

            <type>CICS</type>

            <type>DB2</type>

            <type>MQ</type>

        </types>

    </source>

</sources>

```

 

<p align="center"><em>Exemple de fichier dependencies.xml</em></p>

 

Pour lancer manuellement le calcul de dépendance vous pouvez utiliser :

 

La commande palette (F1) "Idem zServices: Calculate dependencies" ou les menus contextuels de l'explorer et de l'éditeur (Idem zServices puis Calculate dependencies)

 

#### Lancement d'un Build

 

Pour compiler un programme vous pouvez lancer la commande Build ou Build... depuis :

 

- La commande palette pour build le programme ouvert dans l'éditeur.

- Le menu contextuel de l'éditeur pour build le programme ouvert dans l'éditeur.

- Le menu contextuel de l'explorer pour build le programme sur lequel vous faite clic droit.

 

##### Build

 

Le build permet de compiler le programme directement avec le profil zServices actif.

 

 

Une fois la commande "Build" lancé, vous avez des informations dans l'output "Idem zServices" et vous recevez une notification avec un lien pour accéder à la sysout du job de compilation.

 

##### Build...

 

Le Build... permet aussi de compiler un programme mais avec une étape de configuration supplémentaire. Lors de l'exécution de la commande une vue s'ouvre :

 

 

Depuis cette vue vous pouvez :

 

- Modifier le profil avec lequel réaliser la compilation (sans modifier le profil zServices actif)

- Voir les informations concernant le programme qui va être compiler

  - Le type de compilation qui va etre effectué. Il est modifiable, il suffit de cliquer sur la cellule du tableau et de selectionner les type souhaités.

 

 

    - Les dépendences qui vont être upload sur le mainframe

    - Les paramètres de compilation spécifiques qui seront appliqués, vous pouvez en rajouter directement depuis la case

 

- Choisir d'upload ou non les copy associés au programme

- Lancer le build avec le bouton "Build"

 

De la même façon que le build le résultat apparait dans l'output zServices.

 

##### Build callers

 

Le build callers permet de compiler les programmes qui utilisent une copy. Il s'éxécute depuis la copy directement.

Chaque programme qui appelle la copy sera compiler avec le profil zServices actif.

 

 

##### Build... callers

 

Le build... callers permet aussi de compiler les programmes utilisés par une copy, mais avec une étape de configuration supplémentaire.

Le principe est le même que pour Build...

 

---

 

## Prérequis

 

 

### Habilitations

 

IDEM VSC nécessite les droits suivants :

 

    - PD$$0000 pour les accès HCI SDEV

    - PH$TOP22 pour les accès HCI HY99 et ASYS

    - PDZASU1 pour les accès à Zowe SDEV

    - PHZASU1 pour les accès à Zowe HY99 et ASYS

 

Le rôle R-\*\*\*-TOP-IDEM contient les droits pour SDEV

 

Le rôle R-\*\*\*-TOP-HCI_KLI contient les droits pour HY99 et ASYS

 

\*\*\* = ALL/DVP/DEO/HOF/MOF suivant votre profil :

 

    - ALL : Transverse

    - DVP : Développeur ITIM

    - DEO : Développeur Offshore/TTIS

    - HOF : Homologation

    - MOF : Maîtrise d'ouvrage

 

Pour obtenir ces droits, rendez-vous dans [Whats]() et cliquez sur **Gestion de l'accès utilisateur** :

 

 

Cliquez sur votre profil, puis cliquez sur **Suivant** :

 

 

Saisissez les droits voulus (1), cliquez sur la loupe (2), Cochez les droits qui apparaissent en dessous (3), puis cliquez sur **Suivant** :

 

 

Enfin, cliquez sur **Soumettre** :

 

 

### Licences

 

Certaines fonctionnalités d'IDEM VSC nécessitent une licence pour pouvoir être utilisées.

La plupart des licences sont directement intégrés dans les produits.

 

Pour pouvoir utiliser l'extension "IBM DB2 for Z/OS developper" qui permet d'exécuter des requêtes SQL/DB2 et de parcourir le catalogue DB2 il est nécessaire de récupérer une licence du driver JDBC.

Pour cela, depuis IDEM VSC :

 

- Lancez la palette de commandes (en apuyant sur F1)

- Saisissez "JDBC" puis cliquez sur la commande "Idem First Aid Kit: Retrieve JDBC license file"

 

 

Vous avez maintenant une licence pour utiliser "IBM DB2 for Z/OS developper"

 

---

 

## Notes de version

 

 

### 25.1.1 (16/06/2025)

 

#### Idem Compilation

 

Correction d'un bug sur le calcul de type pour Idem Compilation qui renvoyait toujours "BATCH".

Correction d'un bug sur la compilation des programmes présents dans certains PDS avec un nommage particulier qui empêchait leur compilation.

 

### 25.1.0 (06/05/2025)

 

#### Souche Idem VSC 25.1

 

- Mise à jour des paramètres par défaut pour Zowe v3

- Ajout d'un fichier de log pérenne pour l'installeur

- Ajout du paramétrage "files.autoSave" à OFF par défaut pour éviter de sauvegarder les modifications sur le mainframe sans validation du développeur

 

#### Extensions Marketplace

 

- Ajout de DevX Code Insight en version 25.4.0 [_Release note_]()

  - Cette nouvelle extension permet d'analyser le code source des programmes

  - Générer des graphiques représentant les échanges entre les paragraphes

  - Voir quand et comment une variable est alimentée ou modifiée

  - Et plein d'autres fonctionnalités [_Documentation_]()

  - Les fonctionnalités nécessitant un LLM (Code explain) ne sont pour le moment pas fonctionnelles

- Ajout de DevX Code Coverage en version 25.4.0 [_Release note_]()

  - Cette nouvelle extension permet après une session de debug de visualiser facilement les lignes de code qui ont été exécutées ou non.

  - Pour plus d'informations sur comment utiliser l'extension, vous pouvez consulter la [_Documentation_]()

- Mise à jour de DevX Code Debug en version 25.4.0 [_Release note_]()

- Mise à jour de DevX Explorer en version 25.4.0 [_Release note_]()

  - Timeout de la connexion à la HCI synchronisé avec le paramétrage côté mainframe (avant un timeout de 60m était défini)

- Mise à jour de DevX File-Aid en version 25.4.0 [_Release note_]()

- Mise à jour de IBM DB2 for Z/OS Developer en version 2.2.0 [_Release note_]()

  - Mise à jour du nommage et de la liste des DB2 accessibles depuis IDEM VSC pour plus de clarté.

  - Correction du bug qui empêchait de pouvoir accéder directement aux tables depuis le catalogue

  - Ajout de la possibilité d'éditer les tables directement depuis l'extension

- Mise à jour de IBM Z/Open Editor en version 5.1.0 [_Release note_]()

  - Prise en charge du langage JCL

- Mise à jour de Zowe Explorer en version 3.1.1 [_Release note_]()

  - Ajout de la fonctionnalité de workspace virtuel

  - Amélioration des messages d'erreur

  - Ajout de la fonctionnalité Search PDS members & Search Filtered Data Sets qui permet de chercher une chaîne de caractères dans l'ensemble des membres d'un PDS ou dans l'ensemble des datasets filtrés.

- Mise à jour de Sonarlint en version 4.19.0 [_Release note_]()

- _Annonce de décommissionnement_ : L'extension Cobol Control Flow ne pouvant plus être mise à jour, et une alternative plus complète "Code Insight" étant disponible, nous allons l'enlever dans une future release.

 

#### Extensions zDevOps

 

##### Idem Endevor

 

- Nouveau panel "Endevor" qui sera le hub des fonctionnalités autour de Endevor

- Ajout d'une fonctionnalité permettant de lister les éléments présents dans Endevor correspondant à un filtre

- Ajout de la fonctionnalité détails qui permet de voir les différentes versions d'un élément dans le cycle de vie d'Endevor. No Source, processor group, user et date de génération sont trouvables grâce à la vue détail.

- Correction d'un bug sur la commande retrieve qui empêchait de voir les éléments si on écrivait le filtre en minuscule

- Suppression du cache sur la liste des éléments à retrieve pour la fonction retrieve

- Détermination automatique du 2ème caractère du CCID lors d'un ADD. De futurs travaux sont prévus pour avoir une génération globale et cohérente du CCID.

- Travaux de mise en compatibilité avec Zowe v3

 

##### Idem zServices

 

Nouvelle extension zServices qui permet de travailler depuis un dossier local.

 

La première fonctionnalité disponible dans cette release est l'upload d'un projet local vers le mainframe

 

- Ajout des settings permettant de déclarer ses profils zServices, et de choisir quel est le profil actif

- Idem zServices: Manage profiles => nouvelle commande permettant d'ouvrir une interface pour gérer ses profils zServices

- Idem zServices: Switch profiles => nouvelle commande permettant de choisir le profil zService à utiliser

- Idem zServices: Upload => nouvelle commande qui permet d'upload vers le mainframe les fichiers sélectionnés dans l'explorer

- Idem zServices: Upload project => nouvelle commande qui permet d'upload un projet entier vers le mainframe

 

Cette extension permettra dans le futur aussi de compiler et livrer dans Endevor des sources.

 

##### Idem Compilation

 

- Correction du contrôle de surface sur le settings DDIO.

 

##### Idem First Aid Kit

 

- Mise à jour de la fonction de récupération de licence JDBC pour s'affranchir du fichier de licence provenant d'IDEM Eclipse.

- Mise à jour de la fonction de remise à zéro des paramétrages de SonarQube For Ide et Zowe pour être cohérent avec le paramétrage par défaut

- Ajout de la possibilité de remettre à zéro le paramétrage par défaut de VSCODE via la fonction "Reset Parameters"

 

##### Idem Injector

 

- Ajout d'un lien vers le spool du job soumis après une injection

- Correction d'un bug lors de la création d'une configuration si le fichier settings.json est indisponible

 

##### Idem Audit

 

- Mise en place de traces pour l'ensemble des commandes des extensions IDEM VSC zDevOps.

 

### 24.3.0 (12/12/2024)

 

#### Souche Idem VSC 24.3

 

- Mise à jour de VSCode en version 1.94.2 [_Release note_]()

- Ajout de paramètres pour faire confiance à IDEM VSC sans workspace d'ouvert

- Suppression du raccourci après désinstallation

- Ajout des noms de domaines utilisés par IDEM VSC dans la liste des domaines de confiance

- Ajout d'un nouveau setting par défaut pour éviter Z/Open Editor d'essayer de générer un fichier zapp.yaml quand aucun workspace n'est ouvert

- Ajout de l'installation de NodeJs nécessaire à Sonarlint

 

#### Extensions Marketplace

 

- Mise à jour de DevX Code Debug en version 24.10.0 [_Release note_]()

  - Possibilité de retourner en arrière dans une session de debug

- Mise à jour de DevX Explorer en version 24.10.0 [_Release note_]()

  - Possibilité d'allouer un PDS en copiant les propriétés d'un autre et en en modifiant certaines

  - Possibilité de modifier son mot de passe depuis une commande palette

  - Possibilité de comparer des datasets

- Mise à jour de Devx File-Aid en version 24.10.0 [_Release note_]()

  - Ajout de FileAid DB2

  - Ajout de la possibilité d'utiliser un fichier de critère de sélection

- Mise à jour de IBM DB2 for Z/OS Developer en version 2.1.7 [_Release note_]()

- Mise à jour de IBM Z/Open Editor en version 4.5.0 [_Release note_]()

  - Prise en charge du langage JCL

- Mise à jour de Zowe Explorer en version 2.18.0 [_Release note_]()

- Mise à jour de Sonarlint en version 4.10.0 [_Release note_]()

 

#### Extensions zDevOps

 

##### Idem Endevor

 

Nouvelle extension qui permet de réaliser des actions dans endevor depuis IDEM VSC.

 

- Retrieve d'éléments de Endevor vers un PDS à partir d'un filtre

- Add d'un élément d'un PDS vers Endevor

 

##### Idem zServices

 

Nouvelle possibilité de compiler un programme stocké en local.

 

- Ajout des paramètres de compilation dans les profils zServices

- Ajout des paramètres de compilation dans la vue "manage profiles"

- Ajout des commandes Build et Build... pour les fichiers .cbl et .cob

- Ajout d'une commande calculate dependencies pour analyser les dépendances entre programmes et copies et calculer le type d'un programme

- Correction de l'affichage des erreurs dans les tableaux sur la vue "Manage profiles"

- Ajout d'un indicateur dans la vue "Manage profiles" qui permet de voir et choisir quel est le profil actif

- Modification du fonctionnement du paramètre "Excluded Folder" des profils zServices. Il s'agit maintenant d'"Ignore patterns". Il est possible, à l'image de ce que permet un fichier .gitignore, d'ignorer des fichiers et des dossiers en fonction d'un pattern défini.

- Amélioration de la compatibilité avec différents thèmes pour la webview Manage Profile

- Correction d'un bug empêchant l'activation d'un profil après sa création

 

##### Idem Compilation

 

- Correction du contrôle de surface sur le settings DDIO.

 

##### Idem First Aid Kit

 

- Mise à jour de la fonction de récupération de licence JDBC pour s'affranchir du fichier de licence provenant d'IDEM Eclipse.

- Mise à jour de la fonction de remise à zéro des paramétrages de SonarQube For Ide et Zowe pour être cohérent avec le paramétrage par défaut

- Ajout de la possibilité de remettre à zéro le paramétrage par défaut de VSCODE via la fonction "Reset Parameters"

 

##### Idem Injector

 

- Amélioration des IHM de création et suppression de profils d'injection. Notamment avec l'ajout de sécurité si les fichiers settings.json contiennent des erreurs de syntaxe.

 

##### Idem Audit

 

- Mise en place de traces pour l'ensemble des commandes des extensions IDEM VSC zDevOps.

 

### 24.2.0 (18/07/2024)

 

#### Souche Idem VSC 24.2

 

- Mise à jour de VSCode en version 1.88.0 [_Release note_]()

- Désactivation de la recherche automatique des mises à jour d'extension qui pouvait induire en erreur

 

#### Extensions Marketplace

 

- Mise à jour de DevX Code Debug en version 24.4.0 [_Release note_]()

- Mise à jour de DevX Explorer en version 24.4.0 [_Release note_]()

  - Possibilité d'allouer un PDS en copiant les propriétés d'un autre et en en modifiant certaines

  - Possibilité de modifier son mot de passe depuis une commande palette

  - Possibilité de comparer des datasets

- Mise à jour de Devx File-Aid en version 24.4.0 [_Release note_]()

  - Ajout de FileAid DB2

  - Ajout de la possibilité d'utiliser un fichier de critère de sélection

- Mise à jour de IBM DB2 for Z/OS Developer en version 2.1.5 [_Release note_]()

- Mise à jour de IBM Z/Open Editor en version 4.1.0 [_Release note_]()

- Mise à jour de Zowe Explorer en version 2.13.1 [_Release note_]()

  - Ajout des connexions à ASYS

- Mise à jour de Sonarlint en version 4.4.2 [_Release note_]()

 

#### Extensions zDevOps

 

##### Idem zServices (nouveauté)

 

Ajout d'une nouvelle extension zServices qui permet de travailler depuis un dossier local.

La première fonctionnalité disponible dans cette release est l'upload d'un projet local vers le mainframe

 

- Ajout des settings permettant de déclarer ses profils zServices, et de choisir quel est le profil actif

- Idem zServices: Manage profiles => nouvelle commande permettant d'ouvrir une interface pour gérer ses profils zServices

- Idem zServices: Switch profiles => nouvelle commande permettant de choisir le profil zService à utiliser

- Idem zServices: Upload => nouvelle commande qui permet d'upload vers le mainframe les fichiers sélectionnés dans l'explorer

- Idem zServices: Upload project => nouvelle commande qui permet d'upload un projet entier vers le mainframe

 

Cette extension permettra dans le futur aussi de compiler et livrer dans Endevor des sources.

 

##### Idem Compilation

 

- Correction du contrôle de surface sur le settings DDIO.

 

##### Idem First Aid Kit

 

- Mise à jour de la fonction de récupération de licence JDBC pour s'affranchir du fichier de licence provenant d'IDEM Eclipse.

- Mise à jour de la fonction de remise à zéro des paramétrages de SonarQube For Ide et Zowe pour être cohérent avec le paramétrage par défaut

- Ajout de la possibilité de remettre à zéro le paramétrage par défaut de VSCODE via la fonction "Reset Parameters"

 

##### Idem Injector

 

- Amélioration des IHM de création et suppression de profils d'injection. Notamment avec l'ajout de sécurité si les fichiers settings.json contiennent des erreurs de syntaxe.

 

##### Idem Audit

 

- Mise en place de traces pour l'ensemble des commandes des extensions IDEM VSC zDevOps.

 

### 24.1.0 (11/04/2024)

 

#### Souche Idem VSC 24.1

 

Evolution de l'installeur d'Idem VSC pour gérer le multi versionning d'IDEM VSC et des extensions contenues dans le package.

 

#### Nouvelles Extensions Marketplace

 

De nouvelles extensions du Marketplace viennent compléter le package de base d'IDEM VSC. Ces extensions sont ajoutées avec une configuration par défaut pour être directement fonctionnelles.

 

##### BMC AMI DevX Workbench Explorer 23.1.0

 

L'extension "BMC AMI DevX Workbench Explorer" permet de naviguer sur les partitions z/OS. On y retrouve deux fonctionnalités :

 

- Data set Explorer qui est un explorateur de fichiers reprenant le principe du Host Explorer dans Topaz Workbench

- Job Explorer qui est un explorateur de logs de job reprenant le principe du JES Explorer dans Topaz Workbench

 

_Pour plus d'informations :_ [BMC AMI DevX Workbench Explorer - Guide Utilisateur​​​​​​​](fr/IDEM-VSC/Guides/workbenchExplorer.md)

 

##### BMC AMI DevX Workbench Code Debug 23.1.0

 

L'extension "BMC AMI DevX Workbench Code Debug" permet de débuguer des programmes batch (COBOL, IMS) et CICS. Il s'appuie sur l'interface native de debugging de VSCode. Contrairement à Xpediter dans IDEM, il n'y a pas d'interface pour créer les configurations de debugging, cela se fait au travers d'un fichier launch.json. On retrouve dans cette version de l'extension les fonctionnalités de base de Xpediter telles que la création de breakpoint, breakpoint conditionnel ou encore suivi de variable (espion équivalent watch variables dans Xpediter)

 

_Pour plus d'informations :_ [BMC AMI DevX Workbench Code Debug - Guide Utilisateur](fr/IDEM-VSC/Guides/workbenchCodeDebug.md)

 

##### Cobol Control Flow 1.0.4

 

L'extension "COBOL Control Flow" permet de représenter un programme COBOL sous forme de graphique pour mieux visualiser les liens entre les différents paragraphes du programme.

 

_Pour plus d'informations :_ [COBOL Control Flow - Guide Utilisateur](fr/IDEM-VSC/Guides/cobolControlFlow.md)

 

#### Extensions zDevOps

 

##### Idem VSC Extension 23.1.0

 

Cette première version d'extension d'Idem VSC comporte deux fonctionnalités :

 

- Idem Compilation : Pour la compilation de programmes cobol sur SDEV

- Idem First Aid Kit : Kit de dépannage d'IDEM VSC

 

###### Idem Compilation

 

Dans cette première version, trois commandes sont disponibles depuis la palette de commandes (CTRL+SHIFT+P) :

 

- "Idem Compilation: Configuration ..." : Ouvre la console de gestion les profils de compilation

- "Idem Compilation: Compile ..." : Ouvre la console de compilation unitaire du programme ouvert dans l'éditeur actif

- "Idem Compilation: Compile" : Compile le programme ouvert dans l'éditeur actif avec les valeurs précédemment enregistrées ou calculées par défaut

 

###### Idem First Aid Kit

 

Dans cette première version, trois commandes sont disponibles depuis la palette de commandes (CTRL+SHIFT+P) :

 

- "Idem First Aid Kit: Helpdesk" : Ouvre le Yammer du Helpdesk zDevOps

- "Idem First Aid Kit: Documentation" : Ouvre le SharePoint zDevOps sur la page documentation d'Idem VSC

- "Idem First Aid Kit: Reset Parameters..." : Ouvre la console de gestion permettant de réinitialiser les configurations de bases des extensions packagées (Actuellement vide)

 