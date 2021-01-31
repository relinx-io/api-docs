# Update Type

## Request
* **URL**: `/auth/v1/types/:typeId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `typeId`: Type ID
* **Query Parameters**: None
* **Request Body**:

```yaml
{
    "type": {
        "title": string, // Title. Optional
        "note": string | null // Note. Optional
    }
}
```

* **Sample Request Body**:
```yaml
{
    "type": {
        "title": "Oracle Database",
        "note": ""
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None