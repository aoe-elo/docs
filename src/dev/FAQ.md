# Frequently Asked Questions (FAQ)

## `cURL error 60: SSL certificate problem: unable to get local issuer certificate` error

Check this answer: <https://stackoverflow.com/a/34883260>

- basically run `scoop install curl`

then set `<scoop_directory>` to the path where `scoop` is installed in your
`php.ini` like the following:

```ini
[curl]
; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
curl.cainfo = "<scoop_directory>\apps\curl\current\bin\curl-ca-bundle.crt"

[openssl]
; The location of a Certificate Authority (CA) file on the local filesystem
; to use when verifying the identity of SSL/TLS peers. Most users should
; not specify a value for this directive as PHP will attempt to use the
; OS-managed cert stores in its absence. If specified, this value may still
; be overridden on a per-stream basis via the "cafile" SSL stream context
; option.
openssl.cafile="<scoop_directory>\apps\curl\current\bin\curl-ca-bundle.crt"
```

## Where does the data exchange happen between front- and backend?

There are some places where data might be leaving the PHP side:

Either directly in the `routes`:

- [`/routes/api.php`](/routes/api.php) our public API for people to query data.

- [`/routes/web.php`](/routes/web.php) our internal API for the frontend to
  query data.

Data is given to the frontend via the
[`Web-Controllers`](/app/Http/Controllers/Web).
