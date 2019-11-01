---
description: Additional methods that can be used in combination with the iFrame.
---

# Other methods

### .getBankList

The **getBankList** method fetches all available banks, and runs the **callbackFunction** with the response as argument

```javascript
instantor.getBankList(callbackFunction(payload))
```

Where payload has the following format:

```javascript
{
  status: true | false,
  errorMessage: 'error message',
  tld: {
    name: 'TLD identification',
    count: number
  },
  banks: [
    {
      UUID: 'bank UUID',
      identification: 'bank identification string (bank abbreviation)',
      name: 'display bank name'
    }
    …
  ]
}
```

### .destroy

The **destroy** method dereferences the initialized iframe, removes its DOM element, removes all its referenced callback functions and event listeners.

```javascript
instantor.destroy()
```

