# Register / Sign-In
**Index**
1. [Check Email](#check-email)
2. [Sign-Up](#sign-up)

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
| 0 | Email exists in Database |
| 1 | Email does not exist in Database |

#### Response Example
```JSON
{
	"status": 0
}
```

## Sign-Up
### Request
* Request Type: **POST**
* Request Route: **/sign-up**

Server will register user in database with user data provided.

| Parameter | Type | Necessary | Description |
| --- | --- | --- | --- |
| email | String | Y | Email address to use for sign-in |
| first_name | String | Y | First name of user to register |
| last_name | String | Y | Last name of user to register |
| username | String | Y | Desired username |
| nationality | String | Y | Nationality (code) of user |
| ethnicity | String | Y | Ethnicity (code) of user |
| introduction | String | N | Self-introduction paragraph |
| dob | int | Y | User's date of birth in YYYYMMDD format |

#### Request Example
```JSON
{
	"email": "tstark@gmail.com",
	"first_name": "Tony",
	"last_name": "Stark",
	"username": "tstark",
	"nationality": "US",
	"ethnicity": "US",
	"introduction": "I am Iron Man.",
	"dob": 19700529
}
```

### Response

Server will return a status code and a message (if necessary) based on whether registration process was successful.

| Status Codes | Definition |
| --- | --- |
| 0 | Registration successful |
| 1 | Invalid field input, will provide detailed message |
| 2 | Unknown error |

#### Response Example
```JSON
{
	"status": 1,
	"message": "Missing required field"
}
