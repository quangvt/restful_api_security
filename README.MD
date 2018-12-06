# RESTful API - Web API - Security

# Dependencies
  - express
  - mongoose
  - bodyParser
  - jsonwebtoken

# How to run

## Clone

```sh
$ git clone https://github.com/quangvt/restful_api_security.git
```

## Install dependencies
```sh
$ cd restful_api_security
$ npm install
```

## Start application
```sh
$ npm start
```

## Run with [postman](https://www.getpostman.com/)

### Register User

Method: POST
Url: http://localhost:3000/auth/register
Body:
- Select: x-www-form-urlencoded
- [Key1] = username
- [Value1] = user
- [Key2] = email
- [Value2] = user@example.com
- [Key3] = password
- [Value3] = user1234

Click Send

### Login User and Copy JWT token

Method: POST
Url: http://localhost:3000/auth/login
Body:
- Select: x-www-form-urlencoded
- [Key1] = email
- [Value1] = user@example.com
- [Key2] = password
- [Value2] = user1234

Click Send button

copy the text between double quotes of the returned JSON.
e.g: this is a JSON result: 
```json
{ 
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFkbWluQGV4YW1wbGUuY29tIiwidXNlcm5hbWUiOiJhZG1pbiIsIl9pZCI6IjVjMDdkODg2MmNjYWIxMDYyNzgxZTQwYyIsImlhdCI6MTU0NDEwOTg3OX0.0qtWCbH5yDcLxQV4gJxkQMDAcr4Gt3ZtHFUwzirgmsI"
}
```
so you need copy "eyJhb....msI"

### Get data with JWT token

Method: GET
Url: http://localhost:3000/contact
Headers: 
- [Key1]: Authorization
- [Value1]: "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFkbWluQGV4YW1wbGUuY29tIiwidXNlcm5hbWUiOiJhZG1pbiIsIl9pZCI6IjVjMDdkODg2MmNjYWIxMDYyNzgxZTQwYyIsImlhdCI6MTU0NDEwOTg3OX0.0qtWCbH5yDcLxQV4gJxkQMDAcr4Gt3ZtHFUwzirgmsI"

Click Send button

* Note: format of Value1 must be "JWT + a blank space + JWT token that got from the above step"

### Create new a Contact Item

Method: POST
Url: http://localhost:3000/contact
Body:
- [Key1]: firstName
- [Value1]: David
- [Key2]: lastName
- [Value2]: Beckham
- [Key3]: email
- [Value3]: david@example.com
- [Key4]: company
- [Value4]: Manchester United
- [Key5]: phone
- [Value5]: 44123123123
Headers:
(add one more item)
- [Key]: Authorization
- [Value]: "JWT eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFkbWluQGV4YW1wbGUuY29tIiwidXNlcm5hbWUiOiJhZG1pbiIsIl9pZCI6IjVjMDdkODg2MmNjYWIxMDYyNzgxZTQwYyIsImlhdCI6MTU0NDEwOTg3OX0.0qtWCbH5yDcLxQV4gJxkQMDAcr4Gt3ZtHFUwzirgmsI"

Click Send button

Have Fun
