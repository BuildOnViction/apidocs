
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

