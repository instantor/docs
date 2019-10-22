---
description: >-
  This page provides step-by-step instructions on how to integrate the Instantor
  iframe into your website.
---

# Step-by-step guide for iFrame

### Step 1 - Load **prerequisites** – jQuery library

Instantor script needs some prerequisites for its work – [jQuery library](http://jquery.com/). You can link it from whatever location suits your needs, either locally cached on your server, or from public CDN \(for example, [from Google's CDN](https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js)\).

{% hint style="warning" %}
 **Heads-up!**  
Be sure to load jQuery using HTTPS protocol! You can use your own, local copy, or one provided by CDN \(like in this code snippet example\). **Version 1.7+ is required.** 
{% endhint %}

### Step 2 - **Add** DOM element for the frame

Instantor iFrame requires a DOM element in your HTML code where it will get injected. That can be any block-level HTML element – for example, `<div>`, or `<section>`. This block level HTLM element should contain `id="itor"`

For example, put `<div>` with ID `itor` somewhere in your HTML:

```text
<div id="itor"></div>
```

{% hint style="warning" %}
Please, make sure your CSS code is not interfering with Instantor iframe, nor with iframe-containing DOM element – do not limit heights, the script will actively resize iframe height to match inner content height.
{% endhint %}

### Step 3 - Linking the script

{% hint style="danger" %}
**IMPORTANT!**

Never copy the script to your server. The script is frequently updated to reflect changes in the process. Caching your own version can lead to unhandled issues.
{% endhint %}

Instantor script file needs to be linked in your page. Add the following in the beginning of the`<body>` section of your HTML file:

#### For European markets

```text
<script type="text/javascript" src="
https://frame.euc1.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For Latin American markets

```text
<script type="text/javascript" src="
https://frame.use2.instantor.com/instantor-0.7.3.min.js
"></script>
```

#### For South East Asian markets

```text
<script type="text/javascript" src="
https://frame.apse1.instantor.com/instantor-0.7.3.min.js
"></script>
```

### Step 4 - Initialise Instantor object

Once you have linked the script, you'll need to open new code block, and initialise new Instantor JavaScript object \(the object\).  
To successfully initialise the object, you need to pass Product Key you received from Instantor tech support as an argument to object constructor. 

```bash
<script>
try {
  var itor = new Instantor('Product Key');
} catch(err) {}
</script>
```

{% hint style="info" %}
Failing to do so, Instantor script will fail to load, and report an error in initialisation.
{% endhint %}

### Step 5 - Inject information about the end-user \(optional\)

To differentiate your end-users, we offer for you to inject information in the report, which you will be able to view under **userParam: miscEntryList.** 

You can add as many user/request-specific information as you need. It will be stored as key-value pairs, and is a free-form, with some special keywords. 

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

{% hint style="info" %}
List of example keys: `firstName,` `lastName,` `email`, `account`, `personal_id`, SSN `or personalNumber,` DNI, `clientNumber`, `document, Etc.` 
{% endhint %}

{% hint style="info" %}
Read more about **userParam** keywords in [.userParam](../javascript-api/.userparam.md)
{% endhint %}

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



























