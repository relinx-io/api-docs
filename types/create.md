# Create Type

## Request
* **URL**: `/auth/v1/types`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:

```yaml
{
    "type": {
        "title": string, // Title. Required
        "note": string | null // Note. Optional
    }
}
```

* **Sample Request Body**:
```yaml
{
    "type": {
        "title": "Virtual Machine",
        "note": "WMWare VM"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "type": {
        "id": string
    }
}
```

* **Sample Response Body**:

```yaml
{
    "type": {
        "id": "oLldi0PVH"
    }
}
```
