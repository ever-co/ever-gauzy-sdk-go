# Ever Gauzy Go SDK

Official Go SDK for the [Ever Gauzy](https://gauzy.co) API, auto-generated using [Microsoft Kiota](https://learn.microsoft.com/en-us/openapi/kiota/).

## Installation

```bash
go get github.com/ever-co/ever-gauzy-sdk-go
```

## Quick Start

```go
package main

import (
	"context"
	"fmt"

	evergauzy "github.com/ever-co/ever-gauzy-sdk-go/pkg/evergauzy"
	auth "github.com/microsoft/kiota-abstractions-go/authentication"
	http "github.com/microsoft/kiota-http-go"
)

func main() {
	authProvider := &auth.AnonymousAuthenticationProvider{}
	adapter, _ := http.NewNetHttpRequestAdapter(authProvider)
	adapter.SetBaseUrl("https://api.gauzy.co")

	client := evergauzy.NewEverGauzyApiClient(adapter)

	// Example: List employees
	employees, _ := client.Api().Employee().Get(context.Background(), nil)
	fmt.Println(employees)
}
```

## Authentication

The Gauzy API supports multiple authentication methods:

- **Bearer Token (JWT)**: For user-authenticated requests
- **API Key**: Via `X-API-Key` header
- **OAuth2**: Authorization code flow

## API Documentation

- **Swagger UI**: https://api.gauzy.co/swg
- **Scalar Docs**: https://api.gauzy.co/docs
- **OpenAPI Spec**: https://api.gauzy.co/swg-json

## Development

```bash
git clone https://github.com/ever-co/ever-gauzy-sdk-go.git
cd ever-gauzy-sdk-go
go mod tidy
go build ./...
go test ./...
```

## SDK Generation

This SDK is auto-generated from the Ever Gauzy OpenAPI specification using Microsoft Kiota.
To regenerate, trigger the "Generate SDK" GitHub Action workflow.

## License

This project is licensed under the [AGPL-3.0](LICENSE) license.

## Links

- [Ever Gauzy](https://gauzy.co)
- [API Documentation](https://docs.gauzy.co)
- [GitHub](https://github.com/ever-co/ever-gauzy)
