# Client–Server Questions & Exercises

## Conceptual Questions

* **Q1.** What is a **client** and what is a **server** in our setup?
* **Q2.** What is a **API contract**. Why client and server must agree on it?
* **Q3.** Difference between **URI** and **Origin**? Give Examples.
* **Q4.** What problem does **SOP** solve? Who enforces it?
* **Q5.** What is **CORS**? Who opts in? Why does `curl` ignore CORS but browsers don’t?
* **Q6.** In dev, why is using "allow any origin" for CORS acceptable for class but not acceptable for production?
* **Q7.** What is localhost and why does it equal 127.0.0.1?
* **Q8.** What is a port and why do we run the client and server on different ports on localhost?
* **Q9.** What happens if the backend is not running? What error do you expect from curl and from the browser?
* **Q10.** If you change the backend port from 8080 to 5000, what one thing must you change in the frontend?
* **Q11.** Why test with curl/Postman before/while testing in the browser?
* **Q12.** What is a public tunnel (ngrok) and when would you use it?
* **Q13.** Which approach does our client use: SSR or SPA?
* **Q14.** After a button click, does the client request a new HTML page or data?


## HTTP Basics

* **Q1.** What is the **HTTP Protocol**?
* **Q2.** What are **HTTP headers**? Which one is important for CORS?
* **Q3.** What are **HTTP verbs**? Which one did we use for our API?
* **Q4.** What are **HTTP status codes**? Which one did we use for our API?
* **Q5.** How can you see the full HTTP request and response in the browser?
* **Q6.** How can you see the full HTTP request and response using curl?


## API Contract

* **E1.** Given this minimal contract, fill each cell:

| **Description**   | **Protocol + Verb** | **Path** | **Response** | **Response Status** |
| ----------------- | ------------------- | -------- | ------------ |---------------------|
| Return a greeting |                     |          |              |                     |


## CORS & Origins

* **Q1.** For each pair, decide **Same Origin** or **Cross Origin**:

  * `http://localhost:5173` → `http://localhost:8080`
  * `http://localhost:3000` → `http://127.0.0.1:3000`
  * `https://app.example.com` → `https://api.example.com`
  * `http://localhost:5000` → `https://localhost:5000`
  * `https://foo.example.com:443` → `https://foo.example.com`
  

* **Q2.** Why does `Allow-Origin: *` work for class demos but not for production?


## HTTP & Testing

* **E1.** What happens if you access a server that is not running?
  *  What error do you expect from curl and from the browser?


* **E2.** What happens if you access a server that is running but the path does not exist (e.g. `/api/unknown`)?
  * What error do you expect from curl and from the browser?


## Ngrok 

> Forwarding https://d29dae378e59.ngrok-free.app -> http://localhost:6150

* **Q1.** What does the following ngrok output mean?
* **Q2**. Which URL do you use to access the Server API?


## Implement API Endpoint

> Hard, needs your best prompt ! 💪

* Following API contract, implement a new API endpoint that returns a list of todo items as JSON.

| **Description**      | **Protocol + Verb** | **Path**     | **Response**                                     | **Response Status** |
| -------------------- | ------------------- |--------------|--------------------------------------------------|---------------------|
| Return list of todos | HTTP GET            | `/api/todos` | `[{ "id": 1, "title": "Learn Programming",.. }]` | 200 OK              |

* **E1.** Implement the new API endpoint **on the server** that returns a list of todo items as JSON.
  * Use curl or Postman to verify the response is a JSON array of todos.


* **E2.** Call the new API endpoint **on the client** and render the list of todos.
  * Use fetch to call the endpoint and log the response to the console.
  * Render the list of todos in the DOM.


