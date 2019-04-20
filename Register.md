# Register / Sign-In
**Index**
1. [Check Email](#check-email)
2. [Sign-In](#sign-in)

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

After searching the database, the server will return a status code depending on whether the particular email address was found.

| Status Codes | Definition |
| --- | --- |
| 0 | Email does not exist in Database. |
| 1 | Email exists in Database. Refer to [https://github.com/lb-dev/Twolette-document/blob/master/Sign-in.md](Sign-In) |

#### Response Example
```JSON
{
	"status": 0
}
```

## Sign-In
### Request
* Request Type: **POST**
* Request Route: **/sign-in**

Upon receiving user email and password, server will determine whether the given password matches the email address.

| Parameter | Type | Necessary | Description |
| --- | --- | --- | --- |
| email | String | Y | Email address to sign in with |
| password | String | Y | Password to match up with given email address |

#### Request Example
```JSON
{
	"email": "emailToSearch@gmail.com",
        "password": "password1"
}
```

### Response

After searching the database, the server will return a status code depending on whether the password matches the email address.

| Status Codes | Definition |
| --- | --- |
| 0 | Password does not match email address |
| 1 | Password matches email address |

#### Response Example
```JSON
{
	"status": 0
}
```
