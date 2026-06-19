# API Contract

Draft for team review. MVP scope only.

## Auth

### POST /api/auth/login

Request:
```json
{
  "username": "string",
  "password": "string"
}
```

Response (success, 200):
```json
{
  "token": "jwt-token-string"
}
```

Response (failure, 401):
```json
{
  "error": "Invalid username or password"
}
```

All routes below require an `Authorization: Bearer <token>` header.

## Devices

### GET /api/devices

Returns all devices.

Response (200):
```json
[
  {
    "id": 1,
    "name": "Home Server",
    "ip_address": "192.168.1.10",
    "status": "online",
    "last_checked": "2026-06-19T14:00:00Z",
    "created_at": "2026-06-01T09:00:00Z"
  }
]
```

### POST /api/devices

Adds a new device.

Request:
```json
{
  "name": "Home Server",
  "ip_address": "192.168.1.10"
}
```

Response (201):
```json
{
  "id": 1,
  "name": "Home Server",
  "ip_address": "192.168.1.10",
  "status": "unknown",
  "last_checked": null,
  "created_at": "2026-06-19T14:00:00Z"
}
```

### GET /api/devices/:id

Returns a single device.

Response (200): same shape as one item in GET /api/devices
Response (404): `{ "error": "Device not found" }`

### DELETE /api/devices/:id

Removes a device.

Response (204): no body

## Status

### GET /api/devices/:id/status

Triggers a status check (TCP port check, not ICMP ping, since
ICMP is often blocked on cloud hosts) and returns current status.

Response (200):
```json
{
  "id": 1,
  "status": "online",
  "last_checked": "2026-06-19T14:05:00Z"
}
```

## Open Questions for the Team

- Do we check port 22, port 80, or let the user pick a port per device?
- Token expiry time, how long before login is required again?
- Do we need a /api/auth/register endpoint or are accounts seeded manually for now?
