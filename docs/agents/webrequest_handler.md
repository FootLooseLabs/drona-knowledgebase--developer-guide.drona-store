This is has the web socket hosted on this which act as the communication between external agents to the internal agents
it also manages the auth service.

it starts the Express server at port 8877

## To generate the Auth token and client ID

### WebRequest URL
#### Method ```POST```
```djangourlpath
localhost:8877/generateToken
```

####Request Body

```json
{
    "email":"narayan_health@footloose.io",
    "role":"ALL",
    "max_connections":100
}
```

####Response 
```json
{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.pTZqhXBzkkbHH6X_NcXhoGegUjOiRSXXsmqLieRSoAc",
    "clientId": "a880fb7ff5dbdd8121cefa3896"
}
```

#### Field Explanation

JSON Key  | Description | Type
------------- | ------------- | -------------
email  | Email Of the user | String
role  | Authorization roles | ENUM
max_connections  | Max_connections allowed to websocket | Number
accessToken  | Token to Access the websocket | String(270-280)
clientId  | Client ID | String(40)
