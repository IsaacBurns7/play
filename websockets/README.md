This directory contains a minimal example WebSocket client and server.

When the page is loaded, it creates a WebSocket connection to the server, then sends a ping every second. The server listens for the ping and sends a response. The client listens for the responses and logs them.

The client starts the connection on the pageshow event and closes it on pagehide: this allows browser to keep the page in the bfcache, which improves page load if the user navigates back to it.

Running the example
The server-side is written in Deno so Deno needs to be installed first. Then, with Deno in your path, you can start the server with a command like:

deno run --allow-net=0.0.0.0:80 --allow-read=./index.html,./client.js,index.css server.js
You can then navigate to http://localhost:80/ and you should see the application running.