# Observer or Signals Design Pattern in JS

## Front-End (Browser)

1. **Register the Event**:

   - This involves using `addEventListener` to set up an event listener on the document or a specific element.
   - The document or element is subscribing to that event.

    ```javascript
    document.addEventListener('myCustomEvent', eventHandler);
    // Or for a specific element
    const element = document.getElementById('myElement');
    element.addEventListener('myCustomEvent', eventHandler);
    ```

3. **Declare the Event Handler**

   - This is the function that contains the logic to be executed when the event is triggered.

    ```javascript
    function eventHandler(event) {
        console.log('My custom event triggered:', event.detail);
    }
    ```

5. **Trigger the Event**

   - This involves creating and dispatching the event using `dispatchEvent` on the document or the specific element.

    ```javascript
    // Create a custom event with optional detail data
    const myEvent = new CustomEvent('myCustomEvent', {
        detail: { someData: 'example data' }
    });

    // Dispatch the event on the document
    document.dispatchEvent(myEvent);
    // Or on a specific element
    element.dispatchEvent(myEvent);
    ```

## Back-End (Node.js)

- Using the `events` module in the back-end provides a way to handle signals and asynchronous events.
- **EventEmitter**: Use the `events` module to create and handle custom events.
- The `EventEmitter` class provides methods like `on`, `emit`, and `removeListener` to manage events.

```javascript
const EventEmitter = require('events');

// Create an instance of EventEmitter
const eventEmitter = new EventEmitter();

// Register an event listener
eventEmitter.on('myCustomEvent', (data) => {
    console.log('My custom event triggered:', data);
});

// Trigger the event
eventEmitter.emit('myCustomEvent', { someData: 'example data' });
```
