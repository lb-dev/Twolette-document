# Register / Sign-In
**Index**
1. [Check Email](#check-email)
2. [Sign-Up](#sign-up)
3. [Token Test](#token-test)

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
| ethnicity | String | Y | Ethnical background of user |
| location | String | Y | Current location of user |
| introduction | String | Y | Self-introduction paragraph |
| dob | int | Y | User's date of birth in seconds since Jan 1st, 1970 |

#### Request Example
```JSON
{
	"email": "tstark@gmail.com",
	"first_name": "Tony",
	"last_name": "Stark",
	"username": "tstark",
	"ethnicity": "caucasian",
	"location": "Malibu",
	"introduction": "I am Iron Man.",
	"dob": 12812400
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
```

## Token Test
### Request
* Request Type: **POST**
* Request Route: **/token_test**

~~Upon receiving an email address, the server will determine whether or not the email address is already registered with an account.~~
This route will test whether the received ID Token is valid.

| Parameter | Type | Necessary | Description |
| --- | --- | --- | --- |
| idToken | String | Y | ID Token of the signed in User |

#### Request Example
```JSON
{
	"idToken": "asdf1234asdf"
}
```

### Response

The server will return a status code based on whether the decoded id token matches a uid in the user database.

| Status Codes | Definition |
| --- | --- |
| 0 | ID Token is valid |
| 1 | ID Token is invalid: decoded token does not match any existing uid |
| 2 | ID Token is invalid: unable to decode token |

#### Response Example
```JSON
{
	"status": 0
}
```
