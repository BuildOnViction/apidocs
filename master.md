
<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tomomaster-apis">TomoMaster APIs v1.3.3</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Happy to code TomoMaster APIs

Base URLs:

* <a href="https://master.tomochain.com">https://master.tomochain.com</a>

* <a href="http://master.tomochain.com">http://master.tomochain.com</a>

License: <a href="https://github.com/tomochain/tomomaster">Github</a>

<h1 id="tomomaster-apis-config">Config</h1>

Get TomoMaster Application Configuration

## Get TomoMaster Application Configuration

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/config \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/config",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/config"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/config")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/config", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/config")
  .header("accept", "application/json")
  .asString();
```

`GET /api/config`

> Example responses

> 200 Response

```json
{
  "blockchain": {
    "rpc": "string",
    "ws": "string",
    "epoch": 900,
    "blockTime": 0
  },
  "explorerUrl": "string",
  "GA": "string"
}
```

<h3 id="get-tomomaster-application-configuration-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[config](#schemaconfig)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-candidates">Candidates</h1>

Get Candidates information

## Get candidates information

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates`

<h3 id="get-candidates-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "123",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "91540333800000001000000",
      "createdAt": "2018-10-31T03:42:39.375Z",
      "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
      "status": "RESIGNED",
      "updatedAt": "2019-01-11T09:21:55.028Z",
      "latestSignedBlock": 2917487,
      "capacityNumber": 91540.33380000001,
      "isMasternode": false,
      "isPenalty": false
    }
  ],
  "total": 100,
  "activeCandidates": 10
}
```

<h3 id="get-candidates-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidate](#schemacandidate)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get masternodes(exclude Proposed candidates) information

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/masternodes \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/masternodes",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/masternodes"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/masternodes")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/masternodes", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/masternodes")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/masternodes`

<h3 id="get-masternodes(exclude-proposed-candidates)-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c52a0df5f0abf3496d9a38f",
      "candidate": "0x1d50df657b6dce50bac634bf18e2d986d807e940",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "574962709628904011242293",
      "capacityNumber": 574962.709628904,
      "createdAt": "2019-01-31T07:16:47.833Z",
      "nodeId": "1d50df657b6dce50bac634bf18e2d986d807e940",
      "owner": "0x300d18c65563d0c9021d7722dd1aab74b9cc447f",
      "status": "MASTERNODE",
      "updatedAt": "2019-04-11T02:56:39.928Z",
      "latestSignedBlock": 3899535,
      "name": "GNBA.GE",
      "rank": 1
    }
  ],
  "activeCandidates": 150,
  "totalSlashed": 1,
  "totalResigned": 53,
  "totalProposed": 10
}
```

<h3 id="get-masternodes(exclude-proposed-candidates)-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[masternode](#schemamasternode)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get slashed Masternodes

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/slashedMNs \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/slashedMNs",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/slashedMNs"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/slashedMNs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/slashedMNs", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/slashedMNs")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/slashedMNs`

<h3 id="get-slashed-masternodes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c4006b47ff073e7961fabd5",
      "candidate": "0x1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "114213709385390179602070",
      "capacityNumber": 114213.70938539018,
      "createdAt": "2019-01-17T04:38:12.051Z",
      "nodeId": "1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "owner": "0xe60f54049759a11d764756ece4d27815e990d92f",
      "status": "SLASHED",
      "updatedAt": "2019-01-29T10:38:18.268Z",
      "latestSignedBlock": 1220265
    }
  ],
  "total": 1
}
```

<h3 id="get-slashed-masternodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[slashedMN](#schemaslashedmn)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get proposed Masternodes

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/proposedMNs \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/proposedMNs",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/proposedMNs"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/proposedMNs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/proposedMNs", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/proposedMNs")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/proposedMNs`

<h3 id="get-proposed-masternodes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c4006b47ff073e7961fabd5",
      "candidate": "0x1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "114213709385390179602070",
      "capacityNumber": 114213.70938539018,
      "createdAt": "2019-01-17T04:38:12.051Z",
      "nodeId": "1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "owner": "0xe60f54049759a11d764756ece4d27815e990d92f",
      "status": "PROPOSED",
      "updatedAt": "2019-01-29T10:38:18.268Z",
      "latestSignedBlock": 1220265
    }
  ],
  "total": 1
}
```

<h3 id="get-proposed-masternodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[proposedMN](#schemaproposedmn)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get resigned Masternodes

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/resignedMNs \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/resignedMNs",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/resignedMNs"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/resignedMNs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/resignedMNs", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/resignedMNs")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/resignedMNs`

<h3 id="get-resigned-masternodes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c4006b37ff073e7961fab14",
      "candidate": "0x7a3b86261cd2042a3190c81dd37d0a12e0397daf",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "40508760000000000000000",
      "capacityNumber": 40508.76,
      "createdAt": "2019-01-17T04:38:11.949Z",
      "nodeId": "7a3b86261cd2042a3190c81dd37d0a12e0397daf",
      "owner": "0xbff690303287ce327c319f575c7671c3ad626de4",
      "status": "RESIGNED",
      "updatedAt": "2019-01-29T10:11:19.464Z",
      "latestSignedBlock": 957442
    }
  ],
  "total": 1
}
```

<h3 id="get-resigned-masternodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[resignedMN](#schemaresignedmn)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get candidate's information

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}`

<h3 id="get-candidate's-information-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
{
  "_id": "123",
  "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "91540333800000001000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
  "status": "RESIGNED",
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "latestSignedBlock": "2917487",
  "capacityNumber": 91540.33380000001,
  "isMasternode": false,
  "isPenalty": false
}
```

<h3 id="get-candidate's-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateDetail](#schemacandidatedetail)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get voters who voted for the candidate

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string/voters \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string/voters",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string/voters"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string/voters")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string/voters", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string/voters")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}/voters`

<h3 id="get-voters-who-voted-for-the-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5bd924a9aa41b819395d9207",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "voter": "0xf2cce442c7ab5baf194838081b5f9396330ecfb8",
      "__v": 0,
      "capacity": "105000000000000000000",
      "createdAt": "2018-10-31T03:42:33.922Z",
      "updatedAt": "2019-01-05T02:11:31.489Z",
      "capacityNumber": 105
    }
  ],
  "total": 100
}
```

<h3 id="get-voters-who-voted-for-the-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateVoter](#schemacandidatevoter)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Masternode checking

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string/isMasternode \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string/isMasternode",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string/isMasternode"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string/isMasternode")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string/isMasternode", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string/isMasternode")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}/isMasternode`

<h3 id="masternode-checking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
"1"
```

<h3 id="masternode-checking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[isMasternode](#schemaismasternode)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Candidate checking

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string/isCandidate \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string/isCandidate",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string/isCandidate"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string/isCandidate")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string/isCandidate", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string/isCandidate")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}/isCandidate`

<h3 id="candidate-checking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|

> Example responses

> 200 Response

```json
"1"
```

<h3 id="candidate-checking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[isCandidate](#schemaiscandidate)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Owner checking

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string/string/isOwner \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string/string/isOwner",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string/string/isOwner"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string/string/isOwner")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string/string/isOwner", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string/string/isOwner")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}/{owner}/isOwner`

<h3 id="owner-checking-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|owner|path|string|true|owner's address|

> Example responses

> 200 Response

```json
"true"
```

<h3 id="owner-checking-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[isOwner](#schemaisowner)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get reward of candidate

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/string/string/getRewards \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/string/string/getRewards",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/string/string/getRewards"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/string/string/getRewards")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/string/string/getRewards", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/string/string/getRewards")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/{candidate}/{owner}/getRewards`

<h3 id="get-reward-of-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|owner|path|string|true|owner's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be9216",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "Voter",
      "lockBalance": "1000",
      "reward": "8.03540381764608993247",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.435Z",
      "updatedAt": "2018-12-18T23:36:31.435Z"
    }
  ],
  "total": 100
}
```

<h3 id="get-reward-of-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[candidateRewards](#schemacandidaterewards)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list of slashed masternodes

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/candidates/slashed/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/candidates/slashed/string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/candidates/slashed/string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/candidates/slashed/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/candidates/slashed/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/candidates/slashed/string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/candidates/slashed/{epoch}`

<h3 id="get-list-of-slashed-masternodes-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|epoch|path|string|true|epoch number|

> Example responses

> 200 Response

```json
{
  "items": {},
  "blockNumber": 3899700,
  "epoch": 4334,
  "networkId": 88
}
```

<h3 id="get-list-of-slashed-masternodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[slashedMasternodes](#schemaslashedmasternodes)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-voters">Voters</h1>

Get Voter information

## Get voted candidates

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/voters/string/candidates \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/voters/string/candidates",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/voters/string/candidates"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/voters/string/candidates")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/voters/string/candidates", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/voters/string/candidates")
  .header("accept", "application/json")
  .asString();
```

`GET /api/voters/{voter}/candidates`

<h3 id="get-voted-candidates-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|voter's address|
|limit|query|number|false|Number of record in a query|
|page|query|number|false|Page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000000000000000000",
      "capacityNumber": 10,
      "candidateName": "Earth"
    }
  ],
  "total": 100
}
```

<h3 id="get-voted-candidates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[voterCandidates](#schemavotercandidates)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get reward of voter

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/voters/string/rewards \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/voters/string/rewards",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/voters/string/rewards"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/voters/string/rewards")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/voters/string/rewards", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/voters/string/rewards")
  .header("accept", "application/json")
  .asString();
```

`GET /api/voters/{voter}/rewards`

<h3 id="get-reward-of-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|voter's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be922a",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "MasterNode",
      "lockBalance": "1000",
      "reward": "25.97042513863216266174",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.580Z",
      "updatedAt": "2018-12-18T23:36:31.580Z",
      "candidateName": "0x11621900588eca4410c00097a9f59237f34064cd"
    }
  ],
  "total": 100
}
```

<h3 id="get-reward-of-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[voterRewards](#schemavoterrewards)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get ROI of masternode and voter

> Code samples

```shell
curl --request GET \
  --url 'https://master.tomochain.com/api/voters/annualReward?candidate=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/voters/annualReward?candidate=string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/voters/annualReward?candidate=string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/voters/annualReward?candidate=string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/voters/annualReward?candidate=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/voters/annualReward?candidate=string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/voters/annualReward`

<h3 id="get-roi-of-masternode-and-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|query|string|true|candidate's address|

> Example responses

> 200 Response

```json
{
  "epochDuration": 30,
  "lastEpoch": 6945,
  "numberOfMN": 150,
  "capacity": 200000,
  "voterROI": 6,
  "mnROI": 29
}
```

<h3 id="get-roi-of-masternode-and-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[annualReward](#schemaannualreward)|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-transaction">Transaction</h1>

Get transactions of candidate and voter

## Get transactions of a candidate

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/transactions/candidate/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/transactions/candidate/string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/transactions/candidate/string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/transactions/candidate/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/transactions/candidate/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/transactions/candidate/string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/transactions/candidate/{candidate}`

<h3 id="get-transactions-of-a-candidate-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|candidate|path|string|true|candidate's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c247c545e769d2f2c10ab38",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0x0f96e419c89dcf1397a6206959334a4485c5a158a0320cb8a8e98db3b7888141",
      "event": "Vote",
      "voter": "0xe91dc9746eed1b5971aabd6e1681da1a4d06be8d",
      "owner": "",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "capacity": "11000000000000000000",
      "blockNumber": 2897395,
      "createdAt": "2018-12-27T07:16:36.000Z",
      "__v": 0
    }
  ],
  "total": 100
}
```

<h3 id="get-transactions-of-a-candidate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[txCandidate](#schematxcandidate)|

<aside class="success">
This operation does not require authentication
</aside>

## Get transactions of a voter

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/transactions/voter/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/transactions/voter/string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/transactions/voter/string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/transactions/voter/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/transactions/voter/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/transactions/voter/string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/transactions/voter/{voter}`

<h3 id="get-transactions-of-a-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|string|true|voter's address|
|limit|query|number|false|number of records|
|page|query|number|false|page number|

> Example responses

> 200 Response

```json
{
  "items": [
    {
      "_id": "5c24a189ff305840a2498bf0",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0xf8f2d402c6b1cb5f891b687d69ddcd920e58d9e9fe002857cac0e7ce47998884",
      "event": "Unvote",
      "voter": "0x487d62d33467c4842c5e54eb370837e4e88bba0f",
      "owner": "",
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000999000000000000000",
      "blockNumber": 763397,
      "createdAt": "2018-12-27T09:55:21.000Z",
      "__v": 0
    }
  ],
  "total": 100
}
```

<h3 id="get-transactions-of-a-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[txVoter](#schematxvoter)|

<aside class="success">
This operation does not require authentication
</aside>

## Get a transaction's detail

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/transactions/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/transactions/string",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/transactions/string"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/transactions/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/transactions/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/transactions/string")
  .header("accept", "application/json")
  .asString();
```

`GET /api/transactions/{tx}`

<h3 id="get-a-transaction's-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tx|path|string|true|Transaction|

> Example responses

> 200 Response

```json
{
  "_id": "5c52a4465f0abf3496da0e91",
  "tx": "0xdd03614f86982663b4c17eaaf9051b3df7a88fefc445df41921fa223c6178bf7",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "1715000000000000000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x7e0d154cba89190ce1801031cba9d46ad21eb317",
  "blockNumber": 1310702,
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "voter": "0x7e0d154cba89190ce1801031cba9d46ad21eb317",
  "candidate": "",
  "event": "Withdraw"
}
```

<h3 id="get-a-transaction's-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[transaction](#schematransaction)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomomaster-apis-signer">Signer</h1>

Get a list of signers

## Get a list of latest signers

> Code samples

```shell
curl --request GET \
  --url https://master.tomochain.com/api/signers/get/latest \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "master.tomochain.com",
  "port": null,
  "path": "/api/signers/get/latest",
  "headers": {
    "accept": "application/json"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://master.tomochain.com/api/signers/get/latest"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

```ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://master.tomochain.com/api/signers/get/latest")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("master.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/signers/get/latest", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://master.tomochain.com/api/signers/get/latest")
  .header("accept", "application/json")
  .asString();
```

`GET /api/signers/get/latest`

> Example responses

> 200 Response

```json
{
  "_id": "5c52a4465f0abf3496da0e91",
  "signers": [
    "0x98ffa09ae64a3ad63289ee0def385e6455b777e5",
    "0x6670fe10f076539459753b7aabc53fc218644042",
    "0x71ab3b4352084f13bedb15693cd6bb923a1b80a1"
  ],
  "__v": 0,
  "networkId": "1715000000000000000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "blockNumber": 1310702,
  "updatedAt": "2019-01-11T09:17:59.535Z"
}
```

<h3 id="get-a-list-of-latest-signers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[signers](#schemasigners)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_config">config</h2>
<!-- backwards compatibility -->
<a id="schemaconfig"></a>
<a id="schema_config"></a>
<a id="tocSconfig"></a>
<a id="tocsconfig"></a>

```json
{
  "blockchain": {
    "rpc": "string",
    "ws": "string",
    "epoch": 900,
    "blockTime": 0
  },
  "explorerUrl": "string",
  "GA": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|blockchain|object|false|none|Tomochain's configurations|
|» rpc|string|false|none|rpc|
|» ws|string|false|none|websocket|
|» epoch|number|false|none|Number of blocks for 1 epoch|
|» blockTime|number|false|none|Block time|
|explorerUrl|string|false|none|Tomoscan's API|
|GA|string|false|none|Google Analytic code|

<h2 id="tocS_candidate">candidate</h2>
<!-- backwards compatibility -->
<a id="schemacandidate"></a>
<a id="schema_candidate"></a>
<a id="tocScandidate"></a>
<a id="tocscandidate"></a>

```json
{
  "items": [
    {
      "_id": "123",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "91540333800000001000000",
      "createdAt": "2018-10-31T03:42:39.375Z",
      "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
      "status": "RESIGNED",
      "updatedAt": "2019-01-11T09:21:55.028Z",
      "latestSignedBlock": 2917487,
      "capacityNumber": 91540.33380000001,
      "isMasternode": false,
      "isPenalty": false
    }
  ],
  "total": 100,
  "activeCandidates": 10
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of candidate|
|activeCandidates|number|false|none|Number of active candidate|

<h2 id="tocS_candidateDetail">candidateDetail</h2>
<!-- backwards compatibility -->
<a id="schemacandidatedetail"></a>
<a id="schema_candidateDetail"></a>
<a id="tocScandidatedetail"></a>
<a id="tocscandidatedetail"></a>

```json
{
  "_id": "123",
  "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "91540333800000001000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x11621900588eca4410c00097a9f59237f34064cd",
  "status": "RESIGNED",
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "latestSignedBlock": "2917487",
  "capacityNumber": 91540.33380000001,
  "isMasternode": false,
  "isPenalty": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|false|none|id|
|candidate|string|false|none|candidate's address|
|smartContractAddress|string|false|none|smart contract's address|
|__v|number|false|none|__v|
|capacity|string|false|none|capacity in wei|
|createdAt|string|false|none|creation date of candidate|
|owner|string|false|none|owner's address|
|status|string|false|none|candidate's status|
|updatedAt|string|false|none|update time|
|latestSignedBlock|string|false|none|latest signed block|
|capacityNumber|number|false|none|capacity number|
|isMasternode|boolean|false|none|is masternode|
|isPenalty|boolean|false|none|is penalty|

<h2 id="tocS_candidateRewards">candidateRewards</h2>
<!-- backwards compatibility -->
<a id="schemacandidaterewards"></a>
<a id="schema_candidateRewards"></a>
<a id="tocScandidaterewards"></a>
<a id="tocscandidaterewards"></a>

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be9216",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "Voter",
      "lockBalance": "1000",
      "reward": "8.03540381764608993247",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.435Z",
      "updatedAt": "2018-12-18T23:36:31.435Z"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Number of candidate|

<h2 id="tocS_candidateVoter">candidateVoter</h2>
<!-- backwards compatibility -->
<a id="schemacandidatevoter"></a>
<a id="schema_candidateVoter"></a>
<a id="tocScandidatevoter"></a>
<a id="tocscandidatevoter"></a>

```json
{
  "items": [
    {
      "_id": "5bd924a9aa41b819395d9207",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "voter": "0xf2cce442c7ab5baf194838081b5f9396330ecfb8",
      "__v": 0,
      "capacity": "105000000000000000000",
      "createdAt": "2018-10-31T03:42:33.922Z",
      "updatedAt": "2019-01-05T02:11:31.489Z",
      "capacityNumber": 105
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of voters|

<h2 id="tocS_voterCandidates">voterCandidates</h2>
<!-- backwards compatibility -->
<a id="schemavotercandidates"></a>
<a id="schema_voterCandidates"></a>
<a id="tocSvotercandidates"></a>
<a id="tocsvotercandidates"></a>

```json
{
  "items": [
    {
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000000000000000000",
      "capacityNumber": 10,
      "candidateName": "Earth"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of rewards|

<h2 id="tocS_voterRewards">voterRewards</h2>
<!-- backwards compatibility -->
<a id="schemavoterrewards"></a>
<a id="schema_voterRewards"></a>
<a id="tocSvoterrewards"></a>
<a id="tocsvoterrewards"></a>

```json
{
  "items": [
    {
      "_id": "5c19847f0e77307940be922a",
      "epoch": 3193,
      "startBlock": 2872801,
      "endBlock": 2873700,
      "address": "0x11621900588eca4410c00097a9f59237f34064cd",
      "validator": "0x11621900588eca4410c00097a9f59237f34064cd",
      "reason": "MasterNode",
      "lockBalance": "1000",
      "reward": "25.97042513863216266174",
      "rewardTime": "2018-12-18T23:36:18.000Z",
      "signNumber": 843,
      "__v": 0,
      "createdAt": "2018-12-18T23:36:31.580Z",
      "updatedAt": "2018-12-18T23:36:31.580Z",
      "candidateName": "0x11621900588eca4410c00097a9f59237f34064cd"
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Voter's reward array|
|total|number|false|none|Number of candidate|

<h2 id="tocS_isMasternode">isMasternode</h2>
<!-- backwards compatibility -->
<a id="schemaismasternode"></a>
<a id="schema_isMasternode"></a>
<a id="tocSismasternode"></a>
<a id="tocsismasternode"></a>

```json
"1"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|0|

<h2 id="tocS_isCandidate">isCandidate</h2>
<!-- backwards compatibility -->
<a id="schemaiscandidate"></a>
<a id="schema_isCandidate"></a>
<a id="tocSiscandidate"></a>
<a id="tocsiscandidate"></a>

```json
"1"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|1|
|*anonymous*|0|

<h2 id="tocS_txCandidate">txCandidate</h2>
<!-- backwards compatibility -->
<a id="schematxcandidate"></a>
<a id="schema_txCandidate"></a>
<a id="tocStxcandidate"></a>
<a id="tocstxcandidate"></a>

```json
{
  "items": [
    {
      "_id": "5c247c545e769d2f2c10ab38",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0x0f96e419c89dcf1397a6206959334a4485c5a158a0320cb8a8e98db3b7888141",
      "event": "Vote",
      "voter": "0xe91dc9746eed1b5971aabd6e1681da1a4d06be8d",
      "owner": "",
      "candidate": "0x11621900588eca4410c00097a9f59237f34064cd",
      "capacity": "11000000000000000000",
      "blockNumber": 2897395,
      "createdAt": "2018-12-27T07:16:36.000Z",
      "__v": 0
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's transactions array|
|total|number|false|none|Number of candidate|

<h2 id="tocS_txVoter">txVoter</h2>
<!-- backwards compatibility -->
<a id="schematxvoter"></a>
<a id="schema_txVoter"></a>
<a id="tocStxvoter"></a>
<a id="tocstxvoter"></a>

```json
{
  "items": [
    {
      "_id": "5c24a189ff305840a2498bf0",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "tx": "0xf8f2d402c6b1cb5f891b687d69ddcd920e58d9e9fe002857cac0e7ce47998884",
      "event": "Unvote",
      "voter": "0x487d62d33467c4842c5e54eb370837e4e88bba0f",
      "owner": "",
      "candidate": "0xfc5571921c6d3672e13b58ea23dea534f2b35fa0",
      "capacity": "10000999000000000000000",
      "blockNumber": 763397,
      "createdAt": "2018-12-27T09:55:21.000Z",
      "__v": 0
    }
  ],
  "total": 100
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's transactions array|
|total|number|false|none|Number of candidate|

<h2 id="tocS_slashedMN">slashedMN</h2>
<!-- backwards compatibility -->
<a id="schemaslashedmn"></a>
<a id="schema_slashedMN"></a>
<a id="tocSslashedmn"></a>
<a id="tocsslashedmn"></a>

```json
{
  "items": [
    {
      "_id": "5c4006b47ff073e7961fabd5",
      "candidate": "0x1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "114213709385390179602070",
      "capacityNumber": 114213.70938539018,
      "createdAt": "2019-01-17T04:38:12.051Z",
      "nodeId": "1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "owner": "0xe60f54049759a11d764756ece4d27815e990d92f",
      "status": "SLASHED",
      "updatedAt": "2019-01-29T10:38:18.268Z",
      "latestSignedBlock": 1220265
    }
  ],
  "total": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of candidate|

<h2 id="tocS_proposedMN">proposedMN</h2>
<!-- backwards compatibility -->
<a id="schemaproposedmn"></a>
<a id="schema_proposedMN"></a>
<a id="tocSproposedmn"></a>
<a id="tocsproposedmn"></a>

```json
{
  "items": [
    {
      "_id": "5c4006b47ff073e7961fabd5",
      "candidate": "0x1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "114213709385390179602070",
      "capacityNumber": 114213.70938539018,
      "createdAt": "2019-01-17T04:38:12.051Z",
      "nodeId": "1c5a1cb41c920c2532cbb77be5845b258eca32f3",
      "owner": "0xe60f54049759a11d764756ece4d27815e990d92f",
      "status": "PROPOSED",
      "updatedAt": "2019-01-29T10:38:18.268Z",
      "latestSignedBlock": 1220265
    }
  ],
  "total": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of candidate|

<h2 id="tocS_resignedMN">resignedMN</h2>
<!-- backwards compatibility -->
<a id="schemaresignedmn"></a>
<a id="schema_resignedMN"></a>
<a id="tocSresignedmn"></a>
<a id="tocsresignedmn"></a>

```json
{
  "items": [
    {
      "_id": "5c4006b37ff073e7961fab14",
      "candidate": "0x7a3b86261cd2042a3190c81dd37d0a12e0397daf",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "40508760000000000000000",
      "capacityNumber": 40508.76,
      "createdAt": "2019-01-17T04:38:11.949Z",
      "nodeId": "7a3b86261cd2042a3190c81dd37d0a12e0397daf",
      "owner": "0xbff690303287ce327c319f575c7671c3ad626de4",
      "status": "RESIGNED",
      "updatedAt": "2019-01-29T10:11:19.464Z",
      "latestSignedBlock": 957442
    }
  ],
  "total": 1
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Candidate's data|
|total|number|false|none|Total number of candidate|

<h2 id="tocS_isOwner">isOwner</h2>
<!-- backwards compatibility -->
<a id="schemaisowner"></a>
<a id="schema_isOwner"></a>
<a id="tocSisowner"></a>
<a id="tocsisowner"></a>

```json
"true"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|true|
|*anonymous*|false|

<h2 id="tocS_transaction">transaction</h2>
<!-- backwards compatibility -->
<a id="schematransaction"></a>
<a id="schema_transaction"></a>
<a id="tocStransaction"></a>
<a id="tocstransaction"></a>

```json
{
  "_id": "5c52a4465f0abf3496da0e91",
  "tx": "0xdd03614f86982663b4c17eaaf9051b3df7a88fefc445df41921fa223c6178bf7",
  "smartContractAddress": "0x0000000000000000000000000000000000000088",
  "__v": 0,
  "capacity": "1715000000000000000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "owner": "0x7e0d154cba89190ce1801031cba9d46ad21eb317",
  "blockNumber": 1310702,
  "updatedAt": "2019-01-11T09:17:59.535Z",
  "voter": "0x7e0d154cba89190ce1801031cba9d46ad21eb317",
  "candidate": "",
  "event": "Withdraw"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|false|none|id|
|tx|string|false|none|transaction hash|
|smartContractAddress|string|false|none|smart contract's address|
|__v|number|false|none|__v|
|capacity|string|false|none|capacity in wei|
|createdAt|string|false|none|creation date of candidate|
|owner|string|false|none|owner's address|
|blockNumber|number|false|none|blockNumber|
|updatedAt|string|false|none|update time|
|voter|string|false|none|voter address|
|candidate|string|false|none|candidate address|
|event|string|false|none|event|

#### Enumerated Values

|Property|Value|
|---|---|
|event|Vote|
|event|Unvote|
|event|Withdraw|
|event|Propose|
|event|Resign|

<h2 id="tocS_signers">signers</h2>
<!-- backwards compatibility -->
<a id="schemasigners"></a>
<a id="schema_signers"></a>
<a id="tocSsigners"></a>
<a id="tocssigners"></a>

```json
{
  "_id": "5c52a4465f0abf3496da0e91",
  "signers": [
    "0x98ffa09ae64a3ad63289ee0def385e6455b777e5",
    "0x6670fe10f076539459753b7aabc53fc218644042",
    "0x71ab3b4352084f13bedb15693cd6bb923a1b80a1"
  ],
  "__v": 0,
  "networkId": "1715000000000000000000",
  "createdAt": "2018-10-31T03:42:39.375Z",
  "blockNumber": 1310702,
  "updatedAt": "2019-01-11T09:17:59.535Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|false|none|id|
|signers|[string]|false|none|List of latest signers|
|__v|number|false|none|__v|
|networkId|string|false|none|capacity in wei|
|createdAt|string|false|none|creation date of candidate|
|blockNumber|number|false|none|blockNumber|
|updatedAt|string|false|none|update time|

<h2 id="tocS_masternode">masternode</h2>
<!-- backwards compatibility -->
<a id="schemamasternode"></a>
<a id="schema_masternode"></a>
<a id="tocSmasternode"></a>
<a id="tocsmasternode"></a>

```json
{
  "items": [
    {
      "_id": "5c52a0df5f0abf3496d9a38f",
      "candidate": "0x1d50df657b6dce50bac634bf18e2d986d807e940",
      "smartContractAddress": "0x0000000000000000000000000000000000000088",
      "__v": 0,
      "capacity": "574962709628904011242293",
      "capacityNumber": 574962.709628904,
      "createdAt": "2019-01-31T07:16:47.833Z",
      "nodeId": "1d50df657b6dce50bac634bf18e2d986d807e940",
      "owner": "0x300d18c65563d0c9021d7722dd1aab74b9cc447f",
      "status": "MASTERNODE",
      "updatedAt": "2019-04-11T02:56:39.928Z",
      "latestSignedBlock": 3899535,
      "name": "GNBA.GE",
      "rank": 1
    }
  ],
  "activeCandidates": 150,
  "totalSlashed": 1,
  "totalResigned": 53,
  "totalProposed": 10
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|[object]|false|none|Masternode's data|
|activeCandidates|number|false|none|Total number of active masternode(status = 'MASTERNODE')|
|totalSlashed|number|false|none|Number of slashed masternode|
|totalResigned|number|false|none|Number of resigned masternode|
|totalProposed|number|false|none|Number of proposed masternode|

<h2 id="tocS_slashedMasternodes">slashedMasternodes</h2>
<!-- backwards compatibility -->
<a id="schemaslashedmasternodes"></a>
<a id="schema_slashedMasternodes"></a>
<a id="tocSslashedmasternodes"></a>
<a id="tocsslashedmasternodes"></a>

```json
{
  "items": {},
  "blockNumber": 3899700,
  "epoch": 4334,
  "networkId": 88
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|items|object|false|none|Masternode's data|
|blockNumber|number|false|none|Blocknumber slashed|
|epoch|number|false|none|epoch slashed|
|networkId|number|false|none|Network id|

<h2 id="tocS_annualReward">annualReward</h2>
<!-- backwards compatibility -->
<a id="schemaannualreward"></a>
<a id="schema_annualReward"></a>
<a id="tocSannualreward"></a>
<a id="tocsannualreward"></a>

```json
{
  "epochDuration": 30,
  "lastEpoch": 6945,
  "numberOfMN": 150,
  "capacity": 200000,
  "voterROI": 6,
  "mnROI": 29
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|epochDuration|number|false|none|Epoch duration in minutes|
|lastEpoch|number|false|none|Last epoch|
|numberOfMN|number|false|none|Masternode numbers|
|capacity|string|false|none|Masternode capacity|
|voterROI|number|false|none|Voter ROI|
|mnROI|number|false|none|Masternode ROI|

