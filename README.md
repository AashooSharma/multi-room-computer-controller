# **Multi-Room Computer Controller**

A browser-based admin control panel to manage multiple Windows computers across multiple rooms.
Supports adding custom actions, managing rooms, selecting computers, and mapping actions to systems — all via JSON-based databases hosted on GitHub.

---

## 🚀 **Features**

### **1️⃣ Multi-Room Computer Management**

* Each room contains multiple computers
* Select room or individual PCs
* Add/remove rooms via `rooms.json`

### **2️⃣ Action Control System**

* Built-in actions: Restart, Shutdown, Run URL, Custom Command
* Add own custom actions via `add-actions.html`
* JSON-based action database with real-time preview

### **3️⃣ Task Assignment Dashboard**

* A table showing:

  * **Rows:** Computers
  * **Columns:** Actions
  * Assign any action to any PC
* Actions & Rooms load from GitHub JSON URLs

### **4️⃣ Fully JSON-Driven**

* Two lightweight databases:

  * `actions.json`
  * `rooms.json`
* Easy to edit, update, and fetch directly using GitHub Raw URLs.

---

## 📁 **Project Structure**

```
📦 multi-room-computer-controller
 ┣ 📄 index.html
 ┣ 📄 add-actions.html
 ┣ 📄 tasks.html
 ┣ 📄 actions.json
 ┣ 📄 rooms.json
 ┗ 📄 README.md
```

---

## 🌐 Host JSON Database on GitHub

### **Your JSON files will be publicly accessible like this:**

```
https://raw.githubusercontent.com/<username>/<repo-name>/main/actions.json
https://raw.githubusercontent.com/<username>/<repo-name>/main/rooms.json
```

Paste these URLs directly inside your HTML:

```js
fetch("https://raw.githubusercontent.com/<username>/<repo>/main/actions.json")
```

---

## 🧩 JSON Database Format

### **actions.json**

```json
{
  "actions": [
    {
      "id": "restart_pc",
      "name": "Restart System",
      "type": "system",
      "command": "shutdown /r /t 0"
    },
    {
      "id": "shutdown_pc",
      "name": "Shutdown System",
      "type": "system",
      "command": "shutdown /s /t 0"
    },
    {
      "id": "open_google",
      "name": "Open Google",
      "type": "url",
      "url": "https://google.com"
    }
  ]
}
```

---

### **rooms.json**

```json
{
  "rooms": [
    {
      "id": "room_1101",
      "name": "Room 1101",
      "computers": ["PC-1", "PC-2", "PC-3"]
    },
    {
      "id": "room_2103",
      "name": "Room 2103",
      "computers": ["PC-4", "PC-5", "PC-6", "PC-7"]
    },
    {
      "id": "room_3102",
      "name": "Room 3102",
      "computers": ["PC-8", "PC-9"]
    },
    {
      "id": "room_4104",
      "name": "Room 4104",
      "computers": ["PC-10", "PC-11", "PC-12"]
    }
  ]
}
```

---

## 🛠 How to Host JSON Database

1. GitHub → New Repo
2. Name → **multi-room-computer-controller**
3. Upload:

   * `actions.json`
   * `rooms.json`
4. Commit
5. Open any file
6. Click → **Raw**
7. Copy the URL → use inside your app

---
