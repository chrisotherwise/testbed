# Ontrack Mobile API Summary v4.0

## **1. Login**

It enables users to authenticate and retrieve task list for the day.

**POST /api/v4/session?username=\<username\>&timestamp=\<timestamp\>&hash=\<hashvalue\>**


## **2. Task list**

Retrieve task list.

**GET /api/v4/gang/mygang/assigned/tasks?token=\<token\>**



## **3. Upload files (images,videos, answers to task questions and measures)**

Upload resources from the App to the Backend.

**POST /api/v4/\<contract reference\>/\<job reference\>/tasks/\<task id\>?token=\<token\>**



## **4. Add a new task**

Create a new task on the App.

**POST /api/v4/gang/mygang/assigned/tasks?token=\<token\>**



## **5. Get surface types and materials**

Retrieve a list of materials and surfaces.

**GET /api/v4/surface_types?token=\<token\>**


<div style="page-break-after: always;"></div>


## **6. Send calling cards**

Send callingcard details once scanned.

**POST /api/v4/customercare/callingcards?token=\<token\>**



## **7. Heart beat location service**

Share current location of the device.

**POST /api/v4/session/location?token=\<token\>**



## **8. Health check**

Check the availability of the endpoints.

**GET /api/v4/hc?token=\<token\>**


<div style="page-break-after: always;"></div>


# Sample data

## **Task list**

Retrieve task details for the day.

```json
{
    "error": 0,
    "data": {
        "Tasks": [
            {
                "id": "5231443",
                "job_id": "892771",
                "streamorder": "5",
                "Reference": null,
                "GangGroup": {
                    "id": "3",
                    "name": "Grab",
                    "reference": "GR"
                },
                "Status": {
                    "id": "35",
                    "name": "Pending"
                },
                "InterimState": {
                    "id": "1",
                    "name": "Not Applicable"
                },
                "Option": null,
                "Additions": [],
                "Job": {
                    "id": "892771",
                    "contract_id": "79",
                    "address_1": "12 Priestley Way",
                    "address_2": "",
                    "town": "London",
                    "postcode": "",
                    "daily_fine": "0",
                    "type_id": "1",
                    "description": "",
                    "JobReferences": [],
                    "RoadType": {
                        "id": "10",
                        "name": "---"
                    },
                    "Location": null,
                    "address": "12 Priestley Way,<br />London,",
                    "Contract": {
                        "id": "79",
                        "name": "Demo",
                        "reference": "DEMO"
                    },
                    "PrimaryReference": {
                        "contract_id": "79",
                        "reference": "demo-01042019",
                        "primary": "1"
                    }
                },
                "name": "Grab",
                "no_measure_prompt": 1,
                "abort_prompt": 1,
                "risk_assessment_needed": 1,
                "task_question_without_measure": 0,
                "priority": 1,
                "Questions": [
                    {
                        "id": 1000,
                        "question_id": "1116918",
                        "sort_order": "1",
                        "name": "Tile tape used?",
                        "tag": "tag1116918",
                        "field_type": "booleanSwitch",
                        "placeholder_text": null,
                        "answer": "",
                        "condition": "",
                        "section_condition": "",
                        "default_answer": "",
                        "section_id": "1",
                        "section_name": "GRAB",
                        "is_mandatory": "0"
                    },
                    {
                        "id": 1005,
                        "question_id": "1116919",
                        "sort_order": "2",
                        "name": "Length used (m)",
                        "tag": "tag1116919",
                        "field_type": "decimal",
                        "placeholder_text": "e.g. 0.95",
                        "answer": "",
                        "condition": "$tag1116918==0",
                        "section_condition": "",
                        "default_answer": null,
                        "section_id": "1",
                        "section_name": "",
                        "is_mandatory": "1"
                    },
                    {
                        "id": 1010,
                        "question_id": "1116920",
                        "sort_order": "3",
                        "name": "Cable protection plates used?",
                        "tag": "tag1116920",
                        "field_type": "booleanSwitch",
                        "placeholder_text": null,
                        "answer": "",
                        "condition": "",
                        "section_condition": "",
                        "default_answer": null,
                        "section_id": "2",
                        "section_name": "",
                        "is_mandatory": "0"
                    },
                    {
                        "id": 1015,
                        "question_id": "1116921",
                        "sort_order": "4",
                        "name": "How many?",
                        "tag": "tag1116921",
                        "field_type": "integer",
                        "placeholder_text": "e.g. 2",
                        "answer": "",
                        "condition": "$tag1116920==0",
                        "section_condition": "",
                        "default_answer": null,
                        "section_id": "2",
                        "section_name": "",
                        "is_mandatory": "1"
                    }
                ],
                "Tagmapping": [
                    {
                        "id": 5000,
                        "sort_order": "99",
                        "tag": "other-hazard",
                        "tag_title": "Other hazard",
                        "tag_section": "HAZARD"
                    },
                    {
                        "id": 5003,
                        "sort_order": "1",
                        "tag": "customer-phonecall-required",
                        "tag_title": "Customer phonecall required",
                        "tag_section": "CUSTOMER_CONCERN"
                    },
                    {
                        "id": 5006,
                        "sort_order": "1",
                        "tag": "clean-up-required",
                        "tag_title": "Cleanup required",
                        "tag_section": "CUSTOMER_CONCERN"
                    },
                    {
                        "id": 5009,
                        "sort_order": "1",
                        "tag": "damage",
                        "tag_title": "Damage",
                        "tag_section": "CUSTOMER_CONCERN"
                    },
                    {
                        "id": 5012,
                        "sort_order": "1",
                        "tag": "vulnerable-customer",
                        "tag_title": "Vulnerable customer",
                        "tag_section": "CUSTOMER_CONCERN"
                    },
                    {
                        "id": 5015,
                        "sort_order": "1",
                        "tag": "other-customer-concern",
                        "tag_title": "Other customer concern",
                        "tag_section": "CUSTOMER_CONCERN"
                    },
                    {
                        "id": 5018,
                        "sort_order": "1",
                        "tag": "other-street-works-issue",
                        "tag_title": "Other street works issue",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5021,
                        "sort_order": "1",
                        "tag": "open-excavation-spoil-slg-on-site",
                        "tag_title": "Open excavation, spoil, SLG on site",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5024,
                        "sort_order": "1",
                        "tag": "traffic-management-on-site",
                        "tag_title": "Traffic management on site",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5027,
                        "sort_order": "1",
                        "tag": "no-low-level-concrete",
                        "tag_title": "No low level concrete",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5030,
                        "sort_order": "1",
                        "tag": "missing-items",
                        "tag_title": "Missing items e.g kerbs, edgings",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5033,
                        "sort_order": "1",
                        "tag": "potential-defect-on-site",
                        "tag_title": "Potential defect on site",
                        "tag_section": "STREETWORKS"
                    },
                    {
                        "id": 5036,
                        "sort_order": "1",
                        "tag": "knock-calling-card",
                        "tag_title": "KNOCK - calling card",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5039,
                        "sort_order": "2",
                        "tag": "permit-board",
                        "tag_title": "Permit board",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5042,
                        "sort_order": "3",
                        "tag": "pedestrian-walkway",
                        "tag_title": "Pedestrian walkway",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5045,
                        "sort_order": "4",
                        "tag": "pre-site",
                        "tag_title": "Pre site",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5048,
                        "sort_order": "5",
                        "tag": "apparatus-pipe-depth",
                        "tag_title": "Apparatus / pipe depth",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5051,
                        "sort_order": "6",
                        "tag": "material-ticket",
                        "tag_title": "Material ticket",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5054,
                        "sort_order": "7",
                        "tag": "fill-surround-depth",
                        "tag_title": "Finefill / shingle / surround depth",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5057,
                        "sort_order": "8",
                        "tag": "clegg-layers",
                        "tag_title": "Clegg / layers",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5060,
                        "sort_order": "9",
                        "tag": "backfill-depth",
                        "tag_title": "Backfill depth",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5063,
                        "sort_order": "10",
                        "tag": "low-level-concrete",
                        "tag_title": "Low level concrete",
                        "tag_section": "COMPLIANCE"
                    },
                    {
                        "id": 5066,
                        "sort_order": "1",
                        "tag": "near-miss",
                        "tag_title": "Near Miss",
                        "tag_section": "NEAR_MISS"
                    }
                ]
            }
        ]
    }
}

```

## **Get surface types and materials**

Retrieve a list of materials and surfaces.

```json
{
   "error":0,
   "data":{
      "SurfaceTypes":[
         {
            "id":"1",
            "code":"F/W",
            "name":"Footway",
            "Materials":[
               {
                  "id":"1",
                  "name":"6mm DBM",
                  "status_id":"274"
               },
               {
                  "id":"3",
                  "name":"Mastic",
                  "status_id":"274"
               },
               {
                  "id":"4",
                  "name":"30/14 HRA",
                  "status_id":"274"
               },
               {
                  "id":"5",
                  "name":"Block Paving (Black) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"6",
                  "name":"Block Paving (Brindle) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"7",
                  "name":"Block Paving (Red) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"8",
                  "name":"Block Paving (Grey) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"9",
                  "name":"Block Paving (Buff) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"10",
                  "name":"Block Paving (Charcoal) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"11",
                  "name":"Cobble Setts",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"2",
            "code":"C/W",
            "name":"Carriageway",
            "Materials":[
               {
                  "id":"3",
                  "name":"Mastic",
                  "status_id":"274"
               },
               {
                  "id":"4",
                  "name":"30/14 HRA",
                  "status_id":"274"
               },
               {
                  "id":"5",
                  "name":"Block Paving (Black) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"6",
                  "name":"Block Paving (Brindle) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"7",
                  "name":"Block Paving (Red) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"8",
                  "name":"Block Paving (Grey) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"9",
                  "name":"Block Paving (Buff) 200x100x50mm",
                  "status_id":"274"
               },
               {
                  "id":"10",
                  "name":"Block Paving (Charcoal) 200x100x50mm",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"8",
            "code":"LB",
            "name":"Link Box",
            "Materials":[
               {
                  "id":"1184",
                  "name":"Gravel",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"9",
            "code":"UM",
            "name":"Unmade",
            "Materials":[
               {
                  "id":"1184",
                  "name":"Gravel",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"11",
            "code":"SPR",
            "name":"Special Requests",
            "Materials":[
               {
                  "id":"1189",
                  "name":"Heavy Lift",
                  "status_id":"274"
               },
               {
                  "id":"1190",
                  "name":"Remove & Dispose of Spoil",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"12",
            "code":"FP",
            "name":"Footpath",
            "Materials":[
               {
                  "id":"1",
                  "name":"6mm DBM",
                  "status_id":"274"
               },
               {
                  "id":"3",
                  "name":"Mastic",
                  "status_id":"274"
               },
               {
                  "id":"4",
                  "name":"30/14 HRA",
                  "status_id":"274"
               }
            ]
         },
         {
            "id":"13",
            "code":"SS",
            "name":"Substation",
            "Materials":[
               {
                  "id":"1001",
                  "name":"Slabs - Supply & Lay",
                  "status_id":"274"
               },
               {
                  "id":"1025",
                  "name":"Sand",
                  "status_id":"274"
               },
               {
                  "id":"1145",
                  "name":"Conservation Slabs",
                  "status_id":"274"
               },
               {
                  "id":"1164",
                  "name":"Imperial 600x600 Slab",
                  "status_id":"274"
               },
               {
                  "id":"1165",
                  "name":"Imperial 750x600 Slab",
                  "status_id":"274"
               },
               {
                  "id":"1166",
                  "name":"Imperial 900x600 Slab",
                  "status_id":"274"
               },
               {
                  "id":"1184",
                  "name":"Gravel",
                  "status_id":"274"
               }
            ]
         }
      ]
   }
}

```
