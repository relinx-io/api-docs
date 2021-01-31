# Create Relation

## Request
* **URL**: `/auth/v1/relations`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```json
{
    "relation": {
        "activeVerb": string, // Active verb. Required
        "passiveVerb": string, // Passive verb. Required
        "note": string | null // Note. Optional
    }
}
```

* **Sample Request Body**:
```json
{
    "relation": {
        "activeVerb": "Uses",
        "passiveVerb": "Used by",
        "note": ""
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "relation": {
        "id": string
    }
}
```

* **Sample Response Body**:

```json
{
    "relation": {
        "id": "oLldi0PVH"
    }
}
```
