# Chart-sl
Messageing esili
els
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Simple Messaging App</title>
  <style>
    body { font-family: Arial, sans-serif; background-color: #f4f4f4; }
    #chat { width: 300px; height: 400px; border: 1px solid #ccc; padding: 10px; overflow-y: auto; }
    #message { width: 100%; padding: 10px; margin-top: 10px; }
    .message { padding: 5px; background-color: #e5e5e5; margin: 5px 0; border-radius: 5px; }
  </style>
</head>
<body>

  <h2>Simple Messaging App</h2>
  <div id="chat"></div>
  <input type="text" id="messageInput" placeholder="Type your message..." onkeypress="sendMessage(event)">
  <button onclick="send()">Send</button>

  <script>
    const chat = document.getElementById('chat');

    function sendMessage(event) {
      if (event.key === 'Enter') {
        send();
      }
    }

    function send() {
      const message = document.getElementById('messageInput').value;
      if (message.trim() === '') return;

      const messageElement = document.createElement('div');
      messageElement.className = 'message';
      messageElement.textContent = message;
      chat.appendChild(messageElement);

      document.getElementById('messageInput').value = '';
      chat.scrollTop = chat.scrollHeight;  // Auto-scroll to the bottom
    }
  </script>

</body>
</html>
