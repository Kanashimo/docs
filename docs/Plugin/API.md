# Purchase - POST
/api/purchase

```json
{
    "player": playername, (String)
    "pack": packid, (Int)
    "order": orderid, (Int)
    "secret": secret (String)
}```

Returns

```json
{
    "message": "Zakup zakończony sukcesem", (String) "Beautiful message"
    "realised": is_realised_in_minecraft, (Boolean)
    "status": "success"||"forbidden"||"fail" (String)
}```

"status" has three possible values:
- "succes" Everything went smoothly, proceed to realize order.
- "fail" Something with values is wrong in input JSON. Possible error in JSON parsing. Not proceeded to realize order.
- "forbidden" You provided wrong secret. Not proceeded to realize order.

# Health Check - GET
/api/health

Returns

```json
{
    "healthy": true (Boolean) Always true. If no response that means something is totally wrong. Mayby server is not working?
}```
