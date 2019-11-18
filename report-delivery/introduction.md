# Delivery introduction

Once the Widget has been implemented on your website the customer can enter the data collection process. The data collection process begins when the customer completes a successful login on their respective online bank interface in the iFrame.

As data is being received from the bank - one or more reports are compiled and sent to you as client as a HTTPS POST request to a pre-defined callback URL. The data report sent is encrypted, which you can decrypt using the decryption key provided to you by Instantor.

A report will be delivered to you even if a process error would occur during the data collection process. The report will state the process error and only in case of a successful data collection process - the status in the data report will be "ok". This process allows you as a client to be aware of any interactions between Instantor and the customer.

The time required for a report to be delivered depends on the amount of data, on the customer's bank account and on the bank interface speed, but the expected time for 12 months of transactions should be under a minute.

