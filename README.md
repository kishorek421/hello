To execute the equivalent of the Selenium Python `driver.execute_script()` command in the Google Chrome Developer Console using JavaScript, you can use the following approach:

1. First, identify the `submit_button` element using its XPath.
2. Use JavaScript to remove the `disabled` attribute from the element.

### Google Console JavaScript Code

```javascript
// Find the element using XPath
var submit_button = document.evaluate(
  "//input[@type='submit' and @value='Sign in']", // Replace with your exact XPath expression
  document,
  null,
  XPathResult.FIRST_ORDERED_NODE_TYPE,
  null
).singleNodeValue;

// Remove the 'disabled' attribute
if (submit_button) {
  submit_button.removeAttribute('disabled');
}
```

### Explanation:

1. **Finding the Element:**
   - `document.evaluate()` is used to find the element using an XPath expression.
   - `XPathResult.FIRST_ORDERED_NODE_TYPE` is used to get the first node that matches the XPath.
   - `singleNodeValue` returns the first matching element.

2. **Removing the `disabled` Attribute:**
   - The `removeAttribute('disabled')` method removes the `disabled` attribute from the found element, enabling it.

### Notes:

- Replace the XPath in `document.evaluate()` with the exact XPath expression of your target element.
- This code should be run in the console on the page where the element is present to manipulate the DOM directly.
- Be cautious while running such scripts on any page, especially on production sites or sites you do not own, as it can have unintended consequences.

If you have any specific modifications or additional requirements, feel free to ask!
