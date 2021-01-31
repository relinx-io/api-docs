# Set Property Value of Item

## Request
* **URL**: `/auth/v1/values`
* **Method**: `POST`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**:
```json
{
    "value": {
        "itemId": string, // Item ID. Required
        "propertyId": string, // Property ID. Required
        "value": string // Value. Required. See Note below
    }
}
```

* **Sample Request Body**:
```json
{
    "value": {
        "itemId": "2Ezv8qpXi",
        "propertyId": "98beMqnFw",
        "value": "some value"
    }
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:

```json
{
    "value": {
        "id": string
    }
}
```

* **Sample Response Body**:

```json
{
    "value": {
        "id": "oLldi0PVH"
    }
}
```

## Note
All Values are saved as text in the following format depending on Property Data Type:
* `String` - Plain text (e.g. `"some value"`)
* `Number` - Integer or decimal number with a period as a decimal separator (e.g. `"123"`, `"0.123"`, `"12345.67"`)
* `Date` - Stored in `yyyy-mm-dd` format (e.g. `"2020-12-31"`)
* `Boolean` - Stored as `"yes"` or `"no"`
* `List` - Only List Element ID is stored (e.g. `"rnx"` for the List Element `{ id: "rnx", title: "Relinx" }`)
