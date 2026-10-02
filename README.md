# 👻 GhostChat

### Self-Destructing Real-Time Chat

GhostChat is a real-time chat application built for temporary conversations. Users can create a private chat room, share the room with others, and communicate in real time.

Once a room expires, its conversation disappears instead of being kept as permanent chat history.

## ✨ Features

- 💬 **Real-time messaging** — Send and receive messages instantly.
- 🔐 **Private chat rooms** — Conversations are isolated inside individual rooms.
- 👻 **Self-destructing chats** — Rooms automatically disappear after their lifetime.
- ⏳ **Room expiration** — Temporary rooms use an expiration timer.
- 🔗 **Shareable rooms** — Share a room link with other participants.
- 🗑️ **Temporary data** — Chat data is stored only for the lifetime of the room.
- 📱 **Responsive UI** — Designed to work across desktop and mobile devices.
- 🎨 **Modern interface** — Built with Tailwind CSS.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **Next.js 16** | Full-stack React framework |
| **React** | User interface |
| **TypeScript** | Type-safe development |
| **Tailwind CSS** | Styling and responsive UI |
| **Redis** | Temporary chat and room data |
| **Redis TTL** | Automatic expiration of temporary data |

## 🧠 How It Works

GhostChat is built around the concept of **ephemeral conversations**.

When a user creates a chat room, the application generates a unique room and stores its temporary state in Redis.

```text
                 Create Room
                     │
                     ▼
              Generate Room ID
                     │
                     ▼
              Store in Redis
                     │
                     ▼
                Set TTL
                     │
                     ▼
              Share Room Link
                     │
                     ▼
             Users Join Chat
                     │
                     ▼
            Real-Time Messages
                     │
                     ▼
               TTL Expires
                     │
                     ▼
              Room Disappears
```

### Redis TTL

Redis provides a **Time To Live (TTL)** mechanism that allows temporary data to automatically expire.

Instead of manually maintaining a cleanup process for every chat room, the application can associate an expiration time with the room's stored data.

This makes Redis a natural fit for temporary chat sessions.

## 🏗️ Architecture

```text
┌───────────────┐
│     Client    │
│   Next.js UI  │
└───────┬───────┘
        │
        │ API / Real-Time Events
        ▼
┌────────────────────┐
│     Next.js App    │
│  Server/API Layer  │
└─────────┬──────────┘
          │
          ▼
┌────────────────────┐
│       Redis        │
│                    │
│  Rooms             │
│  Messages          │
│  Expiration / TTL  │
└────────────────────┘
```

## 🚀 Getting Started

### Prerequisites

Make sure you have:

- Node.js installed
- A Redis instance
- npm, pnpm, yarn, or Bun

### Clone the repository

```bash
git clone https://github.com/VaibhavKatariya/GhostChat.git

cd GhostChat
```

### Install dependencies

```bash
npm install
```

Or:

```bash
pnpm install
```

### Configure environment variables

Create a `.env.local` file and add the Redis configuration required by the application.

```env
REDIS_URL=your_redis_url
REDIS_TOKEN=your_redis_token
```

> Use the exact environment variable names required by your implementation.

### Run the development server

```bash
npm run dev
```

Open **http://localhost:3000** in your browser.

## 📂 Project Structure

```text
ghost-chat/
├── src/
│   ├── app/
│   │   ├── api/
│   │   ├── ...
│   │   └── page.tsx
│   ├── components/
│   └── ...
├── public/
├── .env.local
├── next.config.ts
├── package.json
├── tsconfig.json
└── README.md
```

## 🔥 Why I Built This

I built GhostChat to explore how **real-time communication** and **temporary data storage** can be combined in a modern full-stack application.

The project gave me hands-on experience with:

- Next.js 16 App Router
- React and TypeScript
- Real-time communication
- Redis
- Redis TTL and data expiration
- Temporary session management
- API development
- State management
- Responsive UI development

## 🔒 Privacy Note

GhostChat is designed for temporary conversations, but disappearing messages should not be considered a guarantee of complete privacy.

A participant can still copy, screenshot, or otherwise save a message before the room expires.

## 🚧 Future Improvements

- [ ] Typing indicators
- [ ] Online/offline presence
- [ ] Read receipts
- [ ] Custom room expiration times
- [ ] Password-protected rooms
- [ ] Message-level expiration
- [ ] Image/file sharing
- [ ] End-to-end encryption
- [ ] Rate limiting and abuse protection

## 📜 License

This project is licensed under the MIT License.

---

**GhostChat** — conversations that don't stay forever. 👻