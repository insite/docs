# How to generate an access token with a long lifetime

By default, API access tokens expire after 24 hours. For automated processes, scheduled tasks, or long-running integrations, you can generate a token with an extended lifetime by invoking a specific endpoint with your API Client Secret.

#### Endpoint

```
POST /v2/{partition}/security/tokens/generate
```

#### Request Body

| Property   | Type    | Description               |
| ---------- | ------- | ------------------------- |
| `Secret`   | string  | Your API client secret    |
| `Lifetime` | integer | Token lifetime in seconds |

#### Common Lifetime Values

| Duration | Seconds  |
| -------- | -------- |
| 1 hour   | 3600     |
| 1 day    | 86400    |
| 30 days  | 2592000  |
| 1 year   | 31536000 |

#### Example (PowerShell)

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

#### Response

A successful request returns a JSON object containing your access token:

```json
{
    "AccessToken": "eyJhbGciOiJIUzI1NiIs...",
    "TokenType": "Bearer",
	  "ExpiresIn": 31536000,
    "Lifetime": "31,536,000 seconds (~52 weeks)"
}
```

#### Security considerations

* Remember to store long-lived tokens securely
* Use the shortest lifetime that meets your requirements
* Rotate tokens periodically, even before they expire
* Revoke tokens immediately if compromised
