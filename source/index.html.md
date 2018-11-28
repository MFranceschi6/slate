---
title: BeepBeep Challenge
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

<h1 id="beepbeep-challenge">BeepBeep Challenge v0.1.9</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Returns info about BeepBeep user challenges

Base URLs:

* <a href="0.0.0.0:5003">0.0.0.0:5003</a>

License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">APLv2</a>

<h1 id="beepbeep-challenge-default">Default</h1>

## getChallenges

<a id="opIdgetChallenges"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5003/users/{runner_id}/challenges \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5003/users/{runner_id}/challenges HTTP/1.1
Host: 5003
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5003/users/{runner_id}/challenges',
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

fetch('0.0.0.0:5003/users/{runner_id}/challenges',
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

result = RestClient.get '0.0.0.0:5003/users/{runner_id}/challenges',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5003/users/{runner_id}/challenges', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5003/users/{runner_id}/challenges");
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
    req, err := http.NewRequest("GET", "0.0.0.0:5003/users/{runner_id}/challenges", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/{runner_id}/challenges`

Get all the challenges of an user

<h3 id="getchallenges-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|runner_id|path|integer|true|The id of the user|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "run_challenged_id": 0,
    "run_challenger_id": 0,
    "runner_id": 0,
    "start_date": 0,
    "result": true
  }
]
```

<h3 id="getchallenges-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A, possibly empty, list of challenges|Inline|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Connection with Data Service failed|None|

<h3 id="getchallenges-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[allOf]|false|none|none|

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|object|false|none|none|
|»» id|integer|false|none|The ID of the Challenge|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» *anonymous*|[Challenge](#schemachallenge)|false|none|none|
|»» run_challenged_id|integer|true|none|ID of the challenged run|
|»» run_challenger_id|integer|false|none|ID of the challenger run|
|»» runner_id|integer|true|none|The id of the user who made this run|
|»» start_date|integer(timestamp)|false|none|The timestamp when this challenge was made|
|»» result|boolean|false|none|The result of the challenge that can been won or lost|

<aside class="success">
This operation does not require authentication
</aside>

## createChallenge

<a id="opIdcreateChallenge"></a>

> Code samples

```shell
# You can also use wget
curl -X POST 0.0.0.0:5003/users/{runner_id}/challenges \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST 0.0.0.0:5003/users/{runner_id}/challenges HTTP/1.1
Host: 5003
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5003/users/{runner_id}/challenges',
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
  "run_challenged_id": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('0.0.0.0:5003/users/{runner_id}/challenges',
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

result = RestClient.post '0.0.0.0:5003/users/{runner_id}/challenges',
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

r = requests.post('0.0.0.0:5003/users/{runner_id}/challenges', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5003/users/{runner_id}/challenges");
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
    req, err := http.NewRequest("POST", "0.0.0.0:5003/users/{runner_id}/challenges", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /users/{runner_id}/challenges`

Create a new challenge

> Body parameter

```json
{
  "run_challenged_id": 0
}
```

<h3 id="createchallenge-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|User has to provide its id and the run_challenged_id|
|» run_challenged_id|body|integer|true|none|
|runner_id|path|integer|true|The id of the user|

> Example responses

> 204 Response

```json
0
```

<h3 id="createchallenge-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|The challenge were added succesfully|integer|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Something went wrong trying to parse the request|[Error](#schemaerror)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Connection with Data Service failed|None|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUserChallenges

<a id="opIddeleteUserChallenges"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE 0.0.0.0:5003/users/{runner_id}/challenges

```

```http
DELETE 0.0.0.0:5003/users/{runner_id}/challenges HTTP/1.1
Host: 5003

```

```javascript

$.ajax({
  url: '0.0.0.0:5003/users/{runner_id}/challenges',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

fetch('0.0.0.0:5003/users/{runner_id}/challenges',
{
  method: 'DELETE'

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

result = RestClient.delete '0.0.0.0:5003/users/{runner_id}/challenges',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('0.0.0.0:5003/users/{runner_id}/challenges', params={

)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5003/users/{runner_id}/challenges");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "0.0.0.0:5003/users/{runner_id}/challenges", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /users/{runner_id}/challenges`

Delete all the Challenges of a specified User

<h3 id="deleteuserchallenges-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|runner_id|path|integer|true|The id of the user|

<h3 id="deleteuserchallenges-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The challenges are succesfully deleted|None|

<aside class="success">
This operation does not require authentication
</aside>

## getChallengeID

<a id="opIdgetChallengeID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id} \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id} HTTP/1.1
Host: 5003
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
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

fetch('0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
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

result = RestClient.get '0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}");
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
    req, err := http.NewRequest("GET", "0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /users/{runner_id}/challenges/{challenge_id}`

Get The challenge *challenge_id* of the user *runner_id*

<h3 id="getchallengeid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|runner_id|path|integer|true|The id of the user|
|challenge_id|path|integer|true|The id of the challenge|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "run_challenged_id": 0,
  "run_challenger_id": 0,
  "runner_id": 0,
  "start_date": 0,
  "result": true
}
```

<h3 id="getchallengeid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The challenge of the user|[ResponseChallenge](#schemaresponsechallenge)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## completeChallenge

<a id="opIdcompleteChallenge"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT 0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT 0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id} HTTP/1.1
Host: 5003
Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
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
  "run_challenger_id": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
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

result = RestClient.put '0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}',
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

r = requests.put('0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}");
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
    req, err := http.NewRequest("PUT", "0.0.0.0:5003/users/{runner_id}/challenges/{challenge_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /users/{runner_id}/challenges/{challenge_id}`

Complete the challenge specied with the run challenger

> Body parameter

```json
{
  "run_challenger_id": 0
}
```

<h3 id="completechallenge-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|The id of the run challenger|
|» run_challenger_id|body|integer|true|none|
|runner_id|path|integer|true|The id of the user|
|challenge_id|path|integer|true|The id of the challenge|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "run_challenged_id": 0,
  "run_challenger_id": 0,
  "runner_id": 0,
  "start_date": 0,
  "result": true
}
```

<h3 id="completechallenge-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The challenge succesfully updated|[ResponseChallenge](#schemaresponsechallenge)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|The specified resource was not found|[Error](#schemaerror)|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|Connection with Data Service failed|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSchallenge">Challenge</h2>

<a id="schemachallenge"></a>

```json
{
  "run_challenged_id": 0,
  "run_challenger_id": 0,
  "runner_id": 0,
  "start_date": 0,
  "result": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|run_challenged_id|integer|true|none|ID of the challenged run|
|run_challenger_id|integer|false|none|ID of the challenger run|
|runner_id|integer|true|none|The id of the user who made this run|
|start_date|integer(timestamp)|false|none|The timestamp when this challenge was made|
|result|boolean|false|none|The result of the challenge that can been won or lost|

<h2 id="tocSresponsechallenge">ResponseChallenge</h2>

<a id="schemaresponsechallenge"></a>

```json
{
  "id": 0,
  "run_challenged_id": 0,
  "run_challenger_id": 0,
  "runner_id": 0,
  "start_date": 0,
  "result": true
}

```

### Properties

*allOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|integer|false|none|The ID of the Challenge|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Challenge](#schemachallenge)|false|none|none|

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

