# Webhook
> A way for one application to send real-time data to another via HTTP callbacks whenever a specific event occurs.

## ELI5

| Technical Term | Real-World Analogy |
|:-:|:-:|
| Webhook | Giving the pizza shop your phone number so they call you when your order is ready |
| Polling | Calling the pizza shop every 2 minutes to ask "is it ready yet?" |
| Webhook URL | Your phone number — where the notification gets sent |
| Event | The pizza being ready — the thing that triggers the call |
| Payload (JSON data) | What the pizza shop tells you on the call — "your large pepperoni is ready for pickup" |
| POST request | The phone call itself — the delivery method of the message |

## Example

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
