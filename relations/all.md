# Get All Relations

## Request
* **URL**: `/auth/v1/relations`
* **Method**: `GET`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**:
    * `pageNo`: Page number. Qreater than or equal to 0. Required
    * `pageSize`: Page size. Between 1 and 20. Required
    * `q`: Query string to filter results. Optional
* **Request Body**: None
* **Sample Request**: `/auth/v1/relations?q=abc&pageNo=0&pageSize=10`

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "relations": [
        {
            "id": string, // Relation ID
            "activeVerb": string, // Relation expressed in active voice (e.g. "Uses")
            "passiveVerb": string, // Relation expressed in passive voice (e.g. "Used by")
            "note": string | null // Note
        },
        ...
    ],
    "totalCount": number
}
```

* **Sample Response Body**:

```yaml
{
    "relations": [
        {
            "id": "8IIYyHJqI",
            "activeVerb": "References",
            "passiveVerb": "Referenced by",
            "note": null
        },
        {
            "id": "L5Jwnsazv",
            "activeVerb": "Owns",
            "passiveVerb": "Owned by",
            "note": null
        },
        {
            "id": "G35Ytad0h",
            "activeVerb": "Depends on",
            "passiveVerb": "Depended by",
            "note": "Indicates dependency"
        }
    ],
    "totalCount": 3
}
```
