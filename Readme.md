This package is modification of https://github.com/projectdiscovery/expirablelru and "container/list" packages.


LRU cache package for golang with generic and expiry support.

### How to install package
```
go get github.com/aaabhilash97/lru
```

### Usage 

```go
package main

import (
    "github.com/aaabhilash97/lru"
    "fmt"
)

func main() {
    var cache *lru.Cache[string, string]
    cache = lru.NewLRU(100, evictCallback, time.Minute*30, time.Minute*45)

    _ = cache.Add("key", "text")
    text, ok := cache.Get(key)
    fmt.Println(text)
}
```