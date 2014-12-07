Simple Push Library
===================

Let's use push notifications in Firefox OS! This library will help you with this, creating as many notification channels as you need.

Expose a simple interface to Push (you need to add it to your HTML). This works as simple as:
<pre>
// 1) Register your channels
SimplePush.createChannel(
 'fooChannel',
 function(version) {
   // Implement your logic here
   // ...
 },
 function onRegistered(error, endpoint) {
   // Do whatever you need with the endpoint & error
   // 2) Start listening! This is inside the registration due to
   // we need to ensure that the handler was registered.
   // We delegate into the app the logic for registering more than
   // one channel recursively.
   SimplePush.start()
 });
</pre>