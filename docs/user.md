# USER API SPEC

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
    "username" : "husni",
    "password" : "rahasia",
    "name" : "Husni Mubarok"
}
```

Response Body (Success) :

```json
{
    "username" : "husni",
    "name" : "Husni Mubarok"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Username must not blank, ..."
}
```
## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
    "username" : "husni",
    "password" : "rahasia",
}
```

Response Body (Success) :

```json
{
    "username" : "husni",
    "name" : "Husni Mubarok",
    "token" : "uuid"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Username or Password wrong..."
}
```

## Get User

Endpoint : GET /api/users/current

Request Header :
- X-API-TOKEN : token

Response Body (Success) :

```json
{
    "username" : "husni",
    "name" : "Husni Mubarok"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Unauthorized..."
}
```

## Update User

Endpoint : PATCH /api/users/current

Request Header :
- X-API-TOKEN : token

Request Body :

```json
{
    "password" : "rahasia", //not mandatory
    "name" : "Husni Mubarok" //not mandatory
}
```

Response Body (Success) :

```json
{
    "username" : "husni",
    "name" : "Husni Mubarok"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Unauthorized..."
}
```

## Logout User

Endpoint : DELETE /api/users/current

Request Header :
- X-API-TOKEN : token

Response Body (Success) :

```json
{
    "data" : "OK"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Unauthorized..."
}
```