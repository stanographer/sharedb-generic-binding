# sharedb-generic-binding
Base class for binding [sharedb](https://github.com/share/sharedb) text diff data operations sent to a generic HTML element.
Implementation of curran's commit to enable StringBinding, binding.setup() on non-textarea HTML elements.

## Usage

```bash
npm install sharedb-generic-binding --save
```

Then use familiar code to bind to a ShareDB connection.

```js
// Require it.
const ShareGenericBinding = require('sharedb-generic-binding');

// Setup the connection.
const socket = new WebSocket('ws://YOUR_HOST:YOUR_PORT', [], socketOptions);
const connection = new sharedb.Connection(socket);
const doc = connection.get('examples', 'textarea');

// Subscribe to the document.
doc.subscribe((err) => {
  if (err) throw err;
  const element = document.getElementById('YOUR_DIV_OR_WHATEVER');
  const binding = new ShareGenericBinding(element, doc);
  binding.setup();
});
```
