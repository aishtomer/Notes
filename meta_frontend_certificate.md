# 🧠 How the Internet & Web Servers Work

## 🌐 How the Internet Works

* The **Internet** is a massive **interconnected network** of devices.
* Devices communicate using **wired or wireless connections**, forming **networks**.
* **Network switches** help connect multiple devices within and across networks.
* When multiple networks are connected via switches, it becomes the **Internet**.
* The Internet uses a **client-server model**:

  * **Clients** = your devices (phones, laptops, etc.)
  * **Servers** = computers that provide services/data (like websites, messaging, video)
* **Undersea cables** enable global connectivity, transferring data across continents.

## 💻 What Is a Server?

* A **server** is a **computer** that runs **applications or services** for clients.
* It's called a "server" because it *serves* data/services to clients.
* Most servers are housed in **data centers**.

## 🏢 Data Centers

* Contain **hundreds/thousands of servers**.
* Designed for:

  * **24/7 power & internet**
  * **Cooling systems**
  * **Global distribution** to reduce latency (users connect to the nearest one)
* **Server hardware** depends on function:

  * Image storage → large **hard drive**
  * Heavy computation → fast **CPU + lots of memory**

## 🧩 Hardware vs. Software

* **Hardware** = physical components (hard drives, processors). Hard to change.
* **Software** = code that runs on hardware. Easy to update/change.

## 🌍 What is a Web Server?

* A **web server** is a type of server dedicated to:

  * Hosting **websites**
  * **Storing data**
  * **Handling security**
  * **Managing email**
* Key role: **Handle web requests**:

  * You type a website URL → browser sends a **request**
  * Web server sends back the **response** (webpage)
* This is called the **request-response cycle**.
* Web servers can process **thousands of requests per second**.

---

# 🌐 Webpages, Websites, Browsers & How It All Works

## 📄 Webpages vs. Websites

* **Webpage**: A single document with text, images, videos, etc., displayed in a browser.
* **Website**: A **collection of webpages** linked together (e.g., homepage + article pages).
* Webpages within the **same domain/URL base** = part of the same website.
* Links can also go to **other websites** (external links).

## 🌍 Explosive Web Growth

* **Hundreds of thousands** of websites are launched **daily**.
* Like stacking up digital Lego blocks—one week = more webpages than the stones in the Great Pyramid of Giza.
* **Billions** of webpages exist, and all rely on **core web technologies**.

## 💡 How a Webpage Works

* At its core, a webpage = **text file** written using 3 key technologies:

  1. **HTML** – Structure (skeleton)
  2. **CSS** – Style (makeup, outfit, home décor)
  3. **JavaScript** – Interaction (lights, buttons, energy drinks)

## 📦 Quick Breakdown of Web Technologies

### 🧱 HTML (Hypertext Markup Language)

* Uses **markup tags** (e.g., `<h1>`, `<p>`, `<img>`)
* Organizes content: text, images, videos, etc.

### 🎨 CSS (Cascading Style Sheets)

* Adds color, fonts, layout, spacing.
* Styles HTML content.
* HTML = your friend, CSS = their new hair color.

### ⚙️ JavaScript

* A programming language built into browsers.
* Adds **interactivity**: buttons, forms, live updates.
* Enables features like form validation, dynamic content loading.
* Makes websites **fun, smart, responsive**.

## 🖥️ How Code Becomes a Webpage

* Server sends **webpage code** (HTML + CSS + JS) to browser.
* Browser reads code **line-by-line** and builds visual structure.
* This process = **page rendering**.
* Web server must send a **complete response** to render the page properly.

## 🌐 Web Browsers 101

* A **web browser** is software (Chrome, Firefox, Safari, etc.) used to access the **World Wide Web**.
* Main job: send **requests** and display **responses**.

### 🧭 Address Bar (URL Components)

1. **Protocol**: `http://` or `https://` (uses **HTTP** to talk to servers)
2. **Domain name**: like `example.com`
3. **Path**: specifies **which page** to load

## 🔁 Request-Response Cycle (The Real MVP)

1. You type a URL and hit enter.
2. Browser sends a **request** over the Internet to a **web server**.
3. Web server processes the request.
4. Server sends back the **response** (HTML/CSS/JS).
5. Browser **renders** the webpage for you to see.
6. You interact with the page (e.g., type in search box).
7. Browser sends another request with your search.
8. Server queries its **database**, sends results back.
9. Browser renders **updated webpage**.

## 🔍 Example: Searching the Web

* Open browser → Type `google.com` → Webpage loads from Google's server.
* Search for “restaurants near me” → New request sent with query.
* Server checks **database**, sends back a page with:

  * Links, maps, reviews, etc.
* Browser renders all of it—voilà, dinner plans secured.

## 🧠 Key Takeaways

* **Webpages** are built using **HTML, CSS, JS**.
* **Web servers** store and serve the page.
* **Web browsers** request, receive, and render that content.
* The **request-response cycle** powers everything from Googling memes to binge-watching cat videos.

---

# ☁️ Web Hosting & Hosting Types

## 🧳 What Is Web Hosting?

* **Web hosting** = Renting space on someone else’s web server to store and serve your website.
* No need to own a datacenter or cry into a motherboard.
* Hosting companies handle the **hardware, software, and maintenance**.
* Both **individuals and companies** can rent hosting space.

## 🧨 Why It Matters

* Hosting = essential for making your site **accessible on the internet**.
* Think of it like parking your website on someone else’s property—just without the HOA fees.

## 💼 Types of Web Hosting

### 🧩 **1. Shared Hosting**

* 💸 **Cheapest** option, often **free** (but comes with ads or limitations).
* You **share** server resources (CPU, memory, bandwidth) with **many** other sites.
* 🐢 **Slower** performance due to crowding.
* 🔰 Ideal for:

  * Small personal websites
  * Low traffic sites
  * Beginner developers & test projects

### 🧠 **2. Virtual Private Server (VPS)**

* 🧍 A slice of a real server, but your **own dedicated resources**.
* Shares hardware with other VPS instances, but each has **isolated performance**.
* ⚖️ Balance of **cost + control**.
* 🔧 Good for:

  * Medium-sized sites
  * Apps needing reliable performance
  * Developers needing more power than shared hosting

### 🏢 **3. Dedicated Hosting**

* 🧠 Full hardware server = **all yours**.
* Total control of **CPU, memory, bandwidth**.
* 💰 **Most expensive** traditional option.
* 🧰 Best for:

  * Large businesses
  * High traffic sites
  * Complex web apps needing max performance

### ☁️ **4. Cloud Hosting**

* Runs your site on a **cluster of virtual/physical servers** (not just one machine).
* 💪 Resilient — if one server fails, another picks up the slack.
* 📈 **Scalable resources** — pay only for what you use (CPU, memory, bandwidth).
* 📉 Can get expensive if usage spikes.
* 🧠 Excellent for:

  * Growing businesses
  * Apps with unpredictable traffic
  * Sites needing 99.99% uptime

## 🧾 Key Takeaways

* Hosting puts your website **online**—without it, you're just coding in the void.
* Pick your hosting based on:

  * Traffic
  * Budget
  * Performance needs
* **Shared** = broke student budget.
  **VPS** = tech-savvy control freak.
  **Dedicated** = high-roller.
  **Cloud** = future-proofed flexibility.

---

# 📬 IP Addresses & Data Transmission Over the Internet

## ✉️ Email vs. Postal System Analogy

* Email = instant communication
* Postal system = old-school snail trail
* But they’re **surprisingly similar** in structure:

  * Both need addresses
  * Both can lose, damage, or misorder messages
  * Both involve a sender, a receiver, and a whole lotta luck

## 🌐 What Are IP Addresses?

* IP = **Internet Protocol**
* Like home addresses—but for your computer
* Used so that data (called **IP packets**) knows where to go

## 🔢 Two Main IP Address Versions

1. **IPv4** – four octets, separated by dots (e.g. `192.0.2.235`)
2. **IPv6** – eight groups of hexadecimal digits, separated by colons (e.g. `4527:0a00:1567:0200:ff00:0042:8329`)

   * Introduced because we ran out of IPv4 addresses (too many devices, not enough house numbers)

## 📦 How Data Travels – IP Packets

* Data sent across a network = broken into **IP packets** (also called **datagrams**)
* Each packet has:

  * **Header**:

    * Source IP address
    * Destination IP address
    * Delivery info (kinda like "Fragile: Don't yeet")
  * **Payload**:

    * The actual data (text, image, etc.)
    * Also holds **other protocols**

## 📉 What Can Go Wrong with Packets?

Just like letters, packets can:

* Show up **out of order**
* Get **damaged or corrupted**
* Be **dropped/lost** during transit

## 🛠 How Problems Are Handled – TCP & UDP

### 💂‍♂️ TCP (Transmission Control Protocol)

* Fixes: **Order**, **loss**, and **corruption**
* Ensures data arrives *correctly* and *completely*
* Used for:

  * Text files
  * Images
  * Anything that must arrive in perfect condition
* 🐢 Slight delay due to extra checks

### 🕶 UDP (User Datagram Protocol)

* Fixes **corruption only**
* Allows:

  * Packets to arrive out of order
  * Packets to vanish like your gym motivation
* Used for:

  * Voice calls
  * Live video streaming
  * Anything where *speed > perfection*

## 🧠 Summary (aka TL;DR for your short attention span)

* IP addresses = your device’s home address on the internet
* IP packets = the letters being sent
* **TCP** = perfectionist postman (safe but slow)
* **UDP** = speed freak courier (fast but forgetful)
* Without protocols, the internet would be like a mailroom run by raccoons: chaos.

---

# 🌐 **HTTP & HTTPS Basics**

* **HTTP (Hypertext Transfer Protocol):** Foundation of data exchange on the web. Enables communication between web browsers (clients) and web servers.
* **HTTPS (Secure HTTP):** Encrypted version of HTTP. Ensures secure communication (look for the 🔒 lock icon in your browser).
* **Encryption:** Converts data into secret code to prevent unauthorized access.

## 📤 **HTTP Request Structure**

Each HTTP request includes:

1. **Request Line**

   * Format: `METHOD /path HTTP/version`
   * Example: `GET /home.html HTTP/1.1`

2. **HTTP Methods**

   * `GET`: Retrieve data.
   * `POST`: Send data.
   * `PUT`: Replace existing resource.
   * `DELETE`: Remove a resource.
   * `PATCH`: Partially update a resource.

3. **Headers**

   * `Host`: Server’s domain.
   * `User-Agent`: Info about the client/browser.
   * `Accept`: Expected content types.
   * `Accept-Language`: Preferred language.
   * `Content-Type`: Type of body content (e.g., JSON).

4. **Body (Optional)**

   * Usually included with `POST`, `PUT`, or `PATCH` requests.
   * Contains the data being sent.

   **Example:**

   ```http
   POST /users HTTP/1.1
   Host: example.com
   Content-Type: text/json

   {
     "key1": "value1",
     "key2": "value2"
   }
   ```

## 📥 **HTTP Response Structure**

1. **Status Line**

   * Format: `HTTP/version status_code status_message`
   * Example: `HTTP/1.1 200 OK`

2. **Headers**

   * `Date`: When the response was generated.
   * `Server`: Info about the web server software.
   * `Content-Length`: Size of the response.
   * `Content-Type`: Type of media returned.

3. **Body**

   * Contains requested content (HTML, image, JSON, etc.)

   **Example:**

   ```http
   HTTP/1.1 200 OK
   Date: Fri, 11 Feb 2022 15:00:00 GMT+2
   Server: Apache/2.2.14 (Linux)
   Content-Length: 84
   Content-Type: text/html

   <html>
     <head><title>Test</title></head>
     <body>Test HTML page.</body>
   </html>
   ```

## ✅ **HTTP Status Codes**

Grouped by **first digit**:

| Category              | Range   | Description                  | Common Codes                                                                            |
| --------------------- | ------- | ---------------------------- | --------------------------------------------------------------------------------------- |
| **1xx** Informational | 100–199 | Request received, continuing | 100 Continue, 101 Switching Protocols                                                   |
| **2xx** Success       | 200–299 | Request successful           | 200 OK, 201 Created, 202 Accepted, 204 No Content                                       |
| **3xx** Redirection   | 300–399 | Resource moved               | 301 Moved Permanently, 302 Found                                                        |
| **4xx** Client Error  | 400–499 | Client-side issues           | 400 Bad Request, 401 Unauthorized, 403 Forbidden, 404 Not Found, 405 Method Not Allowed |
| **5xx** Server Error  | 500–599 | Server-side issues           | 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable                     |


## 🔐 **Why HTTPS Matters**

* Prevents eavesdropping or tampering.
* Essential for transmitting sensitive info (like credit card data).
* Behaves like HTTP but encrypts the communication.

## 🧠 **Summary**

* **HTTP**: Request-response protocol for web communication.
* **HTTPS**: Secure, encrypted version of HTTP.
* **Requests**: Include method, path, headers, (optional) body.
* **Responses**: Include status code, headers, (optional) body.
* **Status Codes**: Indicate result (success, error, etc.).
* You use **HTTPS every day**—every time you log in, buy something, or browse securely online.

---

# Other Internet Protocols

## 🔌 **1. Dynamic Host Configuration Protocol (DHCP)**

* **Purpose**: Assigns IP addresses to devices on a network automatically.
* **Works Over**: User Datagram Protocol (UDP).
* **DHCP Server**: Keeps track of connected devices and their assigned IPs.


## 🌐 **2. Domain Name System Protocol (DNS)**

* **Purpose**: Resolves domain names (like `meta.com`) to IP addresses.
* **Function**: Helps your computer know where to send requests when visiting websites.

## 📥 **3. Internet Message Access Protocol (IMAP)**

* **Purpose**: Used by email clients to download and manage emails from a server.
* **Benefit**: Allows access to email from multiple devices and keeps messages synced.

## 📤 **4. Simple Mail Transfer Protocol (SMTP)**

* **Purpose**: Sends emails from clients to mail servers.
* **Note**: Can also receive emails, but **IMAP is more commonly used** for that.

## 📨 **5. Post Office Protocol (POP)**

* **Purpose**: Downloads emails from server to local device.
* **Key Difference from IMAP**:

  * **POP**: Deletes emails from the server after download.
  * **IMAP**: Keeps emails on the server.
* **Use Case**: Sometimes used in automation due to its simplicity.

## 📁 **6. File Transfer Protocol (FTP)**

* **Purpose**: Transfers files between computers and servers (e.g., uploading website files).
* **Functions**: List, send, receive, delete files on a remote server.
* **Requirements**:

  * FTP Server on the server side.
  * FTP Client on the local machine.

## 🔐 **7. Secure Shell Protocol (SSH)**

* **Purpose**: Securely access and control a remote computer/server.
* **Features**:

  * Encrypts all communication.
  * Commonly used for remote administration.

## 🔒 **8. Secure File Transfer Protocol (SFTP)**

* **Purpose**: Securely transfers files using SSH.
* **Key Point**: Unlike FTP, **SFTP encrypts data**, preventing third-party interception.
* **Compatibility**: Most FTP clients also support SFTP.

---

## 🖥️ **Web Pages, Websites, and Web Applications**

### ✅ **Web Page**

* A **single document** made with HTML, CSS, and JavaScript.
* Displays **text, images, videos, and content** in a web browser.
* Example: An individual article or product page.

### 🌐 **Website**

* A **collection of web pages** under a **single domain name**.
* Pages are connected via **hyperlinks** (HTML links to other content).
* Example: An online encyclopedia with multiple articles.

### 💻 **Web Application**

* A website with a **high level of interactivity and dynamic content**.
* Responds to **user input** and customizes data per user.
* Example: Online food ordering or email services.
* **Key difference**:

  * **Website** = mostly informative.
  * **Web Application** = interactive and user-driven.

---

## 🧰 **Frameworks and Libraries**

### 🧱 **Libraries**

* Reusable code packages that offer **specific functionality**.
* **Unopinionated** – the developer controls how and when to use them.
* Example: An email validation library.
* **Used when** you need help with small, focused tasks.
* Benefit: Saves time, prevents repetitive work.

### 🏗️ **Frameworks**

* Provide a **structure/blueprint** for building applications.
* **Opinionated** – enforce best practices and coding conventions.
* Handle **common app features** (e.g., HTTP requests/responses).
* Developer plugs in their own code within the framework’s structure.
* Example: Django, React, Angular, etc.
* Benefit: Faster development, built-in best practices.
* Downside: Less flexibility, possible library conflicts.

---

## ⚖️ **Frameworks vs Libraries**

| Feature             | Libraries                         | Frameworks                                     |
| ------------------- | --------------------------------- | ---------------------------------------------- |
| Scope               | Specific functionality            | Full app structure                             |
| Control             | Developer controls flow           | Framework controls flow (inversion of control) |
| Opinionatedness     | Low (unopinionated)               | High (opinionated)                             |
| Flexibility         | High                              | Limited to framework structure                 |
| Ease of Replacement | Easy to replace                   | Harder to replace                              |
| Example Use         | Email validation, date formatting | Handling routing, requests, app logic          |

---

## 💡 **Other Key Notes**

* **Open Source**: Code is freely available to use/modify.
* **Proprietary**: Code is licensed or developed internally.
* **Reuse is essential** in modern development: Saves time, reduces bugs, and avoids reinventing the wheel.
* Most frameworks **include libraries**, and you can also add your own libraries to them.

---

Here are all the **important notes** extracted and clearly organized from your passage on **APIs**:

---

## 🔌 **API (Application Programming Interface)**

### ✅ **Definition**

* A **set of functions and procedures** for building apps that interact with an OS, application, or service.
* Acts as a **bridge**, **gateway**, or **middleware** between systems.
* APIs are used to **access features, services, or data**.
* Broad term – covers many types of tools and systems.

---

## 👩‍💻 **Importance for Web Developers**

* Used **daily** to retrieve, send, and manipulate data.
* Enable communication between **frontend (browser)** and **backend (server)**.
* **Extend browser functionality**, fetch external data, or control hardware via sensors.

---

## 🌐 **Types of APIs in Web Development**

### 1. **Browser or Web APIs**

* **Built into browsers**.
* Provide **predefined functions** to interact with web documents and user devices.

#### 📋 Examples:

| API                 | Function                                                       |
| ------------------- | -------------------------------------------------------------- |
| **DOM API**         | Represents HTML as a tree of JavaScript objects.               |
| **Geolocation API** | Gets user's geographic location.                               |
| **Fetch API**       | Makes HTTP requests (replaces XMLHttpRequest).                 |
| **Canvas API**      | Draws graphics/images via JavaScript.                          |
| **History API**     | Manages browser session history.                               |
| **Web Storage API** | Stores key-value pairs locally (localStorage, sessionStorage). |

---

### 2. **REST API (Representational State Transfer)**

* **Most common data API** in web and mobile development.
* Used to **send/receive data** between client and server.
* REST uses **HTTP methods** for CRUD operations:

#### 🧾 HTTP Methods:

| Method | Purpose       |
| ------ | ------------- |
| GET    | Retrieve data |
| POST   | Create data   |
| PUT    | Update data   |
| DELETE | Delete data   |

#### 🔗 Endpoints:

* Specific **URLs** that represent resources or actions.
* Example: `https://api.example.com/users`

#### 📦 Response Types:

* Often return data in **JSON format**.
* Sometimes return full HTML/webpages.

---

### 3. **Sensor-Based APIs (IoT APIs)**

* Used in **Internet of Things (IoT)** devices.
* Enable **physical sensors** to communicate data via APIs.

#### 📱 Examples:

| Device          | Use Case                      |
| --------------- | ----------------------------- |
| **Philips Hue** | Smart lighting systems.       |
| **NodeBots**    | JavaScript-controlled robots. |

---

## 💡 **Key Concepts to Remember**

* **APIs = Extenders + Connectors**: They enhance what you can do as a developer and link systems together.
* REST APIs are the **data backbone** for modern apps.
* Good API design includes **discoverable endpoints**, **predictable responses**, and **clear documentation**.
* As a developer, you may use:

  * **Your own APIs**
  * **Third-party APIs**
  * **Built-in browser APIs**

---

