# Walkthrough: Minimal Client–Server (React / .NET)

## 1. Introduction

### Goal

* **Client-Server** Client (React) call API Endpoint `GET /api/todo` from Server (.NET).

### Expected Outcome

- Two repos (**`frontendTodo`**, **`backendTodo`**)
- React Client
- .NET Server
- API Contract: `GET /api/todo` returns `200 OK` + `Hello World`
- Curl/Postman testing your API
- What is SOP ?
- What is CORS ?
- Fix CORS for local dev
- Share code via Git (GitHub)
- Share your local server with ngrok

---

## 2. Prerequisites

* **Node** ≥ 18 → `node -v`
* **npm** ≥ 9 → `npm -v`
* **.NET SDK** ≥ 8 → `dotnet --version`
* **Git** + a GitHub account
* **curl** (Git Bash/macOS/Linux have it)
* **Postman** (install from postman.com)

**Verify tools**

```sh
node -v                           # v18+ (e.g. v22.x)
npm -v                            # v9+  (e.g. 10.x)
dotnet --version                  # 8.x
curl --version                    # prints version
```

---

## 3. Setup

* **Shell**: Git Bash (Windows) or Terminal (Linux/macOS).
* **Repos**: One `frontendTodo`, one `backendTodo`.
* **Terminals**: Plan for two terminals (A: backend, B: frontend).

---

## 4. Steps

### Step 1 — Initialize GitHub repositories

* **Why**: Keep frontend and backend separate and shareable.

```sh
# clone the empty frontend repo
git clone https://github.com/<you>/frontendTodo.git

# clone the empty backend repo
git clone https://github.com/<you>/backendTodo.git
```

**Verify**

* Two folders exist: `frontendTodo/` and `backendTodo/`.

---

### Step 2 — Create Client (Vite, JavaScript)

**What**: Create a minimal React app with a single component.

```sh
cd frontendTodo
npm create vite@latest . -- --template react
npm install
```

**Replace: `src/Main.jsx`:**

```jsx
import { useState } from 'react'

const API = 'http://localhost:5000'       // Change to your SERVER URL later

export default function Main() {
  const [text, setText] = useState('')

  async function callApi() {
    try {
      const res = await fetch(`${API}/api/todo`)
      const data = await res.text()
      setText(data)
    } catch {
      setText('Request failed')
    }
  }

  return (
    <div>
      <button onClick={callApi}>Call API</button>
      <h1>{text}</h1>
    </div>
  )
}
```

**Edit: `src/main.jsx` to render `Main`**

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import Main from './Main.jsx'

ReactDOM.createRoot(document.getElementById('root')).render(<Main />)
```

**Run Client**

```sh
npm run dev
npm run dev -- --port 3000        # specify port if needed
```

* Open the printed URL → see page with a **Call API** button.


---

### Step 3 — Create Server (.NET Minimal API)

**What**: Provide `/api/todo` endpoint returning text.

```sh
cd backendTodo
dotnet new web                     # minimal API template
```

**Replace: `Program.cs`**

```csharp
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/api/todo", () => "Hello World");

app.Run();
```

**Run Server**

```sh
dotnet run
dotnet run --urls http://localhost:5000  # specify port if needed
```

---

### Step 4 — Test Server (curl & Postman)

**What**: Verify server works before wiring the frontend.

```sh
# simple
curl http://localhost:5000/api/todo

# verbose
curl -v http://localhost:5000/api/todo
```

**Expected**

* Body `Hello World`, status `200 OK`.

**Postman**

![postman](_assets/postman.png)

---

### Step 5 — Share code via Git

* **Why**: Push your work; teammates can pull and run.

```sh
# You
git add .
git commit -m "create minimal client"
# git commit -m "create minimal server"
git push

# Teammate (first time)
git clone https://github.com/<you>/frontendTodo.git
git clone https://github.com/<you>/backendTodo.git

# Teammate (later updates)
cd frontendTodo && git pull
cd backendTodo && git pull
```

**Verify**

* Teammate can build/run both projects locally.

---

### Step 6 — Run both locally

**Terminal A (Server)**

```sh
cd backendTodo
dotnet run --urls http://localhost:5000
```

**Terminal B (Client)**

```sh
cd frontendTodo
npm run dev -- --port 3000
```

* Open the frontend URL → click **Call API**.
What's the result?

**Concepts**

* **URI** = `scheme://host:port/path` (e.g. `http://localhost:5000/api/todo`).
* **Origin** = `scheme + host + port` → ports differ → different origins.
* **SOP** = Same-Origin Policy, browser security model. Blocks cross-origin calls by default.
* **CORS** = Cross-Origin Resource Sharing, opt-in headers from server to relax SOP.
* **Why blocked?** Browser Origin ≠ Server Origin → SOP blocks call → frontend shows error.

---

### Step 7 — Fix CORS (dev-only)

**What**: Unblock local cross-origin calls during class/dev.
  
**Replace: `Program.cs`**

```csharp
var builder = WebApplication.CreateBuilder(args);

// CORS for local dev only
builder.Services.AddCors(o =>
{
    o.AddDefaultPolicy(p => p
        .AllowAnyOrigin()
        .AllowAnyHeader()
        .AllowAnyMethod());
});

var app = builder.Build();

app.UseCors(); // must be before endpoints

app.MapGet("/api/todo", () => "Hello World");

app.Run();
```

* Restart backend:

```sh
dotnet run --urls http://localhost:5000
```

**Common pitfalls**

* **UseCors order**: Call `app.UseCors()` before mapping endpoints.
* **Prod caution**: Don’t ship `AllowAnyOrigin` to production.

---

### Step 8 — Expose Server with ngrok

* **What**: Share your local backend publicly for class/testing.


* Install & auth:

```sh
# Configure auth token (from the ngrok dashboard)
ngrok config add-authtoken <YOUR_TOKEN>

# Verify configuration
ngrok config check
```

* Run the tunnel (backend must be running):

```sh
ngrok http http://localhost:5000
```

* Copy the **Forwarding** URL like `https://xxx.ngrok-free.app`.

Point the frontend to ngrok URL (`frontendTodo/src/Main.jsx`):

```jsx
const API = 'https://xxx.ngrok-free.app'  // Teammate’s ngrok URL
```

**Verify**

```sh
curl https://abcd-xyz.ngrok-free.app/api/todo
```

**Common pitfalls**

* **Mixed content**: If frontend runs on https, prefer https ngrok URL.
* **Tunnel died**: Keep the ngrok terminal open.

---

## 5. Troubleshooting

### Process management cheat sheet

```sh
ps aux | grep dotnet                   # list processes
ps aux | grep node
ps aux | grep ngrok

kill -9 <PID>                          # kill by PID
```

---

## 6. Summary / Next Steps

### What you now have

* **Client**: React app making HTTP requests.
* **Server**: .NET app listening on a port.
* **API contract**: `HTTP GET /api/todo` returns `200 OK` + `Hello World`.
* **SOP/CORS**: why cross-origin calls are blocked by default and how to enable them.
* **curl/Postman**: quick, browser-free API checks.
* **ngrok**: public HTTPS tunnel to your local backend.

---

## 7. Appendix — Full Reference Code

### frontendTodo/src/Main.jsx

```jsx
import { useState } from 'react'

const API = 'http://localhost:5000'

export default function Main() {
  const [text, setText] = useState('')

  async function callApi() {
    try {
      const res = await fetch(`${API}/api/todo`)
      const data = await res.text()
      setText(data)
    } catch {
      setText('Request failed')
    }
  }

  return (
    <div>
      <button onClick={callApi}>Call API</button>
      <h1>{text}</h1>
    </div>
  )
}
```

### frontendTodo/src/main.jsx

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import Main from './Main.jsx'

ReactDOM.createRoot(document.getElementById('root')).render(<Main />)
```

### backendTodo/Program.cs (dev-only CORS)

```csharp
var builder = WebApplication.CreateBuilder(args);

// dev-only CORS
builder.Services.AddCors(o =>
{
    o.AddDefaultPolicy(p => p
        .AllowAnyOrigin()
        .AllowAnyHeader()
        .AllowAnyMethod());
});

var app = builder.Build();

app.UseCors();

app.MapGet("/api/todo", () => "Hello World");

app.Run();
```

### Handy commands

```sh
# Run Server
dotnet run --urls http://localhost:5000

# Run Client
npm run dev -- --port 3000

# Test Server API (backend must be running)
curl http://localhost:5000/api/todo

# Share Server with ngrok (backend must be running)
ngrok http http://localhost:5000
```
