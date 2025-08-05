# EmailJS Setup Guide

To make your contact form functional and send emails to your inbox, follow these steps:

## Step 1: Create EmailJS Account

1. Go to [EmailJS.com](https://www.emailjs.com/) and sign up for a free account
2. Verify your email address

## Step 2: Create Email Service

1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" (or your preferred email provider)
4. Connect your email account (deepanshujaat309@gmail.com)
5. Note down the **Service ID** (you'll need this)

## Step 3: Create Email Template

1. Go to "Email Templates" in your dashboard
2. Click "Create New Template"
3. Use this template:

**Template Name:** Contact Form Template

**Subject:** New Contact Form Message from {{from_name}}

**Content:**
```
Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio contact form.
```

4. Save the template and note down the **Template ID**

## Step 4: Update Your Code

1. Open `script.js` in your portfolio
2. Replace `"YOUR_USER_ID"` with your actual EmailJS User ID
3. Replace `'service_id'` with your Service ID
4. Replace `'template_id'` with your Template ID

### Example:
```javascript
// Initialize EmailJS
(function() {
    emailjs.init("abc123def456"); // Your actual User ID
})();

// In submitForm function:
emailjs.send('service_abc123', 'template_xyz789', {
    from_name: data.name,
    from_email: data.email,
    subject: data.subject,
    message: data.message,
    to_email: 'deepanshujaat309@gmail.com'
})
```

## Step 5: Test Your Form

1. Open your portfolio in a browser
2. Fill out the contact form
3. Submit the form
4. Check your email inbox for the message

## Troubleshooting

- Make sure all IDs are correct
- Check browser console for any errors
- Verify your email service is properly connected
- Ensure your template variables match the ones in the code

## Security Note

The EmailJS User ID is public and safe to include in your code. The service uses your email service credentials to send emails on your behalf.

## Free Plan Limits

EmailJS free plan includes:
- 200 emails per month
- Basic email templates
- Gmail, Outlook, and other email services

This should be sufficient for a portfolio website. 