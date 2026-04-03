# WppCatcher

## 1. Overview

**WppCatcher** is a development tool that intercepts, stores, and displays WhatsApp messages sent by backend applications without delivering them to the real recipient. It works as a **“MailCatcher for WhatsApp”**, enabling real-time inspection, debugging, and message simulation.

## 2. Value Proposition

- 🔒 Prevents accidental sends in production
- 🧪 Simplifies automated testing
- 👀 Full visibility of messages
- ⚡ Real-time feedback
- 🔌 Pluggable via Strategy Pattern

## 3. Product Concept

### 🔁 Mental Model

> “My system thinks it is sending WhatsApp messages…  
> but they are actually going to WppCatcher”

## 4. Refined Architecture

### 4.1 Layers

#### 1. Application (your SaaS)

- Triggers events (e.g., \`delivery.created\`)

#### 2. Messaging Abstraction

\`\`\`ts
interface WhatsappProvider {
send(data: SendMessageDTO): Promise<void>;
}
\`\`\`

#### 3. Providers

- TwilioProvider
- EvolutionProvider
- WppCatcherProvider (core of this project)

#### 4. WppCatcher Core

- Receive messages
- Persist data
- Emit realtime events
- Simulate inbound messages

#### 5. UI (Web App)

- Mobile-like interface simulation
- Technical debugging view

## 5. Core Features

### 5.1 WhatsApp-like Inbox

- Conversations grouped by phone number
- Last message preview
- New message badges

### 5.2 Real-time Chat

- WebSocket-based updates
- Messages appear instantly
- Auto-scroll behavior
