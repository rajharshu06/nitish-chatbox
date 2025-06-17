<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Nitish.exe - Your AI Messenger</title>
  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: #0f172a;
      color: white;
      display: flex;
      flex-direction: column;
      height: 100vh;
    }

    header {
      background-color: #1e293b;
      padding: 20px;
      text-align: center;
      font-size: 1.8rem;
      font-weight: bold;
      color: #38bdf8;
    }

    .chatbox {
      flex: 1;
      padding: 20px;
      overflow-y: auto;
      background-color: #1e1e2f;
    }

    .message {
      margin: 10px 0;
      padding: 12px 15px;
      border-radius: 10px;
      max-width: 70%;
      line-height: 1.4;
    }

    .user {
      background-color: #3b82f6;
      align-self: flex-end;
      color: white;
      margin-left: auto;
    }

    .bot {
      background-color: #475569;
      align-self: flex-start;
      color: #cbd5e1;
      margin-right: auto;
    }

    .input-area {
      display: flex;
      background-color: #1e293b;
      padding: 15px;
    }

    .input-area input {
      flex: 1;
      padding: 10px;
      border-radius: 8px;
      border: none;
      outline: none;
      font-size: 1rem;
    }

    .input-area button {
      padding: 10px 18px;
      margin-left: 10px;
      border: none;
      background-color: #38bdf8;
      color: white;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
    }

    .input-area button:hover {
      background-color: #0ea5e9;
    }

    .message-container {
      display: flex;
      flex-direction: column;
    }
  </style>
</head>
<body>

  <header>
    🤖 Nitish.exe - Smart Messenger Bot
  </header>

  <div class="chatbox" id="chatbox">
    <div class="message bot">Hello! I'm Nitish.exe. How can I assist you today?</div>
  </div>

  <div class="input-area">
    <input type="text" id="userInput" placeholder="Type a message..." />
    <button onclick="sendMessage()">Send</button>
  </div>

  <script>
    const chatbox = document.getElementById("chatbox");

    function sendMessage() {
      const input = document.getElementById("userInput");
      const message = input.value.trim();
      if (message === "") return;

      // User message
      appendMessage("user", message);

      // Bot reply (basic)
      setTimeout(() => {
        const reply = generateBotReply(message);
        appendMessage("bot", reply);
      }, 500);

      input.value = "";
    }

    function appendMessage(sender, text) {
      const msg = document.createElement("div");
      msg.className = message ${sender};
      msg.textContent = text;
      document.getElementById("chatbox").appendChild(msg);
      chatbox.scrollTop = chatbox.scrollHeight;
    }

    function generateBotReply(userMessage) {
      // Simple hardcoded responses
      const msg = userMessage.toLowerCase();
      if (msg.includes("hello") || msg.includes("hi")) {
        return "Hi there! 😊 How can I help you?";
      } else if (msg.includes("your name")) {
        return "I'm Nitish.exe – your personal smart assistant!";
      } else if (msg.includes("time")) {
        return "⏰ The current time is: " + new Date().toLocaleTimeString();
      } else if (msg.includes("date")) {
        return "📅 Today's date is: " + new Date().toLocaleDateString();
      } else {
        return "Hmm... I'm still learning. Please ask something else!";
      }
    }
  </script>

</body>
</html>
