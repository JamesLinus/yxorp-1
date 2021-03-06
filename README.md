yxorp
=====

A tiny reverse-proxy

*See what I did there?*

Install with `go get github.com/gomicroprojects/yxorp`

Example config JSON file:

    {
        "www.example.com": {
            "TargetURL": "http://localhost:8080/example"
        },
        "www2.example.com": {
            "TargetURL": "http://localhost:8081/",
            "GZ": true
        }
    }

## The idea

Suppose you have now finished a couple of Go projects and you want to deploy them on a server. But you only have one IP address available and want to serve multiple projects under different domains on port 80.

yxorp to the rescue.

It:

* provides a host-based reverse-proxy.
* is configurable with a simple JSON file.
* will act as a normal HTTP reverse proxy.
* bonus: will optionally GZip encode the response.

The core functionality will be accomplished by using the [httputil](http://golang.org/pkg/net/http/httputil/) package. It provides a [ReverseProxy](http://golang.org/pkg/net/http/httputil/#ReverseProxy). No need to reinvent the wheel.

## Starting

Start with [yxorp.go](yxorp.go)

## www.gomicroprojects.com
