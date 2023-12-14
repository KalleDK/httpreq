HTTPReq for [`libdns`](https://github.com/libdns/libdns)
=======================

[![Go Reference](https://pkg.go.dev/badge/test.svg)](https://pkg.go.dev/github.com/libdns/httpreq)

This package implements the [libdns interfaces](https://github.com/libdns/libdns) for HTTPReq, allowing you to manage DNS records.

Please note that HTTPReq is more or less only used for ACME DNS and therefor only is able to create and delete TXT records

For a server to use it with see [acmeproxy](https://github.com/mdbraber/acmeproxy/tree/master)

Example configuration
----------------------
```go
// Without Auth
p := httpreq.Provider{
    Endpoint: "https://example.com:9090",
}

// With Auth
p := httpreq.Provider{
    Endpoint: "https://example.com:9090",
    Credentials: httpreq.Credentials{
        Username: "admin",
        Password: "password",
    },
}

// With Custom Client
p := httpreq.Provider{
	Endpoint: "https://example.com:9090",
	Credentials: httpreq.Credentials{
		Username: "admin",
		Password: "admin",
	},
	HTTPClient: http.Client{
		Timeout: 10 * time.Second,
	}
}
```
