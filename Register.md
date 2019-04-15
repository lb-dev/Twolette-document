# Register / Login
## Check Email
### Request
* Request Type: **POST**
* Request Route: **/check_email**

Upon receiving an email address, the server will determine whether or not the email address is already registered with an account.

| Parameter | Type | Necessary | Description |
| --- | --- | --- | --- |
| email | String | Y | Email address to search for in DB |

#### Request Example
```JSON
{
	"email": "emailToSearch@gmail.com"
}
```

### Response

After searching the database, the server will return aa status code depending on whether the particular email address was found.

| Status Codes | Definition |
| --- | --- |
| 0 | Email does not exist in Database. |
| 1 | Email exists in Database. |

#### Response Example
```JSON
{
	"status": 0
}
```
