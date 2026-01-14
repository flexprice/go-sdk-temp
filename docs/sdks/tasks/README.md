# Tasks

## Overview

### Available Operations

* [GetTasks](#gettasks) - List tasks
* [PostTasks](#posttasks) - Create a new task
* [GetTasksResult](#gettasksresult) - Get task processing result
* [GetTasksID](#gettasksid) - Get a task
* [GetTasksIDDownload](#gettasksiddownload) - Download task export file
* [PutTasksIDStatus](#puttasksidstatus) - Update task status

## GetTasks

List tasks with optional filtering

### Example Usage

<!-- UsageSnippet language="go" operationID="get_/tasks" method="get" path="/tasks" -->
```go
package main

import(
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

    res, err := s.Tasks.GetTasks(ctx, operations.GetTasksRequest{})
    if err != nil {
        log.Fatal(err)
    }
    if res != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                | Type                                                                     | Required                                                                 | Description                                                              |
| ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------------ |
| `ctx`                                                                    | [context.Context](https://pkg.go.dev/context#Context)                    | :heavy_check_mark:                                                       | The context to use for the request.                                      |
| `request`                                                                | [operations.GetTasksRequest](../../models/operations/gettasksrequest.md) | :heavy_check_mark:                                                       | The request object to use for the request.                               |
| `opts`                                                                   | [][operations.Option](../../models/operations/option.md)                 | :heavy_minus_sign:                                                       | The options for this request.                                            |

### Response

**[*components.DtoListTasksResponse](../../models/components/dtolisttasksresponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400                           | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |

## PostTasks

Create a new task for processing files asynchronously

### Example Usage

<!-- UsageSnippet language="go" operationID="post_/tasks" method="post" path="/tasks" -->
```go
package main

import(
	"context"
	gosdktemp "github.com/flexprice/go-sdk-temp"
	"github.com/flexprice/go-sdk-temp/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := gosdktemp.New(
        "https://api.example.com",
        gosdktemp.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Tasks.PostTasks(ctx, components.DtoCreateTaskRequest{
        EntityType: components.TypesEntityTypeFeatures,
        FileType: components.TypesFileTypeJSON,
        FileURL: "https://juicy-fundraising.biz/",
        TaskType: components.TypesTaskTypeImport,
    })
    if err != nil {
        log.Fatal(err)
    }
    if res != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                          | Type                                                                               | Required                                                                           | Description                                                                        |
| ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `ctx`                                                                              | [context.Context](https://pkg.go.dev/context#Context)                              | :heavy_check_mark:                                                                 | The context to use for the request.                                                |
| `request`                                                                          | [components.DtoCreateTaskRequest](../../models/components/dtocreatetaskrequest.md) | :heavy_check_mark:                                                                 | The request object to use for the request.                                         |
| `opts`                                                                             | [][operations.Option](../../models/operations/option.md)                           | :heavy_minus_sign:                                                                 | The options for this request.                                                      |

### Response

**[*components.DtoTaskResponse](../../models/components/dtotaskresponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400                           | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |

## GetTasksResult

Get the result of a task processing workflow

### Example Usage

<!-- UsageSnippet language="go" operationID="get_/tasks/result" method="get" path="/tasks/result" -->
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

    res, err := s.Tasks.GetTasksResult(ctx, "<id>")
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
| `workflowID`                                             | *string*                                                 | :heavy_check_mark:                                       | Workflow ID                                              |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*components.ModelsTemporalWorkflowResult](../../models/components/modelstemporalworkflowresult.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400, 404                      | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |

## GetTasksID

Get a task by ID

### Example Usage

<!-- UsageSnippet language="go" operationID="get_/tasks/{id}" method="get" path="/tasks/{id}" -->
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

    res, err := s.Tasks.GetTasksID(ctx, "<id>")
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
| `id`                                                     | *string*                                                 | :heavy_check_mark:                                       | Task ID                                                  |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[*components.DtoTaskResponse](../../models/components/dtotaskresponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400, 404                      | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |

## GetTasksIDDownload

Generate a presigned URL for downloading an exported file (supports both Flexprice-managed and customer-owned S3)

### Example Usage

<!-- UsageSnippet language="go" operationID="get_/tasks/{id}/download" method="get" path="/tasks/{id}/download" -->
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

    res, err := s.Tasks.GetTasksIDDownload(ctx, "<id>")
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
| `id`                                                     | *string*                                                 | :heavy_check_mark:                                       | Task ID                                                  |
| `opts`                                                   | [][operations.Option](../../models/operations/option.md) | :heavy_minus_sign:                                       | The options for this request.                            |

### Response

**[map[string]string](../../.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400, 404                      | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |

## PutTasksIDStatus

Update a task's status

### Example Usage

<!-- UsageSnippet language="go" operationID="put_/tasks/{id}/status" method="put" path="/tasks/{id}/status" -->
```go
package main

import(
	"context"
	gosdktemp "github.com/flexprice/go-sdk-temp"
	"github.com/flexprice/go-sdk-temp/models/components"
	"log"
)

func main() {
    ctx := context.Background()

    s := gosdktemp.New(
        "https://api.example.com",
        gosdktemp.WithSecurity("<YOUR_API_KEY_HERE>"),
    )

    res, err := s.Tasks.PutTasksIDStatus(ctx, "<id>", components.DtoUpdateTaskStatusRequest{
        TaskStatus: components.TypesTaskStatusCompleted,
    })
    if err != nil {
        log.Fatal(err)
    }
    if res != nil {
        // handle response
    }
}
```

### Parameters

| Parameter                                                                                      | Type                                                                                           | Required                                                                                       | Description                                                                                    |
| ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| `ctx`                                                                                          | [context.Context](https://pkg.go.dev/context#Context)                                          | :heavy_check_mark:                                                                             | The context to use for the request.                                                            |
| `id`                                                                                           | *string*                                                                                       | :heavy_check_mark:                                                                             | Task ID                                                                                        |
| `body`                                                                                         | [components.DtoUpdateTaskStatusRequest](../../models/components/dtoupdatetaskstatusrequest.md) | :heavy_check_mark:                                                                             | Status update                                                                                  |
| `opts`                                                                                         | [][operations.Option](../../models/operations/option.md)                                       | :heavy_minus_sign:                                                                             | The options for this request.                                                                  |

### Response

**[*components.DtoSuccessResponse](../../models/components/dtosuccessresponse.md), error**

### Errors

| Error Type                    | Status Code                   | Content Type                  |
| ----------------------------- | ----------------------------- | ----------------------------- |
| sdkerrors.ErrorsErrorResponse | 400, 404                      | application/json              |
| sdkerrors.ErrorsErrorResponse | 500                           | application/json              |
| sdkerrors.APIError            | 4XX, 5XX                      | \*/\*                         |