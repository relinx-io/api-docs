# Add Link between Types

## Request
* **URL**: `/auth/v1/type-links`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```yaml
{
    "typeLink": { // Link between Types (e.g. A -> B). Self-references are allowed
        "relationId": string, // Relation ID. Required
        "type1Id": string, // First side (i.e side A). Required
        "type2Id": string, // Second side (i.e side B). Required
        "isRequired1": boolean, // First side (i.e. side A) required. Required
        "isRequired2": boolean // Second side (i.e. side B) required. Required
    }
}
```

* **Sample Request Body**:
```yaml
{
    "typeLink": {
        "relationId": "w5vt9Ud76",
        "type1Id": "RPoiDeFc6",
        "type2Id": "u_tgpRd7p",
        "isRequired1": false,
        "isRequired2": true
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "typeLink": {
        "id": string
    }
}
```

* **Sample Response Body**:

```yaml
{
    "typeLink": {
        "id": "oLldi0PVH"
    }
}
```
