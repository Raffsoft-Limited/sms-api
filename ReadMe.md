Here's the markdown documentation for the given API:

---

# Send SMS API

This API endpoint allows you to send an SMS message through the system.

## Endpoint

```
GET http://ems.raffsoft.com/api/sendsms/
```

## Query Parameters

| Parameter       | Type   | Description                                                              |
|-----------------|--------|--------------------------------------------------------------------------|
| `sender`        | string | The name or identifier of the sender.                                     |
| `message`       | string | The content of the SMS message to be sent.                                |
| `recipient`     | string | The phone number of the recipient (in international format).              |
| `account`       | string | The account ID associated with the sender.                                |
| `authorization` | string | The authorization token required to authenticate the request.             |

## Example Request

```http
GET http://ems.raffsoft.com/api/sendsms/?sender=SenderId&message=Hello%20World&recipient=256700000000&account=12345&authorization=authorization_token
```

## Example Response

```json
{
    "recipient": "256700000000",
    "response": "ybs_autocreate_status=OK"
}
```

## Error Responses

### Invalid Authorization

```json
{
  "error": "Invalid authorization token."
}
```

### Missing Parameters

```json
{
  "error":  "Required parameter is missing."
}
```

### Invalid Phone Number

```json
{
  "error": "Invalid phone number format."
}
```

## Notes

- Ensure the phone number is in the correct international format.
- The `authorization` token should be valid and active.
- The `message` content should be URL-encoded to avoid issues with special characters.


---

This documentation should help you understand how to interact with the Send SMS API and handle potential responses and errors.
