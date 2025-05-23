

---

# 📞 Amazon Connect Service Calculator API v 1.8.5

This project provides API endpoints to calculate estimated service costs for Amazon Connect services, manage calculation collections, and update existing calculation entries.

---

## 🔗 Base URL
```
http://localhost:5000
```

---

## 📊 Service Calculations

### 1. Inbound Voice and Video
```http
POST /api/calculations
```
```json
{
  "service_id": 1,
  "country_id": 1,
  "call_type_id": 1,
  "daily_usage": 22,
  "business_days": 22,
  "aht": 22
}
```

### 2. Outbound Voice and Video
```http
POST /api/calculations
```
```json
{
  "service_id": 1,
  "country_id": 616,
  "call_type_id": 2,
  "daily_usage": 22,
  "business_days": 22,
  "aht": 22
}
```

### 3. Messaging and Chat
```http
POST /api/calculations
```
```json
{
  "service_id": 3,
  "chat_usage": 100,
  "sms_usage": 50,
  "apple_messages": 30,
  "whatsapp_messaging": 40,
  "chat_experiences": 20
}
```

### 4. Email
```http
POST /api/calculations
```
```json
{
  "service_id": 4,
  "email_usage": 100
}
```

### 5. Task
```http
POST /api/calculations
```
```json
{
  "service_id": 5,
  "task_usage": 100
}
```

### 6. Case
```http
POST /api/calculations
```
```json
{
  "service_id": 7,
  "case_usage": 100
}
```

### 7. Customer Profile
```http
POST /api/calculations
```
```json
{
  "service_id": 8,
  "cp_daily_azq": 250,
  "cp_daily_ext": 150
}
```

### 8. Guides
```http
POST /api/calculations
```
```json
{
  "service_id": 9,
  "msg_sent": 100
}
```

### 9. Agent Assist
```http
POST /api/calculations
```
```json
{
  "service_id": 10,
  "agent_usage": 1
}
```

### 10. Voice ID
```http
POST /api/calculations
```
```json
{
  "service_id": 11,
  "voiceid_usage": 100
}
```

### 11. Amazon Q in Connect
```http
POST /api/calculations
```
```json
{
  "service_id": 2,
  "chat_azq_usage": 1000,
  "voice_azq_usage": 500
}
```

### 12. Amazon Connect Services
```http
POST /api/calculations
```
```json
{
  "service_id": 12,
  "invoice_acs": 1000,
  "outbound_acs": 1000,
  "chat_usage_acs": 1000,
  "email_acs": 1000,
  "task_acs": 1000,
  "sms_acs": 1000,
  "apple_acs": 1000,
  "whatsapp_acs": 1000,
  "guide_acs": 1000,
  "outcamp_acs": 1000
}
```

### 13. Connect Lens
```http
POST /api/calculations
```
```json
{
  "service_id": 13,
  "cl_voice_calls": 5000003,
  "cl_chat_message": 1000,
  "cl_performance_eval": 100,
  "cl_screen_rec": 1000,
  "cl_external_voice": 3000000,
  "cl_external_connector": 1
}
```

### 14. Forecasting and Scheduling
```http
POST /api/calculations
```
```json
{
  "service_id": 14,
  "agent_forecasted": 100
}
```

---

## 📁 Collection Management

### 1. Create a Collection
```http
POST /api/calculations/collections
```
```json
{
  "collection_name": "Company XYZ"
}
```

### 2. Add Calculation to Collection
```http
POST /api/calculations/collections/add
```
```json
{
  "collection_id": 1,
  "calculation_id": 1
}
```

### 3. Get Calculations from a Collection
```http
GET /api/calculations/collections/1
```

### 4. Get All Collections
```http
GET /api/calculations/collections
```

### 5. Update Collections
```http
PATCH http://localhost:5000/api/calculations/collections/:id
```
```json
{
    "collection_name": "Updated Collection Name"
}
```

### 6. Delete Collections
```http
DELETE http://localhost:5000/api/calculations/collections/:id
```

### 7. Delete Calculation from Collection
```http
DELETE http://localhost:5000/api/calculations/collections/:collection_id/calculation-results/:calculation_id
```
---

## ✏️ Update Calculations (NEW)

Use this endpoint to update an existing calculation. Replace `:id` with your calculation result ID.

```http
PATCH /api/calculations/calculation-results/:id
```
```json
{
  "daily_usage": 25,
  "business_days": 20,
  "aht": 30
}
```

> ⚠️ You **do not need to include** the following fields when updating:
- `service_id`
- `country_id`
- `call_type_id`

## 🗑️ Delete Calculations (NEW)

Use this endpoint to delete an existing calculation. Replace `:id` with your calculation result ID.

```http
DELETE /api/calculations/calculation-results/:id
```

Message if Deleted
```json
{
    "message": "Calculation result deleted successfully"
}
```
**-averi4113**
---


#   a w s c a l c u  
 