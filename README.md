# Real-time Notification & Chat App with FastAPI + WebSocket

This project is a real-time WebSocket-based system built using FastAPI for the backend and HTML/CSS/JavaScript for the frontend. It enables real-time updates between a server and multiple clients. The server tracks the number of connected users and subscribers, and supports sending/receiving notifications.

---

## Project Structure

Project/
│
├── app/
│   ├── main.py             # FastAPI entry point
│   ├── server.py           # Handles WebSocket logic for the server dashboard
│   ├── client.py           # Handles WebSocket logic for client subscribers
│   └── shared_tools.py     # Shared utilities for managing WebSocket connections
│
├── pages/
│   ├── client.html         # Client UI (subscriber interface)
│   ├── server.html         # Server UI (dashboard to view counts/messages)
│   ├── css/
│   │   ├── client.css      # Styling for client UI
│   │   └── server.css      # Styling for server UI
│   ├── js/
│   │   ├── client.js       # JavaScript for handling client-side WebSocket
│   │   └── server.js       # JavaScript for handling server-side WebSocket
│   └── images/
│       └── Server Background.png  # Optional background image for UI
│
└── README.md               # Project documentation

---

## Features

- Real-time bi-directional communication using WebSockets.
- Displays live counts of connected clients and subscribers.
- Clients can send notifications to the server.
- Server UI displays incoming messages and stats in real time.
- Fully web-based using HTML/CSS/JS frontend with FastAPI backend.

---

## Requirements

- Python 3.8+
- FastAPI
- Uvicorn

Install dependencies:

pip install fastapi uvicorn

---

## Running the Project

1. Navigate to the project directory:

cd Project

2. Start the FastAPI server:

python -m uvicorn app.main:app --reload

3. Access the interfaces in your browser:

- Server Dashboard:  
   http://127.0.0.1:8000/server

- Client Page:  
   http://127.0.0.1:8000/

---

## WebSocket Routes

- /ws/server: WebSocket connection for the server dashboard.
- /ws/client: WebSocket connection for individual clients.

---

## How It Works

- When a client connects, they can subscribe to receive messages.
- The server receives notifications from clients and broadcasts updated connection counts.
- Clients and the server stay synced through real-time WebSocket messages.

---

## Message Format Examples

Client Sends:

{ "action": "subscribe", "user_id": "abc123" }

{ "action": "notify", "message": "Hello from the client!" }

Server Responds:

{
  "type": "counts",
  "subscribers": 5,
  "clients": 12
}

---

## TODO (Optional Enhancements)

- Add user authentication for clients.
- Store and display message history.
- Show timestamp for each message.
- Improve UI responsiveness on mobile.

---

## License

This project is open-source and licensed under the MIT License.
