---
title: TomoChain JSON-RPC APIs
language_tabs:
  - shell: cURL
  - javascript--node: Node.JS
  - go: GO
  - ruby: Ruby
  - python: Python
  - java: Java
language_clients:
  - shell: ""
  - javascript--node: native
  - go: ""
  - ruby: ""
  - python: ""
  - java: ""
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---


<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tomochain-json-rpc">Tomochain JSON-RPC v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

A collection holding all the Tomochain JSON-RPC API calls
[Swagger Docs](https://tomochain.github.io/rpc-swagger/)

Base URLs:

* <a href="https://rpc.tomochain.com/">https://rpc.tomochain.com/</a>

<h1 id="tomochain-json-rpc-web3">web3</h1>

API for web3 request

## clientRequest

<a id="opIdclientRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//clientVersion \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"web3_clientVersion","params":[],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//clientVersion",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'web3_clientVersion', params: [], id: 1}));
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

	url := "https://rpc.tomochain.com//clientVersion"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//clientVersion")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//clientVersion", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//clientVersion")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"web3_clientVersion\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /clientVersion`

Returns the current client version.

**Parameters**

none

**Returns**

`String` - The current client version

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "web3_clientVersion",
  "params": [],
  "id": 1
}
```

<h3 id="clientrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[clientVersionRequest](#schemaclientversionrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="clientrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sha3Request

<a id="opIdsha3Request"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//sha3 \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"web3_sha3","params":["0x68656c6c6f20776f726c64"],"id":64}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//sha3",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'web3_sha3',
  params: ['0x68656c6c6f20776f726c64'],
  id: 64
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

	url := "https://rpc.tomochain.com//sha3"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//sha3")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//sha3", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//sha3")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"web3_sha3\",\"params\":[\"0x68656c6c6f20776f726c64\"],\"id\":64}")
  .asString();
```

`POST /sha3`

Returns Keccak-256 (not the standardized SHA3-256) of the given data.

**Parameters**

- `DATA` - the data to convert into a SHA3 hash

`params: [
  "0x68656c6c6f20776f726c64"
]`

**Returns**

`DATA` - The SHA3 result of the given string.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "web3_sha3",
  "params": [
    "0x68656c6c6f20776f726c64"
  ],
  "id": 64
}
```

<h3 id="sha3request-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sha3request](#schemasha3request)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="sha3request-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-net">net</h1>

API for network request

## versionRequest

<a id="opIdversionRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//version \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_version","params":[],"id":67}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//version",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'net_version', params: [], id: 67}));
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

	url := "https://rpc.tomochain.com//version"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//version")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//version", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//version")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_version\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /version`

Returns the current network id.

**Parameters**

none

**Returns**

- `String` - The current network id.

  - `"88"`: Tomochain Mainnet

  - `"89"`: Tomochain Testnet

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_version",
  "params": [],
  "id": 67
}
```

<h3 id="versionrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[versionrequest](#schemaversionrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="versionrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## listeningRequest

<a id="opIdlisteningRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//listening \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_listening","params":[],"id":67}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//listening",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'net_listening', params: [], id: 67}));
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

	url := "https://rpc.tomochain.com//listening"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//listening")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//listening", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//listening")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_listening\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /listening`

Returns `true` if client is actively listening for network connections.

**Parameters**

none

**Returns**

- `Boolean` - `true` when listening, otherwise `false`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_listening",
  "params": [],
  "id": 67
}
```

<h3 id="listeningrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listeningrequest](#schemalisteningrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="listeningrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## peerCountRequest

<a id="opIdpeerCountRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//peerCount \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"net_peerCount","params":[],"id":74}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//peerCount",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'net_peerCount', params: [], id: 74}));
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

	url := "https://rpc.tomochain.com//peerCount"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//peerCount")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//peerCount", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//peerCount")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"net_peerCount\",\"params\":[],\"id\":74}")
  .asString();
```

`POST /peerCount`

Returns number of peers currently connected to the client.

**Parameters**

none

**Returns**

- `QUANTITY` - integer of the number of connected peers.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "net_peerCount",
  "params": [],
  "id": 74
}
```

<h3 id="peercountrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[peerCountRequest](#schemapeercountrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="peercountrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-eth">eth</h1>

API for eth information

## protocolVersionRequest

<a id="opIdprotocolVersionRequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//protocolVersion \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_protocolVersion","params":[],"id":67}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//protocolVersion",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_protocolVersion', params: [], id: 67}));
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

	url := "https://rpc.tomochain.com//protocolVersion"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//protocolVersion")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//protocolVersion", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//protocolVersion")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_protocolVersion\",\"params\":[],\"id\":67}")
  .asString();
```

`POST /protocolVersion`

Returns the current ethereum protocol version.

**Parameters**

none

**Returns**

- `String` - The current ethereum protocol version

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_protocolVersion",
  "params": [],
  "id": 67
}
```

<h3 id="protocolversionrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[protocolVersionRequest](#schemaprotocolversionrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="protocolversionrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## syncingrequest

<a id="opIdsyncingrequest"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//syncing \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_syncing","params":[],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//syncing",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_syncing', params: [], id: 1}));
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

	url := "https://rpc.tomochain.com//syncing"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//syncing")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//syncing", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//syncing")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_syncing\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /syncing`

Returns an object with data about the sync status or false.

**Parameters**

none

**Returns**

- `Object|Boolean`, An object with sync status data or FALSE, when not syncing:

  - `startingBlock`: `QUANTITY` - The block at which the import started (will only be reset, after the sync reached his head)

  - `currentBlock`: `QUANTITY` - The current block, same as eth_blockNumber

  - `highestBlock`: `QUANTITY` - The estimated highest block

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_syncing",
  "params": [],
  "id": 1
}
```

<h3 id="syncingrequest-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[syncingrequest](#schemasyncingrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="syncingrequest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## coinbase

<a id="opIdcoinbase"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//coinbase \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_coinbase","params":[],"id":64}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//coinbase",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_coinbase', params: [], id: 64}));
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

	url := "https://rpc.tomochain.com//coinbase"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//coinbase")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//coinbase", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//coinbase")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_coinbase\",\"params\":[],\"id\":64}")
  .asString();
```

`POST /coinbase`

Returns the client coinbase address.
**Parameters**
none
**Returns**
- `DATA`, 20 bytes - the current coinbase address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_coinbase",
  "params": [],
  "id": 64
}
```

<h3 id="coinbase-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[coinbaserequest](#schemacoinbaserequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="coinbase-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## gasPrice

<a id="opIdgasPrice"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//gasPrice \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_gasPrice","params":[],"id":73}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//gasPrice",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_gasPrice', params: [], id: 73}));
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

	url := "https://rpc.tomochain.com//gasPrice"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//gasPrice")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//gasPrice", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//gasPrice")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_gasPrice\",\"params\":[],\"id\":73}")
  .asString();
```

`POST /gasPrice`

Returns the current price per gas in wei.
**Parameters**
none
**Returns**
- `QUANTITY` - integer of the current gas price in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_gasPrice",
  "params": [],
  "id": 73
}
```

<h3 id="gasprice-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[gasPriceRequest](#schemagaspricerequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gasprice-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## accounts

<a id="opIdaccounts"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//accounts \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_accounts","params":[],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//accounts",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_accounts', params: [], id: 1}));
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

	url := "https://rpc.tomochain.com//accounts"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//accounts")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//accounts", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//accounts")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_accounts\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /accounts`

Returns a list of addresses owned by client.

**Parameters**

none

**Returns**

- `Array of DATA`, 20 Bytes - addresses owned by the client

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_accounts",
  "params": [],
  "id": 1
}
```

<h3 id="accounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[accountsrequest](#schemaaccountsrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## blockNumber

<a id="opIdblockNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//blockNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_blockNumber","params":[],"id":83}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//blockNumber",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_blockNumber', params: [], id: 83}));
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

	url := "https://rpc.tomochain.com//blockNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//blockNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//blockNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//blockNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_blockNumber\",\"params\":[],\"id\":83}")
  .asString();
```

`POST /blockNumber`

Returns the number of most recent block.
**Parameters**
none
**Returns**
- `QUANTITY` - integer of the current block number the client is on.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_blockNumber",
  "params": [],
  "id": 83
}
```

<h3 id="blocknumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[blockNumberRequest](#schemablocknumberrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="blocknumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBalance

<a id="opIdgetBalance"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBalance \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x2b5634c42055806a59e9107ed44d43c426e58258","latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBalance",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBalance',
  params: ['0x2b5634c42055806a59e9107ed44d43c426e58258', 'latest'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBalance"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBalance")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBalance", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBalance")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBalance\",\"params\":[\"0x2b5634c42055806a59e9107ed44d43c426e58258\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getBalance`

Returns the balance of the account of given address.

**Parameters**

- `DATA`, 20 Bytes - address to check for balance.
- `QUANTITY|TAG` - integer block number, or the string "latest", "earliest" or "pending", see the default block parameter

`params: [
   ' 0x2b5634c42055806a59e9107ed44d43c426e58258',
   'latest'
]`

**Returns**
- `QUANTITY` - integer of the current balance in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBalance",
  "params": [
    "0x2b5634c42055806a59e9107ed44d43c426e58258",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getbalance-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBalanceRequest](#schemagetbalancerequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getbalance-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getStorageAt

<a id="opIdgetStorageAt"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getStorageAt \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getStorageAt","params":["0x295a70b2de5e3953354a6a8344e616ed314d7251","0x0","latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getStorageAt",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getStorageAt',
  params: ['0x295a70b2de5e3953354a6a8344e616ed314d7251', '0x0', 'latest'],
  id: 1
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

	url := "https://rpc.tomochain.com//getStorageAt"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getStorageAt")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getStorageAt", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getStorageAt")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getStorageAt\",\"params\":[\"0x295a70b2de5e3953354a6a8344e616ed314d7251\",\"0x0\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getStorageAt`

Returns the balance of the account of given address.

**Parameters**

- `DATA`, 20 Bytes - address to check for balance.

- `QUANTITY|TAG` - integer block number, or the string "latest", "earliest" or "pending", see the default block parameter

`params: [
      '0x2b5634c42055806a59e9107ed44d43c426e58258',
      'latest'
      ]`

**Returns**

- `QUANTITY` - integer of the current balance in wei.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getStorageAt",
  "params": [
    "0x295a70b2de5e3953354a6a8344e616ed314d7251",
    "0x0",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getstorageat-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getStorageAtRequest](#schemagetstorageatrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getstorageat-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionCount

<a id="opIdgetTransactionCount"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getTransactionCount \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionCount","params":["0xbf1dcb735e512b731abd3404c15df6431bd03d42","latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getTransactionCount",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getTransactionCount',
  params: ['0xbf1dcb735e512b731abd3404c15df6431bd03d42', 'latest'],
  id: 1
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

	url := "https://rpc.tomochain.com//getTransactionCount"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getTransactionCount")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getTransactionCount", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getTransactionCount")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionCount\",\"params\":[\"0xbf1dcb735e512b731abd3404c15df6431bd03d42\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getTransactionCount`

Returns the number of transactions sent from an address.

**Parameters**

- `DATA`, 20 Bytes - address.
- `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

`params: [
  '0x407d73d8a49eeb85d32cf465507dd71d507100c1',
  'latest' // state at the latest block
]`

**Returns**

- `QUANTITY` - integer of the number of transactions send from this address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionCount",
  "params": [
    "0xbf1dcb735e512b731abd3404c15df6431bd03d42",
    "latest"
  ],
  "id": 1
}
```

<h3 id="gettransactioncount-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionCountRequest](#schemagettransactioncountrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gettransactioncount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockTransactionCountByHash

<a id="opIdgetBlockTransactionCountByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockTransactionCountByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockTransactionCountByHash","params":["0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockTransactionCountByHash",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockTransactionCountByHash',
  params: ['0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockTransactionCountByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockTransactionCountByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockTransactionCountByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockTransactionCountByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByHash\",\"params\":[\"0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34\"],\"id\":1}")
  .asString();
```

`POST /getBlockTransactionCountByHash`

Returns the number of transactions in a block from a block matching the given block hash.

**Parameters**

- `DATA`, 32 Bytes - hash of a block

`params: [
  '0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34'
]`

**Returns**

- `QUANTITY` - integer of the number of transactions in this block.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByHash",
  "params": [
    "0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"
  ],
  "id": 1
}
```

<h3 id="getblocktransactioncountbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockTransactionCountByHashRequest](#schemagetblocktransactioncountbyhashrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblocktransactioncountbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockTransactionCountByNumber

<a id="opIdgetBlockTransactionCountByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockTransactionCountByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockTransactionCountByNumber","params":["0x52A8CA"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockTransactionCountByNumber",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockTransactionCountByNumber',
  params: ['0x52A8CA'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockTransactionCountByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockTransactionCountByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockTransactionCountByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockTransactionCountByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockTransactionCountByNumber\",\"params\":[\"0x52A8CA\"],\"id\":1}")
  .asString();
```

`POST /getBlockTransactionCountByNumber`

Returns the number of transactions in a block matching the given block number.

**Parameters**

- `QUANTITY|TAG` - integer of a block number, or the string `"earliest"`, `"latest"` or `"pending"`, as in the default block parameter.

`params: [
  '0x85', // 232
]`

**Returns**

- `QUANTITY` - integer of the number of transactions in this block.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByNumber",
  "params": [
    "0x52A8CA"
  ],
  "id": 1
}
```

<h3 id="getblocktransactioncountbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockTransactionCountByNumberRequest](#schemagetblocktransactioncountbynumberrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblocktransactioncountbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCode

<a id="opIdgetCode"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getCode \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCode","params":["0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b","0x2"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getCode",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getCode',
  params: ['0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b', '0x2'],
  id: 1
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

	url := "https://rpc.tomochain.com//getCode"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getCode")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getCode", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getCode")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCode\",\"params\":[\"0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b\",\"0x2\"],\"id\":1}")
  .asString();
```

`POST /getCode`

Returns code at a given address.

**Parameters**

- `DATA`, 20 Bytes - address

- `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

`params: [
  '0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b',
  '0x2'  // 2
]`

**Returns**

- `DATA` - the code from the given address.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCode",
  "params": [
    "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
    "0x2"
  ],
  "id": 1
}
```

<h3 id="getcode-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCodeRequest](#schemagetcoderequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getcode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sign

<a id="opIdsign"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//sign \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sign","params":["0x9b2055d370f73ec7d8a03e965129118dc8f5bf83","0xdeadbeaf"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//sign",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_sign',
  params: ['0x9b2055d370f73ec7d8a03e965129118dc8f5bf83', '0xdeadbeaf'],
  id: 1
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

	url := "https://rpc.tomochain.com//sign"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//sign")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//sign", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//sign")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sign\",\"params\":[\"0x9b2055d370f73ec7d8a03e965129118dc8f5bf83\",\"0xdeadbeaf\"],\"id\":1}")
  .asString();
```

`POST /sign`

The sign method calculates an Ethereum specific signature with: `sign(keccak256("\x19Ethereum Signed Message:\n" + len(message) + message)))`.

By adding a prefix to the message makes the calculated signature recognisable as an Ethereum specific signature.  This prevents misuse where a malicious DApp can sign arbitrary data (e.g. transaction) and use the signature to impersonate the victim.

**Note:** the address to sign with must be unlocked.

**Parameters**

  - `DATA`, 20 Bytes - address

  - `DATA`, N Bytes - message to sign

**Returns**

- `DATA`: Signature

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sign",
  "params": [
    "0x9b2055d370f73ec7d8a03e965129118dc8f5bf83",
    "0xdeadbeaf"
  ],
  "id": 1
}
```

<h3 id="sign-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[signrequest](#schemasignrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="sign-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sendTransaction

<a id="opIdsendTransaction"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//sendTransaction \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sendTransaction","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"}],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//sendTransaction",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_sendTransaction',
  params: [
    {
      from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
      to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
      gas: '0x76c0',
      gasPrice: '0x9184e72a000',
      value: '0x9184e72a',
      data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675'
    }
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//sendTransaction"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//sendTransaction")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//sendTransaction", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//sendTransaction")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendTransaction\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")
  .asString();
```

`POST /sendTransaction`

Creates new message call transaction or a contract creation, if the data field contains code.

**Parameters**

`Object` - The transaction object

  - `from`: `DATA`, 20 Bytes - The address the transaction is send from.

  - `to`: `DATA`, 20 Bytes - (optional when creating new contract) The address the transaction is directed to.

  - `gas`: `QUANTITY` - (optional, default: 90000) Integer of the gas provided for the transaction execution. It will return unused gas.

  - `gasPrice`: `QUANTITY` - (optional, default: To-Be-Determined) Integer of the gasPrice used for each paid gas

  - `value`: `QUANTITY` - (optional) Integer of the value sent with this transaction

  - `data`: `DATA` - The compiled code of a contract OR the hash of the invoked method signature and encoded parameters. For details see Ethereum Contract ABI

  - `nonce`: `QUANTITY` - (optional) Integer of a nonce. This allows to overwrite your own pending transactions that use the same nonce.

`params: [{
  "from": " 0xb60e8dd61c5d32be8058bb8eb970870f07233155",
  "to": " 0xd46e8dd67c5d32be8058bb8eb970870f07244567",
  "gas": "0x76c0", // 30400
  "gasPrice": "0x9184e72a000", // 10000000000000
  "value": "0x9184e72a", // 2441406250
  "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
}]`
**Returns**
- `DATA`, 32 Bytes - the transaction hash, or the zero hash if the transaction is not yet available.

 Use `eth_getTransactionReceipt` to get the contract address, after the transaction was mined, when you created a contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendTransaction",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}
```

<h3 id="sendtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sendTransactionRequest](#schemasendtransactionrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[[Param](#schemaparam)]|true|none|
|»» Param|body|[Param](#schemaparam)|false|none|
|»»» from|body|string|true|none|
|»»» to|body|string|true|none|
|»»» gas|body|string|true|none|
|»»» gasPrice|body|string|true|none|
|»»» value|body|string|true|none|
|»»» data|body|string|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="sendtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## sendRawTransaction

<a id="opIdsendRawTransaction"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//sendRawTransaction \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_sendRawTransaction","params":["0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//sendRawTransaction",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_sendRawTransaction',
  params: [
    '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//sendRawTransaction"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//sendRawTransaction")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//sendRawTransaction", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//sendRawTransaction")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_sendRawTransaction\",\"params\":[\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"],\"id\":1}")
  .asString();
```

`POST /sendRawTransaction`

Creates new message call transaction or a contract creation for signed transactions.

**Parameters**

- `DATA`, The signed transaction data.

`params: ["0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"]`
**Returns**

- `DATA`, 32 Bytes - the transaction hash, or the zero hash if the transaction is not yet available.

Use `eth_getTransactionReceipt` to get the contract address, after the transaction was mined, when you created a contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendRawTransaction",
  "params": [
    "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
  ],
  "id": 1
}
```

<h3 id="sendrawtransaction-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[sendRawTransactionRequest](#schemasendrawtransactionrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="sendrawtransaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## call

<a id="opIdcall"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//call \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_call","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"},"latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//call",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_call',
  params: [
    {
      from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
      to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
      gas: '0x76c0',
      gasPrice: '0x9184e72a000',
      value: '0x9184e72a',
      data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675'
    },
    'latest'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//call"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//call")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//call", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//call")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_call\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"},\"latest\"],\"id\":1}")
  .asString();
```

`POST /call`

Executes a new message call immediately without creating a transaction on the block chain.

**Parameters**

`Object` [required]- The transaction call object

  - `from`: `DATA`, 20 Bytes - (optional) The address the transaction is sent from.

  - `to`: `DATA`, 20 Bytes - The address the transaction is directed to.

  - `gas`: `QUANTITY` - (optional) Integer of the gas provided for the transaction execution. eth_call consumes zero gas, but this parameter may be needed by some executions.

  - `gasPrice`: `QUANTITY` - (optional) Integer of the gasPrice used for each paid gas

  - `value`: `QUANTITY` - (optional) Integer of the value sent with this transaction

  - `data`: `DATA` - (optional) Hash of the method signature and encoded parameters. For details see Ethereum Contract ABI

  - `QUANTITY|TAG` - integer block number, or the string `"latest"`, `"earliest"` or `"pending"`, see the default block parameter

**Returns**
- `DATA` - the return value of executed contract.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_call",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    },
    "latest"
  ],
  "id": 1
}
```

<h3 id="call-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[callrequest](#schemacallrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[[Param1](#schemaparam1)]|true|none|
|»» Param1|body|[Param1](#schemaparam1)|false|none|
|»»» from|body|string|false|none|
|»»» to|body|string|false|none|
|»»» gas|body|string|false|none|
|»»» gasPrice|body|string|false|none|
|»»» value|body|string|false|none|
|»»» data|body|string|false|none|
|» id|body|integer(int32)|true|none|

<h3 id="call-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## estimateGas

<a id="opIdestimateGas"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//estimateGas \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_estimateGas","params":[{"from":"0xb60e8dd61c5d32be8058bb8eb970870f07233155","to":"0xd46e8dd67c5d32be8058bb8eb970870f07244567","gas":"0x76c0","gasPrice":"0x9184e72a000","value":"0x9184e72a","data":"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"}],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//estimateGas",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_estimateGas',
  params: [
    {
      from: '0xb60e8dd61c5d32be8058bb8eb970870f07233155',
      to: '0xd46e8dd67c5d32be8058bb8eb970870f07244567',
      gas: '0x76c0',
      gasPrice: '0x9184e72a000',
      value: '0x9184e72a',
      data: '0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675'
    }
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//estimateGas"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//estimateGas")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//estimateGas", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//estimateGas")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_estimateGas\",\"params\":[{\"from\":\"0xb60e8dd61c5d32be8058bb8eb970870f07233155\",\"to\":\"0xd46e8dd67c5d32be8058bb8eb970870f07244567\",\"gas\":\"0x76c0\",\"gasPrice\":\"0x9184e72a000\",\"value\":\"0x9184e72a\",\"data\":\"0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675\"}],\"id\":1}")
  .asString();
```

`POST /estimateGas`

Generates and returns an estimate of how much gas is necessary to allow the transaction to complete.  The transaction will not be added to the blockchain. Note that the estimate may be significantly more  than the amount of gas actually used by the transaction, for a variety of reasons including EVM mechanics and node performance.

**Parameters**

See `eth_call` parameters, expect that all properties are optional. If no gas limit is specified geth uses  the block gas limit from the pending block as an upper bound. As a result the returned estimate might not be  enough to executed the call/transaction when the amount of gas is higher than the pending block gas limit.

**Returns**
- `QUANTITY` - the amount of gas used.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_estimateGas",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}
```

<h3 id="estimategas-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[estimateGasRequest](#schemaestimategasrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="estimategas-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockByHash

<a id="opIdgetBlockByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockByHash","params":["0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",true],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockByHash",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockByHash',
  params: ['0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624', true],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByHash\",\"params\":[\"0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624\",true],\"id\":1}")
  .asString();
```

`POST /getBlockByHash`

Returns information about a block by hash.

**Parameters**

- `BLOCKHASH` [required] - a string representing a BLOCKHASH
- `Boolean` [required] - If true it returns the full transaction objects, if false only the hashes of the transactions.
`params: [
  '0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624',
  true
]`

**Returns**
`Object` - A block object, or null when no block was found:

  - `number`: `QUANTITY` - the block number. null when its pending block.

  - `hash`: `DATA`, 32 Bytes - hash of the block. `null` when its pending block.

  - `parentHash`: `DATA`, 32 Bytes - hash of the parent block.

  - `nonce`: `DATA`, 8 Bytes - hash of the generated proof-of-work. `null` when its pending block.

  - `sha3Uncles`: `DATA`, 32 Bytes - SHA3 of the uncles data in the block.

  - `logsBloom`: `DATA`, 256 Bytes - the bloom filter for the logs of the block. `null` when its pending block.

  - `transactionsRoot`: `DATA`, 32 Bytes - the root of the transaction trie of the block.

  - `stateRoot`: `DATA`, 32 Bytes - the root of the final state trie of the block.

  - `receiptsRoot`: `DATA`, 32 Bytes - the root of the receipts trie of the block.

  - `miner`: `DATA`, 20 Bytes - the address of the beneficiary to whom the mining rewards were given.

  - `difficulty`: `QUANTITY` - integer of the difficulty for this block.

  - `totalDifficulty`: `QUANTITY` - integer of the total difficulty of the chain until this block.

  - `extraData`: `DATA` - the "extra data" field of this block.

  - `size`: `QUANTITY` - integer the size of this block in bytes.

  - `gasLimit`: `QUANTITY` - the maximum gas allowed in this block.

  - `gasUsed`: `QUANTITY` - the total used gas by all transactions in this block.

  - `timestamp`: `QUANTITY` - the unix timestamp for when the block was collated.

  - `transactions`: `Array` - Array of transaction objects, or 32 Bytes transaction hashes depending on the last given parameter.

  - `uncles`: `Array` - Array of uncle hashes.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByHash",
  "params": [
    "0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",
    true
  ],
  "id": 1
}
```

<h3 id="getblockbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockByHashRequest](#schemagetblockbyhashrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblockbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockByNumber

<a id="opIdgetBlockByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockByNumber","params":["0x0",true],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockByNumber",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_getBlockByNumber', params: ['0x0', true], id: 1}));
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

	url := "https://rpc.tomochain.com//getBlockByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockByNumber\",\"params\":[\"0x0\",true],\"id\":1}")
  .asString();
```

`POST /getBlockByNumber`

Returns information about a block by block number.

**Parameters**

`BLOCKNUMBER` [required] - a hex code of an integer representing the BLOCKNUMBER or one of the following special params:
  
  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

`FULLTX` [required] - a boolean value specified whether you want to get transactions list or not

`params: [
  '0x0',
  true
]`

**Returns**

- `RETURN VALUE` - block data of the given `BLOCKNUMBER`

See `eth_getBlockByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": [
    "0x0",
    true
  ],
  "id": 1
}
```

<h3 id="getblockbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockByNumberRequest](#schemagetblockbynumberrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblockbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockSignersByNumber

<a id="opIdgetBlockSignersByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockSignersByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockSignersByNumber","params":["0xA61F98"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockSignersByNumber",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockSignersByNumber',
  params: ['0xA61F98'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockSignersByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockSignersByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockSignersByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockSignersByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")
  .asString();
```

`POST /getBlockSignersByNumber`

Returns the signers set of the block of given `BLOCKNUMBER`.

**Parameters**

`BLOCKNUMBER` [required] - a hex code of an integer representing the `BLOCKNUMBER` or one of the following special params:
  
  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

`params: [
  '0xA61F98'
]`

**Returns**

- `SIGNERS` - signers set of the block of given `BLOCKNUMBER`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}
```

<h3 id="getblocksignersbynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockSignersByNumberRequest](#schemagetblocksignersbynumberrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblocksignersbynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockSignersByHash

<a id="opIdgetBlockSignersByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockSignersByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockSignersByHash","params":["0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockSignersByHash",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockSignersByHash',
  params: ['0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockSignersByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockSignersByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockSignersByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockSignersByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockSignersByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")
  .asString();
```

`POST /getBlockSignersByHash`

Returns the signers set of the block of given `BLOCKHASH`.

**Parameters**

- `BLOCKHASH` [required] - a string representing a `BLOCKHASH`

`params: [
  '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'
]`

**Returns**

- `SIGNERS` - signers set of the block of given `BLOCKHASH`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}
```

<h3 id="getblocksignersbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockSignersByHashRequest](#schemagetblocksignersbyhashrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblocksignersbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockFinalityByNumber

<a id="opIdgetBlockFinalityByNumber"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockFinalityByNumber \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockFinalityByNumber","params":["0xA61F98"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockFinalityByNumber",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockFinalityByNumber',
  params: ['0xA61F98'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockFinalityByNumber"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockFinalityByNumber")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockFinalityByNumber", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockFinalityByNumber")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByNumber\",\"params\":[\"0xA61F98\"],\"id\":1}")
  .asString();
```

`POST /getBlockFinalityByNumber`

Returns the the finality of the block of given BLOCKNUMBER.

**Parameters**

- `BLOCKNUMBER` [required] - a hex code of an integer representing the `BLOCKNUMBER` or one of the following special params:

  - `latest`: get block data of the latest block

  - `pending`: get block data of pending block

  - `earliest`: get the genesis block

`params: [
  '0xA61F98'
]`

**Returns**

- `BLOCK_FINALITY` - integer of the the finality of the block of given `BLOCKNUMBER`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}
```

<h3 id="getblockfinalitybynumber-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockFinalityByNumberRequest](#schemagetblockfinalitybynumberrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblockfinalitybynumber-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBlockFinalityByHash

<a id="opIdgetBlockFinalityByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBlockFinalityByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getBlockFinalityByHash","params":["0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBlockFinalityByHash",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getBlockFinalityByHash',
  params: ['0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'],
  id: 1
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

	url := "https://rpc.tomochain.com//getBlockFinalityByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBlockFinalityByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBlockFinalityByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBlockFinalityByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getBlockFinalityByHash\",\"params\":[\"0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f\"],\"id\":1}")
  .asString();
```

`POST /getBlockFinalityByHash`

Returns the the finality of the block of given `BLOCKHASH`.

**Parameters**

`BLOCKHASH` [required] - a string representing a `BLOCKHASH`

`params: [
  '0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f'
]`

**Returns**

- `BLOCK_FINALITY` - integer of the the finality of the block of given `BLOCKHASH`.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}
```

<h3 id="getblockfinalitybyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBlockFinalityByHashRequest](#schemagetblockfinalitybyhashrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getblockfinalitybyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCandidates

<a id="opIdgetCandidates"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getCandidates \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCandidates","params":["latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getCandidates",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'eth_getCandidates', params: ['latest'], id: 1}));
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

	url := "https://rpc.tomochain.com//getCandidates"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getCandidates")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getCandidates", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getCandidates")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidates\",\"params\":[\"latest\"],\"id\":1}")
  .asString();
```

`POST /getCandidates`

Returns the statuses of all candidates at a specific epoch

**Parameters**

  - `EPOCH_NUMBER` [required] - a hex code of an integer representing the `EPOCH_NUMBER` or the following special param:

      - `latest`: get the status of candidate at the current time

  `params: [
    'latest'
  ]`

**Returns**

  - `EPOCH` - the epoch number of the query of this request

  - `CANDIDATES` - list of candidates along with their statuses and capacities

      - `STATUS` - a string representing status of the corresponding candidate

      - `MASTERNODE` - if the candidate is a masternode
      
      - `SLASHED` - if the candidate is slashed

      - `PROPOSED` - if the candidate is proposed, have not been a masternode yet

      - `empty string` - if it's not a candidate

  - `CAPACITY` - capacity of the corresponding candidate

  - `SUCCESS` - true if the request is successful, otherwise it's false

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidates",
  "params": [
    "latest"
  ],
  "id": 1
}
```

<h3 id="getcandidates-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCandidatesRequest](#schemagetcandidatesrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getcandidates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getCandidateStatus

<a id="opIdgetCandidateStatus"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getCandidateStatus \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getCandidateStatus","params":["0x1d50df657b6dce50bac634bf18e2d986d807e940","latest"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getCandidateStatus",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getCandidateStatus',
  params: ['0x1d50df657b6dce50bac634bf18e2d986d807e940', 'latest'],
  id: 1
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

	url := "https://rpc.tomochain.com//getCandidateStatus"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getCandidateStatus")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getCandidateStatus", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getCandidateStatus")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getCandidateStatus\",\"params\":[\"0x1d50df657b6dce50bac634bf18e2d986d807e940\",\"latest\"],\"id\":1}")
  .asString();
```

`POST /getCandidateStatus`

Returns the status of the candidate of given `COINBASE_ADDRESS` at a specific epoch

**Parameters**

  - `COINBASE_ADDRESS` [required] - a string representing a `COINBASE_ADDRESS` (length: 40, start with 0x )

  - `EPOCH_NUMBER` [required] - a hex code of an integer representing the `EPOCH_NUMBER` or the following special param:

  - `latest`: get the status of candidate at the current time

**Example**

  `params: [
    '0x1d50df657b6dce50bac634bf18e2d986d807e940',
    'latest'
  ]`

**Returns**

  - `STATUS` - a string representing status of the candicate of given `COINBASE_ADDRESS`

      - `MASTERNODE` - if the candidate is a masternode

      - `SLASHED` - if the candidate is slashed

      - `PROPOSED` - if the candidate is proposed, have not been a masternode yet

      - `empty string` - if it's not a candidate

  - `CAPACITY` - capacity of the candidate

  - `EPOCH` - the epoch number of the query of this request

  - `SUCCESS` - true if the request is successful, otherwise it's false

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidateStatus",
  "params": [
    "0x1d50df657b6dce50bac634bf18e2d986d807e940",
    "latest"
  ],
  "id": 1
}
```

<h3 id="getcandidatestatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getCandidateStatusRequest](#schemagetcandidatestatusrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getcandidatestatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByHash

<a id="opIdgetTransactionByHash"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getTransactionByHash \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByHash","params":["0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getTransactionByHash",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getTransactionByHash',
  params: ['0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1'],
  id: 1
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

	url := "https://rpc.tomochain.com//getTransactionByHash"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getTransactionByHash")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getTransactionByHash", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getTransactionByHash")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByHash\",\"params\":[\"0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByHash`

Returns the information about a transaction requested by transaction hash.

**Parameters**

- `DATA`, 32 Bytes - hash of a transaction

**Example**
`params: [
  "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
]`
**Returns**

`Object` - A transaction object, or null when no transaction was found:

  - `hash`: `DATA`, 32 Bytes - hash of the transaction.

  - `nonce`: `QUANTITY` - the number of transactions made by the sender prior to this one.

  - `blockHash`: `DATA`, 32 Bytes - hash of the block where this transaction was in. `null` when its pending.

  - `blockNumber`: `QUANTITY` - block number where this transaction was in. `null` when its pending.

  - `transactionIndex`: `QUANTITY` - integer of the transactions index position in the block. `null` when its pending.

  - `from`: `DATA`, 20 Bytes - address of the sender.

  - `to`: `DATA`, 20 Bytes - address of the receiver. `null` when its a contract creation transaction.

  - `value`: `QUANTITY` - value transferred in Wei.

  - `gasPrice`: `QUANTITY` - gas price provided by the sender in Wei.

  - `gas`: `QUANTITY` - gas provided by the sender.

  - `input`: `DATA` - the data send along with the transaction.

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByHash",
  "params": [
    "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyhash-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByHashRequest](#schemagettransactionbyhashrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gettransactionbyhash-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByBlockHashAndIndex

<a id="opIdgetTransactionByBlockHashAndIndex"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getTransactionByBlockHashAndIndex \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByBlockHashAndIndex","params":["0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7","0x0"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getTransactionByBlockHashAndIndex",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getTransactionByBlockHashAndIndex',
  params: ['0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7', '0x0'],
  id: 1
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

	url := "https://rpc.tomochain.com//getTransactionByBlockHashAndIndex"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getTransactionByBlockHashAndIndex")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getTransactionByBlockHashAndIndex", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getTransactionByBlockHashAndIndex")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockHashAndIndex\",\"params\":[\"0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7\",\"0x0\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByBlockHashAndIndex`

Returns information about a transaction by block hash and transaction index position.
**Parameters**

- `DATA`, 32 Bytes - hash of a block.
- `QUANTITY` - integer of the transaction index position.
**Example**
`params: [
  '0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7',
  '0x0' // 0
]`
**Returns**
See `eth_getTransactionByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockHashAndIndex",
  "params": [
    "0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7",
    "0x0"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyblockhashandindex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByBlockHashAndIndexRequest](#schemagettransactionbyblockhashandindexrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gettransactionbyblockhashandindex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionByBlockNumberAndIndex

<a id="opIdgetTransactionByBlockNumberAndIndex"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getTransactionByBlockNumberAndIndex \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionByBlockNumberAndIndex","params":["0x52A96E","0x1"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getTransactionByBlockNumberAndIndex",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getTransactionByBlockNumberAndIndex',
  params: ['0x52A96E', '0x1'],
  id: 1
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

	url := "https://rpc.tomochain.com//getTransactionByBlockNumberAndIndex"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getTransactionByBlockNumberAndIndex")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getTransactionByBlockNumberAndIndex", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getTransactionByBlockNumberAndIndex")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionByBlockNumberAndIndex\",\"params\":[\"0x52A96E\",\"0x1\"],\"id\":1}")
  .asString();
```

`POST /getTransactionByBlockNumberAndIndex`

Returns information about a transaction by block number and transaction index position.

**Parameters**

- `QUANTITY|TAG` - a block number, or the string `"earliest"`, `"latest"` or `"pending"`, as in the default block parameter.
- `QUANTITY` - the transaction index position.

**Example**
`params: [
  '0x29c', // 668
  '0x0' // 0
]`

**Returns**

See `eth_getTransactionByHash`

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockNumberAndIndex",
  "params": [
    "0x52A96E",
    "0x1"
  ],
  "id": 1
}
```

<h3 id="gettransactionbyblocknumberandindex-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionByBlockNumberAndIndexRequest](#schemagettransactionbyblocknumberandindexrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gettransactionbyblocknumberandindex-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getTransactionReceipt

<a id="opIdgetTransactionReceipt"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getTransactionReceipt \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"eth_getTransactionReceipt","params":["0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getTransactionReceipt",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'eth_getTransactionReceipt',
  params: ['0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f'],
  id: 1
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

	url := "https://rpc.tomochain.com//getTransactionReceipt"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getTransactionReceipt")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getTransactionReceipt", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getTransactionReceipt")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"eth_getTransactionReceipt\",\"params\":[\"0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f\"],\"id\":1}")
  .asString();
```

`POST /getTransactionReceipt`

Returns the receipt of a transaction by transaction hash.

**Note:** That the receipt is not available for pending transactions.

**Parameters**

- `DATA`, 32 Bytes - hash of a transaction

**Example**

  `params: [
    '0xb903239f8543d04b5dc1ba6579132b143087c68db1b2168786408fcbce568238'
  ]`

**Returns**

`Object` - A transaction receipt object, or `null` when no receipt was found:

  - `transactionHash`: `DATA`, 32 Bytes - hash of the transaction.

  - `transactionIndex`: `QUANTITY` - integer of the transactions index position in the block.

  - `blockHash`: `DATA`, 32 Bytes - hash of the block where this transaction was in.

  - `blockNumber`: `QUANTITY` - block number where this transaction was in.

  - `cumulativeGasUsed`: `QUANTITY` - The total amount of gas used when this transaction was executed in the block.

  - `gasUsed`: `QUANTITY` - The amount of gas used by this specific transaction alone.

  - `contractAddress`: `DATA`, 20 Bytes - The contract address created, if the transaction was a contract creation, otherwise `null`.

  - `logs`: `Array` - Array of log objects, which this transaction generated.

  - `logsBloom`: `DATA`, 256 Bytes - Bloom filter for light clients to quickly retrieve related logs.

It also returns either :

  - `root` : `DATA` 32 bytes of post-transaction stateroot (pre Byzantium)

  - `status`: `QUANTITY` either `1` (success) or `0` (failure)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionReceipt",
  "params": [
    "0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"
  ],
  "id": 1
}
```

<h3 id="gettransactionreceipt-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getTransactionReceiptRequest](#schemagettransactionreceiptrequest)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="gettransactionreceipt-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-tomox">tomox</h1>

API for tomox request

## getAskTree

<a id="opIdgetAskTree"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getAskTree \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getAskTree","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getAskTree",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getAskTree',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getAskTree"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAskTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getAskTree")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAskTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAskTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getAskTree", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getAskTree")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAskTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getAskTree`

Returns the ask tree (price, orders, amount)

**Parameters**

- `baseToken`, 32 Bytes - hash of a base token
- `quoteToken`, 32 Bytes - hash of a quote token

**Example**

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - A ask tree (price, orders, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getAskTree",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getasktree-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getAskTree](#schemagetasktree)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getasktree-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getAsks

<a id="opIdgetAsks"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getAsks \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getAsks","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getAsks",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getAsks',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getAsks"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAsks\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getAsks")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAsks\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAsks\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getAsks", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getAsks")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getAsks\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getAsks`

Returns the asks (price, amount)

**Parameters**

- `baseToken`, 32 Bytes - hash of a base token
- `quoteToken`, 32 Bytes - hash of a quote token

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - A asks (price, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getAsks",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getasks-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getAsks](#schemagetasks)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getasks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBestAsk

<a id="opIdgetBestAsk"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBestAsk \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getBestAsk","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBestAsk",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getBestAsk',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getBestAsk"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestAsk\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBestAsk")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestAsk\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestAsk\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBestAsk", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBestAsk")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestAsk\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getBestAsk`

Returns the best ask

**Parameters**

- `baseToken`, hash of a base token
- `quoteToken`, hash of a quote token

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - the best ask (price, volume)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBestAsk",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getbestask-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBestAsk](#schemagetbestask)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getbestask-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBidTree

<a id="opIdgetBidTree"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBidTree \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getBidTree","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBidTree",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getBidTree',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getBidTree"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBidTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBidTree")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBidTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBidTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBidTree", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBidTree")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBidTree\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getBidTree`

Returns the bid tree (price, orders, amount)

**Parameters**

- `baseToken`, hash of a base token
- `quoteToken`, hash of a quote token

**Example**

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - A bid tree (price, orders, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBidTree",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getbidtree-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBidTree](#schemagetbidtree)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getbidtree-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBids

<a id="opIdgetBids"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBids \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getBids","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBids",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getBids',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getBids"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBids\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBids")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBids\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBids\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBids", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBids")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBids\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getBids`

Returns the bids (price, amount)

**Parameters**

- `baseToken`, hash of a base token
- `quoteToken`, hash of a quote token

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - A bids (price, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBids",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getbids-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBids](#schemagetbids)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getbids-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBestBid

<a id="opIdgetBestBid"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBestBid \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getBestBid","params":["0xf992cf45394dAc5f50A26446de17803a79B940da","0x0000000000000000000000000000000000000001"],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBestBid",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getBestBid',
  params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ],
  id: 1
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

	url := "https://rpc.tomochain.com//getBestBid"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestBid\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBestBid")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestBid\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestBid\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBestBid", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBestBid")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBestBid\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",\"0x0000000000000000000000000000000000000001\"],\"id\":1}")
  .asString();
```

`POST /getBestBid`

Returns the best ask

**Parameters**

- `baseToken`, hash of a base token
- `quoteToken`, hash of a quote token

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    '0x0000000000000000000000000000000000000001'
  ]`

**Returns**

`Object` - the best ask (price, volume)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBestBid",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}
```

<h3 id="getbestbid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBestBid](#schemagetbestbid)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getbestbid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getBorrows

<a id="opIdgetBorrows"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getBorrows \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getBorrows","params":["0xf992cf45394dAc5f50A26446de17803a79B940da",86400],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getBorrows",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getBorrows',
  params: ['0xf992cf45394dAc5f50A26446de17803a79B940da', 86400],
  id: 1
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

	url := "https://rpc.tomochain.com//getBorrows"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBorrows\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getBorrows")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBorrows\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBorrows\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getBorrows", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getBorrows")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getBorrows\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}")
  .asString();
```

`POST /getBorrows`

Returns the borrows (interest, amount)

**Parameters**

- `lendingToken`, hash of a lending token
- `term`, perior of the loan (seconds)

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    86400
  ]`

**Returns**

`Object` - list borrows (interest, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBorrows",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    86400
  ],
  "id": 1
}
```

<h3 id="getborrows-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getBorrows](#schemagetborrows)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getborrows-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## getInvests

<a id="opIdgetInvests"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getInvest \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"tomox_getInvests","params":["0xf992cf45394dAc5f50A26446de17803a79B940da",86400],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getInvest",
  "headers": {
    "content-type": "application/json"
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
  jsonrpc: '2.0',
  method: 'tomox_getInvests',
  params: ['0xf992cf45394dAc5f50A26446de17803a79B940da', 86400],
  id: 1
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

	url := "https://rpc.tomochain.com//getInvest"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getInvests\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getInvest")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getInvests\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getInvests\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getInvest", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getInvest")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"tomox_getInvests\",\"params\":[\"0xf992cf45394dAc5f50A26446de17803a79B940da\",86400],\"id\":1}")
  .asString();
```

`POST /getInvest`

Returns the invests (interest, amount)

**Parameters**

- `lendingToken`, hash of a lending token
- `term`, perior of the loan (seconds)

  `params: [
    '0xf992cf45394dAc5f50A26446de17803a79B940da',
    86400
  ]`

**Returns**

`Object` - list invests (interest, amount)

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getInvests",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    86400
  ],
  "id": 1
}
```

<h3 id="getinvests-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getInvests](#schemagetinvests)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getinvests-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomochain-json-rpc-posv">posv</h1>

API for posv request

## getNetworkInformation

<a id="opIdgetNetworkInformation"></a>

> Code samples

```shell
curl --request POST \
  --url https://rpc.tomochain.com//getNetworkInformation \
  --header 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","method":"posv_getNetworkInformation","params":[],"id":1}'
```

```javascript--node
var http = require("https");

var options = {
  "method": "POST",
  "hostname": "rpc.tomochain.com",
  "port": null,
  "path": "//getNetworkInformation",
  "headers": {
    "content-type": "application/json"
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

req.write(JSON.stringify({jsonrpc: '2.0', method: 'posv_getNetworkInformation', params: [], id: 1}));
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

	url := "https://rpc.tomochain.com//getNetworkInformation"

	payload := strings.NewReader("{\"jsonrpc\":\"2.0\",\"method\":\"posv_getNetworkInformation\",\"params\":[],\"id\":1}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")

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

url = URI("https://rpc.tomochain.com//getNetworkInformation")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request.body = "{\"jsonrpc\":\"2.0\",\"method\":\"posv_getNetworkInformation\",\"params\":[],\"id\":1}"

response = http.request(request)
puts response.read_body
```

```python
import http.client

conn = http.client.HTTPSConnection("rpc.tomochain.com")

payload = "{\"jsonrpc\":\"2.0\",\"method\":\"posv_getNetworkInformation\",\"params\":[],\"id\":1}"

headers = { 'content-type': "application/json" }

conn.request("POST", "//getNetworkInformation", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.post("https://rpc.tomochain.com//getNetworkInformation")
  .header("content-type", "application/json")
  .body("{\"jsonrpc\":\"2.0\",\"method\":\"posv_getNetworkInformation\",\"params\":[],\"id\":1}")
  .asString();
```

`POST /getNetworkInformation`

Returns the network information (chainId, special contracts)

**Returns**

`Object` - network information

> Body parameter

```json
{
  "jsonrpc": "2.0",
  "method": "posv_getNetworkInformation",
  "params": [],
  "id": 1
}
```

<h3 id="getnetworkinformation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[getNetworkInformation](#schemagetnetworkinformation)|true|none|
|» jsonrpc|body|string|true|none|
|» method|body|string|true|none|
|» params|body|[string]|true|none|
|» id|body|integer(int32)|true|none|

<h3 id="getnetworkinformation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful Operation|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_clientVersionRequest">clientVersionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaclientversionrequest"></a>
<a id="schema_clientVersionRequest"></a>
<a id="tocSclientversionrequest"></a>
<a id="tocsclientversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "web3_clientVersion",
  "params": [],
  "id": 1
}

```

clientVersionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_sha3request">sha3request</h2>
<!-- backwards compatibility -->
<a id="schemasha3request"></a>
<a id="schema_sha3request"></a>
<a id="tocSsha3request"></a>
<a id="tocssha3request"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "web3_sha3",
  "params": [
    "0x68656c6c6f20776f726c64"
  ],
  "id": 64
}

```

sha3request

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_versionrequest">versionrequest</h2>
<!-- backwards compatibility -->
<a id="schemaversionrequest"></a>
<a id="schema_versionrequest"></a>
<a id="tocSversionrequest"></a>
<a id="tocsversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_version",
  "params": [],
  "id": 67
}

```

versionrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_listeningrequest">listeningrequest</h2>
<!-- backwards compatibility -->
<a id="schemalisteningrequest"></a>
<a id="schema_listeningrequest"></a>
<a id="tocSlisteningrequest"></a>
<a id="tocslisteningrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_listening",
  "params": [],
  "id": 67
}

```

listeningrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_peerCountRequest">peerCountRequest</h2>
<!-- backwards compatibility -->
<a id="schemapeercountrequest"></a>
<a id="schema_peerCountRequest"></a>
<a id="tocSpeercountrequest"></a>
<a id="tocspeercountrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "net_peerCount",
  "params": [],
  "id": 74
}

```

peerCountRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_protocolVersionRequest">protocolVersionRequest</h2>
<!-- backwards compatibility -->
<a id="schemaprotocolversionrequest"></a>
<a id="schema_protocolVersionRequest"></a>
<a id="tocSprotocolversionrequest"></a>
<a id="tocsprotocolversionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_protocolVersion",
  "params": [],
  "id": 67
}

```

protocolVersionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_syncingrequest">syncingrequest</h2>
<!-- backwards compatibility -->
<a id="schemasyncingrequest"></a>
<a id="schema_syncingrequest"></a>
<a id="tocSsyncingrequest"></a>
<a id="tocssyncingrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_syncing",
  "params": [],
  "id": 1
}

```

syncingrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_coinbaserequest">coinbaserequest</h2>
<!-- backwards compatibility -->
<a id="schemacoinbaserequest"></a>
<a id="schema_coinbaserequest"></a>
<a id="tocScoinbaserequest"></a>
<a id="tocscoinbaserequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_coinbase",
  "params": [],
  "id": 64
}

```

coinbaserequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_gasPriceRequest">gasPriceRequest</h2>
<!-- backwards compatibility -->
<a id="schemagaspricerequest"></a>
<a id="schema_gasPriceRequest"></a>
<a id="tocSgaspricerequest"></a>
<a id="tocsgaspricerequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_gasPrice",
  "params": [],
  "id": 73
}

```

gasPriceRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_accountsrequest">accountsrequest</h2>
<!-- backwards compatibility -->
<a id="schemaaccountsrequest"></a>
<a id="schema_accountsrequest"></a>
<a id="tocSaccountsrequest"></a>
<a id="tocsaccountsrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_accounts",
  "params": [],
  "id": 1
}

```

accountsrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_blockNumberRequest">blockNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemablocknumberrequest"></a>
<a id="schema_blockNumberRequest"></a>
<a id="tocSblocknumberrequest"></a>
<a id="tocsblocknumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_blockNumber",
  "params": [],
  "id": 83
}

```

blockNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBalanceRequest">getBalanceRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetbalancerequest"></a>
<a id="schema_getBalanceRequest"></a>
<a id="tocSgetbalancerequest"></a>
<a id="tocsgetbalancerequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBalance",
  "params": [
    "0x2b5634c42055806a59e9107ed44d43c426e58258",
    "latest"
  ],
  "id": 1
}

```

getBalanceRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getStorageAtRequest">getStorageAtRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetstorageatrequest"></a>
<a id="schema_getStorageAtRequest"></a>
<a id="tocSgetstorageatrequest"></a>
<a id="tocsgetstorageatrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getStorageAt",
  "params": [
    "0x295a70b2de5e3953354a6a8344e616ed314d7251",
    "0x0",
    "latest"
  ],
  "id": 1
}

```

getStorageAtRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionCountRequest">getTransactionCountRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactioncountrequest"></a>
<a id="schema_getTransactionCountRequest"></a>
<a id="tocSgettransactioncountrequest"></a>
<a id="tocsgettransactioncountrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionCount",
  "params": [
    "0xbf1dcb735e512b731abd3404c15df6431bd03d42",
    "latest"
  ],
  "id": 1
}

```

getTransactionCountRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockTransactionCountByHashRequest">getBlockTransactionCountByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocktransactioncountbyhashrequest"></a>
<a id="schema_getBlockTransactionCountByHashRequest"></a>
<a id="tocSgetblocktransactioncountbyhashrequest"></a>
<a id="tocsgetblocktransactioncountbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByHash",
  "params": [
    "0xc8b967161c671ce952a3d50987a78d64157fb5a8e1724804b87d3e9b11e3aa34"
  ],
  "id": 1
}

```

getBlockTransactionCountByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockTransactionCountByNumberRequest">getBlockTransactionCountByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocktransactioncountbynumberrequest"></a>
<a id="schema_getBlockTransactionCountByNumberRequest"></a>
<a id="tocSgetblocktransactioncountbynumberrequest"></a>
<a id="tocsgetblocktransactioncountbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockTransactionCountByNumber",
  "params": [
    "0x52A8CA"
  ],
  "id": 1
}

```

getBlockTransactionCountByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCodeRequest">getCodeRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcoderequest"></a>
<a id="schema_getCodeRequest"></a>
<a id="tocSgetcoderequest"></a>
<a id="tocsgetcoderequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCode",
  "params": [
    "0xa94f5374fce5edbc8e2a8697c15331677e6ebf0b",
    "0x2"
  ],
  "id": 1
}

```

getCodeRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_signrequest">signrequest</h2>
<!-- backwards compatibility -->
<a id="schemasignrequest"></a>
<a id="schema_signrequest"></a>
<a id="tocSsignrequest"></a>
<a id="tocssignrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sign",
  "params": [
    "0x9b2055d370f73ec7d8a03e965129118dc8f5bf83",
    "0xdeadbeaf"
  ],
  "id": 1
}

```

signrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_sendTransactionRequest">sendTransactionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasendtransactionrequest"></a>
<a id="schema_sendTransactionRequest"></a>
<a id="tocSsendtransactionrequest"></a>
<a id="tocssendtransactionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendTransaction",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}

```

sendTransactionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[[Param](#schemaparam)]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_Param">Param</h2>
<!-- backwards compatibility -->
<a id="schemaparam"></a>
<a id="schema_Param"></a>
<a id="tocSparam"></a>
<a id="tocsparam"></a>

```json
{
  "from": 1.0393608864131634e+48,
  "to": 1.2127714812045434e+48,
  "gas": 30400,
  "gasPrice": 10000000000000,
  "value": 2441406250,
  "data": 4.537516814050981e+98
}

```

Param

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|true|none|none|
|to|string|true|none|none|
|gas|string|true|none|none|
|gasPrice|string|true|none|none|
|value|string|true|none|none|
|data|string|true|none|none|

<h2 id="tocS_sendRawTransactionRequest">sendRawTransactionRequest</h2>
<!-- backwards compatibility -->
<a id="schemasendrawtransactionrequest"></a>
<a id="schema_sendRawTransactionRequest"></a>
<a id="tocSsendrawtransactionrequest"></a>
<a id="tocssendrawtransactionrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_sendRawTransaction",
  "params": [
    "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
  ],
  "id": 1
}

```

sendRawTransactionRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_callrequest">callrequest</h2>
<!-- backwards compatibility -->
<a id="schemacallrequest"></a>
<a id="schema_callrequest"></a>
<a id="tocScallrequest"></a>
<a id="tocscallrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_call",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    },
    "latest"
  ],
  "id": 1
}

```

callrequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[[Param1](#schemaparam1)]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_Param1">Param1</h2>
<!-- backwards compatibility -->
<a id="schemaparam1"></a>
<a id="schema_Param1"></a>
<a id="tocSparam1"></a>
<a id="tocsparam1"></a>

```json
{
  "from": "",
  "to": "",
  "gas": "",
  "gasPrice": "",
  "value": "",
  "data": ""
}

```

Param1

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|from|string|false|none|none|
|to|string|false|none|none|
|gas|string|false|none|none|
|gasPrice|string|false|none|none|
|value|string|false|none|none|
|data|string|false|none|none|

<h2 id="tocS_estimateGasRequest">estimateGasRequest</h2>
<!-- backwards compatibility -->
<a id="schemaestimategasrequest"></a>
<a id="schema_estimateGasRequest"></a>
<a id="tocSestimategasrequest"></a>
<a id="tocsestimategasrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_estimateGas",
  "params": [
    {
      "from": "0xb60e8dd61c5d32be8058bb8eb970870f07233155",
      "to": "0xd46e8dd67c5d32be8058bb8eb970870f07244567",
      "gas": "0x76c0",
      "gasPrice": "0x9184e72a000",
      "value": "0x9184e72a",
      "data": "0xd46e8dd67c5d32be8d46e8dd67c5d32be8058bb8eb970870f072445675058bb8eb970870f072445675"
    }
  ],
  "id": 1
}

```

estimateGasRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockByHashRequest">getBlockByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockbyhashrequest"></a>
<a id="schema_getBlockByHashRequest"></a>
<a id="tocSgetblockbyhashrequest"></a>
<a id="tocsgetblockbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByHash",
  "params": [
    "0x9326145f8a2c8c00bbe13afc7d7f3d9c868b5ef39d89f2f4e9390e9720298624",
    true
  ],
  "id": 1
}

```

getBlockByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockByNumberRequest">getBlockByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockbynumberrequest"></a>
<a id="schema_getBlockByNumberRequest"></a>
<a id="tocSgetblockbynumberrequest"></a>
<a id="tocsgetblockbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockByNumber",
  "params": [
    "0x0",
    true
  ],
  "id": 1
}

```

getBlockByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockSignersByNumberRequest">getBlockSignersByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocksignersbynumberrequest"></a>
<a id="schema_getBlockSignersByNumberRequest"></a>
<a id="tocSgetblocksignersbynumberrequest"></a>
<a id="tocsgetblocksignersbynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}

```

getBlockSignersByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockSignersByHashRequest">getBlockSignersByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblocksignersbyhashrequest"></a>
<a id="schema_getBlockSignersByHashRequest"></a>
<a id="tocSgetblocksignersbyhashrequest"></a>
<a id="tocsgetblocksignersbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockSignersByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}

```

getBlockSignersByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockFinalityByNumberRequest">getBlockFinalityByNumberRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockfinalitybynumberrequest"></a>
<a id="schema_getBlockFinalityByNumberRequest"></a>
<a id="tocSgetblockfinalitybynumberrequest"></a>
<a id="tocsgetblockfinalitybynumberrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByNumber",
  "params": [
    "0xA61F98"
  ],
  "id": 1
}

```

getBlockFinalityByNumberRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBlockFinalityByHashRequest">getBlockFinalityByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetblockfinalitybyhashrequest"></a>
<a id="schema_getBlockFinalityByHashRequest"></a>
<a id="tocSgetblockfinalitybyhashrequest"></a>
<a id="tocsgetblockfinalitybyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getBlockFinalityByHash",
  "params": [
    "0x605777ee60ef3ccf21e079fa1b091b0196cf1a2c1dd7c088dd5b1ab03f680b6f"
  ],
  "id": 1
}

```

getBlockFinalityByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByHashRequest">getTransactionByHashRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyhashrequest"></a>
<a id="schema_getTransactionByHashRequest"></a>
<a id="tocSgettransactionbyhashrequest"></a>
<a id="tocsgettransactionbyhashrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByHash",
  "params": [
    "0xd83b26e101dd6480764bade90fc283407919f60b7e65ff83fbf6cdc92f1138a1"
  ],
  "id": 1
}

```

getTransactionByHashRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByBlockHashAndIndexRequest">getTransactionByBlockHashAndIndexRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyblockhashandindexrequest"></a>
<a id="schema_getTransactionByBlockHashAndIndexRequest"></a>
<a id="tocSgettransactionbyblockhashandindexrequest"></a>
<a id="tocsgettransactionbyblockhashandindexrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockHashAndIndex",
  "params": [
    "0x3c82bc62179602b67318c013c10f99011037c49cba84e31ffe6e465a21c521a7",
    "0x0"
  ],
  "id": 1
}

```

getTransactionByBlockHashAndIndexRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionByBlockNumberAndIndexRequest">getTransactionByBlockNumberAndIndexRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionbyblocknumberandindexrequest"></a>
<a id="schema_getTransactionByBlockNumberAndIndexRequest"></a>
<a id="tocSgettransactionbyblocknumberandindexrequest"></a>
<a id="tocsgettransactionbyblocknumberandindexrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionByBlockNumberAndIndex",
  "params": [
    "0x52A96E",
    "0x1"
  ],
  "id": 1
}

```

getTransactionByBlockNumberAndIndexRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getTransactionReceiptRequest">getTransactionReceiptRequest</h2>
<!-- backwards compatibility -->
<a id="schemagettransactionreceiptrequest"></a>
<a id="schema_getTransactionReceiptRequest"></a>
<a id="tocSgettransactionreceiptrequest"></a>
<a id="tocsgettransactionreceiptrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getTransactionReceipt",
  "params": [
    "0xa3ece39ae137617669c6933b7578b94e705e765683f260fcfe30eaa41932610f"
  ],
  "id": 1
}

```

getTransactionReceiptRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCandidatesRequest">getCandidatesRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcandidatesrequest"></a>
<a id="schema_getCandidatesRequest"></a>
<a id="tocSgetcandidatesrequest"></a>
<a id="tocsgetcandidatesrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidates",
  "params": [
    "latest"
  ],
  "id": 1
}

```

getCandidateStatusRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getCandidateStatusRequest">getCandidateStatusRequest</h2>
<!-- backwards compatibility -->
<a id="schemagetcandidatestatusrequest"></a>
<a id="schema_getCandidateStatusRequest"></a>
<a id="tocSgetcandidatestatusrequest"></a>
<a id="tocsgetcandidatestatusrequest"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "eth_getCandidateStatus",
  "params": [
    "0x1d50df657b6dce50bac634bf18e2d986d807e940",
    "latest"
  ],
  "id": 1
}

```

getCandidateStatusRequest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getAskTree">getAskTree</h2>
<!-- backwards compatibility -->
<a id="schemagetasktree"></a>
<a id="schema_getAskTree"></a>
<a id="tocSgetasktree"></a>
<a id="tocsgetasktree"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getAskTree",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getAskTree

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getAsks">getAsks</h2>
<!-- backwards compatibility -->
<a id="schemagetasks"></a>
<a id="schema_getAsks"></a>
<a id="tocSgetasks"></a>
<a id="tocsgetasks"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getAsks",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getAsks

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBestAsk">getBestAsk</h2>
<!-- backwards compatibility -->
<a id="schemagetbestask"></a>
<a id="schema_getBestAsk"></a>
<a id="tocSgetbestask"></a>
<a id="tocsgetbestask"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBestAsk",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getBestAsk

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBidTree">getBidTree</h2>
<!-- backwards compatibility -->
<a id="schemagetbidtree"></a>
<a id="schema_getBidTree"></a>
<a id="tocSgetbidtree"></a>
<a id="tocsgetbidtree"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBidTree",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getBidTree

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBids">getBids</h2>
<!-- backwards compatibility -->
<a id="schemagetbids"></a>
<a id="schema_getBids"></a>
<a id="tocSgetbids"></a>
<a id="tocsgetbids"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBids",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getBids

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBestBid">getBestBid</h2>
<!-- backwards compatibility -->
<a id="schemagetbestbid"></a>
<a id="schema_getBestBid"></a>
<a id="tocSgetbestbid"></a>
<a id="tocsgetbestbid"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBestBid",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    "0x0000000000000000000000000000000000000001"
  ],
  "id": 1
}

```

getBestBid

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getBorrows">getBorrows</h2>
<!-- backwards compatibility -->
<a id="schemagetborrows"></a>
<a id="schema_getBorrows"></a>
<a id="tocSgetborrows"></a>
<a id="tocsgetborrows"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getBorrows",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    86400
  ],
  "id": 1
}

```

getBorrows

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getInvests">getInvests</h2>
<!-- backwards compatibility -->
<a id="schemagetinvests"></a>
<a id="schema_getInvests"></a>
<a id="tocSgetinvests"></a>
<a id="tocsgetinvests"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "tomox_getInvests",
  "params": [
    "0xf992cf45394dAc5f50A26446de17803a79B940da",
    86400
  ],
  "id": 1
}

```

getInvest

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|

<h2 id="tocS_getNetworkInformation">getNetworkInformation</h2>
<!-- backwards compatibility -->
<a id="schemagetnetworkinformation"></a>
<a id="schema_getNetworkInformation"></a>
<a id="tocSgetnetworkinformation"></a>
<a id="tocsgetnetworkinformation"></a>

```json
{
  "jsonrpc": "2.0",
  "method": "posv_getNetworkInformation",
  "params": [],
  "id": 1
}

```

getNetworkInformation

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|jsonrpc|string|true|none|none|
|method|string|true|none|none|
|params|[string]|true|none|none|
|id|integer(int32)|true|none|none|


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


<!-- Generator: Widdershins v4.0.1 -->

<h1 id="tomox-relayer-apis">TomoX Relayer APIs v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URL https://dex.tomochain.com

Base URLs:

* <a href="https://dex.tomochain.com">https://dex.tomochain.com</a>

License: <a href="https://github.com/tomochain/tomox-relayer-apis">Github</a>

<h1 id="tomox-relayer-apis-coinmarketcap">CoinMarketCap</h1>

CoinMarketCap's Ideal API Endpoints

## Market Summary Endpoint

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coinmarketcap/markets
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coinmarketcap/markets",
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

	url := "https://dex.tomochain.com/api/coinmarketcap/markets"

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

url = URI("https://dex.tomochain.com/api/coinmarketcap/markets")

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

conn.request("GET", "/api/coinmarketcap/markets")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coinmarketcap/markets")
  .asString();
```

`GET /api/coinmarketcap/markets`

The summary endpoint is to provide an overview of market data for all tickers and all market pairs on the exchange.

**Returns**

 - `trading_pairs:` `(string - Mandatory)` Identifier of a ticker with delimiter to separate base/quote, eg. BTC-USD (Price of BTC is quoted in USD) 

 - `base_currency:` `(string - Recommended)` Symbol/currency code of base currency, eg. BTC

 - `quote_currency:` `(string - Recommended)` Symbol/currency code of quote currency, eg. USD

 - `last_price:` `(decimal - Mandatory)` Last transacted price of base currency based on given quote currency

 - `lowest_ask:` `(decimal - Mandatory)` Lowest Ask price of base currency based on given quote currency

 - `highest_bid:` `(decimal - Mandatory)` Highest bid price of base currency based on given quote currency

 - `base_volume:` `(decimal - Mandatory)` 24-hr volume of market pair denoted in BASE currency

 - `quote_volume:` `(decimal - Mandatory)` 24-hr volume of market pair denoted in QUOTE currency

 - `price_change_percent_24h:` `(decimal - Mandatory)` 24-hr % price change of market pair

 - `highest_price_24h:` `(decimal - Mandatory)` Highest price of base currency based on given quote currency in the last 24-hrs

 - `lowest_price_24h:` `(decimal - Mandatory)` Lowest price of base currency based on given quote currency in the last 24-hrs

<h3 id="market-summary-endpoint-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint A1

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coinmarketcap/assets
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coinmarketcap/assets",
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

	url := "https://dex.tomochain.com/api/coinmarketcap/assets"

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

url = URI("https://dex.tomochain.com/api/coinmarketcap/assets")

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

conn.request("GET", "/api/coinmarketcap/assets")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coinmarketcap/assets")
  .asString();
```

`GET /api/coinmarketcap/assets`

The assets endpoint is to provide a detailed summary for each currency available on the exchange.

**Returns**

- `name:` `(string - Recommended)` Full name of cryptocurrency.
- `unified_cryptoasset_id:` `(integer - Recommended)` Unique ID of cryptocurrency assigned by Unified Cryptoasset ID.
- `can_withdraw:` `(boolean - Recommended)` Identifies whether withdrawals are enabled or disabled.
- `can_deposit:` `(boolean - Recommended)` Identifies whether deposits are enabled or disabled.
- `min_withdraw:` `(decimal - Recommended)` Identifies the single minimum withdrawal amount of a cryptocurrency.
- `max_withdraw:` `(decimal - Recommended)` Identifies the single maximum withdrawal amount of a cryptocurrency.
- `maker_fee:` `(decimal - Recommended)` Fees applied when liquidity is added to the order book.
- `taker_fee:` `(decimal - Recommended)` Fees applied when liquidity is removed from the order book.

<h3 id="endpoint-a1-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint A2

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coinmarketcap/ticker
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coinmarketcap/ticker",
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

	url := "https://dex.tomochain.com/api/coinmarketcap/ticker"

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

url = URI("https://dex.tomochain.com/api/coinmarketcap/ticker")

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

conn.request("GET", "/api/coinmarketcap/ticker")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coinmarketcap/ticker")
  .asString();
```

`GET /api/coinmarketcap/ticker`

The ticker endpoint is to provide a 24-hour pricing and volume summary for each market pair available on the exchange.

**Returns**

- `base_id:` `(integer - Recommended)` The quote pair Unified Cryptoasset ID.
- `quote_id:` `(integer - Recommended)` The base pair Unified Cryptoasset ID.
- `last_price:` `(decimal - Mandatory)` Last transacted price of base currency based on given quote currency
- `base_volume:` `(decimal - Mandatory)` 24-hour trading volume denoted in BASE currency
- `quote_volume:` `(decimal - Mandatory)` 24 hour trading volume denoted in QUOTE currency
- `isFrozen:` `(integer - Recommended)` Indicates if the market is currently enabled (0) or disabled (1).

<h3 id="endpoint-a2-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint A3

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coinmarketcap/orderbook/TOMO_USDT
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coinmarketcap/orderbook/TOMO_USDT",
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

	url := "https://dex.tomochain.com/api/coinmarketcap/orderbook/TOMO_USDT"

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

url = URI("https://dex.tomochain.com/api/coinmarketcap/orderbook/TOMO_USDT")

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

conn.request("GET", "/api/coinmarketcap/orderbook/TOMO_USDT")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coinmarketcap/orderbook/TOMO_USDT")
  .asString();
```

`GET /api/coinmarketcap/orderbook/{market_pair}`

The order book endpoint is to provide a complete level 2 order book (arranged by best asks/bids) with full depth returned for a given market pair.

**Parameters**

- `market_pair:` `(string - Mandatory)` A pair such as `TOMO_USDT`
- `depth:` `(int - Recommended(used to calculate liquidity score for rankings))` Orders depth quantity: [0,5,10,20,50,100,500]. Not defined or 0 = full order book. Depth = 100 means 50 for each bid/ask side.
- `level:` `(int - Recommended (used to calculate liquidity score for rankings))` Level 1 – Only the best bid and ask. Level 2 – Arranged by best bids and asks. Level 3 – Complete order book, no aggregation.

**Returns**

- `timestamp:` `(timestamp - Mandatory)` Unix timestamp in milliseconds for when the last updated time occurred.
- `bids:` `(decimal - Mandatory)` An array containing 2 elements. The offer price and quantity for each bid order.
- `asks:` `(decimal - Mandatory)` An array containing 2 elements. The ask price and quantity for each ask order.

<h3 id="endpoint-a3-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|market_pair|path|string|true|A pair such as 'TOMO_USDT'|
|depth|query|number|false|Orders depth quantity [0,10,20,50,100,500]. Depth 100 means 50 for each bid/ask side. Default full orderbook.|
|level|query|number|false|Level 1 - Only the best bid and ask. Level 2 - Arranged by best bids and asks. Level 3 - Complete order book, no aggregation.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|level|1|
|level|2|
|level|3|

<h3 id="endpoint-a3-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint A4

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coinmarketcap/trades/TOMO_USDT
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coinmarketcap/trades/TOMO_USDT",
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

	url := "https://dex.tomochain.com/api/coinmarketcap/trades/TOMO_USDT"

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

url = URI("https://dex.tomochain.com/api/coinmarketcap/trades/TOMO_USDT")

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

conn.request("GET", "/api/coinmarketcap/trades/TOMO_USDT")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coinmarketcap/trades/TOMO_USDT")
  .asString();
```

`GET /api/coinmarketcap/trades/{market_pair}`

The trades endpoint is to return data on all recently completed trades for a given market pair.

**Parameters**

- `market_pair:` `(string - Mandatory)` A pair such as `TOMO_USDT`

**Returns**

- `trade_id:` `(integer - Mandatory)` A unique ID associated with the trade for the currency pair transaction. Note: Unix timestamp does not qualify as trade_id.
- `price:` `(decimal - Mandatory)` Last transacted price of base currency based on given quote currency.
- `base_volume:` `(decimal - Mandatory)` Transaction amount in BASE currency.
- `quote_volume:` `(decimal - Mandatory)` Transaction amount in QUOTE currency.
- `timestamp:` `(timestamp - Mandatory)` Unix timestamp in milliseconds for when the transaction occurred.
- `type:` `(string - Mandatory)` Used to determine whether or not the transaction originated as a buy or sell. Buy – Identifies an ask was removed from the order book. Sell – Identifies a bid was removed from the order book.

<h3 id="endpoint-a4-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|market_pair|path|string|true|A pair such as 'TOMO_USDT'|

<h3 id="endpoint-a4-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="tomox-relayer-apis-coingecko">CoinGecko</h1>

CoinGecko's Ideal API Endpoints

## Endpoint 1 - details on cryptoassets traded on an exchange.

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coingecko/pairs
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coingecko/pairs",
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

	url := "https://dex.tomochain.com/api/coingecko/pairs"

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

url = URI("https://dex.tomochain.com/api/coingecko/pairs")

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

conn.request("GET", "/api/coingecko/pairs")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coingecko/pairs")
  .asString();
```

`GET /api/coingecko/pairs`

The endpoint provides a summary on cryptoasset trading pairs available on the exchange.

**Returns**

 - `ticker_id:` `(string - Mandatory)` Identifier of a ticker with delimiter to separate base/target, eg. BTC_ETH 

 - `base:` `(string - Mandatory)` Symbol/currency code of a the base cryptoasset, eg. BTC

 - `target:` `(string - Mandatory)` Symbol/currency code of the target cryptoasset, eg. ETH

<h3 id="endpoint-1---details-on-cryptoassets-traded-on-an-exchange.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint 2 - market related statistics for all markets for the last 24 hours.

> Code samples

```shell
curl --request GET \
  --url https://dex.tomochain.com/api/coingecko/tickers
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coingecko/tickers",
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

	url := "https://dex.tomochain.com/api/coingecko/tickers"

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

url = URI("https://dex.tomochain.com/api/coingecko/tickers")

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

conn.request("GET", "/api/coingecko/tickers")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coingecko/tickers")
  .asString();
```

`GET /api/coingecko/tickers`

The endpoint provides 24-hour pricing and volume information on each market pair available on an exchange.

**Returns**

 - `ticker_id:` `(string - Mandatory)` Identifier of a ticker with delimiter to separate base/target, eg. BTC_ETH 

 - `base_currency:` `(string - Mandatory)` Symbol/currency code of base pair, eg. BTC

 - `target_currency:` `(string - Mandatory)` Symbol/currency code of target pair, eg. ETH

 - `last_price:` `(decimal - Mandatory)` Last transacted price of base currency based on given target currency

 - `base_volume:` `(decimal - Mandatory)` 24 hour trading volume in base pair volume

 - `target_volume:` `(decimal - Mandatory)` 24 hour trading volume in target pair volume

 - `bid:` `(decimal - Mandatory)` Current highest bid price

 - `ask:` `(decimal - Mandatory)` Current lowest ask price
 
 - `high:` `(decimal - Mandatory)` Rolling 24-hours highest transaction price

 - `low:` `(decimal - Mandatory)` Rolling 24-hours lowest transaction price

<h3 id="endpoint-2---market-related-statistics-for-all-markets-for-the-last-24-hours.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint 3 - order book depth of any given trading pair, split into two different arrays for bid and ask orders.

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/coingecko/orderbook?ticker_id=TOMO_USDT'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coingecko/orderbook?ticker_id=TOMO_USDT",
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

	url := "https://dex.tomochain.com/api/coingecko/orderbook?ticker_id=TOMO_USDT"

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

url = URI("https://dex.tomochain.com/api/coingecko/orderbook?ticker_id=TOMO_USDT")

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

conn.request("GET", "/api/coingecko/orderbook?ticker_id=TOMO_USDT")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coingecko/orderbook?ticker_id=TOMO_USDT")
  .asString();
```

`GET /api/coingecko/orderbook`

The endpoint is to provide order book information with at least depth = 100 (50 each side) returned for a given market pair/ticker. 

**Returns**

 - `ticker_id:` `(string - Mandatory)` A pair such as "BTC_ETH", with delimiter between different cryptoassets

 - `timestamp:` `(timestamp - Recommended)` Unix timestamp in milliseconds for when the last updated time occurred.

 - `bids:` `(decimal - Mandatory)` An array containing 2 elements. The offer price and quantity for each bid order

 - `asks:` `(decimal - Mandatory)` An array containing 2 elements. The ask price and quantity for each ask order

<h3 id="endpoint-3---order-book-depth-of-any-given-trading-pair,-split-into-two-different-arrays-for-bid-and-ask-orders.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ticker_id|query|string|true|A ticker such as "BTC_ETH", with delimiter between different cryptoassets|
|depth|query|integer|false|Orders depth quantity: [0, 100, 200, 500...]. 0 returns full depth. Depth = 100 means 50 for each bid/ask side.|

<h3 id="endpoint-3---order-book-depth-of-any-given-trading-pair,-split-into-two-different-arrays-for-bid-and-ask-orders.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

## Endpoint 4 - historical trade data for any given trading pair.

> Code samples

```shell
curl --request GET \
  --url 'https://dex.tomochain.com/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy'
```

```javascript--node
var http = require("https");

var options = {
  "method": "GET",
  "hostname": "dex.tomochain.com",
  "port": null,
  "path": "/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy",
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

	url := "https://dex.tomochain.com/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy"

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

url = URI("https://dex.tomochain.com/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy")

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

conn.request("GET", "/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy")

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

```java
HttpResponse<String> response = Unirest.get("https://dex.tomochain.com/api/coingecko/historical_trades?ticker_id=TOMO_USDT&type=buy")
  .asString();
```

`GET /api/coingecko/historical_trades`

The endpoint is used to return data on historical completed trades for a given market pair.

**Returns**

 - `ticker_id:` `(integer - Mandatory)` A unique ID associated with the trade for the currency pair transaction

 - `price:` `(decimal - Mandatory)` Transaction price in base pair volume.

 - `base_volume:` `(decimal - Mandatory)` Transaction amount in base pair volume.

 - `target_volume:` `(decimal - Mandatory)` Transaction amount in target pair volume.
 
 - `trade_timestamp:` `(timestamp - Mandatory)` Unix timestamp in milliseconds for when the transaction occurred.

 - `type:` `(string - Mandatory)` Used to determine the type of the transaction that was completed.

<h3 id="endpoint-4---historical-trade-data-for-any-given-trading-pair.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ticker_id|query|string|true|A ticker such as "BTC_ETH", with delimiter between different cryptoassets|
|type|query|string|true|To indicate nature of trade - buy/sell|
|limit|query|integer|false|Number of historical trades to retrieve from time of query. [0, 200, 500...]. 0 returns full history.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|buy|
|type|sell|

<h3 id="endpoint-4---historical-trade-data-for-any-given-trading-pair.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad Request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|None|
|406|[Not Acceptable](https://tools.ietf.org/html/rfc7231#section-6.5.6)|Not Acceptable|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Server Internal Error|None|

<aside class="success">
This operation does not require authentication
</aside>

