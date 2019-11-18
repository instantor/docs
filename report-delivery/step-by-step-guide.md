---
description: >-
  Instantor has two ways of delivering a report to you, using a HTTPS POST
  request and / or delivery to your SFTP server.
---

# Delivery methods

### HTTPS delivery

Using the Product Key and Decryption key, you will be able to receive the reports to your specified endpoint and decrypt them. [Instantor API](https://www.instantor.com/api/doc#api-download) provides all the necessary functionality for decrypting the payload, and are available for .NET, Java and PHP.

#### Environments and Callback URLs

You are required to provide Instantor [tech support](mailto:tech@instantor.com) with atleast one Callback URL. Instantor will configure that Callback URL for your production environment. You can ask Instantor to configure any number of environments \(production environment, or staging, or test, etc.\) for you, including a unique Callback URL for each environment. E.g. if a client would like to receive reports from their test-environment to a Callback URL associated to that test-environment. Please read more in the [Identify your customer section](../javascript-api/.userparam.md#special-purpose-keys) on how to specify the environment in your webpage integration.

### Expected response

After data delivery and decryption, the client is required to respond to the original HTTPS request with plain text message in form of`OK: <msg_id>`, where `<msg_id>`  is unique identifier for that report and is sent as a POST parameter with key msg\_id.

#### Example: 

```text
...source=Product-Key&msg_id=msg-154c798aa69-1463637551721&action=report%2Fuser%2Fdata&encryption=B64%2FMD5%2FAES%2FCBC%2FPKCS5&payload=fLaaLEvgWN9leASb0g3TNZx4yp0D4yjFcnUNpOgsIHJH9...
```

#### Expected response:

```text
OK: msg-154c798aa69-1463637551721
```

### SDK to receive reports

#### Java SDK 

You can download the latest version of the Instantor Java SDK here: 

[https://www.instantor.com/api/doc/static/instantor-api-0.4.5-java.zip](https://www.instantor.com/api/doc/static/instantor-api-0.4.5-java.zip)

#### PHP SDK

You can download the latest version of the Instantor PHP SDK here:

[https://www.instantor.com/api/doc/static/instantor-api-php-0.1.4.zip](https://www.instantor.com/api/doc/static/instantor-api-php-0.1.4.zip)

[https://www.instantor.com/api/doc/static/instantor-api-php-7.zip](https://www.instantor.com/api/doc/static/instantor-api-php-7.zip)

#### .NET API 

You can download the latest version of the Instantor .NET API here

[https://www.instantor.com/api/doc/static/instantor-api-net-0.5.zip](https://www.instantor.com/api/doc/static/instantor-api-net-0.5.zip)

### SFTP delivery

Reports can be delivered to your server by SFTP. Please provide an endpoint and credentials so that we can configure our system appropriately.   
  
You are required to host the SFTP server yourself. 

{% hint style="info" %}
This delivery method is mandatory if you are receiving a human-readable PDF report instead of a JSON file.
{% endhint %}

