---
title: Swagger Petstore
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers:
  - >-
    <a href="https://github.com/Rebilly/generator-openapi-repo">Find out how to
    create Github repo for your OpenAPI spec.</a>
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="swagger-petstore">Swagger Petstore v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is a sample server Petstore server.
You can find out more about Swagger at
[http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).
For this sample, you can use the api key `special-key` to test the authorization filters.
# Introduction
This API is documented in **OpenAPI format** and is based on
[Petstore sample](http://petstore.swagger.io/) provided by [swagger.io](http://swagger.io) team.
It was **extended** to illustrate features of [generator-openapi-repo](https://github.com/Rebilly/generator-openapi-repo)
tool and [ReDoc](https://github.com/Rebilly/ReDoc) documentation. In addition to standard
OpenAPI syntax we use a few [vendor extensions](https://github.com/Rebilly/ReDoc/blob/master/docs/redoc-vendor-extensions.md).
# OpenAPI Specification
This API is documented in **OpenAPI format** and is based on
[Petstore sample](http://petstore.swagger.io/) provided by [swagger.io](http://swagger.io) team.
It was **extended** to illustrate features of [generator-openapi-repo](https://github.com/Rebilly/generator-openapi-repo)
tool and [ReDoc](https://github.com/Rebilly/ReDoc) documentation. In addition to standard
OpenAPI syntax we use a few [vendor extensions](https://github.com/Rebilly/ReDoc/blob/master/docs/redoc-vendor-extensions.md).
# Cross-Origin Resource Sharing
This API features Cross-Origin Resource Sharing (CORS) implemented in compliance with  [W3C spec](https://www.w3.org/TR/cors/).
And that allows cross-domain communication from the browser.
All responses have a wildcard same-origin which makes them completely public and accessible to everyone, including any code on any site.

Base URLs:

* <a href="http://petstore.swagger.io/v2">http://petstore.swagger.io/v2</a>

* <a href="https://petstore.swagger.io/v2">https://petstore.swagger.io/v2</a>

<a href="http://swagger.io/terms/">Terms of service</a>
Email: <a href="mailto:apiteam@swagger.io">Support</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

- oAuth2 authentication. 

    - Flow: implicit
    - Authorization URL = [http://petstore.swagger.io/api/oauth/dialog](http://petstore.swagger.io/api/oauth/dialog)

|Scope|Scope Description|
|---|---|
|write:pets|modify pets in your account|
|read:pets|read your pets|

* API Key (api_key)
    - Parameter Name: **api_key**, in: header. 

<h1 id="swagger-petstore-pet">pet</h1>

Everything about your Pets

## addPet

<a id="opIdaddPet"></a>

> Code samples

```csharp
PetStore.v1.Pet pet = new PetStore.v1.Pet();
pet.setApiKey("your api key");
pet.petType = PetStore.v1.Pet.TYPE_DOG;
pet.name = "Rex";
// set other fields
PetStoreResponse response = pet.create();
if (response.statusCode == HttpStatusCode.Created)
{
  // Successfully created
}
else
{
  // Something wrong -- check response for errors
  Console.WriteLine(response.getRawResponse());
}

```

```php
$form = new \PetStore\Entities\Pet();
$form->setPetType("Dog");
$form->setName("Rex");
// set other fields
try {
    $pet = $client->pets()->create($form);
} catch (UnprocessableEntityException $e) {
    var_dump($e->getErrors());
}

```

`POST /pet`

*Add a new pet to the store*

Add new pet to the store inventory.

> Body parameter

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Pet>
  <petType>string</petType>
  <id>0</id>
  <category>
    <id>0</id>
    <name>string</name>
  </category>
  <name>Guru</name>
  <photoUrls>string</photoUrls>
  <tags>
    <id>0</id>
    <name>string</name>
  </tags>
  <status>available</status>
</Pet>
```

<h3 id="addpet-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pet](#schemapet)|false|Pet object that needs to be added to the store|

<h3 id="addpet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Invalid input|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## updatePet

<a id="opIdupdatePet"></a>

> Code samples

```php
$form = new \PetStore\Entities\Pet();
$form->setPetId(1);
$form->setPetType("Dog");
$form->setName("Rex");
// set other fields
try {
    $pet = $client->pets()->update($form);
} catch (UnprocessableEntityException $e) {
    var_dump($e->getErrors());
}

```

`PUT /pet`

*Update an existing pet*

> Body parameter

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Pet>
  <petType>string</petType>
  <id>0</id>
  <category>
    <id>0</id>
    <name>string</name>
  </category>
  <name>Guru</name>
  <photoUrls>string</photoUrls>
  <tags>
    <id>0</id>
    <name>string</name>
  </tags>
  <status>available</status>
</Pet>
```

<h3 id="updatepet-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pet](#schemapet)|false|Pet object that needs to be added to the store|

<h3 id="updatepet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Pet not found|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Validation exception|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## getPetById

<a id="opIdgetPetById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/pet/{petId} \
  -H 'Accept: application/xml' \
  -H 'api_key: API_KEY'

```

```http
GET http://petstore.swagger.io/v2/pet/{petId} HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml',
  'api_key':'API_KEY'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/{petId}',
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
  'Accept':'application/xml',
  'api_key':'API_KEY'

};

fetch('http://petstore.swagger.io/v2/pet/{petId}',
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
  'Accept' => 'application/xml',
  'api_key' => 'API_KEY'
}

result = RestClient.get 'http://petstore.swagger.io/v2/pet/{petId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml',
  'api_key': 'API_KEY'
}

r = requests.get('http://petstore.swagger.io/v2/pet/{petId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/{petId}");
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
        "Accept": []string{"application/xml"},
        "api_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/pet/{petId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /pet/{petId}`

*Find pet by ID*

Returns a single pet

<h3 id="getpetbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet to return|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Pet>
  <petType>string</petType>
  <id>0</id>
  <category>
    <id>0</id>
    <name>string</name>
  </category>
  <name>Guru</name>
  <photoUrls>string</photoUrls>
  <tags>
    <id>0</id>
    <name>string</name>
  </tags>
  <status>available</status>
</Pet>
```

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

<h3 id="getpetbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pet](#schemapet)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Pet not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## updatePetWithForm

<a id="opIdupdatePetWithForm"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/pet/{petId} \
  -H 'Content-Type: application/x-www-form-urlencoded' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://petstore.swagger.io/v2/pet/{petId} HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/x-www-form-urlencoded

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/{petId}',
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
  "name": "string",
  "status": "string"
}';
const headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Authorization':'Bearer {access-token}'

};

fetch('http://petstore.swagger.io/v2/pet/{petId}',
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
  'Content-Type' => 'application/x-www-form-urlencoded',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://petstore.swagger.io/v2/pet/{petId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/x-www-form-urlencoded',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://petstore.swagger.io/v2/pet/{petId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/{petId}");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/pet/{petId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /pet/{petId}`

*Updates a pet in the store with form data*

> Body parameter

```yaml
name: string
status: string

```

<h3 id="updatepetwithform-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet that needs to be updated|
|body|body|object|false|none|
|» name|body|string|false|Updated name of the pet|
|» status|body|string|false|Updated status of the pet|

<h3 id="updatepetwithform-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Invalid input|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## deletePet

<a id="opIddeletePet"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://petstore.swagger.io/v2/pet/{petId} \
  -H 'api_key: string' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE http://petstore.swagger.io/v2/pet/{petId} HTTP/1.1
Host: petstore.swagger.io

api_key: string

```

```javascript
var headers = {
  'api_key':'string',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/{petId}',
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
  'api_key':'string',
  'Authorization':'Bearer {access-token}'

};

fetch('http://petstore.swagger.io/v2/pet/{petId}',
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
  'api_key' => 'string',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'http://petstore.swagger.io/v2/pet/{petId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'api_key': 'string',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('http://petstore.swagger.io/v2/pet/{petId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/{petId}");
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
        "api_key": []string{"string"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://petstore.swagger.io/v2/pet/{petId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /pet/{petId}`

*Deletes a pet*

<h3 id="deletepet-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|false|none|
|petId|path|integer(int64)|true|Pet id to delete|

<h3 id="deletepet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid pet value|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## uploadFile

<a id="opIduploadFile"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/pet/{petId}/uploadImage \
  -H 'Content-Type: application/octet-stream' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST http://petstore.swagger.io/v2/pet/{petId}/uploadImage HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/octet-stream
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/octet-stream',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/{petId}/uploadImage',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = 'string';
const headers = {
  'Content-Type':'application/octet-stream',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('http://petstore.swagger.io/v2/pet/{petId}/uploadImage',
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
  'Content-Type' => 'application/octet-stream',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'http://petstore.swagger.io/v2/pet/{petId}/uploadImage',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/octet-stream',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('http://petstore.swagger.io/v2/pet/{petId}/uploadImage', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/{petId}/uploadImage");
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
        "Content-Type": []string{"application/octet-stream"},
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/pet/{petId}/uploadImage", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /pet/{petId}/uploadImage`

*uploads an image*

> Body parameter

```yaml
string

```

<h3 id="uploadfile-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet to update|
|body|body|string(binary)|false|none|

> Example responses

> 200 Response

```json
{
  "code": 0,
  "type": "string",
  "message": "string"
}
```

<h3 id="uploadfile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ApiResponse](#schemaapiresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## findPetsByStatus

<a id="opIdfindPetsByStatus"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/pet/findByStatus?status=available \
  -H 'Accept: application/xml' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://petstore.swagger.io/v2/pet/findByStatus?status=available HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/findByStatus',
  method: 'get',
  data: '?status=available',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/xml',
  'Authorization':'Bearer {access-token}'

};

fetch('http://petstore.swagger.io/v2/pet/findByStatus?status=available',
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
  'Accept' => 'application/xml',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://petstore.swagger.io/v2/pet/findByStatus',
  params: {
  'status' => 'array[string]'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://petstore.swagger.io/v2/pet/findByStatus', params={
  'status': [
  "available"
]
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/findByStatus?status=available");
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
        "Accept": []string{"application/xml"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/pet/findByStatus", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /pet/findByStatus`

*Finds Pets by status*

Multiple status values can be provided with comma seperated strings

<h3 id="findpetsbystatus-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|status|query|array[string]|true|Status values that need to be considered for filter|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<petType>string</petType>
<id>0</id>
<category>
  <id>0</id>
  <name>string</name>
</category>
<name>Guru</name>
<photoUrls>string</photoUrls>
<tags>
  <id>0</id>
  <name>string</name>
</tags>
<status>available</status>
```

```json
[
  {
    "petType": "string",
    "id": 0,
    "category": {
      "id": 0,
      "name": "string"
    },
    "name": "Guru",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  }
]
```

<h3 id="findpetsbystatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid status value|None|

<h3 id="findpetsbystatus-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pet](#schemapet)]|false|none|none|
|» petType|string|false|none|Type of a pet|
|» id|[Id](#schemaid)(int64)|false|none|Pet ID|
|» category|[Category](#schemacategory)|false|none|Categories this pet belongs to|
|»» id|[Id](#schemaid)(int64)|false|none|Category ID|
|»» name|string|false|none|Category name|
|» name|string|true|none|The name given to a pet|
|» photoUrls|[string]|true|none|The list of URL to a cute photos featuring pet|
|» tags|[[Tag](#schematag)]|false|none|Tags attached to the pet|
|»» id|[Id](#schemaid)(int64)|false|none|Tag ID|
|»» name|string|false|none|Tag name|
|» status|string|false|none|Pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## findPetsByTags

<a id="opIdfindPetsByTags"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/pet/findByTags?tags=string \
  -H 'Accept: application/xml' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET http://petstore.swagger.io/v2/pet/findByTags?tags=string HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/pet/findByTags',
  method: 'get',
  data: '?tags=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/xml',
  'Authorization':'Bearer {access-token}'

};

fetch('http://petstore.swagger.io/v2/pet/findByTags?tags=string',
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
  'Accept' => 'application/xml',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'http://petstore.swagger.io/v2/pet/findByTags',
  params: {
  'tags' => 'array[string]'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('http://petstore.swagger.io/v2/pet/findByTags', params={
  'tags': [
  "string"
]
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/pet/findByTags?tags=string");
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
        "Accept": []string{"application/xml"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/pet/findByTags", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /pet/findByTags`

*Finds Pets by tags*

Muliple tags can be provided with comma seperated strings. Use tag1, tag2, tag3 for testing.

<h3 id="findpetsbytags-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|tags|query|array[string]|true|Tags to filter by|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<petType>string</petType>
<id>0</id>
<category>
  <id>0</id>
  <name>string</name>
</category>
<name>Guru</name>
<photoUrls>string</photoUrls>
<tags>
  <id>0</id>
  <name>string</name>
</tags>
<status>available</status>
```

```json
[
  {
    "petType": "string",
    "id": 0,
    "category": {
      "id": 0,
      "name": "string"
    },
    "name": "Guru",
    "photoUrls": [
      "string"
    ],
    "tags": [
      {
        "id": 0,
        "name": "string"
      }
    ],
    "status": "available"
  }
]
```

<h3 id="findpetsbytags-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid tag value|None|

<h3 id="findpetsbytags-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pet](#schemapet)]|false|none|none|
|» petType|string|false|none|Type of a pet|
|» id|[Id](#schemaid)(int64)|false|none|Pet ID|
|» category|[Category](#schemacategory)|false|none|Categories this pet belongs to|
|»» id|[Id](#schemaid)(int64)|false|none|Category ID|
|»» name|string|false|none|Category name|
|» name|string|true|none|The name given to a pet|
|» photoUrls|[string]|true|none|The list of URL to a cute photos featuring pet|
|» tags|[[Tag](#schematag)]|false|none|Tags attached to the pet|
|»» id|[Id](#schemaid)(int64)|false|none|Tag ID|
|»» name|string|false|none|Tag name|
|» status|string|false|none|Pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

<h1 id="swagger-petstore-store">store</h1>

Access to Petstore orders

## getInventory

<a id="opIdgetInventory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/store/inventory \
  -H 'Accept: application/json' \
  -H 'api_key: API_KEY'

```

```http
GET http://petstore.swagger.io/v2/store/inventory HTTP/1.1
Host: petstore.swagger.io
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'api_key':'API_KEY'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/store/inventory',
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
  'Accept':'application/json',
  'api_key':'API_KEY'

};

fetch('http://petstore.swagger.io/v2/store/inventory',
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
  'Accept' => 'application/json',
  'api_key' => 'API_KEY'
}

result = RestClient.get 'http://petstore.swagger.io/v2/store/inventory',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'api_key': 'API_KEY'
}

r = requests.get('http://petstore.swagger.io/v2/store/inventory', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/store/inventory");
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
        "api_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/store/inventory", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /store/inventory`

*Returns pet inventories by status*

Returns a map of status codes to quantities

> Example responses

> 200 Response

```json
{
  "property1": 0,
  "property2": 0
}
```

<h3 id="getinventory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="getinventory-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» **additionalProperties**|integer(int32)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## placeOrder

<a id="opIdplaceOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/store/order \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/xml'

```

```http
POST http://petstore.swagger.io/v2/store/order HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/json
Accept: application/xml

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/xml'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/store/order',
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
  "petId": 0,
  "quantity": 1,
  "shipDate": "2018-11-18T18:10:45Z",
  "status": "placed",
  "complete": false
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/xml'

};

fetch('http://petstore.swagger.io/v2/store/order',
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
  'Accept' => 'application/xml'
}

result = RestClient.post 'http://petstore.swagger.io/v2/store/order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/xml'
}

r = requests.post('http://petstore.swagger.io/v2/store/order', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/store/order");
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
        "Accept": []string{"application/xml"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/store/order", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /store/order`

*Place an order for a pet*

> Body parameter

```json
{
  "id": 0,
  "petId": 0,
  "quantity": 1,
  "shipDate": "2018-11-18T18:10:45Z",
  "status": "placed",
  "complete": false
}
```

<h3 id="placeorder-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Order](#schemaorder)|false|order placed for purchasing the pet|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Order>
  <id>0</id>
  <petId>0</petId>
  <quantity>1</quantity>
  <shipDate>2018-11-18T18:10:45Z</shipDate>
  <status>placed</status>
  <complete>false</complete>
</Order>
```

```json
{
  "id": 0,
  "petId": 0,
  "quantity": 1,
  "shipDate": "2018-11-18T18:10:45Z",
  "status": "placed",
  "complete": false
}
```

<h3 id="placeorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Order|None|

<aside class="success">
This operation does not require authentication
</aside>

## getOrderById

<a id="opIdgetOrderById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/store/order/{orderId} \
  -H 'Accept: application/xml'

```

```http
GET http://petstore.swagger.io/v2/store/order/{orderId} HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/store/order/{orderId}',
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
  'Accept':'application/xml'

};

fetch('http://petstore.swagger.io/v2/store/order/{orderId}',
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
  'Accept' => 'application/xml'
}

result = RestClient.get 'http://petstore.swagger.io/v2/store/order/{orderId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml'
}

r = requests.get('http://petstore.swagger.io/v2/store/order/{orderId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/store/order/{orderId}");
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
        "Accept": []string{"application/xml"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/store/order/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /store/order/{orderId}`

*Find purchase order by ID*

For valid response try integer IDs with value <= 5 or > 10. Other values will generated exceptions

<h3 id="getorderbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|integer(int64)|true|ID of pet that needs to be fetched|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Order>
  <id>0</id>
  <petId>0</petId>
  <quantity>1</quantity>
  <shipDate>2018-11-18T18:10:45Z</shipDate>
  <status>placed</status>
  <complete>false</complete>
</Order>
```

```json
{
  "id": 0,
  "petId": 0,
  "quantity": 1,
  "shipDate": "2018-11-18T18:10:45Z",
  "status": "placed",
  "complete": false
}
```

<h3 id="getorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Order not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## deleteOrder

<a id="opIddeleteOrder"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://petstore.swagger.io/v2/store/order/{orderId}

```

```http
DELETE http://petstore.swagger.io/v2/store/order/{orderId} HTTP/1.1
Host: petstore.swagger.io

```

```javascript

$.ajax({
  url: 'http://petstore.swagger.io/v2/store/order/{orderId}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

fetch('http://petstore.swagger.io/v2/store/order/{orderId}',
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

result = RestClient.delete 'http://petstore.swagger.io/v2/store/order/{orderId}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('http://petstore.swagger.io/v2/store/order/{orderId}', params={

)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/store/order/{orderId}");
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
    req, err := http.NewRequest("DELETE", "http://petstore.swagger.io/v2/store/order/{orderId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /store/order/{orderId}`

*Delete purchase order by ID*

For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

<h3 id="deleteorder-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|string|true|ID of the order that needs to be deleted|

<h3 id="deleteorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Order not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="swagger-petstore-user">user</h1>

Operations about user

## createUser

<a id="opIdcreateUser"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/user \
  -H 'Content-Type: application/json'

```

```http
POST http://petstore.swagger.io/v2/user HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user',
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
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}';
const headers = {
  'Content-Type':'application/json'

};

fetch('http://petstore.swagger.io/v2/user',
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

result = RestClient.post 'http://petstore.swagger.io/v2/user',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('http://petstore.swagger.io/v2/user', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user");
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
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/user", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user`

*Create user*

This can only be done by the logged in user.

> Body parameter

```json
{
  "id": 0,
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}
```

<h3 id="createuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|false|Created user object|

<h3 id="createuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## getUserByName

<a id="opIdgetUserByName"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/user/{username} \
  -H 'Accept: application/xml'

```

```http
GET http://petstore.swagger.io/v2/user/{username} HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/{username}',
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
  'Accept':'application/xml'

};

fetch('http://petstore.swagger.io/v2/user/{username}',
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
  'Accept' => 'application/xml'
}

result = RestClient.get 'http://petstore.swagger.io/v2/user/{username}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml'
}

r = requests.get('http://petstore.swagger.io/v2/user/{username}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/{username}");
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
        "Accept": []string{"application/xml"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/user/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/{username}`

*Get user by user name*

<h3 id="getuserbyname-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The name that needs to be fetched. Use user1 for testing. |

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<User>
  <id>0</id>
  <username>John78</username>
  <firstName>John</firstName>
  <lastName>Smith</lastName>
  <email>john.smith@example.com</email>
  <password>drowssaP123</password>
  <phone>+1-202-555-0192</phone>
  <userStatus>0</userStatus>
</User>
```

```json
{
  "id": 0,
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}
```

<h3 id="getuserbyname-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[User](#schemauser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateUser

<a id="opIdupdateUser"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://petstore.swagger.io/v2/user/{username} \
  -H 'Content-Type: application/json'

```

```http
PUT http://petstore.swagger.io/v2/user/{username} HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/{username}',
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
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}';
const headers = {
  'Content-Type':'application/json'

};

fetch('http://petstore.swagger.io/v2/user/{username}',
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
  'Content-Type' => 'application/json'
}

result = RestClient.put 'http://petstore.swagger.io/v2/user/{username}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.put('http://petstore.swagger.io/v2/user/{username}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/{username}");
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
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://petstore.swagger.io/v2/user/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /user/{username}`

*Updated user*

This can only be done by the logged in user.

> Body parameter

```json
{
  "id": 0,
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}
```

<h3 id="updateuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|name that need to be deleted|
|body|body|[User](#schemauser)|false|Updated user object|

<h3 id="updateuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid user supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUser

<a id="opIddeleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://petstore.swagger.io/v2/user/{username}

```

```http
DELETE http://petstore.swagger.io/v2/user/{username} HTTP/1.1
Host: petstore.swagger.io

```

```javascript

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/{username}',
  method: 'delete',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

fetch('http://petstore.swagger.io/v2/user/{username}',
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

result = RestClient.delete 'http://petstore.swagger.io/v2/user/{username}',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.delete('http://petstore.swagger.io/v2/user/{username}', params={

)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/{username}");
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
    req, err := http.NewRequest("DELETE", "http://petstore.swagger.io/v2/user/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /user/{username}`

*Delete user*

This can only be done by the logged in user.

<h3 id="deleteuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The name that needs to be deleted|

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## createUsersWithArrayInput

<a id="opIdcreateUsersWithArrayInput"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/user/createWithArray \
  -H 'Content-Type: application/json'

```

```http
POST http://petstore.swagger.io/v2/user/createWithArray HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/createWithArray',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "id": 0,
    "username": "John78",
    "firstName": "John",
    "lastName": "Smith",
    "email": "john.smith@example.com",
    "password": "drowssaP123",
    "phone": "+1-202-555-0192",
    "userStatus": 0
  }
]';
const headers = {
  'Content-Type':'application/json'

};

fetch('http://petstore.swagger.io/v2/user/createWithArray',
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

result = RestClient.post 'http://petstore.swagger.io/v2/user/createWithArray',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('http://petstore.swagger.io/v2/user/createWithArray', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/createWithArray");
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
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/user/createWithArray", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user/createWithArray`

*Creates list of users with given input array*

> Body parameter

```json
[
  {
    "id": 0,
    "username": "John78",
    "firstName": "John",
    "lastName": "Smith",
    "email": "john.smith@example.com",
    "password": "drowssaP123",
    "phone": "+1-202-555-0192",
    "userStatus": 0
  }
]
```

<h3 id="createuserswitharrayinput-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserArray](#schemauserarray)|false|List of user object|

<h3 id="createuserswitharrayinput-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## createUsersWithListInput

<a id="opIdcreateUsersWithListInput"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://petstore.swagger.io/v2/user/createWithList \
  -H 'Content-Type: application/json'

```

```http
POST http://petstore.swagger.io/v2/user/createWithList HTTP/1.1
Host: petstore.swagger.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/createWithList',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "id": 0,
    "username": "John78",
    "firstName": "John",
    "lastName": "Smith",
    "email": "john.smith@example.com",
    "password": "drowssaP123",
    "phone": "+1-202-555-0192",
    "userStatus": 0
  }
]';
const headers = {
  'Content-Type':'application/json'

};

fetch('http://petstore.swagger.io/v2/user/createWithList',
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

result = RestClient.post 'http://petstore.swagger.io/v2/user/createWithList',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json'
}

r = requests.post('http://petstore.swagger.io/v2/user/createWithList', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/createWithList");
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
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v2/user/createWithList", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /user/createWithList`

*Creates list of users with given input array*

> Body parameter

```json
[
  {
    "id": 0,
    "username": "John78",
    "firstName": "John",
    "lastName": "Smith",
    "email": "john.smith@example.com",
    "password": "drowssaP123",
    "phone": "+1-202-555-0192",
    "userStatus": 0
  }
]
```

<h3 id="createuserswithlistinput-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserArray](#schemauserarray)|false|List of user object|

<h3 id="createuserswithlistinput-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## loginUser

<a id="opIdloginUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/user/login?username=string&password=string \
  -H 'Accept: application/xml'

```

```http
GET http://petstore.swagger.io/v2/user/login?username=string&password=string HTTP/1.1
Host: petstore.swagger.io
Accept: application/xml

```

```javascript
var headers = {
  'Accept':'application/xml'

};

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/login',
  method: 'get',
  data: '?username=string&password=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/xml'

};

fetch('http://petstore.swagger.io/v2/user/login?username=string&password=string',
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
  'Accept' => 'application/xml'
}

result = RestClient.get 'http://petstore.swagger.io/v2/user/login',
  params: {
  'username' => 'string',
'password' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/xml'
}

r = requests.get('http://petstore.swagger.io/v2/user/login', params={
  'username': 'string',  'password': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/login?username=string&password=string");
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
        "Accept": []string{"application/xml"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/user/login", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/login`

*Logs user into the system*

<h3 id="loginuser-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|username|query|string|true|The user name for login|
|password|query|string|true|The password for login in clear text|

> Example responses

> 200 Response

> successful operation

```json
"OK"
```

<h3 id="loginuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username/password supplied|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|X-Rate-Limit|integer|int32|calls per hour allowed by the user|
|200|X-Expires-After|string|date-time|date in UTC when toekn expires|

<aside class="success">
This operation does not require authentication
</aside>

## logoutUser

<a id="opIdlogoutUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://petstore.swagger.io/v2/user/logout

```

```http
GET http://petstore.swagger.io/v2/user/logout HTTP/1.1
Host: petstore.swagger.io

```

```javascript

$.ajax({
  url: 'http://petstore.swagger.io/v2/user/logout',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

fetch('http://petstore.swagger.io/v2/user/logout',
{
  method: 'GET'

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

result = RestClient.get 'http://petstore.swagger.io/v2/user/logout',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('http://petstore.swagger.io/v2/user/logout', params={

)

print r.json()

```

```java
URL obj = new URL("http://petstore.swagger.io/v2/user/logout");
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

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v2/user/logout", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /user/logout`

*Logs out current logged in user session*

<h3 id="logoutuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSapiresponse">ApiResponse</h2>

<a id="schemaapiresponse"></a>

```json
{
  "code": 0,
  "type": "string",
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|false|none|none|
|type|string|false|none|none|
|message|string|false|none|none|

<h2 id="tocScat">Cat</h2>

<a id="schemacat"></a>

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available",
  "huntingSkill": "lazy"
}

```

*A representation of a cat*

### Properties

*allOf - discriminator: Pet.petType*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Pet](#schemapet)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» huntingSkill|string|true|none|The measured skill for hunting|

#### Enumerated Values

|Property|Value|
|---|---|
|huntingSkill|clueless|
|huntingSkill|lazy|
|huntingSkill|adventurous|
|huntingSkill|aggressive|

<h2 id="tocScategory">Category</h2>

<a id="schemacategory"></a>

```json
{
  "id": 0,
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|[Id](#schemaid)|false|none|Category ID|
|name|string|false|none|Category name|

<h2 id="tocSdog">Dog</h2>

<a id="schemadog"></a>

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available",
  "packSize": 1
}

```

*A representation of a dog*

### Properties

*allOf - discriminator: Pet.petType*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Pet](#schemapet)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» packSize|integer(int32)|true|none|The size of the pack the dog is from|

<h2 id="tocShoneybee">HoneyBee</h2>

<a id="schemahoneybee"></a>

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available",
  "honeyPerDay": 3.14
}

```

*A representation of a honey bee*

### Properties

*allOf - discriminator: Pet.petType*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[Pet](#schemapet)|false|none|none|

*and*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» honeyPerDay|number|true|none|Average amount of honey produced per day in ounces|

<h2 id="tocSid">Id</h2>

<a id="schemaid"></a>

```json
0

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int64)|false|none|none|

<h2 id="tocSorder">Order</h2>

<a id="schemaorder"></a>

```json
{
  "id": 0,
  "petId": 0,
  "quantity": 1,
  "shipDate": "2018-11-18T18:10:45Z",
  "status": "placed",
  "complete": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|[Id](#schemaid)|false|none|Order ID|
|petId|[Id](#schemaid)|false|none|Pet ID|
|quantity|integer(int32)|false|none|none|
|shipDate|string(date-time)|false|none|Estimated ship date|
|status|string|false|none|Order Status|
|complete|boolean|false|none|Indicates whenever order was completed or not|

#### Enumerated Values

|Property|Value|
|---|---|
|status|placed|
|status|approved|
|status|delivered|

<h2 id="tocSpet">Pet</h2>

<a id="schemapet"></a>

```json
{
  "petType": "string",
  "id": 0,
  "category": {
    "id": 0,
    "name": "string"
  },
  "name": "Guru",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|petType|string|false|none|Type of a pet|
|id|[Id](#schemaid)|false|none|Pet ID|
|category|[Category](#schemacategory)|false|none|Categories this pet belongs to|
|name|string|true|none|The name given to a pet|
|photoUrls|[string]|true|none|The list of URL to a cute photos featuring pet|
|tags|[[Tag](#schematag)]|false|none|Tags attached to the pet|
|status|string|false|none|Pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<h2 id="tocStag">Tag</h2>

<a id="schematag"></a>

```json
{
  "id": 0,
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|[Id](#schemaid)|false|none|Tag ID|
|name|string|false|none|Tag name|

<h2 id="tocSuser">User</h2>

<a id="schemauser"></a>

```json
{
  "id": 0,
  "username": "John78",
  "firstName": "John",
  "lastName": "Smith",
  "email": "john.smith@example.com",
  "password": "drowssaP123",
  "phone": "+1-202-555-0192",
  "userStatus": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|[Id](#schemaid)|false|none|none|
|username|string|false|none|User supplied username|
|firstName|string|false|none|User first name|
|lastName|string|false|none|User last name|
|email|string(email)|false|none|User email address|
|password|string(password)|false|none|User password, MUST contain a mix of upper and lower case letters, as well as digits|
|phone|string|false|none|User phone number in international format|
|userStatus|integer(int32)|false|none|User status|

