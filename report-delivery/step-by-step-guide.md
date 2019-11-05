---
description: >-
  Instantor has two ways of delivering a report to you, using a HTTP POST
  request and / or delivery to your SFTP server.
---

# Delivery methods

### HTTP delivery

Using the Product Key and Decryption key, you will be able to receive the reports to your specified endpoint and decrypt them. [Instantor API](https://www.instantor.com/api/doc#api-download) provides all the necessary functionality for decrypting the payload, and are available for .NET, Java and PHP.

#### Environments and Callback URLs

You are required to provide Instantor tech support with a **Callback URL**, which Instantor will configure for your integration. 

You can ask Instantor to set any number of environments configured to send reports to any number of callback URLs. 

Parameter 'environment' is used to control the endpoint for delivering data.

```text
 itor.userParam('environment', 'test');
```

{% hint style="info" %}
Most clients require two environments - "production" and "stage", where production is set as the default environment. 
{% endhint %}

### Expected response

After data delivery and decryption, the customer is required to respond to the original HTTP request with plain text message in form of`OK: <msg_id>`, where `<msg_id>`  is unique identifier for that report and is sent as a POST parameter with key msg\_id.

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

{% embed url="https://instantor-api-0.4.5-java.zip" %}



#### PHP SDK

 You can download the latest version of the Instantor PHP SDK here

{% embed url="https://instantor-api-php-0.1.4.zi" %}

{% embed url="https://instantor-api-php-7.zip" %}

#### .NET API 

 You can download the latest version of the Instantor .NET API here

{% embed url="https://instantor-api-net-0.5.zip" %}



### SFTP delivery

Reports can be delivered to your server by SFTP. Please provide an endpoint and credentials so that we can configure our system appropriately.   
  
You are required to host the SFTP server yourself. 

{% hint style="info" %}
This delivery method is mandatory if you are receiving a human-readable PDF report instead of a JSON file.
{% endhint %}

