google-meet-clone/
│
├── backend/                      # Node.js / Express / WebSocket server
│   │
│   ├── src/
│   │   ├── controllers/          # Handles main logic for API routes
│   │   │   ├── auth.controller.js       # User registration & login
│   │   │   └── room.controller.js       # Create / validate meeting rooms
│   │   │
│   │   ├── models/
│   │   │   └── user.model.js            # Database schema for User
│   │   │
│   │   ├── routes/
│   │   │   ├── auth.routes.js           # /api/auth/register, /api/auth/login
│   │   │   ├── room.routes.js           # /api/room/create, /api/room/join
│   │   │   └── index.js                 # Combines all API routes
│   │   │
│   │   ├── services/
│   │   │   ├── db.js                    # Database connection (MongoDB/Postgres)
│   │   │   └── signaling.service.js     # WebSocket logic for WebRTC signaling
│   │   │
│   │   ├── middleware/
│   │   │   └── auth.middleware.js       # Protects routes using JWT verification
│   │   │
│   │   ├── utils/
│   │   │   └── generateRoomCode.js      # Helper to generate unique room codes
│   │   │
│   │   └── server.js                    # Main entry point – starts Express + WebSocket
│   │
│   ├── .env                             # Environment variables (DB_URI, JWT_SECRET, etc.)
│   ├── .gitignore
│   └── package.json                     # Backend dependencies
│
├── frontend/                    # React / Vite client
│   │
│   ├── public/
│   │   ├── favicon.ico
│   │   └── icons/
│   │       ├── mic-on.svg
│   │       ├── mic-off.svg
│   │       ├── video-on.svg
│   │       └── video-off.svg
│   │
│   ├── src/
│   │   ├── assets/
│   │   │   └── logo.png
│   │   │
│   │   ├── components/
│   │   │   ├── common/
│   │   │   │   ├── Button.jsx
│   │   │   │   ├── Input.jsx
│   │   │   │   └── LoadingSpinner.jsx
│   │   │   │
│   │   │   ├── meeting/
│   │   │   │   ├── VideoPlayer.jsx      # Displays user video
│   │   │   │   ├── ControlBar.jsx       # Mute/unmute, leave call, etc.
│   │   │   │   └── ChatMessage.jsx      # Single chat bubble
│   │   │   │
│   │   │   ├── layout/
│   │   │   │   ├── Header.jsx
│   │   │   │   └── Footer.jsx
│   │   │   │
│   │   │   └── ProtectedRoute.jsx       # Redirects unauthenticated users
│   │   │
│   │   ├── context/
│   │   │   ├── AuthContext.jsx          # Manages user authentication
│   │   │   ├── SocketContext.jsx        # Manages WebSocket connection
│   │   │   └── RoomContext.jsx          # Tracks room state & peer streams
│   │   │
│   │   ├── hooks/
│   │   │   ├── useAuth.js               # Access AuthContext easily
│   │   │   ├── useSocket.js             # Access SocketContext easily
│   │   │   └── useWebRTC.js             # Core RTCPeerConnection logic
│   │   │
│   │   ├── pages/
│   │   │   ├── HomePage.jsx             # Main page (Host / Join)
│   │   │   ├── LoginPage.jsx
│   │   │   ├── RegisterPage.jsx
│   │   │   ├── RoomPage.jsx             # Video call interface (grid of streams)
│   │   │   └── NotFoundPage.jsx
│   │   │
│   │   ├── services/
│   │   │   ├── api.js                   # Axios instance for HTTP requests
│   │   │   └── signaling.client.js      # Handles WebSocket client logic
│   │   │
│   │   ├── styles/
│   │   │   └── index.css                # Main CSS or Tailwind styles
│   │   │
│   │   ├── App.jsx                      # Main app with router
│   │   ├── main.jsx                     # React DOM root + Context wrappers
│   │   └── utils.js                     # Small client-side helper functions
│   │
│   ├── .env                             # Frontend env vars (VITE_API_URL, VITE_WS_URL)
│   ├── .gitignore
│   ├── index.html                       # Vite entry HTML
│   ├── package.json                     # Frontend dependencies
│   ├── tailwind.config.js
│   ├── postcss.config.js
│   └── vite.config.js                   # Vite setup
│
└── .gitignore                           # Root .gitignore (node_modules, .env, etc.)
