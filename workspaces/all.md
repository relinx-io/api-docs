# Get All Workspaces

Lists all Workspaces you own or are shared with you.

## Request

* **URL**: `/auth/v1/workspaces`
* **Method**: `GET`
* **Required Headers**
    * `Authorization: ApiKey YOUR_API_KEY`
* **Request Parameters**: None
* **Query Parameters**: None
* **Request Body**: None

## Response
* **Status**: `200 OK`
* **Response Body**:

```yaml
{
    "workspaces": [
        {
            "id": string, // Workspace ID
            "title": string,
            "note": string | null,
            "role": { // Members's role in this workspace. See CONSTANTS
                "id": string
            }
        },
        ...
    ]
}
```

* **Sample Response Body**:

```yaml
{
    "workspaces": [
        {
            "id": "ORxw3jm_b",
            "title": "My Workspace",
            "note": "",
            "role": {
                "id": "owner"
            }
        },
        {
            "id": "MQgeoeqbd",
            "title": "Shared with me",
            "note": "Note",
            "role": {
                "id": "reader"
            }
        }
    ]
}
```
