# Update Item

## Request
* **URL**: `/auth/v1/items/:itemId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `itemId`: Item ID
* **Query Parameters**: None
* **Request Body**:

```yaml
{
    "item": {
        "title": string, // Title. Optional
        "note": string | null, // Note. Optional
        "parentId": string | null, // Parent Item ID. Null for root Items. Optional
        "typeId": string // Type ID. Optional
    }
}
```

* **Sample Request Body**:
```yaml
{
    "item": {
        "title": "Production Database",
        "parentId": "Fz8w_OObG",
        "typeId": "yXnCWkUrN"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None