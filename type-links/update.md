# Update Link between Types

## Request
* **URL**: `/auth/v1/type-links/:typeLinkId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `typeLinkId`: TypeLink ID
* **Query Parameters**: None
* **Request Body**:
```json
{
    "typeLink": { // Link between Types (e.g. A -> B)
        "relationId": string, // Relation ID. Optional
        "type1Id": string, // First side (i.e A). Optional
        "type2Id": string, // Second side (i.e B). Optional
        "isRequired1": boolean, // First side required (i.e. A). Optional
        "isRequired2": boolean // Second side required (i.e. B). Optional
    }
}
```

* **Sample Request Body**:
```json
{
    "typeLink": {
        "relationId": "u_tgpRd7p",
        "type1Id": "RPoiDeFc6",
        "isRequired1": false
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None