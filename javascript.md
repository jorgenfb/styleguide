Javascript
=========

## Documentation
Use [JSDoc](http://en.wikipedia.org/wiki/JSDoc) which is similar to JavaDoc.

### Types
Since javascript uses dynamic types, your must document the expected input/return type of your functions. Types are defined in curly brackets `{}` after the JSDoc tag, like: `@param {String} name`. Optional parameters are wrapped in square brackets `[]`, like `@param {Boolean} [verbose]`. Default values are documented by putting `=defaultValue` inside the square brackets: `@param {Number} [timeout=5000]`. Function accepting parameters of different types are shown by separating types by pipe `|`, like `@param {Function|String} url`.


This is a great example:

```javascript
/**
 * Creates a template function from the given url
 *
 * @param {String|Function} url template url as a string, or as a function computing the url string
 * @param {Number} [timeout=50000] time to wait before giving up.
 * @return {Funtion}
 */
 createTemplate(url, timeout){ ... }
```


