---
layout: default
title: Hawkbit API
parent: API
nav_order: 2
---
# Hawkbit API Documentation


## Authentication

Endpoints require a valid Json Web Token to be included in the header of the request as a bearer Token. A Json Web Token can be acquired after the Login to the iot device manager GUI.

# TODO ASK Tobias for the authentication

* auto-gen TOC:
{:toc}


<!-- >
> <span style="color:brown">Table of contents</span>
>
> [GET /targets/deploymentData/{targetId}](#get-deployment-data)
>
> [GET /deploymentData/{targetId}](#get-deployment-data)
>
> [GET /actions/{targetId}](#get-target-actions)
>
> [GET /actions/state/{targetId}](#get-target-action-state)
>
> [POST /updateTarget/{targetId}](#update-target)
>
> [GET /getTargetDistributions/{targetId}](#get-target-compatible-distributions)
>
> [GET /getSoftwareModules](#get-software-modules)
>
> [POST /createSoftwareModule](#create-software-module)
>
> [GET /getSoftwareTypes](#get-software-module-types)
>
> [POST /createSoftwareType](#create-software-module-type)
>
> [DELETE /deleteSoftwareType/{softwareModuleTypeId}](#delete-software-module-type)
>
> [GET /getSoftwareModuleArtifact/{softwareModuleId}](#get-software-module-artifact)
>
> [POST /uploadSoftwareModuleArtifact](#upload-software-module-artifact)
>
> [GET /getSoftwareTypes](#post-distribution-set-type)
>
> [GET /getSoftwareTypes](#get-distribution-set-type)
>
> [GET /getDistributionset](#get-distribution-set)
>
> [POST /postDistributionSet](#post-distribution-set)
> -->

## Targets : 

### GET deployment data
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving actions, action states and distribution informations related to the deployments of a specific target

> <span style="color:brown"> Request URL </span>

> GET /deploymentData/{targetId}  

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| limit (optional) | The maximum number of retrieved entries in a page (default is 10 and 0 means all entries). |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>


```json
[
    {
        "action": {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1624449095804,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1624449095804,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/489"
                }
                "self": {
                    "href": "https://domain.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/489"
                }
            },
            "id": 489,
            "forceType": "forced"
        },
        "distribution": {
            "createdBy": "osb-technical",
            "createdAt": 1624446668365,
            "lastModifiedBy": "osb-technical",
            "lastModifiedAt": 1624446668494,
            "name": "ECU-2.2.0.21.2.1-AppFS-osb_test-1.5.11_b-testingSignDist",
            "description": "",
            "version": "ECU-2.2.0.21.2.1-AppFS-osb_test-1.5.11_b",
            "modules": [
                {
                    "createdBy": "osb-technical",
                    "createdAt": 1624446623094,
                    "lastModifiedBy": "osb-technical",
                    "lastModifiedAt": 1624446666814,
                    "name": "ECU-2.2.0.21.2.1-AppFS-osb_test-1.5.11_b",
                    "version": "ECU-2.2.0.21.2.1-AppFS-osb_test-1.5.11_b",
                    "type": "raucbundle",
                    "deleted": false,
                    "_links": {
                        "self": {
                            "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/272"
                        }
                    },
                    "id": 272
                }
            ],
            "requiredMigrationStep": false,
            "type": "testingdist",
            "complete": true,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/199"
                },
                "modules": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/199/assignedSM?offset=0&limit=50{&sort}",
                    "templated": true
                },
                "type": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsettypes/6"
                },
                "metadata": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/199/metadata?offset=0&limit=50{&sort,q}",
                    "templated": true
                }
            },
            "id": 199
        },
        "action_states": {
            "content": [
                {
                    "type": "finished",
                    "messages": [
                        "Software bundle installed successful."
                    ],
                    "reportedAt": 1624449612545,
                    "id": 10470
                },
                {
                    "type": "running",
                    "messages": [
                        "idle"
                    ],
                    "reportedAt": 1624449611455,
                    "id": 10469
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Installing done."
                    ],
                    "reportedAt": 1624449610237,
                    "id": 10468
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Updating slots done."
                    ],
                    "reportedAt": 1624449609257,
                    "id": 10467
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Copying image to configfs.0 done."
                    ],
                    "reportedAt": 1624449608220,
                    "id": 10466
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Copying image to configfs.0"
                    ],
                    "reportedAt": 1624449607230,
                    "id": 10465
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Checking slot configfs.0 done."
                    ],
                    "reportedAt": 1624449604176,
                    "id": 10464
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Checking slot configfs.0"
                    ],
                    "reportedAt": 1624449603037,
                    "id": 10463
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Copying image to rootfs.0 done."
                    ],
                    "reportedAt": 1624449601946,
                    "id": 10462
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Copying image to rootfs.0"
                    ],
                    "reportedAt": 1624449600908,
                    "id": 10461
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Checking slot rootfs.0 done."
                    ],
                    "reportedAt": 1624449599807,
                    "id": 10460
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Checking slot rootfs.0"
                    ],
                    "reportedAt": 1624449598793,
                    "id": 10459
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Copying image to appfs.0 done."
                    ],
                    "reportedAt": 1624449597789,
                    "id": 10458
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Copying image to appfs.0"
                    ],
                    "reportedAt": 1624449596772,
                    "id": 10457
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Checking slot appfs.0 done."
                    ],
                    "reportedAt": 1624449595769,
                    "id": 10456
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Checking slot appfs.0"
                    ],
                    "reportedAt": 1624449594520,
                    "id": 10455
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Updating slots"
                    ],
                    "reportedAt": 1624449592741,
                    "id": 10454
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Determining target install group done."
                    ],
                    "reportedAt": 1624449586421,
                    "id": 10453
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Determining target install group"
                    ],
                    "reportedAt": 1624449578432,
                    "id": 10452
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Loading manifest file done."
                    ],
                    "reportedAt": 1624449568989,
                    "id": 10451
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Loading manifest file"
                    ],
                    "reportedAt": 1624449561382,
                    "id": 10450
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Checking bundle done."
                    ],
                    "reportedAt": 1624449553033,
                    "id": 10449
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Verifying signature done."
                    ],
                    "reportedAt": 1624449547725,
                    "id": 10448
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Verifying signature"
                    ],
                    "reportedAt": 1624449542319,
                    "id": 10447
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Checking bundle"
                    ],
                    "reportedAt": 1624449534120,
                    "id": 10446
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Determining slot states done."
                    ],
                    "reportedAt": 1624449527219,
                    "id": 10445
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Determining slot states"
                    ],
                    "reportedAt": 1624449520162,
                    "id": 10444
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Installing"
                    ],
                    "reportedAt": 1624449514219,
                    "id": 10443
                },
                {
                    "type": "running",
                    "messages": [
                        "installing"
                    ],
                    "reportedAt": 1624449510914,
                    "id": 10442
                },
                {
                    "type": "running",
                    "messages": [
                        "File checksum OK."
                    ],
                    "reportedAt": 1624449505824,
                    "id": 10441
                },
                {
                    "type": "running",
                    "messages": [
                        "Download complete. 0.31 MB/s"
                    ],
                    "reportedAt": 1624449504827,
                    "id": 10440
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/272/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1624449311295,
                    "id": 10439
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1624449309970,
                    "id": 10438
                },
                {
                    "type": "running",
                    "messages": [
                        null
                    ],
                    "reportedAt": 1624449095811,
                    "id": 10437
                }
            ],
            "total": 34,
            "size": 34
        }
    },
    {
        "action": {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1624360739224,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1624360739224,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/486"
                }
            },
            "id": 486,
            "forceType": "forced"
        },
        "distribution": {
            "createdBy": "osb-technical",
            "createdAt": 1624355109226,
            "lastModifiedBy": "osb-technical",
            "lastModifiedAt": 1624355109365,
            "name": "ECU-2.2.0.21.2.0-AppFS-osb_test-1.5.11-testingSignDist",
            "description": "",
            "version": "ECU-2.2.0.21.2.0-AppFS-osb_test-1.5.11",
            "modules": [
                {
                    "createdBy": "osb-technical",
                    "createdAt": 1624355066238,
                    "lastModifiedBy": "osb-technical",
                    "lastModifiedAt": 1624355107658,
                    "name": "ECU-2.2.0.21.2.0-AppFS-osb_test-1.5.11",
                    "version": "ECU-2.2.0.21.2.0-AppFS-osb_test-1.5.11",
                    "type": "raucbundle",
                    "deleted": false,
                    "_links": {
                        "self": {
                            "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/267"
                        }
                    },
                    "id": 267
                }
            ],
            "requiredMigrationStep": false,
            "type": "testingdist",
            "complete": true,
            "deleted": true,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/194"
                },
                "modules": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/194/assignedSM?offset=0&limit=50{&sort}",
                    "templated": true
                },
                "type": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsettypes/6"
                },
                "metadata": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/194/metadata?offset=0&limit=50{&sort,q}",
                    "templated": true
                }
            },
            "id": 194
        },
        "action_states": {
            "content": [
                {
                    "type": "finished",
                    "messages": [
                        "Software bundle installed successful."
                    ],
                    "reportedAt": 1624361213612,
                    "id": 10368
                },
                {
                    "type": "running",
                    "messages": [
                        "idle"
                    ],
                    "reportedAt": 1624361212424,
                    "id": 10367
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Installing done."
                    ],
                    "reportedAt": 1624361211055,
                    "id": 10366
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Updating slots done."
                    ],
                    "reportedAt": 1624361209924,
                    "id": 10365
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Copying image to configfs.0 done."
                    ],
                    "reportedAt": 1624361208665,
                    "id": 10364
                },
                {
                    "type": "running",
                    "messages": [
                        "95% Copying image to configfs.0"
                    ],
                    "reportedAt": 1624361207561,
                    "id": 10363
                },
                {
                    "type": "running",
                    "messages": [
                        "95% Checking slot configfs.0 done."
                    ],
                    "reportedAt": 1624361206116,
                    "id": 10362
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Checking slot configfs.0"
                    ],
                    "reportedAt": 1624361204934,
                    "id": 10361
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Copying image to rootfs.0 done."
                    ],
                    "reportedAt": 1624361203671,
                    "id": 10360
                },
                {
                    "type": "running",
                    "messages": [
                        "85% Copying image to rootfs.0"
                    ],
                    "reportedAt": 1624361202470,
                    "id": 10359
                },
                {
                    "type": "running",
                    "messages": [
                        "85% Checking slot rootfs.0 done."
                    ],
                    "reportedAt": 1624361201243,
                    "id": 10358
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Checking slot rootfs.0"
                    ],
                    "reportedAt": 1624361199337,
                    "id": 10357
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Updating slots"
                    ],
                    "reportedAt": 1624361188543,
                    "id": 10356
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Determining target install group done."
                    ],
                    "reportedAt": 1624361178157,
                    "id": 10355
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Determining target install group"
                    ],
                    "reportedAt": 1624361169613,
                    "id": 10354
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Loading manifest file done."
                    ],
                    "reportedAt": 1624361162515,
                    "id": 10353
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Loading manifest file"
                    ],
                    "reportedAt": 1624361155672,
                    "id": 10352
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Checking bundle done."
                    ],
                    "reportedAt": 1624361148254,
                    "id": 10351
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Verifying signature done."
                    ],
                    "reportedAt": 1624361137345,
                    "id": 10350
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Verifying signature"
                    ],
                    "reportedAt": 1624361128235,
                    "id": 10349
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Checking bundle"
                    ],
                    "reportedAt": 1624361120524,
                    "id": 10348
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Determining slot states done."
                    ],
                    "reportedAt": 1624361114158,
                    "id": 10347
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Determining slot states"
                    ],
                    "reportedAt": 1624361107934,
                    "id": 10346
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Installing"
                    ],
                    "reportedAt": 1624361101742,
                    "id": 10345
                },
                {
                    "type": "running",
                    "messages": [
                        "installing"
                    ],
                    "reportedAt": 1624361096797,
                    "id": 10344
                },
                {
                    "type": "running",
                    "messages": [
                        "File checksum OK."
                    ],
                    "reportedAt": 1624361088780,
                    "id": 10343
                },
                {
                    "type": "running",
                    "messages": [
                        "Download complete. 0.23 MB/s"
                    ],
                    "reportedAt": 1624361086932,
                    "id": 10342
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/267/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1624360840851,
                    "id": 10341
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1624360839495,
                    "id": 10340
                },
                {
                    "type": "running",
                    "messages": [
                        null
                    ],
                    "reportedAt": 1624360739230,
                    "id": 10339
                }
            ],
            "total": 30,
            "size": 30
        }
    },
    {
        "action": {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1620214993539,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1620214993539,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/481"
                }
            },
            "id": 481,
            "forceType": "forced"
        },
        "distribution": {
            "createdBy": "osb-technical",
            "createdAt": 1620214516429,
            "lastModifiedBy": "osb-technical",
            "lastModifiedAt": 1620214516667,
            "name": "ECU-2.2.0.21.0.0-AppFS-Poettinger-1.5.6-testingSignDist",
            "description": "",
            "version": "ECU-2.2.0.21.0.0-AppFS-Poettinger-1.5.6",
            "modules": [
                {
                    "createdBy": "osb-technical",
                    "createdAt": 1620214465682,
                    "lastModifiedBy": "osb-technical",
                    "lastModifiedAt": 1620214514751,
                    "name": "ECU-2.2.0.21.0.0-AppFS-Poettinger-1.5.6",
                    "version": "ECU-2.2.0.21.0.0-AppFS-Poettinger-1.5.6",
                    "type": "raucbundle",
                    "deleted": false,
                    "_links": {
                        "self": {
                            "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/235"
                        }
                    },
                    "id": 235
                }
            ],
            "requiredMigrationStep": false,
            "type": "testingdist",
            "complete": true,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/168"
                },
                "modules": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/168/assignedSM?offset=0&limit=50{&sort}",
                    "templated": true
                },
                "type": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsettypes/6"
                },
                "metadata": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/168/metadata?offset=0&limit=50{&sort,q}",
                    "templated": true
                }
            },
            "id": 168
        },
        "action_states": {
            "content": [
                {
                    "type": "finished",
                    "messages": [
                        "Software bundle installed successful."
                    ],
                    "reportedAt": 1620215489995,
                    "id": 10206
                },
                {
                    "type": "running",
                    "messages": [
                        "idle"
                    ],
                    "reportedAt": 1620215488739,
                    "id": 10205
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Installing done."
                    ],
                    "reportedAt": 1620215487109,
                    "id": 10204
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Updating slots done."
                    ],
                    "reportedAt": 1620215485798,
                    "id": 10203
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Copying image to appfs.0 done."
                    ],
                    "reportedAt": 1620215484484,
                    "id": 10202
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Copying image to appfs.0"
                    ],
                    "reportedAt": 1620215483051,
                    "id": 10201
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Checking slot appfs.0 done."
                    ],
                    "reportedAt": 1620215481515,
                    "id": 10200
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Checking slot appfs.0"
                    ],
                    "reportedAt": 1620215480113,
                    "id": 10199
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Copying image to configfs.0 done."
                    ],
                    "reportedAt": 1620215478860,
                    "id": 10198
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Copying image to configfs.0"
                    ],
                    "reportedAt": 1620215477551,
                    "id": 10197
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Checking slot configfs.0 done."
                    ],
                    "reportedAt": 1620215476305,
                    "id": 10196
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Checking slot configfs.0"
                    ],
                    "reportedAt": 1620215474870,
                    "id": 10195
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Copying image to rootfs.0 done."
                    ],
                    "reportedAt": 1620215470641,
                    "id": 10194
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Copying image to rootfs.0"
                    ],
                    "reportedAt": 1620215469008,
                    "id": 10193
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Checking slot rootfs.0 done."
                    ],
                    "reportedAt": 1620215467810,
                    "id": 10192
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Checking slot rootfs.0"
                    ],
                    "reportedAt": 1620215458940,
                    "id": 10191
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Updating slots"
                    ],
                    "reportedAt": 1620215451152,
                    "id": 10190
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Determining target install group done."
                    ],
                    "reportedAt": 1620215444626,
                    "id": 10189
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Determining target install group"
                    ],
                    "reportedAt": 1620215438445,
                    "id": 10188
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Loading manifest file done."
                    ],
                    "reportedAt": 1620215430211,
                    "id": 10187
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Loading manifest file"
                    ],
                    "reportedAt": 1620215419583,
                    "id": 10186
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Checking bundle done."
                    ],
                    "reportedAt": 1620215409348,
                    "id": 10185
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Verifying signature done."
                    ],
                    "reportedAt": 1620215400409,
                    "id": 10184
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Verifying signature"
                    ],
                    "reportedAt": 1620215393972,
                    "id": 10183
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Checking bundle"
                    ],
                    "reportedAt": 1620215387761,
                    "id": 10182
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Determining slot states done."
                    ],
                    "reportedAt": 1620215379142,
                    "id": 10181
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Determining slot states"
                    ],
                    "reportedAt": 1620215369080,
                    "id": 10180
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Installing"
                    ],
                    "reportedAt": 1620215360070,
                    "id": 10179
                },
                {
                    "type": "running",
                    "messages": [
                        "installing"
                    ],
                    "reportedAt": 1620215352937,
                    "id": 10178
                },
                {
                    "type": "running",
                    "messages": [
                        "File checksum OK."
                    ],
                    "reportedAt": 1620215347540,
                    "id": 10177
                },
                {
                    "type": "running",
                    "messages": [
                        "Download complete. 0.24 MB/s"
                    ],
                    "reportedAt": 1620215346229,
                    "id": 10176
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/235/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1620215075992,
                    "id": 10175
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1620215074558,
                    "id": 10174
                },
                {
                    "type": "running",
                    "messages": [
                        null
                    ],
                    "reportedAt": 1620214993545,
                    "id": 10173
                }
            ],
            "total": 34,
            "size": 34
        }
    },
    {
        "action": {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1613640902500,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1613640902500,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/435"
                }
            },
            "id": 435,
            "forceType": "forced"
        },
        "distribution": {
            "createdBy": "osb-technical",
            "createdAt": 1613567101650,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1613640023744,
            "name": "ECU-2.2.0.21.0.0-R-AppFS-Poettinger-1.5.1-testingSignDist",
            "description": "",
            "version": "ECU-2.2.0.21.0.0-R-AppFS-1.5.1",
            "modules": [
                {
                    "createdBy": "osb-technical",
                    "createdAt": 1613567050118,
                    "lastModifiedBy": "osb-technical",
                    "lastModifiedAt": 1613567099820,
                    "name": "ECU-2.2.0.21.0.0-R-AppFS-Poettinger-1.5.1",
                    "version": "ECU-2.2.0.21.0.0-R-AppFS-1.5.1",
                    "type": "raucbundle",
                    "deleted": false,
                    "_links": {
                        "self": {
                            "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/176"
                        }
                    },
                    "id": 176
                }
            ],
            "requiredMigrationStep": false,
            "type": "testingdist",
            "complete": true,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/131"
                },
                "modules": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/131/assignedSM?offset=0&limit=50{&sort}",
                    "templated": true
                },
                "type": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsettypes/6"
                },
                "metadata": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/131/metadata?offset=0&limit=50{&sort,q}",
                    "templated": true
                }
            },
            "id": 131
        },
        "action_states": {
            "content": [
                {
                    "type": "finished",
                    "messages": [
                        "Software bundle installed successful."
                    ],
                    "reportedAt": 1613650255230,
                    "id": 8895
                },
                {
                    "type": "running",
                    "messages": [
                        "idle"
                    ],
                    "reportedAt": 1613650249074,
                    "id": 8894
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Installing done."
                    ],
                    "reportedAt": 1613650243316,
                    "id": 8893
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Updating slots done."
                    ],
                    "reportedAt": 1613650236900,
                    "id": 8892
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Copying image to appfs.1 done."
                    ],
                    "reportedAt": 1613650230178,
                    "id": 8891
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Copying image to appfs.1"
                    ],
                    "reportedAt": 1613650221648,
                    "id": 8890
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Checking slot appfs.1 done."
                    ],
                    "reportedAt": 1613650215117,
                    "id": 8889
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Checking slot appfs.1"
                    ],
                    "reportedAt": 1613650205498,
                    "id": 8888
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Copying image to configfs.1 done."
                    ],
                    "reportedAt": 1613650199297,
                    "id": 8887
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Copying image to configfs.1"
                    ],
                    "reportedAt": 1613650192932,
                    "id": 8886
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Checking slot configfs.1 done."
                    ],
                    "reportedAt": 1613650186513,
                    "id": 8885
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Checking slot configfs.1"
                    ],
                    "reportedAt": 1613650181013,
                    "id": 8884
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Copying image to rootfs.1 done."
                    ],
                    "reportedAt": 1613650173432,
                    "id": 8883
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Copying image to rootfs.1"
                    ],
                    "reportedAt": 1613650165874,
                    "id": 8882
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Checking slot rootfs.1 done."
                    ],
                    "reportedAt": 1613650154180,
                    "id": 8881
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Checking slot rootfs.1"
                    ],
                    "reportedAt": 1613650140456,
                    "id": 8880
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Updating slots"
                    ],
                    "reportedAt": 1613650127079,
                    "id": 8879
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Determining target install group done."
                    ],
                    "reportedAt": 1613650109651,
                    "id": 8878
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Determining target install group"
                    ],
                    "reportedAt": 1613650094771,
                    "id": 8877
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Loading manifest file done."
                    ],
                    "reportedAt": 1613650081430,
                    "id": 8876
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Loading manifest file"
                    ],
                    "reportedAt": 1613650068812,
                    "id": 8875
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Checking bundle done."
                    ],
                    "reportedAt": 1613650055865,
                    "id": 8874
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Verifying signature done."
                    ],
                    "reportedAt": 1613650041243,
                    "id": 8873
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Verifying signature"
                    ],
                    "reportedAt": 1613650028232,
                    "id": 8872
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Checking bundle"
                    ],
                    "reportedAt": 1613650017704,
                    "id": 8871
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Determining slot states done."
                    ],
                    "reportedAt": 1613650007623,
                    "id": 8870
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Determining slot states"
                    ],
                    "reportedAt": 1613649997244,
                    "id": 8869
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Installing"
                    ],
                    "reportedAt": 1613649983475,
                    "id": 8868
                },
                {
                    "type": "running",
                    "messages": [
                        "installing"
                    ],
                    "reportedAt": 1613649970667,
                    "id": 8867
                },
                {
                    "type": "running",
                    "messages": [
                        "File checksum OK."
                    ],
                    "reportedAt": 1613649960117,
                    "id": 8866
                },
                {
                    "type": "running",
                    "messages": [
                        "Download complete. 0.33 MB/s"
                    ],
                    "reportedAt": 1613649953989,
                    "id": 8865
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads range bytes=65950560- of: /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613649755360,
                    "id": 8864
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613649747619,
                    "id": 8863
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads range bytes=52973400- of: /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613648976656,
                    "id": 8862
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613648970678,
                    "id": 8861
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads range bytes=43544136- of: /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613648345508,
                    "id": 8860
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613648339517,
                    "id": 8859
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads range bytes=35685328- of: /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613642625665,
                    "id": 8821
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613642618760,
                    "id": 8820
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads range bytes=14934016- of: /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613641878457,
                    "id": 8816
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613641872226,
                    "id": 8815
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/176/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1613641060025,
                    "id": 8810
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1613641038978,
                    "id": 8809
                },
                {
                    "type": "running",
                    "messages": [
                        null
                    ],
                    "reportedAt": 1613640902500,
                    "id": 8808
                }
            ],
            "total": 44,
            "size": 44
        }
    },
    {
        "action": {
            "createdBy": "bht",
            "createdAt": 1604409403720,
            "lastModifiedBy": "bht",
            "lastModifiedAt": 1604409403720,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/366"
                }
            },
            "id": 366,
            "forceType": "forced"
        },
        "distribution": {
            "createdBy": "osb-technical",
            "createdAt": 1604409174462,
            "lastModifiedBy": "osb-technical",
            "lastModifiedAt": 1604409174617,
            "name": "2.2.0.20.2.5-testingSignDist",
            "description": "description",
            "version": "2.2.0.20.2.5",
            "modules": [
                {
                    "createdBy": "osb-technical",
                    "createdAt": 1604409121879,
                    "lastModifiedBy": "osb-technical",
                    "lastModifiedAt": 1604409172711,
                    "name": "2.2.0.20.2.5",
                    "description": "description",
                    "version": "2.2.0.20.2.5",
                    "type": "raucbundle",
                    "deleted": false,
                    "_links": {
                        "self": {
                            "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/109"
                        }
                    },
                    "id": 109
                }
            ],
            "requiredMigrationStep": false,
            "type": "testingdist",
            "complete": true,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/97"
                },
                "modules": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/97/assignedSM?offset=0&limit=50{&sort}",
                    "templated": true
                },
                "type": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsettypes/6"
                },
                "metadata": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/97/metadata?offset=0&limit=50{&sort,q}",
                    "templated": true
                }
            },
            "id": 97
        },
        "action_states": {
            "content": [
                {
                    "type": "finished",
                    "messages": [
                        "Software bundle installed successful."
                    ],
                    "reportedAt": 1604409660942,
                    "id": 6899
                },
                {
                    "type": "running",
                    "messages": [
                        "idle"
                    ],
                    "reportedAt": 1604409660140,
                    "id": 6898
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Installing done."
                    ],
                    "reportedAt": 1604409659331,
                    "id": 6897
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Updating slots done."
                    ],
                    "reportedAt": 1604409658531,
                    "id": 6896
                },
                {
                    "type": "running",
                    "messages": [
                        "100% Copying image to appfs.1 done."
                    ],
                    "reportedAt": 1604409657739,
                    "id": 6895
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Copying image to appfs.1"
                    ],
                    "reportedAt": 1604409656891,
                    "id": 6894
                },
                {
                    "type": "running",
                    "messages": [
                        "96% Checking slot appfs.1 done."
                    ],
                    "reportedAt": 1604409656089,
                    "id": 6893
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Checking slot appfs.1"
                    ],
                    "reportedAt": 1604409655274,
                    "id": 6892
                },
                {
                    "type": "running",
                    "messages": [
                        "93% Copying image to configfs.1 done."
                    ],
                    "reportedAt": 1604409654485,
                    "id": 6891
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Copying image to configfs.1"
                    ],
                    "reportedAt": 1604409653691,
                    "id": 6890
                },
                {
                    "type": "running",
                    "messages": [
                        "90% Checking slot configfs.1 done."
                    ],
                    "reportedAt": 1604409652906,
                    "id": 6889
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Checking slot configfs.1"
                    ],
                    "reportedAt": 1604409652105,
                    "id": 6888
                },
                {
                    "type": "running",
                    "messages": [
                        "86% Copying image to rootfs.1 done."
                    ],
                    "reportedAt": 1604409650967,
                    "id": 6887
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Copying image to rootfs.1"
                    ],
                    "reportedAt": 1604409649228,
                    "id": 6886
                },
                {
                    "type": "running",
                    "messages": [
                        "83% Checking slot rootfs.1 done."
                    ],
                    "reportedAt": 1604409645861,
                    "id": 6885
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Checking slot rootfs.1"
                    ],
                    "reportedAt": 1604409642896,
                    "id": 6884
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Updating slots"
                    ],
                    "reportedAt": 1604409640053,
                    "id": 6883
                },
                {
                    "type": "running",
                    "messages": [
                        "80% Determining target install group done."
                    ],
                    "reportedAt": 1604409636604,
                    "id": 6882
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Determining target install group"
                    ],
                    "reportedAt": 1604409633037,
                    "id": 6881
                },
                {
                    "type": "running",
                    "messages": [
                        "60% Loading manifest file done."
                    ],
                    "reportedAt": 1604409629472,
                    "id": 6880
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Loading manifest file"
                    ],
                    "reportedAt": 1604409625896,
                    "id": 6879
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Checking bundle done."
                    ],
                    "reportedAt": 1604409622782,
                    "id": 6878
                },
                {
                    "type": "running",
                    "messages": [
                        "40% Verifying signature done."
                    ],
                    "reportedAt": 1604409619886,
                    "id": 6877
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Verifying signature"
                    ],
                    "reportedAt": 1604409616796,
                    "id": 6876
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Checking bundle"
                    ],
                    "reportedAt": 1604409613691,
                    "id": 6875
                },
                {
                    "type": "running",
                    "messages": [
                        "20% Determining slot states done."
                    ],
                    "reportedAt": 1604409610430,
                    "id": 6874
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Determining slot states"
                    ],
                    "reportedAt": 1604409607364,
                    "id": 6873
                },
                {
                    "type": "running",
                    "messages": [
                        "0% Installing"
                    ],
                    "reportedAt": 1604409606266,
                    "id": 6872
                },
                {
                    "type": "running",
                    "messages": [
                        "installing"
                    ],
                    "reportedAt": 1604409603611,
                    "id": 6871
                },
                {
                    "type": "running",
                    "messages": [
                        "File checksum OK."
                    ],
                    "reportedAt": 1604409600917,
                    "id": 6870
                },
                {
                    "type": "running",
                    "messages": [
                        "Download complete. 0.48 MB/s"
                    ],
                    "reportedAt": 1604409599990,
                    "id": 6869
                },
                {
                    "type": "download",
                    "messages": [
                        "Update Server: Target downloads /DEFAULT/controller/v1/0x4790700247911210827700658799135448120000/softwaremodules/109/artifacts/raucb.bundle"
                    ],
                    "reportedAt": 1604409464676,
                    "id": 6868
                },
                {
                    "type": "retrieved",
                    "messages": [
                        "Update Server: Target retrieved update action and should start now the download."
                    ],
                    "reportedAt": 1604409463646,
                    "id": 6867
                },
                {
                    "type": "running",
                    "messages": [
                        null
                    ],
                    "reportedAt": 1604409403730,
                    "id": 6866
                }
            ],
            "total": 34,
            "size": 34
        }
    }
]


```

### GET target actions
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving actions informations related to the deployments of a specific target

> <span style="color:brown"> Request URL </span>

> GET /actions/{targetId}

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| limit (optional) | The maximum number of retrieved entries in a page (default is 5 and 0 means all entries). |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
{
    "content": [
        {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1624449095804,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1624449095804,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/489"
                }
            },
            "id": 489,
            "forceType": "forced"
        },
        {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1624360739224,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1624360739224,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/486"
                }
            },
            "id": 486,
            "forceType": "forced"
        },
        {
            "createdBy": "bf-extern@osb-ag.de",
            "createdAt": 1620214993539,
            "lastModifiedBy": "bf-extern@osb-ag.de",
            "lastModifiedAt": 1620214993539,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/481"
                }
            },
            "id": 481,
            "forceType": "forced"
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1613640902500,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1613640902500,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/435"
                }
            },
            "id": 435,
            "forceType": "forced"
        },
        {
            "createdBy": "bht",
            "createdAt": 1604409403720,
            "lastModifiedBy": "bht",
            "lastModifiedAt": 1604409403720,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210827700658799135448120000/actions/366"
                }
            },
            "id": 366,
            "forceType": "forced"
        }
    ],
    "total": 5,
    "size": 5
}
```

### GET target action states

> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving action states informations related to a specific action excuted by the target.

> <span style="color:brown"> Request URL </span>

> GET /actions/state/{targetId} 

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| actionId (required) | the id of the action that the api call will return the corresponding action states |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
{
    "content": [
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1619691791134,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1619691791134,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210800400813798905348120000/actions/479"
                }
            },
            "id": 479,
            "forceType": "forced"
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1619690146916,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1619690146916,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210800400813798905348120000/actions/478"
                }
            },
            "id": 478,
            "forceType": "forced"
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1619689916517,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1619689916517,
            "type": "update",
            "status": "finished",
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/targets/0x4790700247911210800400813798905348120000/actions/477"
                }
            },
            "id": 477,
            "forceType": "forced"
        }
    ],
    "total": 3,
    "size": 3
}
```

### GET target compatible distributions
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of the compatible distributions with the chosen targetId

> <span style="color:brown"> Request URL </span>

> GET /getTargetDistributions/{targetId} 

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

> 
> <span style="color:brown"> Important Remark </span>
> 
> The assignment of the distributions to the targets are done manuelly using target metadata and distribution tags. This can be done following these steps. 

> 1. Choose the target in question
> 2. Add a new key to this target metadata. Add a new **Key = distribution_tag** and **Value = "Distribution Tag"** (the same "Distribution Tag" name needs to be used to tag the compatible distributions in the next step) for exemple : iot-demonstrator
> 3. Tag the compatible distributions using the same **"Distribution Tag"** as in the device metadata For exemple : iot-demonstrator
>  
> The tagged distributions will be then returned by calling this GET API call and considered as compatible distributions to the chosen target.
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>
```json
[
    {
        "createdBy": "osb-aws-configrollout",
        "createdAt": 1606301520143,
        "lastModifiedBy": "osb",
        "lastModifiedAt": 1619611252207,
        "name": "iot-demonstrator-image-raspberrypi3",
        "description": "",
        "version": "1.0a",
        "modules": [
            {
                "createdBy": "osb-aws-configrollout",
                "createdAt": 1606301277552,
                "lastModifiedBy": "osb-aws-configrollout",
                "lastModifiedAt": 1606301304963,
                "name": "iot-demonstrator-image-raspberrypi3",
                "description": "",
                "version": "1.0a",
                "type": "raucbundle",
                "vendor": "",
                "deleted": false,
                "_links": {
                    "self": {
                        "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/115"
                    }
                },
                "id": 115
            }
        ],
        "requiredMigrationStep": false,
        "type": "releasedist",
        "complete": true,
        "deleted": false,
        "_links": {
            "self": {
                "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/103"
            }
        },
        "id": 103
    },
    {
        "createdBy": "osb-aws-configrollout",
        "createdAt": 1606301589181,
        "lastModifiedBy": "osb",
        "lastModifiedAt": 1619611254584,
        "name": "iot-demonstrator-image-raspberrypi3",
        "description": "",
        "version": "1.0b",
        "modules": [
            {
                "createdBy": "osb-aws-configrollout",
                "createdAt": 1606301329181,
                "lastModifiedBy": "osb-aws-configrollout",
                "lastModifiedAt": 1606301418697,
                "name": "iot-demonstrator-image-raspberrypi3",
                "description": "",
                "version": "1.0b",
                "type": "raucbundle",
                "vendor": "",
                "deleted": false,
                "_links": {
                    "self": {
                        "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/116"
                    }
                },
                "id": 116
            }
        ],
        "requiredMigrationStep": false,
        "type": "releasedist",
        "complete": true,
        "deleted": false,
        "_links": {
            "self": {
                "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/distributionsets/104"
            }
        },
        "id": 104
    }
]
```

### POST target distribution

> <span style="color:brown"> Implementation notes </span>

> Handles the Post request of triggering a rollout of the distribution (distributionId) to the chosen target (targetId)

> <span style="color:brown"> Request URL </span>

> POST /updateTarget/{targetId}

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| distributionId (required) | the id of the distribution that will be rolled out to the specified targetId in the path param|

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
```

### GET target metadata

> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution set types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### POST target metadata
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set type

> <span style="color:brown"> Request URL </span>

> POST /postDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"optionalmodules":[{"id" : }, {"id" : }], "name": "distribution", description":"Desc1", "mandatorymodules": [{"id" : },{"id" : }], "key" : "CustomerName__DIST"}]
>
> **Exemple :** [{"optionalmodules":[{"id" : 100},{"id" : 101 }], "name": "definitiondist", description":"Desc1", "mandatorymodules": [{"id" : 102 },{"id" : 103 }], "key" : "definitiondist"}]
>
> **Remark :** The customer name of the api caller will by automatically appened as a prefix to the name and the key of the created distribution type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__definitiondist" 
> "key" : "ESEC__definitiondist"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | definitiondist/releasedist/testingdist |
| key | definitiondist/releasedist/testingdist |
| description | "description" |
| mandatorymodules | [{"id": },{"id": }, ..] |
| optionalmodules | [{"id": },{"id": }, ..] |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### DELETE target metadata

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```


## Software modules: 

### GET software modules
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the software modules belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getSoftwareModules

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
{
    "content": [
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1621277188857,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1621295015048,
            "name": "esec_est_sw_module",
            "description": "",
            "version": "version1",
            "type": "esec_roots",
            "vendor": "",
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/243"
                }
            },
            "id": 243
        }
    ],
    "total": 1
}
```

### POST software module
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new software module.

> <span style="color:brown"> Request URL </span>

> POST /createSoftwareModule  

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None| None |

> **Event Body :** [{"vendor":"vendor_name","name":"software_module_name","description":"description1", "type":"CustomerName__bundle",version":"software_module_version"}]
>
> **Exemple :** [{"vendor":"esec","name":"Root-FS ECU-2.2.0.21.2.1","description":"description1" ,"type":"esec_configfs", "version":"ECU-2.2.0.21.2.1"}]
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
```

### DELETE software module
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new software module.

> <span style="color:brown"> Request URL </span>

> POST /createSoftwareModule  

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None| None |

> **Event Body :** [{"vendor":"vendor_name","name":"software_module_name","description":"description1", "type":"CustomerName__bundle",version":"software_module_version"}]
>
> **Exemple :** [{"vendor":"esec","name":"Root-FS ECU-2.2.0.21.2.1","description":"description1" ,"type":"esec_configfs", "version":"ECU-2.2.0.21.2.1"}]
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
```

## Software module types: 

### GET Software module types
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the software module types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getSoftwareTypes

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
{
    "content": [
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1621276299270,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1621276299270,
            "name": "esec_roots",
            "description": "",
            "key": "esec_roots",
            "maxAssignments": 1,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremoduletypes/41"
                }
            },
            "id": 41
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1621276328747,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1621276328747,
            "name": "esec_appfs",
            "description": "",
            "key": "esec_appfs",
            "maxAssignments": 2147483647,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremoduletypes/42"
                }
            },
            "id": 42
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1621276344914,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1621276344914,
            "name": "esec_configfs",
            "description": "",
            "key": "esec_configfs",
            "maxAssignments": 1,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremoduletypes/43"
                }
            },
            "id": 43
        },
        {
            "createdBy": "osb-aws-configrollout",
            "createdAt": 1621276358287,
            "lastModifiedBy": "osb-aws-configrollout",
            "lastModifiedAt": 1621276358287,
            "name": "esec_raucbundle",
            "description": "",
            "key": "esec_raucbundle",
            "maxAssignments": 1,
            "deleted": false,
            "_links": {
                "self": {
                    "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremoduletypes/44"
                }
            },
            "id": 44
        }
    ],
    "total": 4
}
```

### POST Software module type

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new software module type. 

> <span style="color:brown"> Request URL </span>

> POST /createSoftwareType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |
>
> **Event Body :** [{"name" : "softwareModuleType", "description" : "Desc1", "maxAssignments" : 1, "key" : "softwareModuleType"}]
>
> **Exemple :** [{"name" : "rootfs", "description" : "Desc1", "maxAssignments":1, "key" : "rootfs"}]
>
> **Remark :** The customer name of the api caller will by appened as a prefix to the name and the key of the created software module type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__rootfs" 
> "key" : "ESEC__rootfs"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | rootfs/appfs/configfs |
| description | "description" |
| maxAssignments | 1 |
| key | rootfs/appfs/configfs |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
```

### DELETE Software Module type
> <span style="color:brown"> Implementation notes </span>

> Handles the DELETE request of deleting the software modules type with the specified id in the path param

> <span style="color:brown"> Request URL </span>

> DELETE /deleteSoftwareType/{softwareModuleTypeId}

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

## Software module artifact: 

### GET software module artifact
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the software module artifacts of the corresponding software module specified in the path param.

> <span style="color:brown"> Request URL </span>

> GET /getSoftwareModuleArtifact/{softwareModuleId}

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json
[
    {
        "createdBy": "osb-aws-configrollout",
        "createdAt": 1621285590445,
        "lastModifiedBy": "osb-aws-configrollout",
        "lastModifiedAt": 1621285590445,
        "hashes": {
            "sha1": "8f93542443e98f41fe98e97d6d2a147193b1b005",
            "md5": "f20d9f2072bbeb6691c0f9c5099b01f3",
            "sha256": "9a30a503b2862c51c3c5acd7fbce2f1f784cf4658ccf8e87d5023a90c21c0714"
        },
        "providedFilename": "test_upload16.txt",
        "size": 9,
        "_links": {
            "self": {
                "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/243/artifacts/281"
            }
        },
        "id": 281
    },
    {
        "createdBy": "osb-aws-configrollout",
        "createdAt": 1621293322021,
        "lastModifiedBy": "osb-aws-configrollout",
        "lastModifiedAt": 1621293322021,
        "hashes": {
            "sha1": "8f93542443e98f41fe98e97d6d2a147193b1b005",
            "md5": "f20d9f2072bbeb6691c0f9c5099b01f3",
            "sha256": "9a30a503b2862c51c3c5acd7fbce2f1f784cf4658ccf8e87d5023a90c21c0714"
        },
        "providedFilename": "test_upload15.txt",
        "size": 9,
        "_links": {
            "self": {
                "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/243/artifacts/282"
            }
        },
        "id": 282
    },
    {
        "createdBy": "osb-aws-configrollout",
        "createdAt": 1621295015047,
        "lastModifiedBy": "osb-aws-configrollout",
        "lastModifiedAt": 1621295015047,
        "hashes": {
            "sha1": "8f93542443e98f41fe98e97d6d2a147193b1b005",
            "md5": "f20d9f2072bbeb6691c0f9c5099b01f3",
            "sha256": "9a30a503b2862c51c3c5acd7fbce2f1f784cf4658ccf8e87d5023a90c21c0714"
        },
        "providedFilename": "test_upload14.txt",
        "size": 9,
        "_links": {
            "self": {
                "href": "https://hawkbit.prod.esec.aws.esec-experts.com/rest/v1/softwaremodules/243/artifacts/283"
            }
        },
        "id": 283
    }
]

```

### Upload software module artifact
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of uploading a software modules artifacts to the specified software module. Generates a presigned url to upload the software module artifact.

> <span style="color:brown"> Request URL </span>

> POST /feature/hawkbit/SoftwareModuleArtifact/{sw_id}

> <span style="color:brown"> Request query parameter </span>

> | Parameter      | Description  |
|------------------|--------------|
| artifact_name    | the artifact name   |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### Delete software module artifact
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of uploading a software modules artifacts to the specified software module. Generates a presigned url to upload the software module artifact.

> <span style="color:brown"> Request URL </span>

> POST /feature/hawkbit/SoftwareModuleArtifact/{sw_id}

> <span style="color:brown"> Request query parameter </span>

> | Parameter      | Description  |
|------------------|--------------|
| artifact_name    | the artifact name   |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

## Distribution set:

### GET distribution sets
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution sets belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionset

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### POST distribution set
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### DELETE distribution set

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

## Distribution set type:

### GET distribution set type
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution set types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### POST distribution set type
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set type

> <span style="color:brown"> Request URL </span>

> POST /postDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"optionalmodules":[{"id" : }, {"id" : }], "name": "distribution", description":"Desc1", "mandatorymodules": [{"id" : },{"id" : }], "key" : "CustomerName__DIST"}]
>
> **Exemple :** [{"optionalmodules":[{"id" : 100},{"id" : 101 }], "name": "definitiondist", description":"Desc1", "mandatorymodules": [{"id" : 102 },{"id" : 103 }], "key" : "definitiondist"}]
>
> **Remark :** The customer name of the api caller will by automatically appened as a prefix to the name and the key of the created distribution type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__definitiondist" 
> "key" : "ESEC__definitiondist"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | definitiondist/releasedist/testingdist |
| key | definitiondist/releasedist/testingdist |
| description | "description" |
| mandatorymodules | [{"id": },{"id": }, ..] |
| optionalmodules | [{"id": },{"id": }, ..] |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### DELETE distribution set type

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

## Distribution set tags:

### GET distribution set tags
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution set types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### POST distribution set tag
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set type

> <span style="color:brown"> Request URL </span>

> POST /postDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"optionalmodules":[{"id" : }, {"id" : }], "name": "distribution", description":"Desc1", "mandatorymodules": [{"id" : },{"id" : }], "key" : "CustomerName__DIST"}]
>
> **Exemple :** [{"optionalmodules":[{"id" : 100},{"id" : 101 }], "name": "definitiondist", description":"Desc1", "mandatorymodules": [{"id" : 102 },{"id" : 103 }], "key" : "definitiondist"}]
>
> **Remark :** The customer name of the api caller will by automatically appened as a prefix to the name and the key of the created distribution type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__definitiondist" 
> "key" : "ESEC__definitiondist"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | definitiondist/releasedist/testingdist |
| key | definitiondist/releasedist/testingdist |
| description | "description" |
| mandatorymodules | [{"id": },{"id": }, ..] |
| optionalmodules | [{"id": },{"id": }, ..] |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### DELETE distribution set tag

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```


### Assign distribution set tag
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution set types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### Unassign distribution set tag
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set type

> <span style="color:brown"> Request URL </span>

> POST /postDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"optionalmodules":[{"id" : }, {"id" : }], "name": "distribution", description":"Desc1", "mandatorymodules": [{"id" : },{"id" : }], "key" : "CustomerName__DIST"}]
>
> **Exemple :** [{"optionalmodules":[{"id" : 100},{"id" : 101 }], "name": "definitiondist", description":"Desc1", "mandatorymodules": [{"id" : 102 },{"id" : 103 }], "key" : "definitiondist"}]
>
> **Remark :** The customer name of the api caller will by automatically appened as a prefix to the name and the key of the created distribution type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__definitiondist" 
> "key" : "ESEC__definitiondist"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | definitiondist/releasedist/testingdist |
| key | definitiondist/releasedist/testingdist |
| description | "description" |
| mandatorymodules | [{"id": },{"id": }, ..] |
| optionalmodules | [{"id": },{"id": }, ..] |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

## Distribution set metadata:

### GET distribution set metadata
> <span style="color:brown"> Implementation notes </span>

> Handles the GET request of retrieving the list of all the distribution set types belonging to the specific customer that is executing the api call

> <span style="color:brown"> Request URL </span>

> GET /getDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### POST distribution set metadata
> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set type

> <span style="color:brown"> Request URL </span>

> POST /postDistributionsetType

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"optionalmodules":[{"id" : }, {"id" : }], "name": "distribution", description":"Desc1", "mandatorymodules": [{"id" : },{"id" : }], "key" : "CustomerName__DIST"}]
>
> **Exemple :** [{"optionalmodules":[{"id" : 100},{"id" : 101 }], "name": "definitiondist", description":"Desc1", "mandatorymodules": [{"id" : 102 },{"id" : 103 }], "key" : "definitiondist"}]
>
> **Remark :** The customer name of the api caller will by automatically appened as a prefix to the name and the key of the created distribution type. The example above becomes :
>
> The name and the key of the distribution type become :  
> "name" : "ESEC__definitiondist" 
> "key" : "ESEC__definitiondist"
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| name | definitiondist/releasedist/testingdist |
| key | definitiondist/releasedist/testingdist |
| description | "description" |
| mandatorymodules | [{"id": },{"id": }, ..] |
| optionalmodules | [{"id": },{"id": }, ..] |

>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```

### DELETE distribution set metadata

> <span style="color:brown"> Implementation notes </span>

> Handles the POST request of creating a new distribution set

> <span style="color:brown"> Request URL </span>

> POST /postDistributionSet

> <span style="color:brown"> Request query parameter </span>

> | Parameter        | Description  |
|------------------|--------------|
| None | None |

>
> **Event Body :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"distribution_type", "version":"distribution_version", "modules":[{"id" :}, {"id" :}]}]
>
> **Exemple :** [{"requiredMigrationStep":false, "name":"distribution_name", "description" :"nisl", "type":"ESEC__definitiondist", "version":"distribution_version", "modules":[{"id" :23}, {"id" :24}]}]
>
> **Remark :**   
> Choose a correct type for the new distribution. The distribution type needs to start with the customer name as a prefix and two undersocres "__" like shown in the example above.
> 
> Mandatorymodules that were specified when creating the distribution type are obligatory in the modules list, and optionalmodules are optional.
>
> <span style="color:brown"> Event Body Parameters </span>
>
> | Parameter        | Description  |
|------------------|--------------|
| requiredMigrationStep | false/true |
| name | "distribution_name" |
| description | "description" |
| type | "distribution_type_name" |
| version | "distribution_version" |
| modules | [{"id": },{"id": }, ..] list of the ids of the corresponding software modules |
>
> <span style="color:brown"> Response (Status 200) </span>
>
> <span style="color:brown"> Response example </span>

```json

```