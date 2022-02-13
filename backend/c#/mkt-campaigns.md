# Marketing Campaigns Mini Service

Let's create a service for the marketing team, so they can run campaigns using the current customer base according to different rules.

First, we should develop a customers service that will allow the customer management, the data structure will look like this:

```
/customer
GET, POST, DELETE

{
    "first_name": "John",
    "last_name": "Doe",
    "email": "jdoe@company.com",
    "credit": 400
}
```

Every time a new customer is created, the marketing service will send a welcome email to the customer. The same behaviour when a customer is deleted, it will send a farewell email and also remove the customer from the list.

Welcome email template:

```
Hi %first_name% %last_name%,
Welcome to our company, we are delighted to have you as a customer!

The Company Team.
```

Farewell email template:

```
Hi %first_name% %last_name%,
We are sorry to see you go, we look forward to having you as customer again in the future.

The Company Team.
```

Instead of sending an email, you can simulate it by logging the email using the console (timestamp, to, email body).

The data structure for the marketing campaign will look like this:

```
/campaign
GET, POST, DELETE

{
    "code": "BC"
    "rule": "credit < 500",
    "message": "Hi %first_name%, come over and check out our new arrivals!"
}
```

For simplicity, campaigns don't expire and also they have 1 rule per campaign.

Campaign rules can be set as follows:
- Credit less than X
- Credit between X and Y
- Credit greater than X

You decide how the rule will be saved on the campaign record, then provide guidance on how to save them correctly at creating a campaign. Rules are based on the customer's credit information only.

When running campaigns, the expected output will be a json response that will show campaigns with the corresponding information ready to be sent:

```
{
   "total_messages": 6,
   "campaigns": [
      {
         "code": "BC",
         "messages": [
            {
               "email": "jdoe@company.com",
               "message": "Hi John, come over and check out our new arrivals!"
            },
            {
               "email": "mfox@company.com",
               "message": "Hi Mark, come over and check out our new arrivals!"
            }
         ]
      },
      {
         "code": "SC",
         "messages": [
            {
               "email": "monicab@company.com",
               "message": "Hi Monica, use this promocode to get a 20% off on your next purchase!"
            },
            {
               "email": "rl2020@company.com",
               "message": "Hi Ralph, use this promocode to get a 20% off on your next purchase!"
            }
         ]
      },
      {
         "code": "PC",
         "messages": [
            {
               "email": "annewo@company.com",
               "message": "Anne, you have to come and see these super offers!"
            },
            {
               "email": "gjam@company.com",
               "message": "Greg, you have to come and see these super offers!"
            }
         ]
      }
   ]
}
```

Remember that one campaign can match 0 to many customers registered.

**Considerations:**
- Solution architecture design will be up to you.
- API URL structure for running campaigns is up to you.
- Validation rules for customers data are up to you.
- It will be a big plus if you deploy the services somewhere in the cloud (heroku, gcloud, aws, azure, etc). It's ok if you just do it locally.
- Use github (or other git repo).
- Programming language: C#.
- Log every API call received, log format is up to you.
- Place a README.md file with instructions in the github repo so that the test can be performed and checked.
