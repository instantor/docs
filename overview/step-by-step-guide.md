---
description: >-
  This page provides step-by-step instructions on how to integrate the Instantor
  iframe into your website.
---

# Step-by-step guide for iFrame

### Step 1 - Loading **prerequisites** – jQuery library

The Instantor script requires a [jQuery library](http://jquery.com/). You can link it from whatever location suits your needs, either locally cached on your server, or from public CDN \(for example, [from Google's CDN](https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js)\). Example of Google hosted jQuery library:

```text
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
```

{% hint style="warning" %}
**Heads-up!**  
Be sure to load the jQuery library using a HTTPS protocol! **jQuery version 1.7+ is a minimal requirement.** 
{% endhint %}

### Step 2 - **Place the Instantor iFrame on your website**

The Instantor iFrame requires a DOM element in your HTML code where it will get injected. That can be any block-level HTML element – for example, a `<div>`, or `<section>` element. 

For example, place a `<div>` block-level HTML element with  `id="itor"` inside your HTML:

```text
<div id="itor"></div>
```

{% hint style="warning" %}
Please, make sure your CSS code is not interfering with the Instantor iframe, nor with any iframe-containing DOM element – do not limit heights, the script will actively resize iframe height to match inner content height.
{% endhint %}

### Step 3 - Linking the script

The Instantor script file needs to be linked in your page. Add the following code-block, corresponding with your market of operations, at the beginning of the`<body>` section of your HTML file:

{% hint style="danger" %}
**IMPORTANT!**

Never copy the script to your server. The script is frequently updated to reflect changes in the process. Caching your own version can lead to unhandled issues.
{% endhint %}

#### For European markets:

```text
<script type="text/javascript" src="
https://frame.euc1.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For Latin American markets:

```text
<script type="text/javascript" src="
https://frame.use2.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For South East Asian markets:

```text
<script type="text/javascript" src="
https://frame.apse1.instantor.com/instantor-0.7.3.min.js
"></script>
```

### Step 4 - Initialize the Instantor object

Once you have linked the script, you'll need to add another code-block to your HTML file, and initialize a new Instantor JavaScript object \(the object\). To successfully initialize the object, you need to pass the **Product Key** you received from Instantor as an argument to the object constructor. You can place the following code-block under the code-block from [Step 3 - Linking the script](step-by-step-guide.md#step-3-linking-the-script).

{% hint style="warning" %}
Make sure to replace `Product Key` in the example with the the Product key you have received from Instantor. When failing to do so, the Instantor script will fail to load.
{% endhint %}

```bash
<script>
try {
  var itor = new Instantor('Product Key');
} catch(err) {}
</script>
```

### Step 5 - Inject information about the end-user \(optional\)

To identify an end-user in your process, Instantor allows you to inject user information in the report. You can add as many user/request-specific information as you need. It will be stored as key-value pairs, and is a free-form, with some special keywords. You may find these user parameters under the **userParam: miscEntryList** section of the report you receive.

{% hint style="info" %}
The following example extends the code-block as mentioned in [Step 4 - Initialize the Instantor object](step-by-step-guide.md#step-4-initialize-the-instantor-object).
{% endhint %}

```bash
<script>
try {
  var itor = new Instantor('Product Key');

  itor.userParam('user_identification', '12345678901');
  itor.userParam('firstName', 'NAME');
  itor.userParam('lastName', 'SURNAME');
  itor.userParam('account', '7890 7890 7890 78');
} catch(err) {}
</script>
```

A list of keys that can be used include: _firstName, lastName, email, account, personal\_id, SSN or personalNumber, DNI and clientNumber._ You can read more about userParam keywords in the [.userParam section](../javascript-api/.userparam.md) of this documentation guide.

{% hint style="warning" %}
**IMPORTANT!**

Once the bank login form is loaded, all additional user information will be discarded. Make sure you either accept user-entered information before you load the frame, or you have callback function attached to appropriate event \(**displayChange**\) via [.attachEventListener](../javascript-api/.attacheventlistener.md) method.
{% endhint %}

### Step 6 - Loading the iFrame

To load the Instantor iFrame on your frame, make sure `<itor>` __object has been initialised with the correct product key provided by Instantor. Optionally, as described in step 5, you may injected some user information using the [.userParam](../javascript-api/.userparam.md). 

{% hint style="info" %}
The best practice is to assign `<div>` element as containing – the iFrame is block-level element, so it should be avoided injecting it into inline-level element. Use method `load` to start the injector. 
{% endhint %}

```bash
<script>
try {
  var itor = new Instantor('Product Key');

  itor.userParam('user_identification', '12345678901');
  itor.userParam('firstName', 'NAME');
  itor.userParam('lastName', 'SURNAME');
  itor.userParam('account', '7890 7890 7890 78');

  itor.load('#itor');
} catch(err) {}
</script>
```

{% hint style="danger" %}
Provided target DOM element should be valid [jQuery selector](http://api.jquery.com/category/selectors/). Failing to provide existing DOM element, the injector script will end with error message. Providing non-empty DOM element will result with content being overwritten by Instantor iframe.
{% endhint %}



























