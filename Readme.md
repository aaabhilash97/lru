This package is modification of https://github.com/projectdiscovery/expirablelru and "container/list" packages.
Only difference is added generics support, so we can avoid type assertion.

LRU cache package for golang with expiry support using go generics.

### How to install package
```
go get -u github.com/aaabhilash97/lru
```

### Usage 

```go
package main

import (
	"log"
	"time"

	"github.com/aaabhilash97/lru"
)

func evictCallback(key string, value string) {
	log.Println(key, value)
}

func main() {
	var cache *lru.Cache[string, string]
	cache = lru.NewLRU(100, evictCallback, time.Minute*30, time.Minute*45)

	_ = cache.Add("key", "text")
	text, ok := cache.Get("key")
	log.Println(text, ok)
}

```
