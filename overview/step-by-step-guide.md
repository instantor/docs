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











