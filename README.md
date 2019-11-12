---
description: >-
  A warm welcome to Instantor, we hope to have you up and running with our
  product soon. Please find a description of the Instantor workflow and
  instructions for integration below.
---

# Introduction

Welcome to the Instantor API documentation page! Here you can find all the information on how to integrate with and use the Instantor iFrame on your website. This documentation consists of two parts, the integration of our end-user facing frontend solution into your website and the delivery of our reports to you.

![](.gitbook/assets/how-instantor-works-4steps.png)

The frontend facing solution you will integrate by embedding a code snippet on your website within your loan application flow.

Once a loan applicant has entered the Instantor process, the data collected from the bank will be encrypted and send as HTTP POST request to a customer's predefined endpoint URL. Meaning you will be required to provide a callback URL to Instantor. Once you have received the report in a JSON object, you will be able to use your decision engine based on the data we provide.  

| Glossary |  |
| :--- | :--- |
| Frame / iFrame | The 'widget' integrated into the _customer's_ website, providing access to Instantor's services. |
| End-user | The loan applicant interacting with the frame. |
| Customer | Banks, financial service providers and FinTech's partnering with Instantor. |
| productKey | A unique identifier for your product configuration |
| decryptionKey | A key used to decrypt the report delivered to you |
| Callback URL | An endpoint ****within your IT infrastructure, that can receive the encrypted reports |

### Not already a customer?

Reach out to our team at [our website](https://www.instantor.com/) or [send us an email](mailto:commercial@instantor.com) and we'll happily tell you more about our services.

[commercial@instantor.com](mailto:commercial@instantor.com)

