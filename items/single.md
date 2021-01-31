# Get Single Item

## Request
* **URL**: `/auth/v1/items/:itemId`
* **Method**: `GET`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `itemId`: Item ID
* **Query Parameters**: None
* **Request Body**: None
* **Sample Request**: `/auth/v1/items/QbGOkza1M`

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "item": {
        "id": string, // Item ID
        "title": string, // Title
        "parentId": string | null, // Parent ID. Null for root items
        "note": string | null, // Note
        "type": { // Type
            "id": string,
            "title": string
        },
        "values": [ // Values (aka Property Values)
            {
                "id": string | null, // Value ID. Maybe null if the Property is defined for the Type, but Value is missing
                "value": string | null, // Value. See Note in "Set Property Value of Item"
                "property": { // Property
                    "id": string,
                    "title": string,
                    "dataType": number,
                    "list": [
                        {
                            "id": string,
                            "title": string
                        }
                        ...
                    ]
                },
                "isRequired": boolean, // Required flag defined for the Property
                "isMissing": boolean, // Required but missing
                "isRedundant": boolean // Not defined for the Item's Type but added
            }
        ],
        "links": [ // Links to/from this Item. Self-references are allowed
            {
                "id": string | null, // Maybe null if the Link defined for the Type but missing
                "relation": { // Relation
                    "id": string,
                    "activeVerb": string,
                    "passiveVerb": string
                },
                "item1": { // First side of the Link (i.e. side A)
                    "id": string | null, // Maybe null if the Link defined for the Type but missing
                    "title": string | null, // Maybe null if the Link defined for the Type but missing
                    "type": {
                        "id": string,
                        "title": string
                    }
                },
                "item2": { // Second side of the Link (i.e. side B)
                    "id": string | null, // Maybe null if the Link defined for the Type but missing
                    "title": string | null, // Maybe null if the Link defined for the Type but missing
                    "type": {
                        "id": string,
                        "title": string
                    }
                },
                "isRequired": boolean, // Link is required for the Type for the first side (i.e. side A)
                "isReverseRequired": boolean, // Link is required for the Type for the second side (i.e side B)
                "isMissing": boolean, // Required but not added
                "isRedundant": boolean // Not defined for the Type but added
            }
        ],
        "parents": [ // Item direct parents (ancestors) up to the root Item
            {
                "id": string,
                "title": string,
                "parentId": string | null,
                "type": {
                    "id": string,
                    "title": string
                }
            }
            ...
        ],
        "children": [ // Item direct children (i.e. only 1 level below this Item)
            {
                "id": string,
                "title": string,
                "parentId": string | null,
                "type": {
                    "id": string,
                    "title": string
                }
            }
            ...
        ]
    }
}
```

* **Sample Response Body**:

```yaml
{
    "item": {
        "id": "Fz8w_OObG",
        "title": "Production",
        "parentId": "Fz8w_OObG",
        "note": null,
        "type": {
            "id": "yXnCWkUrN",
            "title": "Oracle Database"
        },
        "values": [
            {
                "id": null,
                "value": null,
                "property": {
                    "id": "JDXw5uobF",
                    "title": "Vendor",
                    "dataType": 5,
                    "list": [
                        {
                            "id": "ora",
                            "title": "Oracle"
                        },
                        {
                            "id": "rnx",
                            "title": "Relinx"
                        }
                    ]
                },
                "isRequired": false,
                "isMissing": true,
                "isRedundant": false
            }
        ],
        "links": [
            {
                "id": null,
                "relation": {
                    "id": "L5Jwnsazv",
                    "activeVerb": "Uses",
                    "passiveVerb": "Used by"
                },
                "item1": {
                    "id": null,
                    "title": null,
                    "type": {
                        "id": "98beMqnFw",
                        "title": "Application Server"
                    }
                },
                "item2": {
                    "id": null,
                    "title": null,
                    "type": {
                        "id": "yXnCWkUrN",
                        "title": "Oracle Database"
                    }
                },
                "isRequired": true,
                "isReverseRequired": false,
                "isMissing": true,
                "isRedundant": false
            }
        ],
        "parents": [
            {
                "id": "Fz8w_OObG",
                "title": "Production Environment",
                "parentId": null,
                "type": {
                    "id": "yXnCWkUrN",
                    "title": "Environment"
                }
            }
        ],
        "children": [
            {
                "id": "v67aYSfLI",
                "title": "Master instance",
                "parentId": "Fz8w_OObG",
                "type": {
                    "id": "98beMqnFw",
                    "title": "Database Instance"
                }
            },
            {
                "id": "yXnCWkUrN",
                "title": "Slave instance",
                "parentId": "Fz8w_OObG",
                "type": {
                    "id": "98beMqnFw",
                    "title": "Database Instance"
                }
            }
        ]
    }
}
```
