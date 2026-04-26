# Task 1 — Intercept Reminder Creation Request in Habit

## Objective

Intercept the request for creating a **reminder** in a **habit** and document the full **Request–Response** cycle.

The request was intercepted and analyzed using **Charles Proxy**.

---

## Tool Used

- **Charles Proxy** — used to capture and inspect the HTTP request and response
- **Mobile application** — used as the source of user actions
- **Wi-Fi connection** — used for traffic interception during testing

---

## Main Request Information

| Field | Value |
|---|---|
| **URL** | `https://ultiself.com/api/commands/reminders` |
| **Method** | `POST` |
| **Status** | Complete |
| **Response Code** | `200 OK` |
| **Content-Type** | `application/json` |
| **Protocol** | `HTTP/2.0` |
| **SSL** | `TLSv1.3 (TLS_AES_256_GCM_SHA384)` |

---

## Request Body

```json
{
  "time_day_reminders": {
    "is_notify_sms": false,
    "date": "1756397165.296375",
    "is_on": true,
    "selected_days": [],
    "is_notify_push": true,
    "time": "6:06 PM",
    "is_every_day": true,
    "habit_id": 165829
  }
}
```

## Response Body 

```json
{
  "success": true,
  "message": "Reminder created successfully",
  "data": {
    "user_id": 8953182,
    "habit_id": 165829,
    "user_habit_id": 5460599,
    "is_every_day": true,
    "is_on": true,
    "time": "6:06 PM",
    "server_time": "12:06",
    "selected_days": [],
    "user_time": "2025-08-28T22:06:19.000000Z",
    "timezone": "+02:00",
    "date": "1756397165.296375",
    "is_notify_push": true,
    "is_notify_sms": false,
    "updated_at": "2025-08-28T16:06:19.000000Z",
    "created_at": "2025-08-28T16:06:19.000000Z",
    "id": 773361,
    "userHabit": {
      "id": 5460599,
      "habit_id": 165829,
      "user_id": 8953182,
      "habit_title": "Cuddling",
      "time_of_day_id": 1,
      "activation_date": "2025-08-28",
      "is_user_created": false,
      "order": 0,
      "frequency_times": 7,
      "days_checked": [
        {
          "day": 0,
          "checked_count": 0,
          "note_id": null
        },
        {
          "day": 1,
          "checked_count": 0,
          "note_id": null
        },
        {
          "day": 2,
          "checked_count": 0,
          "note_id": null
        },
        {
          "day": 3,
          "checked_count": 0,
          "note_id": null
        },
        {
          "day": 4,
          "checked_count": 0,
          "note_id": null
        }
      ],
      "per_day": 2,
      "actionable": null,
      "is_active": true
    }
  }
}
```


