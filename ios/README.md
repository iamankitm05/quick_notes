# iOS Quick Notes


### 1. iOS Notification testing 

1. Create a file with name `any_name.apns`  
2. Paste the json below in your apns file 
3. Update the bundle id, message & title 
4. Drag this file in simulator for notification

```json
{
  "aps": {
    "alert": {
      "title": "New Offer Received",
      "body": "Open the app to grab new discount.",
      "sound": "default"
    }
  },
  "gcm.message_id": "123",
  "Simulator Target Bundle": "com.example",
  "type": "new_offer",
  "priority": "high",
  "content_available": true,
  "mutable_content": true,
  "offer_id": "123",
  "offer_description": "🎉 50% off on selected product.",
}
```