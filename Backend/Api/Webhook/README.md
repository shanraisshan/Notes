# Webhook
> A webhook is a way for one application to send real-time data to another application whenever a specific event occurs. Instead of your app continuously asking ("polling") SendGrid for updates, SendGrid can push data to your app when something happens — like an email being delivered, opened, clicked, bounced, etc.

# Example

### Savyour
https://affiliates.savyour.com/orders
```
{
  order_id: 123,
  amount: 455
}
````

### Sendgrid
SendGrid uses webhooks to notify your server about email events. The specific webhook is called the Event Webhook.

🔁 How it works:
- You provide a webhook URL (an API endpoint on your server) to SendGrid.
- SendGrid monitors your email activity.
- When an event occurs (e.g., email delivered, opened, clicked, bounced), it sends a POST request with event data to your webhook URL in JSON format.
- Your server receives this data and can log it, trigger workflows, update user status, etc.
