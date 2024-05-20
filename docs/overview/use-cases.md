### Endpoints

#### Fetch Account Information

**GET /auth/get**

This endpoint retrieves account information for the authenticated user. It's useful for applications that need to display or process user account details.

**Request:**

- Method: `GET`
- URL: `/auth/get`
- Headers: 
  - `Authorization: Bearer YOUR_API_KEY`

**Response:**

```json
{
  "account_id": "123456789",
  "account_name": "John Doe",
  "account_balance": 1000.50,
  "account_currency": "USD",
  "account_status": "active"
}
```

**Example:**

```bash
curl -X GET http://localhost:3000/auth/get -H "Authorization: Bearer YOUR_API_KEY"
```

**Description:**

When this endpoint is called, the service will respond with detailed account information including the account ID, name, balance, currency, and status.

#### Search for Micro-Deposit Verification Updates

**GET /bank_transfer/event/list**

This endpoint searches for updates on the statuses of micro-deposit verifications. It is useful for verifying the status of small test deposits made to a bank account to confirm account ownership.

**Request:**

- Method: `GET`
- URL: `/bank_transfer/event/list`
- Headers: 
  - `Authorization: Bearer YOUR_API_KEY`

**Response:**

```json
{
  "events": [
    {
      "event_id": "evt_1",
      "status": "verified",
      "timestamp": "2024-05-20T14:00:00Z"
    },
    {
      "event_id": "evt_2",
      "status": "pending",
      "timestamp": "2024-05-20T14:05:00Z"
    }
  ]
}
```

**Example:**

```bash
curl -X GET http://localhost:3000/bank_transfer/event/list -H "Authorization: Bearer YOUR_API_KEY"
```

**Description:**

When this endpoint is called, the service will respond with a list of micro-deposit verification events, including event IDs, statuses, and timestamps.

#### Get Updates on Micro-Deposit Verification Statuses

**GET /bank_transfer/event/sync**

This endpoint retrieves updates on the statuses of micro-deposit verifications. It's intended for synchronizing the latest verification status updates with your application.

**Request:**

- Method: `GET`
- URL: `/bank_transfer/event/sync`
- Headers: 
  - `Authorization: Bearer YOUR_API_KEY`

**Response:**

```json
{
  "updates": [
    {
      "update_id": "upd_1",
      "status": "verified",
      "timestamp": "2024-05-20T14:10:00Z"
    },
    {
      "update_id": "upd_2",
      "status": "failed",
      "timestamp": "2024-05-20T14:15:00Z"
    }
  ]
}
```

**Example:**

```bash
curl -X GET http://localhost:3000/bank_transfer/event/sync -H "Authorization: Bearer YOUR_API_KEY"
```

**Description:**

When this endpoint is called, the service will respond with the latest updates on micro-deposit verification statuses, including update IDs, statuses, and timestamps.