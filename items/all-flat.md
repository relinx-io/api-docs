# Get All Items (Flat)

## Request
* **URL**: `/auth/v1/items/flat`
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
* **Sample Request**: `/auth/v1/items/flat?q=abc&pageNo=0&pageSize=10`

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "items": [
        {
            "id": string, // Item ID
            "title": string, // Title
            "note": string | null, // Note
            "type": { // Type of Item
                "id": string,
                "title": string
            },
            "updatedAt": string, // Last updated date in UTC format
            "linksCount": number // Links count to/from this Item
        }
        ...
    ],
    "totalCount": number
}
```

* **Sample Response Body**:

```json
{
    "items": [
        {
            "id": "1RaLD8UVv",
            "title": "Production Database",
            "note": null,
            "type": {
                "id": "XogKr3aya",
                "title": "Oracle Database"
            },
            "updatedAt": "2020-12-06T04:41:00.233Z",
            "linksCount": 2
        },
        {
            "id": "v67aYSfLI",
            "title": "VM1",
            "note": null,
            "type": {
                "id": "98beMqnFw",
                "title": "VMWare VM"
            },
            "updatedAt": "2021-01-12T20:29:20.229Z",
            "linksCount": 0
        }
    ],
    "totalCount": 2
}
```
