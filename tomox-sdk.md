
<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tomodex-apis">TomoDex APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

TomoDex API Document

Base URLs:

* <a href="https://dex.tomochain.com/api">https://dex.tomochain.com/api</a>

* <a href="http://dex.tomochain.com/api">http://dex.tomochain.com/api</a>

<h1 id="tomodex-apis-accounts">accounts</h1>

Account endpoints

## Find account by user address

<a id="opIdhandleGetAccount"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/account/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/account/string",
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

	url := "https://dex.tomochain.com/api/account/string"

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

url = URI("https://dex.tomochain.com/api/account/string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/account/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/account/string")
  .header("accept", "application/json")
  .asString();
```

`GET /account/{userAddress}`

Returns a single account

<h3 id="find-account-by-user-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|path|string|true|Address of user to return|

> Example responses

> 200 Response

```json
{
  "address": "0xF7349C253FF7747Df661296E0859c44e974fb52E"
}
```

<h3 id="find-account-by-user-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Account](#schemaaccount)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## [Deprecated] Find account's token balance by user address and token address

<a id="opIdhandleGetAccountTokenBalance"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/account/string/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/account/string/string",
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

	url := "https://dex.tomochain.com/api/account/string/string"

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

url = URI("https://dex.tomochain.com/api/account/string/string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/account/string/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/account/string/string")
  .header("accept", "application/json")
  .asString();
```

`GET /account/{userAddress}/{tokenAddress}`

Returns an object contains token balance of user

<h3 id="[deprecated]-find-account's-token-balance-by-user-address-and-token-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|path|string|true|Address of user to find token balance|
|tokenAddress|path|string|true|Address of token|

> Example responses

> 200 Response

```json
{
  "address": "string",
  "symbol": "string",
  "balance": "string",
  "availableBalance": "string",
  "inOrderBalance": "string"
}
```

<h3 id="[deprecated]-find-account's-token-balance-by-user-address-and-token-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[TokenBalance](#schematokenbalance)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Account not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-tokens">tokens</h1>

Token endpoints

## Finds all tokens

<a id="opIdHandleGetTokens"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/tokens \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/tokens",
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

	url := "https://dex.tomochain.com/api/tokens"

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

url = URI("https://dex.tomochain.com/api/tokens")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/tokens", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/tokens")
  .header("accept", "application/json")
  .asString();
```

`GET /tokens`

Return all tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z"
  }
]
```

<h3 id="finds-all-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new token

<a id="opIdHandleCreateToken"></a>

> Code samples

```shell
curl --request POST \
  --url https://dex.tomochain.com/api/tokens \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"name":"string","symbol":"string","address":"string","image":{"url":"string","meta":{}},"contractAddress":"string","active":true,"quote":true,"makeFee":"string","takeFee":"string"}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/tokens",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({
  name: 'string',
  symbol: 'string',
  address: 'string',
  image: {url: 'string', meta: {}},
  contractAddress: 'string',
  active: true,
  quote: true,
  makeFee: 'string',
  takeFee: 'string'
}));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://dex.tomochain.com/api/tokens"

	payload := strings.NewReader("{\"name\":\"string\",\"symbol\":\"string\",\"address\":\"string\",\"image\":{\"url\":\"string\",\"meta\":{}},\"contractAddress\":\"string\",\"active\":true,\"quote\":true,\"makeFee\":\"string\",\"takeFee\":\"string\"}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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

url = URI("https://dex.tomochain.com/api/tokens")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["accept"] = 'application/json'
request.body = "{\"name\":\"string\",\"symbol\":\"string\",\"address\":\"string\",\"image\":{\"url\":\"string\",\"meta\":{}},\"contractAddress\":\"string\",\"active\":true,\"quote\":true,\"makeFee\":\"string\",\"takeFee\":\"string\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

payload = "{\"name\":\"string\",\"symbol\":\"string\",\"address\":\"string\",\"image\":{\"url\":\"string\",\"meta\":{}},\"contractAddress\":\"string\",\"active\":true,\"quote\":true,\"makeFee\":\"string\",\"takeFee\":\"string\"}"

headers = {
    'content-type': "application/json",
    'accept': "application/json"
    }

conn.request("POST", "/api/tokens", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://dex.tomochain.com/api/tokens")
  .header("content-type", "application/json")
  .header("accept", "application/json")
  .body("{\"name\":\"string\",\"symbol\":\"string\",\"address\":\"string\",\"image\":{\"url\":\"string\",\"meta\":{}},\"contractAddress\":\"string\",\"active\":true,\"quote\":true,\"makeFee\":\"string\",\"takeFee\":\"string\"}")
  .asString();
```

`POST /tokens`

Returns newly created token

> Body parameter

```json
{
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "active": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string"
}
```

<h3 id="create-new-token-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Token](#schematoken)|true|Token object that needs to be added|
|» id|body|string|false|none|
|» name|body|string|false|none|
|» symbol|body|string|false|none|
|» address|body|string|false|none|
|» image|body|[Image](#schemaimage)|false|none|
|»» url|body|string|false|none|
|»» meta|body|object|false|none|
|» contractAddress|body|string|false|none|
|» decimals|body|integer(int32)|false|none|
|» active|body|boolean|false|none|
|» listed|body|boolean|false|none|
|» quote|body|boolean|false|none|
|» makeFee|body|string|false|none|
|» takeFee|body|string|false|none|
|» usd|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="create-new-token-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Token](#schematoken)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Finds all base tokens

<a id="opIdHandleGetBaseTokens"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/tokens/base \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/tokens/base",
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

	url := "https://dex.tomochain.com/api/tokens/base"

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

url = URI("https://dex.tomochain.com/api/tokens/base")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/tokens/base", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/tokens/base")
  .header("accept", "application/json")
  .asString();
```

`GET /tokens/base`

Return all base tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z"
  }
]
```

<h3 id="finds-all-base-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-base-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Finds all quote tokens

<a id="opIdHandleGetQuoteTokens"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/tokens/quote \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/tokens/quote",
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

	url := "https://dex.tomochain.com/api/tokens/quote"

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

url = URI("https://dex.tomochain.com/api/tokens/quote")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/tokens/quote", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/tokens/quote")
  .header("accept", "application/json")
  .asString();
```

`GET /tokens/quote`

Return all quote tokens in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "name": "string",
    "symbol": "string",
    "address": "string",
    "image": {
      "url": "string",
      "meta": {}
    },
    "contractAddress": "string",
    "decimals": 0,
    "active": true,
    "listed": true,
    "quote": true,
    "makeFee": "string",
    "takeFee": "string",
    "usd": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z"
  }
]
```

<h3 id="finds-all-quote-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-quote-tokens-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Token](#schematoken)]|false|none|none|
|» id|string|false|read-only|none|
|» name|string|false|none|none|
|» symbol|string|false|none|none|
|» address|string|false|none|none|
|» image|[Image](#schemaimage)|false|none|none|
|»» url|string|false|none|none|
|»» meta|object|false|none|none|
|» contractAddress|string|false|none|none|
|» decimals|integer(int32)|false|read-only|none|
|» active|boolean|false|none|none|
|» listed|boolean|false|read-only|none|
|» quote|boolean|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» usd|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the token information corresponding to an address

<a id="opIdHandleGetToken"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/tokens/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/tokens/string",
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

	url := "https://dex.tomochain.com/api/tokens/string"

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

url = URI("https://dex.tomochain.com/api/tokens/string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/tokens/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/tokens/string")
  .header("accept", "application/json")
  .asString();
```

`GET /tokens/{address}`

Return token object

<h3 id="retrieve-the-token-information-corresponding-to-an-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|string|true|Token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="retrieve-the-token-information-corresponding-to-an-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Token](#schematoken)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid Address|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-pairs">pairs</h1>

Pair endpoints

## Finds all pairs

<a id="opIdHandleGetPairs"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/pairs \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/pairs",
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

	url := "https://dex.tomochain.com/api/pairs"

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

url = URI("https://dex.tomochain.com/api/pairs")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/pairs", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/pairs")
  .header("accept", "application/json")
  .asString();
```

`GET /pairs`

Return all pairs in an array

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "baseTokenSymbol": "string",
    "baseTokenAddress": "string",
    "baseTokenDecimals": 0,
    "quoteTokenSymbol": "string",
    "quoteTokenAddress": "string",
    "quoteTokenDecimals": 0,
    "listed": true,
    "active": true,
    "rank": 0,
    "makeFee": "string",
    "takeFee": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z"
  }
]
```

<h3 id="finds-all-pairs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="finds-all-pairs-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pair](#schemapair)]|false|none|none|
|» id|string|false|read-only|none|
|» baseTokenSymbol|string|false|none|none|
|» baseTokenAddress|string|false|none|none|
|» baseTokenDecimals|integer(int32)|false|read-only|none|
|» quoteTokenSymbol|string|false|none|none|
|» quoteTokenAddress|string|false|none|none|
|» quoteTokenDecimals|integer(int32)|false|read-only|none|
|» listed|boolean|false|read-only|none|
|» active|boolean|false|none|none|
|» rank|integer(int32)|false|read-only|none|
|» makeFee|string|false|read-only|none|
|» takeFee|string|false|read-only|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new pair

<a id="opIdHandleCreatePair"></a>

> Code samples

```shell
curl --request POST \
  --url https://dex.tomochain.com/api/pairs \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"baseTokenSymbol":"string","baseTokenAddress":"string","quoteTokenSymbol":"string","quoteTokenAddress":"string","active":true}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/pairs",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({
  baseTokenSymbol: 'string',
  baseTokenAddress: 'string',
  quoteTokenSymbol: 'string',
  quoteTokenAddress: 'string',
  active: true
}));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://dex.tomochain.com/api/pairs"

	payload := strings.NewReader("{\"baseTokenSymbol\":\"string\",\"baseTokenAddress\":\"string\",\"quoteTokenSymbol\":\"string\",\"quoteTokenAddress\":\"string\",\"active\":true}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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

url = URI("https://dex.tomochain.com/api/pairs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["accept"] = 'application/json'
request.body = "{\"baseTokenSymbol\":\"string\",\"baseTokenAddress\":\"string\",\"quoteTokenSymbol\":\"string\",\"quoteTokenAddress\":\"string\",\"active\":true}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

payload = "{\"baseTokenSymbol\":\"string\",\"baseTokenAddress\":\"string\",\"quoteTokenSymbol\":\"string\",\"quoteTokenAddress\":\"string\",\"active\":true}"

headers = {
    'content-type': "application/json",
    'accept': "application/json"
    }

conn.request("POST", "/api/pairs", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://dex.tomochain.com/api/pairs")
  .header("content-type", "application/json")
  .header("accept", "application/json")
  .body("{\"baseTokenSymbol\":\"string\",\"baseTokenAddress\":\"string\",\"quoteTokenSymbol\":\"string\",\"quoteTokenAddress\":\"string\",\"active\":true}")
  .asString();
```

`POST /pairs`

Returns newly created pair

> Body parameter

```json
{
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "active": true
}
```

<h3 id="create-new-pair-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pair](#schemapair)|true|Pair object that needs to be added|
|» id|body|string|false|none|
|» baseTokenSymbol|body|string|false|none|
|» baseTokenAddress|body|string|false|none|
|» baseTokenDecimals|body|integer(int32)|false|none|
|» quoteTokenSymbol|body|string|false|none|
|» quoteTokenAddress|body|string|false|none|
|» quoteTokenDecimals|body|integer(int32)|false|none|
|» listed|body|boolean|false|none|
|» active|body|boolean|false|none|
|» rank|body|integer(int32)|false|none|
|» makeFee|body|string|false|none|
|» takeFee|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="create-new-pair-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the pair information corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetPair"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/pair?baseToken=string&quoteToken=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/pair?baseToken=string&quoteToken=string",
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

	url := "https://dex.tomochain.com/api/pair?baseToken=string&quoteToken=string"

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

url = URI("https://dex.tomochain.com/api/pair?baseToken=string&quoteToken=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/pair?baseToken=string&quoteToken=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/pair?baseToken=string&quoteToken=string")
  .header("accept", "application/json")
  .asString();
```

`GET /pair`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-pair-information-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="retrieve-the-pair-information-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve pair data corresponding to a baseToken and quoteToken

<a id="opIdHandleGetPairData"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/pair/data?baseToken=string&quoteToken=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/pair/data?baseToken=string&quoteToken=string",
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

	url := "https://dex.tomochain.com/api/pair/data?baseToken=string&quoteToken=string"

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

url = URI("https://dex.tomochain.com/api/pair/data?baseToken=string&quoteToken=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/pair/data?baseToken=string&quoteToken=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/pair/data?baseToken=string&quoteToken=string")
  .header("accept", "application/json")
  .asString();
```

`GET /pair/data`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-pair-data-corresponding-to-a-basetoken-and-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-pair-data-corresponding-to-a-basetoken-and-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all pair data

<a id="opIdHandleGetPairsData"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/pairs/data \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/pairs/data",
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

	url := "https://dex.tomochain.com/api/pairs/data"

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

url = URI("https://dex.tomochain.com/api/pairs/data")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/pairs/data", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/pairs/data")
  .header("accept", "application/json")
  .asString();
```

`GET /pairs/data`

Multiple status values can be provided with comma separated strings

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-all-pair-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-orders">orders</h1>

Order endpoints

## Retrieve the sorted list of orders for an Ethereum address

<a id="opIdhandleGetOrders"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/orders \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders",
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

	url := "https://dex.tomochain.com/api/orders"

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

url = URI("https://dex.tomochain.com/api/orders")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders")
  .header("accept", "application/json")
  .asString();
```

`GET /orders`

Return all orders in an array

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|false|User address|
|pageOffset|query|string|false|Page offset|
|pageSize|query|string|false|Number of items per a page|
|sortBy|query|string|false|Sort for query (time, orderStatus, orderType, orderSide)|
|sortType|query|string|false|asc/dec|
|orderStatus|query|string|false|OPEN/CANCELLED/FILLED/PARTIAL_FILLED|
|orderSide|query|string|false|SELL/BUY|
|orderType|query|string|false|LO/MO|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|hash|query|string|false|hash of order|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z",
      "orderID": "string"
    }
  ]
}
```

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-sorted-list-of-orders-for-an-ethereum-address-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» orders|[[Order](#schemaorder)]|false|none|none|
|»» id|string|false|read-only|none|
|»» userAddress|string|false|none|none|
|»» exchangeAddress|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» status|string|false|none|none|
|»» side|string|false|none|none|
|»» type|string|false|none|none|
|»» hash|string|false|none|none|
|»» signature|[Signature](#schemasignature)|false|none|none|
|»»» V|string|false|none|none|
|»»» R|string|false|none|none|
|»»» S|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» filledAmount|string|false|none|none|
|»» nonce|string|false|none|none|
|»» makeFee|string|false|none|none|
|»» takeFee|string|false|none|none|
|»» pairName|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|
|»» orderID|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Create new order

<a id="opIdHandleNewOrder"></a>

> Code samples

```shell
curl --request POST \
  --url https://dex.tomochain.com/api/orders \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"userAddress":"0x15e08dE16f534c890828F2a0D935433aF5B3CE0C","exchangeAddress":"0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e","baseToken":"0x4d7eA2cE949216D6b120f3AA10164173615A2b6C","quoteToken":"0x0000000000000000000000000000000000000001","side":"SELL/BUY","type":"LO/MO","status":"NEW/CANCELLED","hash":"string","signature":{"V":"string","R":"string","S":"string"},"pricepoint":"21207020000000000000000","amount":"4693386710283129","nonce":"1","makeFee":"1","takeFee":"1"}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({
  userAddress: '0x15e08dE16f534c890828F2a0D935433aF5B3CE0C',
  exchangeAddress: '0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e',
  baseToken: '0x4d7eA2cE949216D6b120f3AA10164173615A2b6C',
  quoteToken: '0x0000000000000000000000000000000000000001',
  side: 'SELL/BUY',
  type: 'LO/MO',
  status: 'NEW/CANCELLED',
  hash: 'string',
  signature: {V: 'string', R: 'string', S: 'string'},
  pricepoint: '21207020000000000000000',
  amount: '4693386710283129',
  nonce: '1',
  makeFee: '1',
  takeFee: '1'
}));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://dex.tomochain.com/api/orders"

	payload := strings.NewReader("{\"userAddress\":\"0x15e08dE16f534c890828F2a0D935433aF5B3CE0C\",\"exchangeAddress\":\"0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e\",\"baseToken\":\"0x4d7eA2cE949216D6b120f3AA10164173615A2b6C\",\"quoteToken\":\"0x0000000000000000000000000000000000000001\",\"side\":\"SELL/BUY\",\"type\":\"LO/MO\",\"status\":\"NEW/CANCELLED\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"},\"pricepoint\":\"21207020000000000000000\",\"amount\":\"4693386710283129\",\"nonce\":\"1\",\"makeFee\":\"1\",\"takeFee\":\"1\"}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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

url = URI("https://dex.tomochain.com/api/orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["accept"] = 'application/json'
request.body = "{\"userAddress\":\"0x15e08dE16f534c890828F2a0D935433aF5B3CE0C\",\"exchangeAddress\":\"0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e\",\"baseToken\":\"0x4d7eA2cE949216D6b120f3AA10164173615A2b6C\",\"quoteToken\":\"0x0000000000000000000000000000000000000001\",\"side\":\"SELL/BUY\",\"type\":\"LO/MO\",\"status\":\"NEW/CANCELLED\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"},\"pricepoint\":\"21207020000000000000000\",\"amount\":\"4693386710283129\",\"nonce\":\"1\",\"makeFee\":\"1\",\"takeFee\":\"1\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

payload = "{\"userAddress\":\"0x15e08dE16f534c890828F2a0D935433aF5B3CE0C\",\"exchangeAddress\":\"0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e\",\"baseToken\":\"0x4d7eA2cE949216D6b120f3AA10164173615A2b6C\",\"quoteToken\":\"0x0000000000000000000000000000000000000001\",\"side\":\"SELL/BUY\",\"type\":\"LO/MO\",\"status\":\"NEW/CANCELLED\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"},\"pricepoint\":\"21207020000000000000000\",\"amount\":\"4693386710283129\",\"nonce\":\"1\",\"makeFee\":\"1\",\"takeFee\":\"1\"}"

headers = {
    'content-type': "application/json",
    'accept': "application/json"
    }

conn.request("POST", "/api/orders", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://dex.tomochain.com/api/orders")
  .header("content-type", "application/json")
  .header("accept", "application/json")
  .body("{\"userAddress\":\"0x15e08dE16f534c890828F2a0D935433aF5B3CE0C\",\"exchangeAddress\":\"0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e\",\"baseToken\":\"0x4d7eA2cE949216D6b120f3AA10164173615A2b6C\",\"quoteToken\":\"0x0000000000000000000000000000000000000001\",\"side\":\"SELL/BUY\",\"type\":\"LO/MO\",\"status\":\"NEW/CANCELLED\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"},\"pricepoint\":\"21207020000000000000000\",\"amount\":\"4693386710283129\",\"nonce\":\"1\",\"makeFee\":\"1\",\"takeFee\":\"1\"}")
  .asString();
```

`POST /orders`

Returns newly created order

> Body parameter

```json
{
  "userAddress": "0x15e08dE16f534c890828F2a0D935433aF5B3CE0C",
  "exchangeAddress": "0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e",
  "baseToken": "0x4d7eA2cE949216D6b120f3AA10164173615A2b6C",
  "quoteToken": "0x0000000000000000000000000000000000000001",
  "side": "SELL/BUY",
  "type": "LO/MO",
  "status": "NEW/CANCELLED",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "21207020000000000000000",
  "amount": "4693386710283129",
  "nonce": "1",
  "makeFee": "1",
  "takeFee": "1"
}
```

<h3 id="create-new-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCreate](#schemaordercreate)|true|Order object that needs to be added|

> Example responses

> 201 Response

```json
{
  "id": "string",
  "userAddress": "string",
  "exchangeAddress": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "status": "string",
  "side": "string",
  "type": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "string",
  "amount": "string",
  "filledAmount": "string",
  "nonce": "string",
  "makeFee": "string",
  "takeFee": "string",
  "pairName": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z",
  "orderID": "string"
}
```

<h3 id="create-new-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Account is blocked|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## [Deprecated] Retrieve the list of positions for an Ethereum address. Positions are order that have been sent to the matching engine and that are waiting to be matched

<a id="opIdhandleGetPositions"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orders/positions?address=string&limit=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/positions?address=string&limit=string",
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

	url := "https://dex.tomochain.com/api/orders/positions?address=string&limit=string"

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

url = URI("https://dex.tomochain.com/api/orders/positions?address=string&limit=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders/positions?address=string&limit=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders/positions?address=string&limit=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orders/positions`

Return all orders in an array

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|limit|query|string|true|Number of orders returned in query|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "userAddress": "string",
    "exchangeAddress": "string",
    "baseToken": "string",
    "quoteToken": "string",
    "status": "string",
    "side": "string",
    "type": "string",
    "hash": "string",
    "signature": {
      "V": "string",
      "R": "string",
      "S": "string"
    },
    "pricepoint": "string",
    "amount": "string",
    "filledAmount": "string",
    "nonce": "string",
    "makeFee": "string",
    "takeFee": "string",
    "pairName": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z",
    "orderID": "string"
  }
]
```

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="[deprecated]-retrieve-the-list-of-positions-for-an-ethereum-address.-positions-are-order-that-have-been-sent-to-the-matching-engine-and-that-are-waiting-to-be-matched-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Order](#schemaorder)]|false|none|none|
|» id|string|false|read-only|none|
|» userAddress|string|false|none|none|
|» exchangeAddress|string|false|none|none|
|» baseToken|string|false|none|none|
|» quoteToken|string|false|none|none|
|» status|string|false|none|none|
|» side|string|false|none|none|
|» type|string|false|none|none|
|» hash|string|false|none|none|
|» signature|[Signature](#schemasignature)|false|none|none|
|»» V|string|false|none|none|
|»» R|string|false|none|none|
|»» S|string|false|none|none|
|» pricepoint|string|false|none|none|
|» amount|string|false|none|none|
|» filledAmount|string|false|none|none|
|» nonce|string|false|none|none|
|» makeFee|string|false|none|none|
|» takeFee|string|false|none|none|
|» pairName|string|false|none|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|
|» orderID|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the list of filled order for an Ethereum address

<a id="opIdhandleGetOrderHistory"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orders/history?address=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/history?address=string",
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

	url := "https://dex.tomochain.com/api/orders/history?address=string"

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

url = URI("https://dex.tomochain.com/api/orders/history?address=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders/history?address=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders/history?address=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orders/history`

Return all orders in an array

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|pageOffset|query|string|false|Page offset, default 0|
|pageSize|query|string|false|Number of items per a page, defaul 50|
|sortBy|query|string|false|Sort for query (time(default), orderStatus, orderType, orderSide)|
|sortType|query|string|false|asc/dec, default asc|
|orderStatus|query|string|false|OPEN/CANCELLED/FILLED/PARTIAL_FILLED|
|orderSide|query|string|false|SELL/BUY|
|orderType|query|string|false|LO/MO|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z",
      "orderID": "string"
    }
  ]
}
```

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-list-of-filled-order-for-an-ethereum-address-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» orders|[[Order](#schemaorder)]|false|none|none|
|»» id|string|false|read-only|none|
|»» userAddress|string|false|none|none|
|»» exchangeAddress|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» status|string|false|none|none|
|»» side|string|false|none|none|
|»» type|string|false|none|none|
|»» hash|string|false|none|none|
|»» signature|[Signature](#schemasignature)|false|none|none|
|»»» V|string|false|none|none|
|»»» R|string|false|none|none|
|»»» S|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» filledAmount|string|false|none|none|
|»» nonce|string|false|none|none|
|»» makeFee|string|false|none|none|
|»» takeFee|string|false|none|none|
|»» pairName|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|
|»» orderID|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the total number of orders for an Ethereum address

<a id="opIdhandleGetCountOrder"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orders/count?address=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/count?address=string",
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

	url := "https://dex.tomochain.com/api/orders/count?address=string"

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

url = URI("https://dex.tomochain.com/api/orders/count?address=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders/count?address=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders/count?address=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orders/count`

Return a positive integer

<h3 id="retrieve-the-total-number-of-orders-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
0
```

<h3 id="retrieve-the-total-number-of-orders-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|integer|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve order nonce for an Ethereum address

<a id="opIdhandleGetOrderNonce"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orders/nonce?address=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/nonce?address=string",
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

	url := "https://dex.tomochain.com/api/orders/nonce?address=string"

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

url = URI("https://dex.tomochain.com/api/orders/nonce?address=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders/nonce?address=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders/nonce?address=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orders/nonce`

Return a positive integer

<h3 id="retrieve-order-nonce-for-an-ethereum-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
0
```

<h3 id="retrieve-order-nonce-for-an-ethereum-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|integer|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Cancel order

<a id="opIdHandleCancelOrder"></a>

> Code samples

```shell
curl --request POST \
  --url https://dex.tomochain.com/api/orders/cancel \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"orderHash":"string","nonce":"string","hash":"string","signature":{"V":"string","R":"string","S":"string"}}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/cancel",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({
  orderHash: 'string',
  nonce: 'string',
  hash: 'string',
  signature: {V: 'string', R: 'string', S: 'string'}
}));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://dex.tomochain.com/api/orders/cancel"

	payload := strings.NewReader("{\"orderHash\":\"string\",\"nonce\":\"string\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"}}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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

url = URI("https://dex.tomochain.com/api/orders/cancel")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["accept"] = 'application/json'
request.body = "{\"orderHash\":\"string\",\"nonce\":\"string\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"}}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

payload = "{\"orderHash\":\"string\",\"nonce\":\"string\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"}}"

headers = {
    'content-type': "application/json",
    'accept': "application/json"
    }

conn.request("POST", "/api/orders/cancel", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://dex.tomochain.com/api/orders/cancel")
  .header("content-type", "application/json")
  .header("accept", "application/json")
  .body("{\"orderHash\":\"string\",\"nonce\":\"string\",\"hash\":\"string\",\"signature\":{\"V\":\"string\",\"R\":\"string\",\"S\":\"string\"}}")
  .asString();
```

`POST /orders/cancel`

Returns the hash of cancelled order

> Body parameter

```json
{
  "orderHash": "string",
  "nonce": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  }
}
```

<h3 id="cancel-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[OrderCancel](#schemaordercancel)|true|Cancel order object|
|» orderHash|body|string|false|none|
|» nonce|body|string|false|none|
|» hash|body|string|false|none|
|» signature|body|[Signature](#schemasignature)|false|none|
|»» V|body|string|false|none|
|»» R|body|string|false|none|
|»» S|body|string|false|none|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="cancel-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## [Deprecated] Cancel all orders

<a id="opIdhandleCancelAllOrders"></a>

> Code samples

```shell
curl --request POST \
  --url 'https://dex.tomochain.com/api/orders/cancelAll?address=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/cancelAll?address=string",
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

	url := "https://dex.tomochain.com/api/orders/cancelAll?address=string"

	req, _ := http.NewRequest("POST", url, nil)

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

url = URI("https://dex.tomochain.com/api/orders/cancelAll?address=string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["accept"] = 'application/json'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("POST", "/api/orders/cancelAll?address=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://dex.tomochain.com/api/orders/cancelAll?address=string")
  .header("accept", "application/json")
  .asString();
```

`POST /orders/cancelAll`

This endpoint should implements signature authentication

<h3 id="[deprecated]-cancel-all-orders-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="[deprecated]-cancel-all-orders-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the order information corresponding to an order hash

<a id="opIdHandleOrderByHash"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/orders/string \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orders/string",
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

	url := "https://dex.tomochain.com/api/orders/string"

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

url = URI("https://dex.tomochain.com/api/orders/string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orders/string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orders/string")
  .header("accept", "application/json")
  .asString();
```

`GET /orders/{hash}`

Return order object

<h3 id="retrieve-the-order-information-corresponding-to-an-order-hash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|order hash|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "userAddress": "string",
  "exchangeAddress": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "status": "string",
  "side": "string",
  "type": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "string",
  "amount": "string",
  "filledAmount": "string",
  "nonce": "string",
  "makeFee": "string",
  "takeFee": "string",
  "pairName": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z",
  "orderID": "string"
}
```

<h3 id="retrieve-the-order-information-corresponding-to-an-order-hash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid order hash|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-orderbook">orderbook</h1>

Order book endpoints

## Retrieve the orderbook (amount and pricepoint) corresponding to a a baseToken and a quoteToken

<a id="opIdHandleGetOrderBook"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orderbook?baseToken=string&quoteToken=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orderbook?baseToken=string&quoteToken=string",
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

	url := "https://dex.tomochain.com/api/orderbook?baseToken=string&quoteToken=string"

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

url = URI("https://dex.tomochain.com/api/orderbook?baseToken=string&quoteToken=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orderbook?baseToken=string&quoteToken=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orderbook?baseToken=string&quoteToken=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orderbook`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pairName": "string",
  "asks": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ],
  "bids": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ]
}
```

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[OrderBook](#schemaorderbook)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the orderbook (full raw orders, including fields such as hashes, maker, taker addresses, signatures, etc.)
corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetRawOrderBook"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/orderbook/raw?baseToken=string&quoteToken=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/orderbook/raw?baseToken=string&quoteToken=string",
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

	url := "https://dex.tomochain.com/api/orderbook/raw?baseToken=string&quoteToken=string"

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

url = URI("https://dex.tomochain.com/api/orderbook/raw?baseToken=string&quoteToken=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/orderbook/raw?baseToken=string&quoteToken=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/orderbook/raw?baseToken=string&quoteToken=string")
  .header("accept", "application/json")
  .asString();
```

`GET /orderbook/raw`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-the-orderbook-(full-raw-orders,-including-fields-such-as-hashes,-maker,-taker-addresses,-signatures,-etc.)
corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "pairName": "string",
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z",
      "orderID": "string"
    }
  ]
}
```

<h3 id="retrieve-the-orderbook-(full-raw-orders,-including-fields-such-as-hashes,-maker,-taker-addresses,-signatures,-etc.)
corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[RawOrderBook](#schemaraworderbook)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the orderbook (amount and pricepoint) corresponding to a lendingToken and a term

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/lending/orderbook?lendingToken=string&term=string'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/lending/orderbook?lendingToken=string&term=string",
  "headers": {}
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

	url := "https://dex.tomochain.com/api/lending/orderbook?lendingToken=string&term=string"

	req, _ := http.NewRequest("GET", url, nil)

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

url = URI("https://dex.tomochain.com/api/lending/orderbook?lendingToken=string&term=string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

conn.request("GET", "/api/lending/orderbook?lendingToken=string&term=string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/lending/orderbook?lendingToken=string&term=string")
  .asString();
```

`GET /lending/orderbook`

Retrieve the orderbook (amount and pricepoint) corresponding to a lendingToken and a term

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-lendingtoken-and-a-term-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|lendingToken|query|string|true|lending token address|
|term|query|string|true|term (e.g 86400 seconds)|

<h3 id="retrieve-the-orderbook-(amount-and-pricepoint)-corresponding-to-a-lendingtoken-and-a-term-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-trades">trades</h1>

Trade endpoints

## Retrieve all trades corresponding to a baseToken or/and a quoteToken

<a id="opIdHandleGetTrades"></a>

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/trades \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/trades",
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

	url := "https://dex.tomochain.com/api/trades"

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

url = URI("https://dex.tomochain.com/api/trades")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/trades", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/trades")
  .header("accept", "application/json")
  .asString();
```

`GET /trades`

Return all trades in an array with total match

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|pageOffset|query|string|false|none|
|pageSize|query|string|false|number of trade item per page, default 50|
|sortBy|query|string|false|Sort for query (suported sort by time)|
|sortType|query|string|false|asc/dec|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "trades": [
    {
      "id": "string",
      "taker": "string",
      "maker": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "makerOrderHash": "string",
      "takerOrderHash": "string",
      "hash": "string",
      "txHash": "string",
      "pairName": "string",
      "pricepoint": "string",
      "amount": "string",
      "status": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z"
    }
  ]
}
```

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-all-trades-corresponding-to-a-basetoken-or/and-a-quotetoken-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» trades|[[Trade](#schematrade)]|false|none|none|
|»» id|string|false|read-only|none|
|»» taker|string|false|none|none|
|»» maker|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» makerOrderHash|string|false|none|none|
|»» takerOrderHash|string|false|none|none|
|»» hash|string|false|none|none|
|»» txHash|string|false|none|none|
|»» pairName|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» status|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve the sorted list of trades for an Ethereum address in which the given address is either maker or taker

<a id="opIdHandleGetTradesHistory"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/trades/history?address=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/trades/history?address=string",
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

	url := "https://dex.tomochain.com/api/trades/history?address=string"

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

url = URI("https://dex.tomochain.com/api/trades/history?address=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/trades/history?address=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/trades/history?address=string")
  .header("accept", "application/json")
  .asString();
```

`GET /trades/history`

Return trades array

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|true|User address|
|pageOffset|query|string|false|none|
|pageSize|query|string|false|number of trade item per page, default 50|
|sortBy|query|string|false|Sort for query (suported sort by time)|
|sortType|query|string|false|asc/dec|
|baseToken|query|string|false|Base token address|
|quoteToken|query|string|false|Quote token address|
|from|query|string|false|the beginning timestamp (number of seconds from 1970/01/01) from which order data has to be queried|
|to|query|string|false|the ending timestamp ((number of seconds from 1970/01/01)) until which order data has to be queried|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "trades": [
    {
      "id": "string",
      "taker": "string",
      "maker": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "makerOrderHash": "string",
      "takerOrderHash": "string",
      "hash": "string",
      "txHash": "string",
      "pairName": "string",
      "pricepoint": "string",
      "amount": "string",
      "status": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z"
    }
  ]
}
```

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|address Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-sorted-list-of-trades-for-an-ethereum-address-in-which-the-given-address-is-either-maker-or-taker-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» total|integer|false|none|none|
|» trades|[[Trade](#schematrade)]|false|none|none|
|»» id|string|false|read-only|none|
|»» taker|string|false|none|none|
|»» maker|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|»» makerOrderHash|string|false|none|none|
|»» takerOrderHash|string|false|none|none|
|»» hash|string|false|none|none|
|»» txHash|string|false|none|none|
|»» pairName|string|false|none|none|
|»» pricepoint|string|false|none|none|
|»» amount|string|false|none|none|
|»» status|string|false|none|none|
|»» createdAt|string(date-time)|false|read-only|none|
|»» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-ohlcv">ohlcv</h1>

OHLCV endpoints

## Retrieve OHLCV data corresponding to a baseToken and a quoteToken

<a id="opIdHandleGetOHLCV"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string",
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

	url := "https://dex.tomochain.com/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string"

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

url = URI("https://dex.tomochain.com/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/ohlcv?baseToken=string&quoteToken=string&timeInterval=string&from=string&to=string")
  .header("accept", "application/json")
  .asString();
```

`GET /ohlcv`

Return all ticks in an array

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|
|timeInterval|query|string|true|Time interval, candle size. Valid values: 1m, 3m, 5m, 15m, 30m, 1h, 2h, 4h, 6h, 8h, 12h, 1d, 1w, 1mo (1 month)|
|from|query|string|true|the beginning timestamp (number of seconds from 1970/01/01) from which ohlcv data has to be queried|
|to|query|string|true|the ending timestamp ((number of seconds from 1970/01/01)) until which ohlcv data has to be queried|

> Example responses

> 200 Response

```json
[
  {
    "pair": {
      "pairName": "string",
      "baseToken": "string",
      "quoteToken": "string"
    },
    "open": "string",
    "high": "string",
    "low": 0,
    "close": "string",
    "volume": "string",
    "count": "string",
    "timestamp": "string"
  }
]
```

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|*** Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-ohlcv-data-corresponding-to-a-basetoken-and-a-quotetoken-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Tick](#schematick)]|false|none|none|
|» pair|[PairID](#schemapairid)|false|none|none|
|»» pairName|string|false|none|none|
|»» baseToken|string|false|none|none|
|»» quoteToken|string|false|none|none|
|» open|string|false|none|none|
|» high|string|false|none|none|
|» low|integer(int32)|false|none|none|
|» close|string|false|none|none|
|» volume|string|false|none|none|
|» count|string|false|none|none|
|» timestamp|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-notifications">notifications</h1>

Notification endpoints

## Retrieve the list of notifications for an address with pagination

<a id="opIdHandleGetNotifications"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/notifications?userAddress=string&page=string&perPage=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/notifications?userAddress=string&page=string&perPage=string",
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

	url := "https://dex.tomochain.com/api/notifications?userAddress=string&page=string&perPage=string"

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

url = URI("https://dex.tomochain.com/api/notifications?userAddress=string&page=string&perPage=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/notifications?userAddress=string&page=string&perPage=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/notifications?userAddress=string&page=string&perPage=string")
  .header("accept", "application/json")
  .asString();
```

`GET /notifications`

Return notifications in an array

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|userAddress|query|string|true|User address|
|page|query|string|true|Page number|
|perPage|query|string|true|the number of records returned per page. Valid values are 10, 20, 30, 40, 50|

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "recipient": "string",
    "message": "string",
    "type": "string",
    "status": "string",
    "createdAt": "2020-06-22T09:54:03Z",
    "updatedAt": "2020-06-22T09:54:03Z"
  }
]
```

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid user address|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<h3 id="retrieve-the-list-of-notifications-for-an-address-with-pagination-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Notification](#schemanotification)]|false|none|none|
|» id|string|false|read-only|none|
|» recipient|string|false|none|none|
|» message|string|false|none|none|
|» type|string|false|none|none|
|» status|string|false|none|none|
|» createdAt|string(date-time)|false|read-only|none|
|» updatedAt|string(date-time)|false|read-only|none|

<aside class="success">
This operation does not require authentication
</aside>

## Update status of a notification from UNREAD to READ

<a id="opIdHandleNewOrder"></a>

> Code samples

```shell
curl --request PUT \
  --url https://dex.tomochain.com/api/notifications/ \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"recipient":"string","message":"string","type":"string","status":"string"}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "PUT",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/notifications/",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({recipient: 'string', message: 'string', type: 'string', status: 'string'}));
req.end();
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://dex.tomochain.com/api/notifications/"

	payload := strings.NewReader("{\"recipient\":\"string\",\"message\":\"string\",\"type\":\"string\",\"status\":\"string\"}")

	req, _ := http.NewRequest("PUT", url, payload)

	req.Header.Add("content-type", "application/json")
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

url = URI("https://dex.tomochain.com/api/notifications/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json'
request["accept"] = 'application/json'
request.body = "{\"recipient\":\"string\",\"message\":\"string\",\"type\":\"string\",\"status\":\"string\"}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

payload = "{\"recipient\":\"string\",\"message\":\"string\",\"type\":\"string\",\"status\":\"string\"}"

headers = {
    'content-type': "application/json",
    'accept': "application/json"
    }

conn.request("PUT", "/api/notifications/", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.put("https://dex.tomochain.com/api/notifications/")
  .header("content-type", "application/json")
  .header("accept", "application/json")
  .body("{\"recipient\":\"string\",\"message\":\"string\",\"type\":\"string\",\"status\":\"string\"}")
  .asString();
```

`PUT /notifications/{id}`

Returns newly updated notification

> Body parameter

```json
{
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string"
}
```

<h3 id="update-status-of-a-notification-from-unread-to-read-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Notification](#schemanotification)|true|Notification object that needs to be updated|
|» id|body|string|false|none|
|» recipient|body|string|false|none|
|» message|body|string|false|none|
|» type|body|string|false|none|
|» status|body|string|false|none|
|» createdAt|body|string(date-time)|false|none|
|» updatedAt|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="update-status-of-a-notification-from-unread-to-read-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Notification](#schemanotification)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid payload|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-info">info</h1>

Info endpoints

## get__info

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/info \
  --header 'accept: */*'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/info",
  "headers": {
    "accept": "*/*"
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

	url := "https://dex.tomochain.com/api/info"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "*/*")

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

url = URI("https://dex.tomochain.com/api/info")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = '*/*'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "*/*" }

conn.request("GET", "/api/info", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/info")
  .header("accept", "*/*")
  .asString();
```

`GET /info`

> Example responses

> 200 Response

<h3 id="get__info-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal server error|None|

<h3 id="get__info-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» exchangeAddress|string|false|none|none|
|» fee|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__info_exchange

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/info/exchange \
  --header 'accept: */*'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/info/exchange",
  "headers": {
    "accept": "*/*"
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

	url := "https://dex.tomochain.com/api/info/exchange"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "*/*")

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

url = URI("https://dex.tomochain.com/api/info/exchange")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = '*/*'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "*/*" }

conn.request("GET", "/api/info/exchange", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/info/exchange")
  .header("accept", "*/*")
  .asString();
```

`GET /info/exchange`

> Example responses

> 200 Response

<h3 id="get__info_exchange-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="get__info_exchange-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» exchangeAddress|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__info_fees

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/info/fees \
  --header 'accept: */*'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/info/fees",
  "headers": {
    "accept": "*/*"
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

	url := "https://dex.tomochain.com/api/info/fees"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("accept", "*/*")

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

url = URI("https://dex.tomochain.com/api/info/fees")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["accept"] = '*/*'

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "*/*" }

conn.request("GET", "/api/info/fees", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/info/fees")
  .header("accept", "*/*")
  .asString();
```

`GET /info/fees`

> Example responses

> 200 Response

<h3 id="get__info_fees-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="get__info_fees-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» fee|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomodex-apis-market">market</h1>

## Retrieve market stats 24h corresponding to a baseToken and a quoteToken

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/market/stats?baseToken=string&quoteToken=string' \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/market/stats?baseToken=string&quoteToken=string",
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

	url := "https://dex.tomochain.com/api/market/stats?baseToken=string&quoteToken=string"

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

url = URI("https://dex.tomochain.com/api/market/stats?baseToken=string&quoteToken=string")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/market/stats?baseToken=string&quoteToken=string", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/market/stats?baseToken=string&quoteToken=string")
  .header("accept", "application/json")
  .asString();
```

`GET /market/stats`

Multiple status values can be provided with comma separated strings

<h3 id="retrieve-market-stats-24h-corresponding-to-a-basetoken-and-a-quotetoken-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|query|string|true|Base token address|
|quoteToken|query|string|true|Quote token address|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}
```

<h3 id="retrieve-market-stats-24h-corresponding-to-a-basetoken-and-a-quotetoken-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pair](#schemapair)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Retrieve all market stats 2

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/market/stats/all \
  --header 'accept: application/json'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/market/stats/all",
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

	url := "https://dex.tomochain.com/api/market/stats/all"

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

url = URI("https://dex.tomochain.com/api/market/stats/all")

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

conn = http.client.HTTPSConnection("dex.tomochain.com")

headers = { 'accept': "application/json" }

conn.request("GET", "/api/market/stats/all", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/market/stats/all")
  .header("accept", "application/json")
  .asString();
```

`GET /market/stats/all`

Multiple status values can be provided with comma separated strings

> Example responses

> 200 Response

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}
```

<h3 id="retrieve-all-market-stats-2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[PairData](#schemapairdata)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|baseToken Parameter missing|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Account">Account</h2>
<!-- backwards compatibility -->
<a id="schemaaccount"></a>
<a id="schema_Account"></a>
<a id="tocSaccount"></a>
<a id="tocsaccount"></a>

```json
{
  "address": "0xF7349C253FF7747Df661296E0859c44e974fb52E"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|address|string|false|none|none|
|tokenBalances|object|false|none|none|
|» address|string|false|none|none|
|» symbol|string|false|none|none|
|» balance|string|false|none|none|
|» availableBalance|string|false|none|none|
|» inOrderBalance|string|false|none|none|
|isBlocked|boolean|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocS_TokenBalance">TokenBalance</h2>
<!-- backwards compatibility -->
<a id="schematokenbalance"></a>
<a id="schema_TokenBalance"></a>
<a id="tocStokenbalance"></a>
<a id="tocstokenbalance"></a>

```json
{
  "address": "string",
  "symbol": "string",
  "balance": "string",
  "availableBalance": "string",
  "inOrderBalance": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address|string|false|none|none|
|symbol|string|false|none|none|
|balance|string|false|none|none|
|availableBalance|string|false|none|none|
|inOrderBalance|string|false|none|none|

<h2 id="tocS_Token">Token</h2>
<!-- backwards compatibility -->
<a id="schematoken"></a>
<a id="schema_Token"></a>
<a id="tocStoken"></a>
<a id="tocstoken"></a>

```json
{
  "id": "string",
  "name": "string",
  "symbol": "string",
  "address": "string",
  "image": {
    "url": "string",
    "meta": {}
  },
  "contractAddress": "string",
  "decimals": 0,
  "active": true,
  "listed": true,
  "quote": true,
  "makeFee": "string",
  "takeFee": "string",
  "usd": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|name|string|false|none|none|
|symbol|string|false|none|none|
|address|string|false|none|none|
|image|[Image](#schemaimage)|false|none|none|
|contractAddress|string|false|none|none|
|decimals|integer(int32)|false|read-only|none|
|active|boolean|false|none|none|
|listed|boolean|false|read-only|none|
|quote|boolean|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|
|usd|string|false|read-only|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocS_Pair">Pair</h2>
<!-- backwards compatibility -->
<a id="schemapair"></a>
<a id="schema_Pair"></a>
<a id="tocSpair"></a>
<a id="tocspair"></a>

```json
{
  "id": "string",
  "baseTokenSymbol": "string",
  "baseTokenAddress": "string",
  "baseTokenDecimals": 0,
  "quoteTokenSymbol": "string",
  "quoteTokenAddress": "string",
  "quoteTokenDecimals": 0,
  "listed": true,
  "active": true,
  "rank": 0,
  "makeFee": "string",
  "takeFee": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|baseTokenSymbol|string|false|none|none|
|baseTokenAddress|string|false|none|none|
|baseTokenDecimals|integer(int32)|false|read-only|none|
|quoteTokenSymbol|string|false|none|none|
|quoteTokenAddress|string|false|none|none|
|quoteTokenDecimals|integer(int32)|false|read-only|none|
|listed|boolean|false|read-only|none|
|active|boolean|false|none|none|
|rank|integer(int32)|false|read-only|none|
|makeFee|string|false|read-only|none|
|takeFee|string|false|read-only|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocS_PairID">PairID</h2>
<!-- backwards compatibility -->
<a id="schemapairid"></a>
<a id="schema_PairID"></a>
<a id="tocSpairid"></a>
<a id="tocspairid"></a>

```json
{
  "pairName": "string",
  "baseToken": "string",
  "quoteToken": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|

<h2 id="tocS_PairData">PairData</h2>
<!-- backwards compatibility -->
<a id="schemapairdata"></a>
<a id="schema_PairData"></a>
<a id="tocSpairdata"></a>
<a id="tocspairdata"></a>

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string",
  "orderVolume": "string",
  "orderCount": "string",
  "askPrice": "string",
  "bidPrice": "string",
  "price": "string",
  "rank": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pair|[PairID](#schemapairid)|false|none|none|
|open|string|false|none|none|
|high|string|false|none|none|
|low|integer(int32)|false|none|none|
|close|string|false|none|none|
|volume|string|false|none|none|
|count|string|false|none|none|
|timestamp|string|false|none|none|
|orderVolume|string|false|none|none|
|orderCount|string|false|none|none|
|askPrice|string|false|none|none|
|bidPrice|string|false|none|none|
|price|string|false|none|none|
|rank|integer(int32)|false|none|none|

<h2 id="tocS_Image">Image</h2>
<!-- backwards compatibility -->
<a id="schemaimage"></a>
<a id="schema_Image"></a>
<a id="tocSimage"></a>
<a id="tocsimage"></a>

```json
{
  "url": "string",
  "meta": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|
|meta|object|false|none|none|

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "id": "string",
  "userAddress": "string",
  "exchangeAddress": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "status": "string",
  "side": "string",
  "type": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "string",
  "amount": "string",
  "filledAmount": "string",
  "nonce": "string",
  "makeFee": "string",
  "takeFee": "string",
  "pairName": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z",
  "orderID": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|userAddress|string|false|none|none|
|exchangeAddress|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|status|string|false|none|none|
|side|string|false|none|none|
|type|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|filledAmount|string|false|none|none|
|nonce|string|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|
|pairName|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|
|orderID|string|false|none|none|

<h2 id="tocS_OrderCreate">OrderCreate</h2>
<!-- backwards compatibility -->
<a id="schemaordercreate"></a>
<a id="schema_OrderCreate"></a>
<a id="tocSordercreate"></a>
<a id="tocsordercreate"></a>

```json
{
  "userAddress": "0x15e08dE16f534c890828F2a0D935433aF5B3CE0C",
  "exchangeAddress": "0x0D3ab14BBaD3D99F4203bd7a11aCB94882050E7e",
  "baseToken": "0x4d7eA2cE949216D6b120f3AA10164173615A2b6C",
  "quoteToken": "0x0000000000000000000000000000000000000001",
  "side": "SELL/BUY",
  "type": "LO/MO",
  "status": "NEW/CANCELLED",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  },
  "pricepoint": "21207020000000000000000",
  "amount": "4693386710283129",
  "nonce": "1",
  "makeFee": "1",
  "takeFee": "1"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|userAddress|string|false|none|none|
|exchangeAddress|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|side|string|false|none|none|
|type|string|false|none|none|
|status|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|nonce|string|false|none|none|
|makeFee|string|false|none|none|
|takeFee|string|false|none|none|

<h2 id="tocS_OrderCancel">OrderCancel</h2>
<!-- backwards compatibility -->
<a id="schemaordercancel"></a>
<a id="schema_OrderCancel"></a>
<a id="tocSordercancel"></a>
<a id="tocsordercancel"></a>

```json
{
  "orderHash": "string",
  "nonce": "string",
  "hash": "string",
  "signature": {
    "V": "string",
    "R": "string",
    "S": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|orderHash|string|false|none|none|
|nonce|string|false|none|none|
|hash|string|false|none|none|
|signature|[Signature](#schemasignature)|false|none|none|

<h2 id="tocS_Signature">Signature</h2>
<!-- backwards compatibility -->
<a id="schemasignature"></a>
<a id="schema_Signature"></a>
<a id="tocSsignature"></a>
<a id="tocssignature"></a>

```json
{
  "V": "string",
  "R": "string",
  "S": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|V|string|false|none|none|
|R|string|false|none|none|
|S|string|false|none|none|

<h2 id="tocS_OrderBook">OrderBook</h2>
<!-- backwards compatibility -->
<a id="schemaorderbook"></a>
<a id="schema_OrderBook"></a>
<a id="tocSorderbook"></a>
<a id="tocsorderbook"></a>

```json
{
  "pairName": "string",
  "asks": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ],
  "bids": [
    {
      "amount": "string",
      "pricepoint": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|asks|[object]|false|none|none|
|» amount|string|false|none|none|
|» pricepoint|string|false|none|none|
|bids|[object]|false|none|none|
|» amount|string|false|none|none|
|» pricepoint|string|false|none|none|

<h2 id="tocS_RawOrderBook">RawOrderBook</h2>
<!-- backwards compatibility -->
<a id="schemaraworderbook"></a>
<a id="schema_RawOrderBook"></a>
<a id="tocSraworderbook"></a>
<a id="tocsraworderbook"></a>

```json
{
  "pairName": "string",
  "orders": [
    {
      "id": "string",
      "userAddress": "string",
      "exchangeAddress": "string",
      "baseToken": "string",
      "quoteToken": "string",
      "status": "string",
      "side": "string",
      "type": "string",
      "hash": "string",
      "signature": {
        "V": "string",
        "R": "string",
        "S": "string"
      },
      "pricepoint": "string",
      "amount": "string",
      "filledAmount": "string",
      "nonce": "string",
      "makeFee": "string",
      "takeFee": "string",
      "pairName": "string",
      "createdAt": "2020-06-22T09:54:03Z",
      "updatedAt": "2020-06-22T09:54:03Z",
      "orderID": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pairName|string|false|none|none|
|orders|[[Order](#schemaorder)]|false|none|none|

<h2 id="tocS_Trade">Trade</h2>
<!-- backwards compatibility -->
<a id="schematrade"></a>
<a id="schema_Trade"></a>
<a id="tocStrade"></a>
<a id="tocstrade"></a>

```json
{
  "id": "string",
  "taker": "string",
  "maker": "string",
  "baseToken": "string",
  "quoteToken": "string",
  "makerOrderHash": "string",
  "takerOrderHash": "string",
  "hash": "string",
  "txHash": "string",
  "pairName": "string",
  "pricepoint": "string",
  "amount": "string",
  "status": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|taker|string|false|none|none|
|maker|string|false|none|none|
|baseToken|string|false|none|none|
|quoteToken|string|false|none|none|
|makerOrderHash|string|false|none|none|
|takerOrderHash|string|false|none|none|
|hash|string|false|none|none|
|txHash|string|false|none|none|
|pairName|string|false|none|none|
|pricepoint|string|false|none|none|
|amount|string|false|none|none|
|status|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocS_Tick">Tick</h2>
<!-- backwards compatibility -->
<a id="schematick"></a>
<a id="schema_Tick"></a>
<a id="tocStick"></a>
<a id="tocstick"></a>

```json
{
  "pair": {
    "pairName": "string",
    "baseToken": "string",
    "quoteToken": "string"
  },
  "open": "string",
  "high": "string",
  "low": 0,
  "close": "string",
  "volume": "string",
  "count": "string",
  "timestamp": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|pair|[PairID](#schemapairid)|false|none|none|
|open|string|false|none|none|
|high|string|false|none|none|
|low|integer(int32)|false|none|none|
|close|string|false|none|none|
|volume|string|false|none|none|
|count|string|false|none|none|
|timestamp|string|false|none|none|

<h2 id="tocS_Notification">Notification</h2>
<!-- backwards compatibility -->
<a id="schemanotification"></a>
<a id="schema_Notification"></a>
<a id="tocSnotification"></a>
<a id="tocsnotification"></a>

```json
{
  "id": "string",
  "recipient": "string",
  "message": "string",
  "type": "string",
  "status": "string",
  "createdAt": "2020-06-22T09:54:03Z",
  "updatedAt": "2020-06-22T09:54:03Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|read-only|none|
|recipient|string|false|none|none|
|message|string|false|none|none|
|type|string|false|none|none|
|status|string|false|none|none|
|createdAt|string(date-time)|false|read-only|none|
|updatedAt|string(date-time)|false|read-only|none|

<h2 id="tocS_ApiResponse">ApiResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapiresponse"></a>
<a id="schema_ApiResponse"></a>
<a id="tocSapiresponse"></a>
<a id="tocsapiresponse"></a>

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

