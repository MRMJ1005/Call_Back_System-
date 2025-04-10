
# 🧠 Voice-Based Appointment Booking Agent (Vapi + n8n + Google Calendar)

This project is a conversational AI-powered calling system that automates the process of **qualifying leads** and **booking interior design consultations** using voice calls.

Built using:
- [Vapi](https://vapi.ai) – voice AI engine
- [n8n](https://n8n.io) – workflow automation
- **Google Calendar** – for managing and booking consultation slots
- **Airtable** – for lead data storage and tracking

---

## 🗣️ Agent Overview

The agent is named **Maya**, a polite and professional virtual assistant working for the Interia sales department. Her job is to:

- Greet inbound leads via voice
- Qualify leads based on budget, location, timeline, and scope
- Check calendar availability
- Book consultation calls with senior designers

---

## ⚙️ Key Features

- **Real-time voice interaction** using Vapi
- **Lead qualification logic** using budget and timeline filters
- **Calendar availability check** via Google Calendar API
- **Webhook integration** via n8n for real-time booking
- **Post-call confirmation** flow using a custom tool

---

## 🔧 The `post-call` Tool

A custom **Function Tool** in Vapi called `post-call` was created to finalize bookings.

- It is triggered **after the user confirms their name and time**
- Sends booking data (name + time) to a webhook (n8n)
- The webhook checks availability and returns a confirmation message to the user **during the same call**

**Example response:**

```json
{
  "actions": [
    {
      "type": "say",
      "text": "Your appointment has been successfully booked for tomorrow at 6 PM. Looking forward to it!"
    }
  ]
}
