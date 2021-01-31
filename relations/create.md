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
```yaml
{
    "relation": {
        "activeVerb": string, // Active verb. Required
        "passiveVerb": string, // Passive verb. Required
        "note": string | null // Note. Optional
    }
}
```

* **Sample Request Body**:
```yaml
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

```yaml
{
    "relation": {
        "id": string
    }
}
```

* **Sample Response Body**:

```yaml
{
    "relation": {
        "id": "oLldi0PVH"
    }
}
```
