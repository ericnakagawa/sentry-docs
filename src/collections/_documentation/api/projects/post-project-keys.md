---
title: 'Create a new Client Key'
---

POST /api/0/projects/_{organization_slug}_/_{project_slug}_/keys/

: Create a new client key bound to a project. The key’s secret and public key are generated by the server.

  <table class="table"><tbody valign="top"><tr><th>Path Parameters:</th><td><ul><li><strong>organization_slug</strong> (<em>string</em>) – the slug of the organization the client keys belong to.</li><li><strong>project_slug</strong> (<em>string</em>) – the slug of the project the client keys belong to.</li></ul></td></tr><tr><th>Parameters:</th><td><strong>name</strong> (<em>string</em>) – the name for the new key.</td></tr><tr><th>Method:</th><td>POST</td></tr><tr><th>Path:</th><td>/api/0/projects/<em>{organization_slug}</em>/<em>{project_slug}</em>/keys/</td></tr></tbody></table>

## Example

```http
POST /api/0/projects/the-interstellar-jurisdiction/pump-station/keys/ HTTP/1.1
Authorization: Bearer {base64-encoded-key-here}
Host: app.getsentry.com
Content-Type: application/json

{
  "name": "Fabulous Key"
}
```

```http
HTTP/1.1 201 CREATED
Allow: GET, POST, HEAD, OPTIONS
Content-Language: en
Content-Length: 811
Content-Type: application/json
Vary: Accept-Language, Cookie
X-Content-Type-Options: nosniff
X-Frame-Options: deny
X-Xss-Protection: 1; mode=block

{
  "name": "Fabulous Key",
  "projectId": 2,
  "secret": "023f204141eb45f1bd95795658106896",
  "label": "Fabulous Key",
  "dsn": {
    "cdn": "https://sentry.io/js-sdk-loader/1d98e4fa473541f29018fb43a2974cd2.min.js",
    "minidump": "https://sentry.io/api/2/minidump/?sentry_key=1d98e4fa473541f29018fb43a2974cd2",
    "public": "https://1d98e4fa473541f29018fb43a2974cd2@sentry.io/2",
    "secret": "https://1d98e4fa473541f29018fb43a2974cd2:023f204141eb45f1bd95795658106896@sentry.io/2",
    "security": "https://sentry.io/api/2/security/?sentry_key=1d98e4fa473541f29018fb43a2974cd2",
    "csp": "https://sentry.io/api/2/csp-report/?sentry_key=1d98e4fa473541f29018fb43a2974cd2"
  },
  "public": "1d98e4fa473541f29018fb43a2974cd2",
  "rateLimit": null,
  "dateCreated": "2018-08-22T18:23:56.910Z",
  "id": "1d98e4fa473541f29018fb43a2974cd2",
  "isActive": true
}
```