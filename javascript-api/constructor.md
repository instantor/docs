# Constructor

The Instantor object constructor accepts one argument -- the product key.

```javascript
Instantor(productKey)
```

| Arguments | Description |
| :--- | :--- |
| **productKey** \(string\) | Main source of identification. Received from Instantor tech support. |

### Example

```javascript
try {
  const instantor = new Instantor('produkt-key.de')
} catch(err) {/* Handle error */}
```



