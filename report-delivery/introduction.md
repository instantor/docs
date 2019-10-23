# Introduction

Once the iFrame has been implemented on your website the end-user can enter the data collection process. The data collection process begins when the end-user completes a succesful login on their respective online bank interface in the iFrame.

As data is being received from the bank - one or more reports are compiled and sent to you as customer as a HTTP POST request to a pre-defined callback URL. The data report sent is encrypted, which you can decrypted using the decryption key provided to you by Instantor.

A report will be delivered to you even if a process error would occur during the data collection process. The report will state the process error and only in case of a successful data collection process - the status in the data report will be "ok". This process allows you as a customer to be aware of any interactions between Instantor and the end-user.

The time required for a report to be delivered depends on the amount of data, on the end-user's bank account and on the bank interface speed, but the expected time for 12 months of transactions should be under a minute.

## Delivery methods

Instantor has two ways of delivering a report to you, using a HTTP POST and delivery to your SFTP server.

### HTTP delivery

Using the Product Key and Decryption key, you will be able to receive the reports to your specified endpoint and decrypt them. [Instantor API](https://www.instantor.com/api/doc#api-download) provides all the necessary functionality for decrypting the payload, and are available for .NET, Java and PHP.

After data delivery and decryption, the customer is required to respond to the original HTTP request with plain text message in form of OK: `<msg_id>`, where `<mesg_id>`  is unique identifier for that report and is sent as a POST parameter with key msg\_id.

### SFTP delivery

