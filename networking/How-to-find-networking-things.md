# Overall Path to CKA
[← Back](..)

## How to test a web server/url availability
- `curl`: `curl -v -L <url>`
> [TCP_NODELAY](https://tools.ietf.org/html/rfc6897.html#section-4.4.2)

## How to test a web server/url performance
- `ab`: `ab -k -c 1 -n 10 <url> # -k for keepalive, -c for cuncurrency, -n for num of request`

## How to test a network availability
- `ping`
- `tracerout/tracert`
- `telnet`
- `nc`: `nc -z -v -n <host> <port-range>`
- `nmap`: `-v -A <ip>`
