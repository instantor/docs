---
description: >-
  This page provides step-by-step instructions on how to integrate the Instantor
  iframe into your website.
---

# Step-by-step guide

{% hint style="warning" %}
 **Take care!** Disclaimer stuff goes here 💩 
{% endhint %}

### Step 1 - Create a website

```markup
<!DOCTYPE html>
<html lang="en">

<body>
    <h1>Welcome to my site!</h1>
</body>

</html>
```

### Step 2 - Include Jquery and Instantor loader script

{% hint style="warning" %}
_NOTE: HERE WE NEED TO CLARIFY WHICH URL TO USE TO FETH THE LOADER. IF THE INFO EXISTS IN .LOAD, WE COULD HAVE A LINK IN THIS HINT?_
{% endhint %}

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script type="https://www.instantor.se/awesomeLoaderByPalm.min.js"></script>
</head>

<body>
    <h1>Welcome to my site!</h1>
</body>

</html>
```

### Step 3 - Add iframe DOM element target

_NOTE: HERE WE NEED TO DECIDE WHAT STYLING THE ITOR-DIV REQUIRES. THE NEW FRAME REQUIRES SOME, CURRENTLY, BUT THE OLD REQUIRES NONE._

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script type="https://www.instantor.se/awesomeLoaderByPalm.min.js"></script>
</head>

<body>
    <h1>Welcome to my site!</h1>
    <div 
        id="itor" 
        style="height: 900px; display: flex; flex-direction: column;" 
    />
</body>

</html>
```

### Step 4 - Use the Instantor loader

{% hint style="warning" %}
Ensure you use the appropriate product key and target DOM element in this step.
{% endhint %}

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script type="https://www.instantor.se/awesomeLoaderByPalm.min.js"></script>
    <script type="text/javascript">
    ready(() => {
        try {
            const instantor = new Instantor('product-key.de')

            /* Load the Instantor iframe into the targeted DOM element */
            instantor.load('#itor')
        } catch (err) { console.log('Something went wrong: ', err) }
    })
    </script>
</head>

<body>
    <h1>Welcome to my site!</h1>
    <div 
        id="itor" 
        style="height: 900px; display: flex; flex-direction: column;" 
    />
</body>

</html>
```

### Step 5 - Attach parameters

There are three different parameters that can be set: [user parameters](../javascript-api/.userparam.md), [transaction parameters](../javascript-api/.transactionparam.md) and [frame parameters](../javascript-api/.frameparam.md), all of which are optional. 

```markup
<!DOCTYPE html>
<html lang="en">
<head>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script type="https://www.instantor.se/awesomeLoaderByPalm.min.js"></script>
    <script type="text/javascript">
    ready(() => {
        try {
            const instantor = new Instantor('product-key.de')
            
            /* Set relevant parameters */
            instantor.userParam('uniqueID', '00000-000-0000')
            instantor.userParam('environment', 'dev')
            instantor.userParam('foo', 'bar')
            
            instantor.transactionParam('identificationOnly', true)
            
            instantor.frameParam('bankID', 'id-of-bank')
            
            instantor.load('#itor')
        } catch (err) { console.log('Something went wrong: ', err) }
    })
    </script>
</head>

<body>
    <h1>Welcome to my site!</h1>
    <div 
        id="itor" 
        style="height: 900px; display: flex; flex-direction: column;" 
    />
</body>

</html>
```



























