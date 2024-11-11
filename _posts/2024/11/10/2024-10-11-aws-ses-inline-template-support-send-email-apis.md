---
title: "Amazon SES adds inline template support to send email APIs"
published: true
---

**Amazon SES** adds inline template support

## Introduction

Posted on: Aug 4, 2024

Amazon Simple Email Service (SES) now allows customers to provide email templates directly within the SendBulkEmail or SendEmail API request. SES will use ... More on:

Link to AWS post: [Click here](https://aws.amazon.com/about-aws/whats-new/2024/11/amazon-ses-inline-template-support-send-email-apis/)
Link to AWS doc: [Click here](https://docs.aws.amazon.com/ses/latest/dg/send-personalized-email-api.html)

---

### Example Usage

- Templates:

1. Stored template code example

```
{
    "FromEmailAddress": "Mary Major <mary.major@example.com>",
    "Destination": {
        "ToAddresses": [
            "alejandro.rosalez@example.com", "jimmy.jet@example.com"
        ]
    },
    "Content": {
        "Template": {
            "TemplateName": "MyTemplate",
            "TemplateData": "{ \"name\":\"Alejandro\", \"favoriteanimal\": \"alligator\" }"
        }
    },
    "ConfigurationSetName": "ConfigSet"
}  
```

2. Inline template code example

```
{
    "FromEmailAddress": "Mary Major <mary.major@example.com>",
    "Destination": {
        "ToAddresses": [
            "alejandro.rosalez@example.com", "jimmy.jet@example.com"
        ]
    },
    "Content": {
        "Template": {
            "TemplateContent": {
                "Subject": "Greetings, {{name}}!",
                "Text": "Dear {{name}},\r\nYour favorite animal is {{favoriteanimal}}.",
                "Html": "<h1>Hello {{name}},</h1><p>Your favorite animal is {{favoriteanimal}}.</p>"
            },
            "TemplateData": "{ \"name\":\"Alejandro\", \"favoriteanimal\": \"alligator\" }"
        }
    },
    "ConfigurationSetName": "ConfigSet"
}
```
