# API Documentation

## Purchase - POST
**Endpoint:** `/api/purchase`

### Request Body
{
    "player": "playername",  // (String) Player name
    "pack": packid,          // (Int) Pack ID
    "order": orderid,        // (Int) Order ID
    "secret": "secret"       // (String) Secret
}

### Response
```json
{
    "message": "Purchase completed successfully", // (String) Beautiful message
    "realised": is_realised_in_minecraft,         // (Boolean) Information if the order was realised in Minecraft
    "status": "success" || "forbidden" || "fail"  // (String) Status of the operation
}
```

### Status
- "success": Everything went smoothly, proceed to realise order.
- "fail": Something is wrong with the values in JSON. Possible error in JSON parsing. Order not proceeded.
- "forbidden": You provided wrong secret. Order not proceeded.

---

## Health Check - GET
**Endpoint:** `/api/health`

### Response
{
    "healthy": true // (Boolean) Always true. If no response that means something is totally wrong. Maybe the server is not working?
}
