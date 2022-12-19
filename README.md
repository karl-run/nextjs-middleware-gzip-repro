# Repro for bug that removes compression on any route that middleware copies headers on

## To reproduce:

Install deps:

```bash
yarn
```

Run the server:

```bash
yarn dev
```

Visit `/`:

Observe the header `Accept-Encoding: gzip, deflate, br` on the request. The response has the header `content-encoding: gzip`, compression works.

Visit `/other`:

Observe the header `Accept-Encoding: gzip, deflate, br` on the request. The response does NOT have `content-encoding: gzip`, compression does not work.
