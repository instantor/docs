# Constructor

The Instantor object constructor accepts one argument -- the product key.

```javascript
new Instantor(productKey)
```

| Arguments | Description |
| :--- | :--- |
| **Product Key**  | Main source of identification, received when partnering with Instantor. |

### Example

```javascript
try {
  const instantor = new Instantor('produkt-key.de')
} catch(err) {/* Handle error */}
```



