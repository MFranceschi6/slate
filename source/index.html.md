---
title: BeepBeep Data Service
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="beepbeep-data-service">BeepBeep Data Service v0.1.9</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Returns info about BeepBeep registered users and their runs

Base URLs:

* <a href="0.0.0.0:5002">0.0.0.0:5002</a>

License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">APLv2</a>

<h1 id="beepbeep-data-service-default">Default</h1>

## addRuns

<a id="opIdaddRuns"></a>

> Code samples

```shell
# You can also use wget
curl -X POST 0.0.0.0:5002/add_runs \
  -H 'Content-Type: application/json'

```

```http
POST 0.0.0.0:5002/add_runs HTTP/1.1
Host: 5002
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/add_runs',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "property1": [
    {
      "title": "string",
      "description": "string",
      "strava_id": 0,
      "distance": 0,
      "start_date": 0,
      "elapsed_time": 0,
      "average_speed": 0,
      "total_elevation_gain": 0,
      "runner_id": 0
    }
  ],
  "property2": [
    {
      "title": "string",
      "description": "string",
      "strava_id": 0,
      "distance": 0,
      "start_date": 0,
      "elapsed_time": 0,
      "average_speed": 0,
      "total_elevation_gain": 0,
      "runner_id": 0
    }
  ]
}';
const headers = {
  'Content-Type':'application/json'

};

fetch('0.0.0.0:5002/add_runs',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json'
}

result = RestClient.post '0.0.0.0:5002/add_runs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('0.0.0.0:5002/add_runs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/add_runs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "0.0.0.0:5002/add_runs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /add_runs`

Adds a bunch of runs to different users

> Body parameter

```json
{
  "property1": [
    {
      "title": "string",
      "description": "string",
      "strava_id": 0,
      "distance": 0,
      "start_date": 0,
      "elapsed_time": 0,
      "average_speed": 0,
      "total_elevation_gain": 0,
      "runner_id": 0
    }
  ],
  "property2": [
    {
      "title": "string",
      "description": "string",
      "strava_id": 0,
      "distance": 0,
      "start_date": 0,
      "elapsed_time": 0,
      "average_speed": 0,
      "total_elevation_gain": 0,
      "runner_id": 0
    }
  ]
}
```

<h3 id="addruns-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|An object of array of objects that describe all the runs of some users|
|» **additionalProperties**|body|[[Run](#schemarun)]|false|none|
|»» title|body|string|true|A title for the run|
|»» description|body|string|true|A more detailed description for the run|
|»» strava_id|body|integer|true|The id of the run when fetched from Strava|
|»» distance|body|number(float)|true|The distance the user run expressed in meters|
|»» start_date|body|integer(timestamp)|true|The timestamp when this run was made|
|»» elapsed_time|body|integer|true|The total time that this run took to complete|
|»» average_speed|body|number(float)|true|The average speed of the run|
|»» total_elevation_gain|body|number(float)|true|The total elevation gained during the run|
|»» runner_id|body|integer|false|The id of the user who made this run|

<h3 id="addruns-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The runs were added succesfully|None|

<aside class="success">
This operation does not require authentication
</aside>

## getUsers

<a id="opIdgetUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5002/users \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5002/users HTTP/1.1
Host: 5002
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/users',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '0.0.0.0:5002/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5002/users', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "0.0.0.0:5002/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users`

Returns the list of all the users

> Example responses

> 200 Response

```json
{
  "users": [
    {
      "id": 0,
      "email": "user@example.com",
      "firstname": "string",
      "lastname": "string",
      "strava_token": "string",
      "age": 0,
      "weight": 0,
      "max_hr": 0,
      "rest_hr": 0,
      "vo2max": 0
    }
  ]
}
```

<h3 id="getusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A, possibly empty, list of users|Inline|

<h3 id="getusers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» users|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|object|false|none|none|
|»»» id|integer|true|none|the ID of the user|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|[UserTemplate](#schemausertemplate)|false|none|none|
|»»» email|string(email)|true|none|The email of the user|
|»»» firstname|string|true|none|The firstname of the user|
|»»» lastname|string|true|none|The lastname of the user|
|»»» strava_token|string|false|none|The strava_token of the user|
|»»» age|integer|true|none|The age of the user|
|»»» weight|number(float)|true|none|The weight of the user|
|»»» max_hr|integer|true|none|The max heartrate of the user|
|»»» rest_hr|integer|true|none|The at rest heartrate of the user|
|»»» vo2max|number(float)|true|none|I have no clue what this is|

<aside class="success">
This operation does not require authentication
</aside>

## addUser

<a id="opIdaddUser"></a>

> Code samples

```shell
# You can also use wget
curl -X POST 0.0.0.0:5002/users \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST 0.0.0.0:5002/users HTTP/1.1
Host: 5002
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/users',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/users',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post '0.0.0.0:5002/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('0.0.0.0:5002/users', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "0.0.0.0:5002/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users`

Register a new User inside the Data Service

> Body parameter

```json
{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}
```

<h3 id="adduser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|true|The description of the new User to add into the DataService|

> Example responses

> 400 Response

```json
{
  "response-code": 0,
  "message": "string"
}
```

<h3 id="adduser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The user was added succesfully|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Something went wrong trying to parse the request|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getSingleUser

<a id="opIdgetSingleUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5002/user/{user_id} \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5002/user/{user_id} HTTP/1.1
Host: 5002
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/user/{user_id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/user/{user_id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '0.0.0.0:5002/user/{user_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5002/user/{user_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/user/{user_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "0.0.0.0:5002/user/{user_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/{user_id}`

Returns a specific User

<h3 id="getsingleuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|The id of the user|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}
```

<h3 id="getsingleuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Information about an User|[ExistingUser](#schemaexistinguser)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## updateSingleUser

<a id="opIdupdateSingleUser"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT 0.0.0.0:5002/user/{user_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT 0.0.0.0:5002/user/{user_id} HTTP/1.1
Host: 5002
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/user/{user_id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/user/{user_id}',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put '0.0.0.0:5002/user/{user_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('0.0.0.0:5002/user/{user_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/user/{user_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "0.0.0.0:5002/user/{user_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /user/{user_id}`

Update the information of a single User

> Body parameter

```json
{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}
```

<h3 id="updatesingleuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ExistingUser](#schemaexistinguser)|true|The description of the update information of the User|
|user_id|path|integer|true|The id of the user|

> Example responses

> 400 Response

```json
{
  "response-code": 0,
  "message": "string"
}
```

<h3 id="updatesingleuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|User succesfully updated|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Something went wrong trying to parse the request|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## deleteSingleUser

<a id="opIddeleteSingleUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE 0.0.0.0:5002/user/{user_id} \
  -H 'Accept: application/json'

```

```http
DELETE 0.0.0.0:5002/user/{user_id} HTTP/1.1
Host: 5002
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/user/{user_id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/user/{user_id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '0.0.0.0:5002/user/{user_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('0.0.0.0:5002/user/{user_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/user/{user_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "0.0.0.0:5002/user/{user_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /user/{user_id}`

Remove an User from the service

<h3 id="deletesingleuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|The id of the user|

> Example responses

> 404 Response

```json
{
  "response-code": 0,
  "message": "string"
}
```

<h3 id="deletesingleuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|User succesfully removed|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getRuns

<a id="opIdgetRuns"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5002/user/{user_id}/runs \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5002/user/{user_id}/runs HTTP/1.1
Host: 5002
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/user/{user_id}/runs',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/user/{user_id}/runs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '0.0.0.0:5002/user/{user_id}/runs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5002/user/{user_id}/runs', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/user/{user_id}/runs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "0.0.0.0:5002/user/{user_id}/runs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/{user_id}/runs`

Get all the run of an user with respect to some criteria

<h3 id="getruns-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|ID of User|
|start-date|query|string(date)|false|If this parameter is set all the runs returned will have a start_date not less than date-start|
|finish-date|query|string(date)|false|If this parameter is set all the runs returned will have a start_date not greater than date-finish|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "title": "string",
    "description": "string",
    "strava_id": 0,
    "distance": 0,
    "start_date": 0,
    "elapsed_time": 0,
    "average_speed": 0,
    "total_elevation_gain": 0,
    "runner_id": 0
  }
]
```

<h3 id="getruns-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A, possibly empty, list of runs|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Something went wrong trying to parse the request|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<h3 id="getruns-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» id|integer|false|none|The ID of the Run|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Run](#schemarun)|false|none|none|
|»» title|string|true|none|A title for the run|
|»» description|string|true|none|A more detailed description for the run|
|»» strava_id|integer|true|none|The id of the run when fetched from Strava|
|»» distance|number(float)|true|none|The distance the user run expressed in meters|
|»» start_date|integer(timestamp)|true|none|The timestamp when this run was made|
|»» elapsed_time|integer|true|none|The total time that this run took to complete|
|»» average_speed|number(float)|true|none|The average speed of the run|
|»» total_elevation_gain|number(float)|true|none|The total elevation gained during the run|
|»» runner_id|integer|false|none|The id of the user who made this run|

<aside class="success">
This operation does not require authentication
</aside>

## getSingleRun

<a id="opIdgetSingleRun"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5002/user/{user_id}/runs/{run_id} \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5002/user/{user_id}/runs/{run_id} HTTP/1.1
Host: 5002
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5002/user/{user_id}/runs/{run_id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('0.0.0.0:5002/user/{user_id}/runs/{run_id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '0.0.0.0:5002/user/{user_id}/runs/{run_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5002/user/{user_id}/runs/{run_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5002/user/{user_id}/runs/{run_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "0.0.0.0:5002/user/{user_id}/runs/{run_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/{user_id}/runs/{run_id}`

Get The run *run_id* of the user *user_id*

<h3 id="getsinglerun-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|ID of the user|
|run_id|path|integer|true|ID of the Run|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "title": "string",
  "description": "string",
  "strava_id": 0,
  "distance": 0,
  "start_date": 0,
  "elapsed_time": 0,
  "average_speed": 0,
  "total_elevation_gain": 0,
  "runner_id": 0
}
```

<h3 id="getsinglerun-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The run of the user|[ResponseRun](#schemaresponserun)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSrun">Run</h2>

<a id="schemarun"></a>

```json
{
  "title": "string",
  "description": "string",
  "strava_id": 0,
  "distance": 0,
  "start_date": 0,
  "elapsed_time": 0,
  "average_speed": 0,
  "total_elevation_gain": 0,
  "runner_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|true|none|A title for the run|
|description|string|true|none|A more detailed description for the run|
|strava_id|integer|true|none|The id of the run when fetched from Strava|
|distance|number(float)|true|none|The distance the user run expressed in meters|
|start_date|integer(timestamp)|true|none|The timestamp when this run was made|
|elapsed_time|integer|true|none|The total time that this run took to complete|
|average_speed|number(float)|true|none|The average speed of the run|
|total_elevation_gain|number(float)|true|none|The total elevation gained during the run|
|runner_id|integer|false|none|The id of the user who made this run|

<h2 id="tocSresponserun">ResponseRun</h2>

<a id="schemaresponserun"></a>

```json
{
  "id": 0,
  "title": "string",
  "description": "string",
  "strava_id": 0,
  "distance": 0,
  "start_date": 0,
  "elapsed_time": 0,
  "average_speed": 0,
  "total_elevation_gain": 0,
  "runner_id": 0
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|integer|false|none|The ID of the Run|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Run](#schemarun)|false|none|none|

<h2 id="tocSusertemplate">UserTemplate</h2>

<a id="schemausertemplate"></a>

```json
{
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|email|string(email)|true|none|The email of the user|
|firstname|string|true|none|The firstname of the user|
|lastname|string|true|none|The lastname of the user|
|strava_token|string|false|none|The strava_token of the user|
|age|integer|true|none|The age of the user|
|weight|number(float)|true|none|The weight of the user|
|max_hr|integer|true|none|The max heartrate of the user|
|rest_hr|integer|true|none|The at rest heartrate of the user|
|vo2max|number(float)|true|none|I have no clue what this is|

<h2 id="tocSexistinguser">ExistingUser</h2>

<a id="schemaexistinguser"></a>

```json
{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|integer|true|none|the ID of the user|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UserTemplate](#schemausertemplate)|false|none|none|

<h2 id="tocSuser">User</h2>

<a id="schemauser"></a>

```json
{
  "id": 0,
  "email": "user@example.com",
  "firstname": "string",
  "lastname": "string",
  "strava_token": "string",
  "age": 0,
  "weight": 0,
  "max_hr": 0,
  "rest_hr": 0,
  "vo2max": 0
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|integer|false|none|the ID of the user|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UserTemplate](#schemausertemplate)|false|none|none|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "response-code": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|response-code|integer|true|none|The code of the HTTP response error|
|message|string|true|none|Additional description about the error|

