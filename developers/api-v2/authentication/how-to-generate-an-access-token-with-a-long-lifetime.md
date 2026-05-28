---
description: Generate API access tokens that last longer than the default 24 hours
icon: clock
---

# How to generate an access token with a long lifetime

By default, API access tokens expire after 24 hours. For automated processes, scheduled tasks, or long-running integrations, you can generate a token with an extended lifetime by invoking a specific endpoint with your API Client Secret.

## Endpoint

```text
POST /v2/{partition}/security/tokens/generate
```

## Request Body

| Property   | Type    | Description               |
| ---------- | ------- | ------------------------- |
| `Secret`   | string  | Your API client secret    |
| `Lifetime` | integer | Token lifetime in seconds |

## Common lifetime values

| Duration | Seconds  |
| -------- | -------- |
| 1 hour   | 3600     |
| 1 day    | 86400    |
| 30 days  | 2592000  |
| 1 year   | 31536000 |

## Examples

#### curl (Linux / macOS)

```bash
curl -X POST "https://sandbox-hub.shiftiq.com/v2/e99/security/tokens/generate" \
    -H "Content-Type: application/json" \
    -d '{
        "Secret": "your-api-client-secret",
        "Lifetime": 31536000
    }'
```

#### PowerShell (Windows)

```powershell
$url = "https://sandbox-hub.shiftiq.com/v2/e99/security/tokens/generate"

$json = @'
{
    "Secret": "your-api-client-secret",
    "Lifetime": 31536000
}
'@

curl.exe -X POST $url `
    -H "Content-Type: application/json" `
    -d $json
```

## Response

A successful request returns a JSON object containing your access token:

```json
{
    "AccessToken": "eyJhbGciOiJIUzI1NiIs...",
    "TokenType": "Bearer",
    "ExpiresIn": 31536000,
    "Lifetime": "31,536,000 seconds (~52 weeks)"
}
```

If the secret is invalid or expired, the endpoint returns `401 Unauthorized`. If the requested lifetime is out of the allowed range (1 minute to 1 year), the endpoint returns `400 Bad Request`.

## Secret expiry and token lifetime

A client secret expires 90 days after it is created. However, the lifetime of a generated access token is independent of the secret's expiry.

* A valid secret can generate an access token with a lifetime between 1 minute and 1 year.
* Once generated, an access token remains valid for its full lifetime even if the secret expires afterward.
* An expired secret cannot be used to generate new access tokens.

For example, you can use a secret to generate a one-year token on day 89. The secret expires the next day, but the token continues to work for the full year.

## Security considerations

* A generated token inherits the full permissions of the user account that created it — treat it with the same care as your account credentials
* Remember to store long-lived tokens securely
* Use the shortest lifetime that meets your requirements
* Rotate tokens periodically, even before they expire
* Revoke tokens immediately if compromised
