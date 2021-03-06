# @paulavery/events - EventEmitter with Promise support
Yes, this is yet another EventEmitter.
It can deal with scopes as well as promises, but it is mostly used by me as a testbed for my buildsystem and for my private projects.

Full documentation can be found at [here](https://paulavery.github.io/events).
And here is a short example:

```js
import EventEmitter from '@paulavery/events';

let emitter = new EventEmitter();
let scope = emitter.child('scope');

emitter.on('scope:event', message => console.log('1. ' + message));
emitter.on('scope:*', (path, message) => console.log('2. ' + message));
scope.on('event', message => console.log('3. ' + message));

emitter.emit('scope:event', 'MESSAGE!').then(() => console.log('Done'));
```
