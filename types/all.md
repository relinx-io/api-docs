# Get All Types

## Request
* **URL**: `/auth/v1/types`
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
* **Sample Request**: `/auth/v1/types?q=abc&pageNo=0&pageSize=10`

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "types": [
        {
            "id": string,
            "title": string,
            "note": string | null
        },
        ...
    ],
    "totalCount": number
}
```

* **Sample Response Body**:

```json
{
    "types": [
        {
            "id": "QbGOkza1M",
            "title": "Virtual Machine",
            "note": null
        },
        {
            "id": "QbGOkza1M",
            "title": "Application Server",
            "note": ""
        },
        {
            "id": "qrzg1_Bk9",
            "title": "Email Account",
            "note": "Email accounts used in the application"
        }
    ],
    "totalCount": 3
}
```
