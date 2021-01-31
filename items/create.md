# Create Item

## Request
* **URL**: `/auth/v1/items`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```json
{
    "item": {
        "title": string, // Title. Required
        "note": string | null, // Note. Optional
        "parentId": string | null, // Parent Item ID. Null for root Items. Optional
        "typeId": string // Type ID. Required
    }
}
```

* **Sample Request Body**:
```json
{
    "item": {
        "title": "Production Database",
        "note": null,
        "parentId": "Fz8w_OObG",
        "typeId": "yXnCWkUrN"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "item": {
        "id": string
    }
}
```

* **Sample Response Body**:

```json
{
    "item": {
        "id": "oLldi0PVH"
    }
}
```
