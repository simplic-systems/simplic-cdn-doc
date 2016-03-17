/auth/login
===

Request a `Json Web Token` for authentication at the api.

## Request details

| Property | - - - | Description |
|---|---|---|
| URL | | `/api/<version>/auth/login` |
| Method | | `post` |
| Success | | Http status *200* |
| Failure | | Http-status *400/500* |
| Content/Media-Type | | `application/json` |
| Authorization | | *no* |
| Roles | | - |

### Method request model

```json
{
	"userName": "<<username>>",
	"password": "<<Password>>"	
}
```

### Method response

**Result with status-code 200**

```json
{
	"token": "<<Json Web Token (JWT)>>"
}
```