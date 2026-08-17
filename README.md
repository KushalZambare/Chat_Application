## Java Chat Application

This is a simple multi-client chat application written in **pure Java**, featuring-

- **Console-based server** (`ChatServer`)
- **Console-based client** (`ChatClient`)
- **Swing GUI client** (`ChatClientGUI`)
- Basic features like online user list, join/leave notifications, and simple commands.

The server accepts multiple clients over TCP sockets and broadcasts messages to all connected users.

---

## Features

- **Multi-client chat**: Multiple clients can connect to the server at the same time.
- **Username system**: Each user chooses a unique username when connecting.
- **Online users listing**: Type `/users` in the console client to see who is online.
- **Basic commands**:
  - `/help` – Show available commands.
  - `/users` – List all online users.
  - `/quit` – Disconnect from the chat.
- **Console client**:
  - Simple text-based Chat in the terminal.
- **GUI client**:
  - Swing-based interface with:
    - Chat history area
    - Input box and *Send* button
    - Online users list
    - Username field and *Connect* button

---

## Project Structure

Key files:

- `ChatApplication.java` – Simple launcher to start the server or console client from a menu.
- `ChatServer.java` – TCP chat server running on port `12345`.
- `ChatClient.java` – Console-based chat client.
- `ChatClientGUI.java` – Swing GUI client.
- `ClientHandler.java` – Per-client handler used by the server.

All files are plain Java source files with no external dependencies.

---

## Requirements

- **Java Development Kit (JDK) 8+** installed
- A terminal / command prompt to run the server and console client

You can check your Java version with:

```bash
java -version
```

---

## How to Compile

Open a terminal in the `ChatApplication` directory and run:

```bash
javac *.java
```

This will compile all `.java` files and generate corresponding `.class` files.

---

## How to Run

### Option 1: Use the launcher (`ChatApplication`)

After compiling, run:

```bash
java ChatApplication
```

You will see a menu:

1. Start Server  
2. Start Client  
3. Exit  

Choose the appropriate option and follow the prompts.

> Note: The launcher only starts the **console client**, not the GUI client.

---

### Option 2: Run each component manually

#### 1. Start the server

In one terminal:

```bash
java ChatServer
```

You should see logs indicating the server is listening on port `12345`.

#### 2. Start a console client

In another terminal:

```bash
java ChatClient
```

Follow the prompts:

- Enter a **unique username**
- Type your messages and press Enter to send
- Use `/help`, `/users`, `/quit` for commands

You can open multiple terminals and run `java ChatClient` in each to simulate multiple users.

#### 3. Start the GUI client

In another terminal:

```bash
java ChatClientGUI
```

Then:

1. Enter a **username** in the top text field.
2. Click **Connect** to connect to the server on `localhost:12345`.
3. Type messages in the bottom input field and press **Enter** or click **Send**.

The right side will show the list of online users.

---

## Commands (Console Client)

Inside the console client (`ChatClient`), you can type:

- `/help` – Show help and available commands.
- `/users` – Show online users.
- `/quit` – Disconnect from the server and close the client.

Any other non-empty line is broadcast as a chat message to all connected clients.

---

## Notes & Limitations

- This is a **learning/demo** project, not a production-grade chat system.
- Communication is **not encrypted** (plain TCP sockets).
- The server always listens on `localhost:12345`. To run over a network, you may need to:
  - Use the server machine’s IP address in the client code.
  - Open/allow the port in your firewall.
- Error handling and reconnection logic are minimal.

---

## Possible Improvements

- Private messaging between users.
- Message history / logging to file.
- Configurable host/port (e.g. via command line args or config file).
- Better GUI (styling, timestamps, notifications).
- Authentication and secure communication (e.g. TLS).

---

## License

You can add your preferred license here (e.g. MIT, Apache 2.0), or keep this project private.

