# CustomerPortal

## Overview

### Available Operations

* [GetPortalExternalID](#getportalexternalid) - Create a customer portal session

## GetPortalExternalID

Generate a dashboard URL/token for a customer to access their billing information

### Example Usage

<!-- UsageSnippet language="go" operationID="get_/portal/{external_id}" method="get" path="/portal/{external_id}" -->
```go
package main

import(
	"context"
	gosdktemp "github.com/flexprice/go-sdk-temp"
	"log"
)

func main() {
    ctx := context.Background()

    s := gosdktemp.New(
        "https://api.example.com",
        gosdktemp.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.CustomerPortal.GetPortalExternalID(ctx, "<id>")
    if err != nil {
        log.Fatal(err)
    }
    if res != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                | Type                                                     | Required                                                 | Description                                              |
| -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| `ctx`                                                    | [context.Context](https://pkg.go.dev/context#Context)    | :heavy_check_mark:                                       | The context to use for the request.                      |
| `externalID`                                             | *string*                                                 | :heavy_check_mark:                                       | Customer External ID                                     |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*components.DtoPortalSessionResponse](../../models/components/dtoportalsessionresponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400, 404                      | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |