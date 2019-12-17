---
description: Additional methods that can be used in combination with the Widget.
---

# Other methods

### .getBankList

The **getBankList** method fetches all available banks, and runs the **callbackFunction** with the response as argument. Be aware this methods requires Instantor to whitelist you. Please contact Instantor tech support when planning to use this method.

```javascript
instantor.getBankList(callbackFunction(payload))
```

Where payload has the following format:

```javascript
{
  banks: [
    {
      UUID: 'bank UUID',
      identification: 'bank identification string (bank abbreviation)',
      name: 'display bank name'
    }
    …
  ],
  tld: {
    name: 'TLD identification',
    count: number
  },
  status: true | false,
  errorMessage: 'error message'
}
```

### .destroy

The **destroy** method dereferences the initialized `<iframe>`, removes the DOM element, removes all its referenced callback functions and event listeners.

```javascript
instantor.destroy()
```

