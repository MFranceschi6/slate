---
title: Beep Beep Statistics Webservice
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

<h1 id="beep-beep-statistics-webservice">Beep Beep Statistics Webservice v0.1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is a statistics web server for the Beep Beep application for retrieving statistics about your runs in a visual graphical format. For more information, visit the Github repository: https://github.com/MFranceschi6/BeepBeep-statistics

Base URLs:

* <a href="0.0.0.0:5001">0.0.0.0:5001</a>

<a href="https://github.com/MFranceschi6/BeepBeep-statistics">Terms of service</a>

License: <a href="https://www.apache.org/licenses/LICENSE-2.0.html">APLv2</a>

<h1 id="beep-beep-statistics-webservice-default">Default</h1>

## getAllStatisticsbyUserID

<a id="opIdgetAllStatisticsbyUserID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5001/statistics/{user_id}/ \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5001/statistics/{user_id}/ HTTP/1.1
Host: 5001
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5001/statistics/{user_id}/',
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

fetch('0.0.0.0:5001/statistics/{user_id}/',
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

result = RestClient.get '0.0.0.0:5001/statistics/{user_id}/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5001/statistics/{user_id}/', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5001/statistics/{user_id}/");
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
    req, err := http.NewRequest("GET", "0.0.0.0:5001/statistics/{user_id}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /statistics/{user_id}/`

By accessing this page and providing an existing user ID, you retrieve a set of 5 arrays about the temporal statistics of your runs for the following attributes, respectively: 'distance', 'average speed', 'average heartrate'. 'total elevation gain', 'elapsed time'.

<h3 id="getallstatisticsbyuserid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|The id of the user whose statistics you want to access|

> Example responses

> 200 Response

```json
{
  "distance_array": [
    0
  ],
  "average_speed_array": [
    0
  ],
  "average_heart_rate_array": [
    0
  ],
  "elevation_gain_array": [
    0
  ],
  "elapsed_time_array": [
    0
  ]
}
```

<h3 id="getallstatisticsbyuserid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|All runs' statistics for the user whose ID was provided|[AllNumericalArrays](#schemaallnumericalarrays)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid user ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found for the user ID supplied.|None|
|503|[Service Unavailable](https://tools.ietf.org/html/rfc7231#section-6.6.4)|The 'dataservice' microservice on which this application depends on is not available. Please, try again later|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## getSingleStatisticsbyUserID

<a id="opIdgetSingleStatisticsbyUserID"></a>

> Code samples

```shell
# You can also use wget
curl -X GET 0.0.0.0:5001/statistics/{user_id}/{statistics_id}/ \
  -H 'Accept: application/json'

```

```http
GET 0.0.0.0:5001/statistics/{user_id}/{statistics_id}/ HTTP/1.1
Host: 5001
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '0.0.0.0:5001/statistics/{user_id}/{statistics_id}/',
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

fetch('0.0.0.0:5001/statistics/{user_id}/{statistics_id}/',
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

result = RestClient.get '0.0.0.0:5001/statistics/{user_id}/{statistics_id}/',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('0.0.0.0:5001/statistics/{user_id}/{statistics_id}/', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("0.0.0.0:5001/statistics/{user_id}/{statistics_id}/");
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
    req, err := http.NewRequest("GET", "0.0.0.0:5001/statistics/{user_id}/{statistics_id}/", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /statistics/{user_id}/{statistics_id}/`

By accessing this page and providing an existing user ID, you retrieve a set of 5 arrays about the temporal statistics of your runs for the following attributes, respectively: 'distance', 'average speed', 'average heartrate'. 'total elevation gain', 'elapsed time'.

<h3 id="getsinglestatisticsbyuserid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|user_id|path|integer|true|The id of the user whose statistics you want to access|
|statistics_id|path|integer|true|Based on the statistics ID passed, one of the following arrays is returned: 1 = distance array; 2 = average speed array; 3 = average heartrate array ; 4 = total elevation gain array; 5 = elapsed time array.|

> Example responses

> 200 Response

```json
{
  "distance_array": [
    0
  ],
  "average_speed_array": [
    0
  ],
  "average_heart_rate_array": [
    0
  ],
  "elevation_gain_array": [
    0
  ],
  "elapsed_time_array": [
    0
  ]
}
```

<h3 id="getsinglestatisticsbyuserid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Runs' statistics of one single statistics type for the user whose ID was provided|[OneNumericalArray](#schemaonenumericalarray)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid user ID supplied or invalid statistics ID supplied.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found for the user ID supplied.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

# Schemas

<h2 id="tocSnumericalarray">NumericalArray</h2>

<a id="schemanumericalarray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSdistancearray">DistanceArray</h2>

<a id="schemadistancearray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSaveragespeedarray">AverageSpeedArray</h2>

<a id="schemaaveragespeedarray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSaverageheartratearray">AverageHeartRateArray</h2>

<a id="schemaaverageheartratearray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSelevationgainarray">ElevationGainArray</h2>

<a id="schemaelevationgainarray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSelapsedtimearray">ElapsedTimeArray</h2>

<a id="schemaelapsedtimearray"></a>

```json
[
  0
]

```

### Properties

*None*

<h2 id="tocSallnumericalarrays">AllNumericalArrays</h2>

<a id="schemaallnumericalarrays"></a>

```json
{
  "distance_array": [
    0
  ],
  "average_speed_array": [
    0
  ],
  "average_heart_rate_array": [
    0
  ],
  "elevation_gain_array": [
    0
  ],
  "elapsed_time_array": [
    0
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|distance_array|[DistanceArray](#schemadistancearray)|false|none|none|
|average_speed_array|[AverageSpeedArray](#schemaaveragespeedarray)|false|none|none|
|average_heart_rate_array|[AverageHeartRateArray](#schemaaverageheartratearray)|false|none|none|
|elevation_gain_array|[ElevationGainArray](#schemaelevationgainarray)|false|none|none|
|elapsed_time_array|[ElapsedTimeArray](#schemaelapsedtimearray)|false|none|none|

<h2 id="tocSonenumericalarray">OneNumericalArray</h2>

<a id="schemaonenumericalarray"></a>

```json
{
  "distance_array": [
    0
  ],
  "average_speed_array": [
    0
  ],
  "average_heart_rate_array": [
    0
  ],
  "elevation_gain_array": [
    0
  ],
  "elapsed_time_array": [
    0
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|distance_array|[DistanceArray](#schemadistancearray)|false|none|none|
|average_speed_array|[AverageSpeedArray](#schemaaveragespeedarray)|false|none|none|
|average_heart_rate_array|[AverageHeartRateArray](#schemaaverageheartratearray)|false|none|none|
|elevation_gain_array|[ElevationGainArray](#schemaelevationgainarray)|false|none|none|
|elapsed_time_array|[ElapsedTimeArray](#schemaelapsedtimearray)|false|none|none|

