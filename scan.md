
<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tomoscan-apis">TomoScan APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

TomoScan APIs

License: <a href="https://github.com/tomochain/tomoscan">Github</a>

<h1 id="tomoscan-apis-accounts">Accounts</h1>

Accounts API

## Get list accounts

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/accounts
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/accounts",
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

	url := "https://example.com/api/accounts"

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

url = URI("https://example.com/api/accounts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/accounts")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/accounts")
  .asString();
```

`GET /api/accounts`

<h3 id="get-list-accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1, maximum = 500|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get account detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/accounts/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/accounts/string",
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

	url := "https://example.com/api/accounts/string"

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

url = URI("https://example.com/api/accounts/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/accounts/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/accounts/string")
  .asString();
```

`GET /api/accounts/{hash}`

<h3 id="get-account-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|account address|

<h3 id="get-account-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list block create

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/accounts/string/mined
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/accounts/string/mined",
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

	url := "https://example.com/api/accounts/string/mined"

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

url = URI("https://example.com/api/accounts/string/mined")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/accounts/string/mined")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/accounts/string/mined")
  .asString();
```

`GET /api/accounts/{hash}/mined`

<h3 id="get-list-block-create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-block-create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-blocks">Blocks</h1>

Blocks API

## Get list blocks

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/blocks
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/blocks",
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

	url := "https://example.com/api/blocks"

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

url = URI("https://example.com/api/blocks")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/blocks")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/blocks")
  .asString();
```

`GET /api/blocks`

<h3 id="get-list-blocks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1, maximum = 500|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-blocks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get block detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/blocks/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/blocks/string",
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

	url := "https://example.com/api/blocks/string"

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

url = URI("https://example.com/api/blocks/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/blocks/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/blocks/string")
  .asString();
```

`GET /api/blocks/{hash}`

<h3 id="get-block-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|block number or block hash|

<h3 id="get-block-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Check exist transaction from/to address inside block

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/blocks/0/address/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/blocks/0/address/string",
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

	url := "https://example.com/api/blocks/0/address/string"

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

url = URI("https://example.com/api/blocks/0/address/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/blocks/0/address/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/blocks/0/address/string")
  .asString();
```

`GET /api/blocks/{blockNumber}/address/{address}`

<h3 id="check-exist-transaction-from/to-address-inside-block-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blockNumber|path|number|true|block number|
|address|path|string|true|address|

<h3 id="check-exist-transaction-from/to-address-inside-block-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list signers of a block

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/blocks/signers/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/blocks/signers/0",
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

	url := "https://example.com/api/blocks/signers/0"

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

url = URI("https://example.com/api/blocks/signers/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/blocks/signers/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/blocks/signers/0")
  .asString();
```

`GET /api/blocks/signers/{blockNumber}`

<h3 id="get-list-signers-of-a-block-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blockNumber|path|number|true|account address|

<h3 id="get-list-signers-of-a-block-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get latest irreversible block

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/blocks/finality/latestIrreversibleBlock
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/blocks/finality/latestIrreversibleBlock",
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

	url := "https://example.com/api/blocks/finality/latestIrreversibleBlock"

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

url = URI("https://example.com/api/blocks/finality/latestIrreversibleBlock")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/blocks/finality/latestIrreversibleBlock")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/blocks/finality/latestIrreversibleBlock")
  .asString();
```

`GET /api/blocks/finality/latestIrreversibleBlock`

<h3 id="get-latest-irreversible-block-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-contracts">Contracts</h1>

Contract API

## Get list verified contract

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/contracts
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/contracts",
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

	url := "https://example.com/api/contracts"

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

url = URI("https://example.com/api/contracts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/contracts")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/contracts")
  .asString();
```

`GET /api/contracts`

<h3 id="get-list-verified-contract-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1, maximum = 500|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-verified-contract-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get contract detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/contracts/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/contracts/string",
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

	url := "https://example.com/api/contracts/string"

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

url = URI("https://example.com/api/contracts/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/contracts/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/contracts/string")
  .asString();
```

`GET /api/contracts/{contractAddress}`

<h3 id="get-contract-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contractAddress|path|string|true|contract address|

<h3 id="get-contract-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Read all function on contract

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/contracts/string/read
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/contracts/string/read",
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

	url := "https://example.com/api/contracts/string/read"

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

url = URI("https://example.com/api/contracts/string/read")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/contracts/string/read")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/contracts/string/read")
  .asString();
```

`GET /api/contracts/{contractAddress}/read`

<h3 id="read-all-function-on-contract-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contractAddress|path|string|true|contract address|

<h3 id="read-all-function-on-contract-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-transactions">Transactions</h1>

Transactions API

## Get list transaction by type

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/txs/listByType/:txType
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/txs/listByType/:txType",
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

	url := "https://example.com/api/txs/listByType/:txType"

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

url = URI("https://example.com/api/txs/listByType/:txType")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/txs/listByType/:txType")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/txs/listByType/:txType")
  .asString();
```

`GET /api/txs/listByType/:txType`

<h3 id="get-list-transaction-by-type-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|txType|path|number|true|signTxs|normalTxs|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-transaction-by-type-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list txs by block number.

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/txs/listByBlock/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/txs/listByBlock/0",
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

	url := "https://example.com/api/txs/listByBlock/0"

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

url = URI("https://example.com/api/txs/listByBlock/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/txs/listByBlock/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/txs/listByBlock/0")
  .asString();
```

`GET /api/txs/listByBlock/{blockNumber}`

<h3 id="get-list-txs-by-block-number.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|blockNumber|path|number|true|block number|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 100|

<h3 id="get-list-txs-by-block-number.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list txs by account address.

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/txs/listByAccount/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/txs/listByAccount/string",
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

	url := "https://example.com/api/txs/listByAccount/string"

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

url = URI("https://example.com/api/txs/listByAccount/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/txs/listByAccount/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/txs/listByAccount/string")
  .asString();
```

`GET /api/txs/listByAccount/{address}`

<h3 id="get-list-txs-by-account-address.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|string|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 100|
|tx_type|query|string|false|in|out|all|
|filterAddress|query|string|false|transaction send to/from address|

<h3 id="get-list-txs-by-account-address.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get transaction detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/txs/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/txs/string",
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

	url := "https://example.com/api/txs/string"

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

url = URI("https://example.com/api/txs/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/txs/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/txs/string")
  .asString();
```

`GET /api/txs/{hash}`

<h3 id="get-transaction-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|transaction hash|

<h3 id="get-transaction-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get internal transaction of an address

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/txs/internal/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/txs/internal/string",
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

	url := "https://example.com/api/txs/internal/string"

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

url = URI("https://example.com/api/txs/internal/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/txs/internal/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/txs/internal/string")
  .asString();
```

`GET /api/txs/internal/{address}`

<h3 id="get-internal-transaction-of-an-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|string|true|account address|

<h3 id="get-internal-transaction-of-an-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-tokens">Tokens</h1>

Tokens API

## Get token detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/tokens/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/tokens/string",
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

	url := "https://example.com/api/tokens/string"

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

url = URI("https://example.com/api/tokens/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/tokens/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/tokens/string")
  .asString();
```

`GET /api/tokens/{hash}`

<h3 id="get-token-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|token address|

<h3 id="get-token-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list token holding of a holder

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/tokens/holding/string/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/tokens/holding/string/string",
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

	url := "https://example.com/api/tokens/holding/string/string"

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

url = URI("https://example.com/api/tokens/holding/string/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/tokens/holding/string/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/tokens/holding/string/string")
  .asString();
```

`GET /api/tokens/holding/{tokenType}/{holder}`

<h3 id="get-list-token-holding-of-a-holder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tokenType|path|string|true|trc20|trc21|trc721|
|holder|path|string|true|holder address|

<h3 id="get-list-token-holding-of-a-holder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-epoch">Epoch</h1>

## Get list epoch

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/epochs
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/epochs",
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

	url := "https://example.com/api/epochs"

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

url = URI("https://example.com/api/epochs")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/epochs")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/epochs")
  .asString();
```

`GET /api/epochs`

<h3 id="get-list-epoch-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-epoch-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get epoch detail

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/epochs/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/epochs/0",
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

	url := "https://example.com/api/epochs/0"

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

url = URI("https://example.com/api/epochs/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/epochs/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/epochs/0")
  .asString();
```

`GET /api/epochs/{epochNumber}`

<h3 id="get-epoch-detail-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|epochNumber|path|number|true|epoch number|

<h3 id="get-epoch-detail-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-rewards">Rewards</h1>

## Get list rewards of a voter

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/rewards/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/rewards/0",
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

	url := "https://example.com/api/rewards/0"

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

url = URI("https://example.com/api/rewards/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/rewards/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/rewards/0")
  .asString();
```

`GET /api/rewards/{voter}`

<h3 id="get-list-rewards-of-a-voter-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|voter|path|number|true|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-rewards-of-a-voter-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list reward of an epoch

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/rewards/epoch/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/rewards/epoch/0",
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

	url := "https://example.com/api/rewards/epoch/0"

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

url = URI("https://example.com/api/rewards/epoch/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/rewards/epoch/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/rewards/epoch/0")
  .asString();
```

`GET /api/rewards/epoch/{epochNumber}`

<h3 id="get-list-reward-of-an-epoch-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|epochNumber|path|number|true|epoch number|
|hash|path|string|true|account address|

<h3 id="get-list-reward-of-an-epoch-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get total rewards of an address

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/rewards/total/string/0/0
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/rewards/total/string/0/0",
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

	url := "https://example.com/api/rewards/total/string/0/0"

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

url = URI("https://example.com/api/rewards/total/string/0/0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/rewards/total/string/0/0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/rewards/total/string/0/0")
  .asString();
```

`GET /api/rewards/total/{address}/{fromEpoch}/{toEpoch}`

<h3 id="get-total-rewards-of-an-address-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|path|string|true|account address|
|fromEpoch|path|number|true|from epoch|
|toEpoch|path|number|true|to epoch|

<h3 id="get-total-rewards-of-an-address-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-token">Token</h1>

## Get list tokens

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/tokens
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/tokens",
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

	url := "https://example.com/api/tokens"

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

url = URI("https://example.com/api/tokens")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/tokens")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/tokens")
  .asString();
```

`GET /api/tokens`

<h3 id="get-list-tokens-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|type|query|string|false|trc20|trc21|trc721, default = trc20|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-tokens-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list trc20 token holder. Require 1 of 2 conditions - address | hash

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/token-holders
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/token-holders",
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

	url := "https://example.com/api/token-holders"

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

url = URI("https://example.com/api/token-holders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/token-holders")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/token-holders")
  .asString();
```

`GET /api/token-holders`

<h3 id="get-list-trc20-token-holder.-require-1-of-2-conditions---address-|-hash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|address|query|string|false|token address|
|hash|query|string|false|account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-trc20-token-holder.-require-1-of-2-conditions---address-|-hash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list token transactions.

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/token-txs/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/token-txs/string",
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

	url := "https://example.com/api/token-txs/string"

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

url = URI("https://example.com/api/token-txs/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/token-txs/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/token-txs/string")
  .asString();
```

`GET /api/token-txs/{tokenType}`

<h3 id="get-list-token-transactions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tokenType|path|string|true|trc20|trc21|trc721|
|holder|query|string|false|holder address|
|token|query|string|false|token address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-token-transactions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list token transactions by transaction hash.

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/token-txs/string/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/token-txs/string/string",
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

	url := "https://example.com/api/token-txs/string/string"

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

url = URI("https://example.com/api/token-txs/string/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/token-txs/string/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/token-txs/string/string")
  .asString();
```

`GET /api/token-txs/{tokenType}/{txHash}`

<h3 id="get-list-token-transactions-by-transaction-hash.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tokenType|path|string|true|trc20|trc21|trc721|
|txHash|path|string|true|token address|
|holder|query|string|false|holder address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-token-transactions-by-transaction-hash.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-orders">Orders</h1>

## Get list order

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/orders
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/orders",
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

	url := "https://example.com/api/orders"

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

url = URI("https://example.com/api/orders")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/orders")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/orders")
  .asString();
```

`GET /api/orders`

<h3 id="get-list-order-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|
|userAddress|query|string|false|userAddress|
|pairName|query|string|false|pairName = btc/tomo|
|side|query|string|false|buy/sell|

<h3 id="get-list-order-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list order of dex

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/orders/listByDex/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/orders/listByDex/string",
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

	url := "https://example.com/api/orders/listByDex/string"

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

url = URI("https://example.com/api/orders/listByDex/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/orders/listByDex/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/orders/listByDex/string")
  .asString();
```

`GET /api/orders/listByDex/{dexAddress}`

<h3 id="get-list-order-of-dex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|dexAddress|path|string|true|address of dex|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-order-of-dex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list order of account

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/orders/listByAccount/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/orders/listByAccount/string",
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

	url := "https://example.com/api/orders/listByAccount/string"

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

url = URI("https://example.com/api/orders/listByAccount/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/orders/listByAccount/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/orders/listByAccount/string")
  .asString();
```

`GET /api/orders/listByAccount/{accountAddress}`

<h3 id="get-list-order-of-account-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|accountAddress|path|string|true|address of account|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-order-of-account-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list order by pair

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/orders/listByPair/string/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/orders/listByPair/string/string",
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

	url := "https://example.com/api/orders/listByPair/string/string"

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

url = URI("https://example.com/api/orders/listByPair/string/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/orders/listByPair/string/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/orders/listByPair/string/string")
  .asString();
```

`GET /api/orders/listByPair/{baseToken}/{quoteToken}`

<h3 id="get-list-order-by-pair-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|path|string|true|base token|
|quoteToken|path|string|true|quote token|
|userAddress|query|string|false|filter account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-order-by-pair-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomoscan-apis-trades">Trades</h1>

## Get list trade

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/trades
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades",
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

	url := "https://example.com/api/trades"

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

url = URI("https://example.com/api/trades")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades")
  .asString();
```

`GET /api/trades`

<h3 id="get-list-trade-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|
|userAddress|query|string|false|userAddress|
|pairName|query|string|false|pairName = btc/tomo|

<h3 id="get-list-trade-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list trade of dex

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/trades/listByDex/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/listByDex/string",
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

	url := "https://example.com/api/trades/listByDex/string"

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

url = URI("https://example.com/api/trades/listByDex/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/listByDex/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/listByDex/string")
  .asString();
```

`GET /api/trades/listByDex/{dexAddress}`

<h3 id="get-list-trade-of-dex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|dexAddress|path|string|true|address of dex|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-trade-of-dex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list trade of account

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/trades/listByAccount/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/listByAccount/string",
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

	url := "https://example.com/api/trades/listByAccount/string"

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

url = URI("https://example.com/api/trades/listByAccount/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/listByAccount/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/listByAccount/string")
  .asString();
```

`GET /api/trades/listByAccount/{accountAddress}`

<h3 id="get-list-trade-of-account-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|accountAddress|path|string|true|address of account|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-trade-of-account-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get list order by pair

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/trades/listByPair/string/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/listByPair/string/string",
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

	url := "https://example.com/api/trades/listByPair/string/string"

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

url = URI("https://example.com/api/trades/listByPair/string/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/listByPair/string/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/listByPair/string/string")
  .asString();
```

`GET /api/trades/listByPair/{baseToken}/{quoteToken}`

<h3 id="get-list-order-by-pair-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|baseToken|path|string|true|base token|
|quoteToken|path|string|true|quote token|
|userAddress|query|string|false|filter account address|
|page|query|number|false|default = 1|
|limit|query|number|false|default 20, maximum = 50|

<h3 id="get-list-order-by-pair-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get trade stats

> Code samples

```shell
curl --request GET \
  --url https://example.com/api/trades/stats/string/string
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/stats/string/string",
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

	url := "https://example.com/api/trades/stats/string/string"

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

url = URI("https://example.com/api/trades/stats/string/string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/stats/string/string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/stats/string/string")
  .asString();
```

`GET /api/trades/stats/{exchangeAddress}/{pairName}`

<h3 id="get-trade-stats-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|exchangeAddress|path|string|true|exchange address|
|pairName|path|string|true|pair|
|date|query|string|false|stats of a special day yyyy-mm-dd|

<h3 id="get-trade-stats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get trade daily stats

> Code samples

```shell
curl --request GET \
  --url 'https://example.com/api/trades/dailyStats/string/string?fromDate=string&toDate=string'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/dailyStats/string/string?fromDate=string&toDate=string",
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

	url := "https://example.com/api/trades/dailyStats/string/string?fromDate=string&toDate=string"

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

url = URI("https://example.com/api/trades/dailyStats/string/string?fromDate=string&toDate=string")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/dailyStats/string/string?fromDate=string&toDate=string")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/dailyStats/string/string?fromDate=string&toDate=string")
  .asString();
```

`GET /api/trades/dailyStats/{exchangeAddress}/{pairName}`

<h3 id="get-trade-daily-stats-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|exchangeAddress|path|string|true|exchange address|
|pairName|path|string|true|pair|
|fromDate|query|string|true|from day yyyy-mm-dd|
|toDate|query|string|true|from day yyyy-mm-dd|

<h3 id="get-trade-daily-stats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get trade weekly stats

> Code samples

```shell
curl --request GET \
  --url 'https://example.com/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0",
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

	url := "https://example.com/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0"

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

url = URI("https://example.com/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/weeklyStats/string/string?fromYear=0&fromWeek=0&toYear=0&toWeek=0")
  .asString();
```

`GET /api/trades/weeklyStats/{exchangeAddress}/{pairName}`

<h3 id="get-trade-weekly-stats-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|exchangeAddress|path|string|true|exchange address|
|pairName|path|string|true|pair|
|fromYear|query|number|true|from year|
|fromWeek|query|number|true|from week 1-53|
|toYear|query|number|true|to year|
|toWeek|query|number|true|to week 1-53|

<h3 id="get-trade-weekly-stats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get trade monthly stats

> Code samples

```shell
curl --request GET \
  --url 'https://example.com/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "example.com",
  "port": null,
  "path": "/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0",
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

	url := "https://example.com/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0"

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

url = URI("https://example.com/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("example.com")

conn.request("GET", "/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://example.com/api/trades/monthlyStats/string/string?fromYear=0&fromMonth=0&toYear=0&toMonth=0")
  .asString();
```

`GET /api/trades/monthlyStats/{exchangeAddress}/{pairName}`

<h3 id="get-trade-monthly-stats-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|exchangeAddress|path|string|true|exchange address|
|pairName|path|string|true|pair|
|fromYear|query|number|true|from year|
|fromMonth|query|number|true|from week 1-12|
|toYear|query|number|true|to year|
|toMonth|query|number|true|to week 1-12|

<h3 id="get-trade-monthly-stats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

