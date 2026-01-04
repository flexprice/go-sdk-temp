<!-- Start SDK Example Usage [usage] -->
```go
package main

import (
	"context"
	"github.com/flexprice/go-sdk-temp/v2"
	"github.com/flexprice/go-sdk-temp/v2/models/operations"
	"log"
)

func main() {
	ctx := context.Background()

	s := v2.New(
		"https://api.example.com",
		v2.WithSecurity("<YOUR_API_KEY_HERE>"),
	)

	res, err := s.Addons.GetAddons(ctx, operations.GetAddonsRequest{})
	if err != nil {
		log.Fatal(err)
	}
	if res != nil {
		// handle response
	}
}

```
<!-- End SDK Example Usage [usage] -->