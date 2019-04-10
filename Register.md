# Register / Login
## Check email
### Request: /user/check_email

param | type | necessary | description
---|---|---|---
username | String | Y |

Response:

```JSON

{
	"status": 0,
	"message": {
		"status": 1
    // 0: user not found; 1: user profile not completed; 2: completed
	}
}

```
