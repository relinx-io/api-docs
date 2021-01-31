# Update Link between Items

## Request
* **URL**: `/auth/v1/links/:linkId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `linkId`: Link ID
* **Query Parameters**: None
* **Request Body**:
```json
{
    "link": { // Link between two Items (i.e. A -> B)
        "item1Id": string, // First side of Link (i.e. side A). Optional
        "item2Id": string, // Second side of Link (i.e. side B). Optional
        "relationId": string // Relation ID. Optional
    }
}

```

* **Sample Request Body**:
```json
{
    "link": {
        "item1Id": "1RaLD8UVv",
        "item2Id": "v67aYSfLI",
        "relationId": "L5Jwnsazv"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None