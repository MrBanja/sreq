# sreq

`sreq` is a simple Go library that provides helper functions for the `net/http` package. It simplifies the process of creating HTTP requests, unmarshalling HTTP responses, and constructing URLs.

## Installation

To install `sreq`, use the following command:

```bash
go get github.com/MrBanja/sreq
```

## Usage

Here's a brief overview of the functions provided by `sreq`:

### NewRequest

`NewRequest` creates a new HTTP request with the given method, URL, and body. The body is an optional JSON-serializable struct.

```go
type User struct {
    Name string `json:"name"`
    Age int `json:"age"`
}
var body = &User{Name: "John", Age: 30}
req, err := sreq.NewRequest(context.TODO(), "GET", "https://example.com", body)
```

### Unmarshal

`Unmarshal` unmarshals the response body into a new instance of the provided type.

```go
type User struct {
    Name string `json:"name"`
    Age int `json:"age"`
}

var body User
err := sreq.Unmarshal(resp, &body)
```

### U

`U` creates a new url.URL instance with the given path appended to the base URL.

```go
u, err := sreq.U("https://example.com/api", "/user/create")
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

`sreq` is released under the MIT License.