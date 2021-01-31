# Get Single Type

## Request
* **URL**: `/auth/v1/types/:typeId`
* **Method**: `GET`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `typeId`: Type ID
* **Query Parameters**: None
* **Request Body**: None
* **Sample Request**: `/auth/v1/types/QbGOkza1M`

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "type": {
        "id": string,
        "title": string,
        "note": string | null,
        "props": [ // Properties defined for this Type
            {
                "id": string,
                "property": {
                    "id": string,
                    "title": string
                },
                "isRequired": boolean // Flag for required Property
            }
        ],
        "links": [ // Links with other Types defined for this Type (e.g. A -> B)
            {
                "id": string,
                "type1": { // First side of the link (i.e. Side A)
                    "id": string,
                    "title": string
                },
                "isRequired1": boolean, // Side A is required
                "type2": { // Second side of the link (i.e. Side B)
                    "id": string,
                    "title": string
                },
                "isRequired2": boolean, // Side B is required
                "relation": { // Relation between these Types
                    "id": string,
                    "activeVerb": string,
                    "passiveVerb": string
                }
            }
        ]
    }
}
```

* **Sample Response Body**:

```yaml
{
    "type": {
        "id": "yXnCWkUrN",
        "title": "Database Server",
        "note": null,
        "props": [
            {
                "id": "Z1K_J5674",
                "isRequired": true,
                "property": {
                    "id": "JDXw5uobF",
                    "title": "Vendor"
                }
            }
        ],
        "links": [
            {
                "id": "lvItiHX5B",
                "type1": {
                    "id": "yXnCWkUrN",
                    "title": "Application Server"
                },
                "isRequired1": false,
                "type2": {
                    "id": "yXnCWkUrN",
                    "title": "Database Server"
                },
                "isRequired2": true,
                "relation": {
                    "id": "G35Ytad0h",
                    "activeVerb": "References",
                    "passiveVerb": "Referenced by"
                }
            }
        ]
    }
}
```
