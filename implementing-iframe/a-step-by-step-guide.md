---
description: >-
  This page provides step-by-step instructions on how to integrate the Instantor
  Widget into your website. The Widget allows your customers to connect to their
  bank through Instantor.
---

# A step-by-step guide

### Step 1 - Loading **prerequisites** – jQuery library

The Instantor script requires a [jQuery library](http://jquery.com/). You can link it from whatever location suits your needs, either locally cached on your server, or from public CDN \(for example, [from Google's CDN](https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js)\). Example of Google hosted jQuery library:

```javascript
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
```

{% hint style="warning" %}
**Heads-up!**  
Be sure to load the jQuery library using a HTTPS protocol! **jQuery version 1.7+ is a minimal requirement.** 
{% endhint %}

### Step 2 - Link the Instantor script

The Instantor script file needs to be linked in your page. Add the following code-block, corresponding with your market of operations, at the beginning of the`<body>` section of your HTML file:

#### For European markets:

```javascript
<script type="text/javascript" src="
https://frame.euc1.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For Latin American markets:

```javascript
<script type="text/javascript" src="
https://frame.use2.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For Southeast Asian markets:

```javascript
<script type="text/javascript" src="
https://frame.apse1.instantor.com/instantor-0.7.3.min.js
"></script>
```

{% hint style="danger" %}
**IMPORTANT!**

Never copy the script to your server. The script is frequently updated to reflect changes in the process. Caching your own version can lead to unhandled issues.
{% endhint %}

### Step 3 - **Place the Instantor Widget on your website**

The Instantor Widget is essentially an `<iframe>` on your website. The `<iframe>` requires a DOM element in your HTML code where it will get injected.  That can be any block-level HTML element – for example, a `<div>`, or `<section>` element. 

For example, place a `<div>` block-level HTML element with  `id="itor"` inside your HTML:

```markup
<div id="itor"></div>
```

{% hint style="warning" %}
Please, make sure your CSS code is not interfering with the Instantor `<iframe>`, nor with any iframe-containing DOM element – do not limit heights, the script will actively resize the `<iframe>` height to match its inner content height.
{% endhint %}

### Step 4 - Initialize the Instantor object

Once you have linked the script, you'll need to add another code-block to your HTML file, and initialize a new Instantor JavaScript object \(the object\). To successfully initialize the object, you need to pass the **Product Key** you received from Instantor as an argument to the object constructor. You can place the following code-block under the code-block from [Step 3 - Linking the script](a-step-by-step-guide.md#step-3-linking-the-script).

```javascript
<script>
  var itor = new Instantor('Product Key');
</script>
```

{% hint style="warning" %}
Make sure to replace `Product Key` in the example with the the Product key you have received from Instantor. When failing to do so, the Instantor script will fail to load.
{% endhint %}

### Step 5 - Inject information about the customer \(optional\)

To identify a customer in your process, Instantor allows you to inject customer information in the report. You can add as many customer/request-specific information as you need. It will be stored as key-value pairs, and is a free-form, with some special keywords. You may find these user parameters under the **userParam: miscEntryList** section of the report you receive.

{% hint style="info" %}
The following example extends the code-block as mentioned in [Step 4 - Initialize the Instantor object](a-step-by-step-guide.md#step-4-initialize-the-instantor-object).
{% endhint %}

```javascript
<script>
  var itor = new Instantor('Product Key');

  itor.userParam('user_identification', '12345678901');
  itor.userParam('firstName', 'NAME');
  itor.userParam('lastName', 'SURNAME');
  itor.userParam('account', '7890 7890 7890 78');
</script>
```

A list of keys that can be used include: _firstName, lastName, email, account, personal\_id, SSN or personalNumber, DNI and clientNumber._ You can read more about userParam keywords in the [.userParam section](../javascript-api/.userparam.md) of this documentation guide.

{% hint style="warning" %}
**IMPORTANT!**

Once the bank login form is loaded, all additional customer information will be discarded. Make sure you either accept user-entered information before you load the frame, or you have callback function attached to appropriate event \(**displayChange**\) via [.attachEventListener](../javascript-api/.attacheventlistener.md) method.
{% endhint %}

### Step 6 - Load the Instantor Widget

To load the Instantor Widget on your website, make sure the `<itor>` __object has been initialised with the correct product key provided by Instantor. Optionally, as described in step 5, you may injected some customer information using the [.userParam](../javascript-api/.userparam.md). 

{% hint style="info" %}
The best practice is to assign `<div>` element as containing – the `<iframe>` is a block-level element, so it should be avoided injecting it into inline-level element. Use method `load` to start the injector. 
{% endhint %}

```javascript
<script>
  var itor = new Instantor('Product Key');

  itor.userParam('user_identification', '12345678901');
  itor.userParam('firstName', 'NAME');
  itor.userParam('lastName', 'SURNAME');
  itor.userParam('account', '7890 7890 7890 78');

  itor.load('#itor');
</script>
```

{% hint style="danger" %}
Provided target DOM element should be valid [jQuery selector](http://api.jquery.com/category/selectors/). Failing to provide existing DOM element, the injector script will end with error message. Providing a non-empty DOM element will result with content being overwritten by the Instantor`<iframe>`.
{% endhint %}



