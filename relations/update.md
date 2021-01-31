# Update Relation

## Request
* **URL**: `/auth/v1/relations/:relationId`
* **Method**: `PUT`
* **Headers**:
    * `Authorization: ApiKey YOUR_API_KEY`
    * `workspaceId: YOUR_WORKSPACE_ID`
* **Request Parameters**:
    * `relationId`: Relation ID
* **Query Parameters**: None
* **Request Body**:

```yaml
{
    "relation": {
        "activeVerb": string, // Active verb. Optional
        "passiveVerb": string, // passive verb. Optional
        "note": string | null // Note. Optional
    }
}
```

* **Sample Request Body**:
```yaml
{
	"relation": {
		"activeVerb": "Owns",
		"passiveVerb": "Owned by",
		"note": "Indicates ownership"
	}
}
```

## Response
* **Status**: `200 OK`
* **Response Body**:
None