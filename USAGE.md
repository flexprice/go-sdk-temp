<!-- Start SDK Example Usage [usage] -->
```go
package main

import (
	"context"
	gosdktemp "github.com/flexprice/go-sdk-temp"
	"github.com/flexprice/go-sdk-temp/models/operations"
	"log"
)

func main() {
	ctx := context.Background()

	s := gosdktemp.New(
		"https://api.example.com",
		gosdktemp.WithSecurity("<YOUR_API_KEY_HERE>"),
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