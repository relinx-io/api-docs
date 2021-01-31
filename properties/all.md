# Get All Properties

## Request
* **URL**: `/auth/v1/properties`
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
* **Sample Request**: `/auth/v1/properties?q=abc&pageNo=0&pageSize=10`

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "properties": [
        {
            "id": string, // Property ID
            "title": string, // Title
            "note": string | null, // Note
            "dataType": number, // Property Data type. See CONSTANTS
            "list": [ // List elements, when dataType = 5 (List)
                {
                    "id": string, // Element ID
                    "title": string // Element title
                }
            ]
        },
        ...
    ],
    "totalCount": number
}
```

* **Sample Response Body**:

```yaml
{
    "properties": [
        {
            "id": "QbGOkza1M",
            "title": "IPv4",
            "note": null,
            "dataType": 1,
            "list": []
        },
        {
            "id": "QbGOkza1M",
            "title": "Licensed",
            "note": null,
            "dataType": 4,
            "list": []
        },
        {
            "id": "qrzg1_Bk9",
            "title": "Vendor",
            "note": "Software vendor",
            "dataType": 5,
            "list": [
                {
                    "id": "ms",
                    "title": "Microsoft"
                },
                {
                    "id": "rnx",
                    "title": "Relinx"
                }
            ]
        }
    ],
    "totalCount": 3
}
```
