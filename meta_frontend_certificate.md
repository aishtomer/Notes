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

### 🏗️ **HTML Basics & History**

* **HTML** stands for **Hypertext Markup Language**.
* **Hypertext**: Text with links to other content.
* **Markup**: Tags and elements used to structure a document.
* Invented by **Sir Tim Berners-Lee** at **CERN**.
* First version of HTML: **1991**.
* Maintained by the **W3C (World Wide Web Consortium)**.
* Current version: **HTML5**.

---

### 🧱 **HTML Structure = The Frame of a Webpage**

* HTML is like the **frame of a building** — it gives structure.
* Files are **.html** (e.g. `index.html`).
* Can be opened in a browser even **without a web server**.

---

### 📄 **HTML Document Skeleton**

1. `<!DOCTYPE html>` – Declares the document type.
2. `<html>` – Root element of the document.

   * `<head>` – Metadata (not displayed on the page).

     * `<title>` – Shown on browser tab.
     * `<meta>` – Info like description, keywords, charset, etc.
   * `<body>` – Actual page content (headings, paragraphs, images, etc.).

---

### 🏷️ **Tags vs. Elements**

* **Tags** = The syntax inside angle brackets (e.g., `<p>`).
* **Elements** = Full construct with opening tag, content, and closing tag (e.g., `<p>Hello</p>`).
* **Self-closing elements**: Don’t need a closing tag. Example: `<br>`.

---

### 📚 **Common HTML Tags**

#### ➤ **Text Elements**

* `<h1>` to `<h6>` – Headings (H1 is biggest/most important).
* `<p>` – Paragraph.
* `<br>` – Line break (self-closing).
* `<strong>` – Strong importance (often bold).
* `<b>` – Just bold (no semantic importance).
* `<em>` – Emphasized (usually italicized).
* `<i>` – Italics (used for technical terms, titles, etc.).

#### ⚖️ **Emphasis vs Italics**

* `<em>` has **semantic meaning** (screen readers notice).
* `<i>` is for **stylistic offset** (screen readers ignore).

---

### 📋 **Lists**

* `<ul>` – Unordered list (bullets).
* `<ol>` – Ordered list (numbers).
* `<li>` – List item (used inside `<ul>` or `<ol>`).

---

### 📦 **Div Tag**

* `<div>` – Block-level container for grouping elements.
* Has **no visual effect** without CSS.
* Can be **nested**.
* Can be **styled with CSS**:

  ```html
  <style>
    div {
      border: 1px solid black;
      padding: 2px;
    }
  </style>
  ```

---

### 💬 **Comments**

* Use `<!-- comment -->` to leave notes in your HTML code.
* Not displayed in the browser.

---

### 🍋 **Little Lemon Restaurant Example**

* `index.html` file created in **Visual Studio Code**.
* Used:

  * `<h1>` for **"Our Menu"**
  * `<h2>` for **"Falafel"** and **"Pasta Salad"**
  * `<p>` for descriptions like "Chickpeas, herbs, and spices".
* File saved, then opened in browser to preview.
* Inspired tip: Look at food websites for HTML tag practice.

---

### 🔶 **HTML Forms**

* **Purpose**: Allow users to input data on web pages (e.g., credit card details, login info).
* **Tag Used**: `<form>`

  * **Attributes**:

    * `action`: URL/path to which the form data is submitted.
    * `method`: HTTP method used to send data (`GET` or `POST`).
* **Common Input Fields**:

  * `<input type="text">` – for single-line input like usernames.
  * `<input type="password">` – masks input for passwords.
  * `<input type="submit">` – creates a button to submit the form.
  * `<input type="checkbox">` – allows multiple options to be selected.
  * `<input type="radio">` – allows only one option in a group to be selected.
  * `<input type="email">`, `<input type="number">`, `<input type="file">` – specialized input types.
* **Other Elements**:

  * `<label>` – gives context to input fields.
  * `<textarea>` – for multi-line text input (e.g., comments).
  * `<select>` and `<option>` – create a dropdown list.

---

### 🔶 **Document Object Model (DOM)**

* **Definition**: A tree-like structure representing an HTML document in the browser.
* **Purpose**: Allows JavaScript to dynamically access and manipulate HTML content.
* **Structure**:

  * Root: `html` object.

    * Contains `head` and `body`.

      * `head` contains elements like `title`.
      * `body` contains visible page content like `div`, `h1`, `p`, etc.
* **JavaScript Interaction with DOM**:

  * Access/modify content and attributes.
  * Add/remove HTML elements.
  * Respond to user actions (e.g., clicks, mouseovers).
  * Create animations (e.g., fade-ins, popups).
* **Use Cases**:

  * Updating a digital clock.
  * Previewing a movie on hover.
  * Disabling/enabling buttons on login forms.
  * Displaying error messages dynamically.
* **Libraries**: React and other JavaScript libraries rely heavily on the DOM.

---

### 🔶 **Web Accessibility**

* **Goal**: Make websites usable by people with a wide range of disabilities.
* **Initiative**: WAI (Web Accessibility Initiative) by W3C.

  * Supported by legislation like the EU Web Accessibility Directive (2016).
* **Disabilities Covered**:

  * Visual, auditory, cognitive, neurological, physical, speech-related.
* **Assistive Technologies**:

  * **Screen readers** – read out webpage content.
  * **Speech recognition software** – convert speech to text or commands.
  * **Subtitles/video scripts** – aid those with hearing or visual impairments.
* **Best Practices**:

  * Use proper HTML structure (e.g., headings, paragraphs).
  * Avoid bad practices like multiple `<br>` tags for spacing.
  * Consider accessibility *from the start* of development.
* **ARIA (Accessible Rich Internet Applications)**:

  * Specification for making complex web applications more accessible.
  * Provides techniques to improve accessibility beyond basic HTML.

---

## 💻 **HTML & CSS Analogy**

* **HTML = Structure of the house** (walls, beams, roof).
* **CSS = Style & Decor** (paint, wallpaper, lighting, furniture).

---

## 🎯 **What CSS Does**

* CSS **tells the browser how to display HTML** elements.
* It styles content with colors, layouts, fonts, and more.
* It’s what stops your site from looking like 1997 vomited on a screen.

---

## 🧱 **Anatomy of a CSS Rule**

```css
selector {
  property: value;
  property: value;
}
```

### Components:

* **Selector** – targets the HTML element(s).
* **Property** – what you want to style (e.g. `color`, `margin`).
* **Value** – the style setting (e.g. `blue`, `10px`).
* **Declaration block** – curly braces `{}` wrapping properties.

---

## 🧠 **CSS Specificity & Precedence**

* **ID selectors override** type and class selectors.
* CSS follows a **specificity hierarchy**.
* The **more specific** the selector, the **more it dominates** like a diva at a karaoke night.

---

## 🛠️ **CSS File Setup**

1. Create HTML file (e.g. `index.html`).
2. Create CSS file (e.g. `style.css`).
3. Link in HTML `<head>`:

   ```html
   <link rel="stylesheet" href="style.css">
   ```

---

## 🔍 **Common CSS Selectors**

### 1. **Element Selector**

* Targets all of a specific tag type.

```css
p {
  color: blue;
}
```

### 2. **ID Selector**

* Targets one unique element.
* Use `#` prefix.

```css
#latest {
  background-color: purple;
}
```

### 3. **Class Selector**

* Targets all elements with a shared class.
* Use `.` prefix.

```css
.navigation {
  margin: 2px;
}
```

### 4. **Element with Class**

* Targets specific tags **with** a class.

```css
p.introduction {
  margin: 2px;
}
```

### 5. **Descendant Selector**

* Targets elements *within* another element.

```css
#blog h1 {
  color: blue;
}
```

* Multiple levels possible:

```css
#blog div h1 {
  color: blue;
}
```

### 6. **Child Selector**

* Targets **direct children** only.

```css
#blog > h1 {
  color: blue;
}
```

* Doesn’t go more than one level deep.

---

## 🖱️ **:hover Pseudo-Class**

* Adds interactivity on mouse hover.

```css
a:hover {
  color: orange;
}
```

* Great for buttons, links, hover effects—basically anything that likes attention.

---

## 🔧 **Pro Tip: VS Code Live Preview**

* Use **Live Preview extension** to see changes instantly without refreshing.
* Right-click your HTML file > **Show Preview**.

---

## 🏁 **Quick Recap**

* **Selector + Declaration Block = CSS Rule**.
* Declaration = **property: value;**
* Styles are applied based on **specificity**.
* Master selectors = master styling.

---

## 🎨 **COLOR in CSS**

### **Color Properties**

Used in many places like `color`, `background-color`, `border-color`, etc.

### **5 Ways to Define Color:**

1. **RGB**

   * Format: `rgb(R, G, B)`
   * Range: 0–255
   * Example: `rgb(255, 0, 0)` = red

2. **RGBA**

   * Format: `rgba(R, G, B, A)`
   * Adds **opacity** (A = 0 to 1)
   * Example: `rgba(255, 0, 0, 0.5)` = 50% transparent red

3. **HSL**

   * Format: `hsl(H, S%, L%)`
   * H = Hue (0–360), S = Saturation, L = Lightness
   * Example: `hsl(0, 100%, 50%)` = pure red

4. **Hexadecimal**

   * Format: `#RRGGBB`
   * Base-16 numbers (0–9, A–F)
   * Example: `#FF0000` = red

5. **Predefined Color Names**

   * Examples: `red`, `green`, `blue`, `black`, `white`, etc.
   * Total: 140 browser-supported names

---

## ✍️ **TEXT in CSS**

### **Text Color**

* Property: `color`
* Example:

  ```css
  p { color: red; }
  ```

### **Font Family**

* Property: `font-family`
* Use **fallbacks** for missing fonts
* Example:

  ```css
  p { font-family: "Courier New", monospace; }
  ```

### **Font Size**

* Property: `font-size`
* Can use `px`, `em`, `%`, etc.
* Example:

  ```css
  p { font-size: 12px; }
  ```

### **Text Transformation**

* Property: `text-transform`
* Values: `uppercase`, `lowercase`, `capitalize`, `none`
* Example:

  ```css
  p { text-transform: uppercase; }
  ```

### **Text Decoration**

* Shorthand Property: `text-decoration`
* Full custom properties:

  * `text-decoration-line`: underline, overline, line-through, none
  * `text-decoration-color`: sets color of the line
  * `text-decoration-style`: solid, double, dotted, dashed, wavy
  * `text-decoration-thickness`: sets line thickness
* Example:

  ```css
  p {
    text-decoration-line: underline;
    text-decoration-color: red;
    text-decoration-style: solid;
    text-decoration-thickness: 5px;
  }
  ```

---

## 📦 **CSS BOX MODEL: The VIP Layout Formula**

> Think of every HTML element as a Russian doll of layout pieces — each part wrapping the other like an overly dramatic fashion show. Here's what you're working with:

---

### 🔹 **The Four Layers of the Box Model**

1. **Content**

   * The *actual stuff*: text, images, videos, memes, emotional damage — whatever.
   * You can control its size using:

     * `width`, `min-width`, `max-width`
     * `height`, `min-height`, `max-height`

2. **Padding**

   * Think of this as the *bubble wrap* around the content.
   * It pushes the border away from the content.
   * Controlled with:

     * `padding-top`, `padding-right`, `padding-bottom`, `padding-left`
   * Shorthand? Use `padding`.

3. **Border**

   * The *frame* that wraps around both the content and padding.
   * You can style it with:

     * `border-width`, `border-style`, `border-color`
     * Widths: `thin`, `medium`, `thick` (or specific pixel values)
   * Types: `solid`, `dashed`, `dotted`, `double`, etc.

4. **Margin**

   * The *personal space* zone — keeps elements from being all up in each other’s business.
   * Controlled with:

     * `margin-top`, `margin-right`, `margin-bottom`, `margin-left`
   * Shorthand? Use `margin`.

---

### 🧠 **Size Calculations Breakdown**

Let’s pretend you passed high school math. Here’s how the browser calculates each box:

* **Padding Box Width** =
  `content width + padding-left + padding-right`

* **Padding Box Height** =
  `content height + padding-top + padding-bottom`

* **Border Box Width** =
  `padding box width + border-left + border-right`

* **Border Box Height** =
  `padding box height + border-top + border-bottom`

* **Margin Box Width** =
  `border box width + margin-left + margin-right`

* **Margin Box Height** =
  `border box height + margin-top + margin-bottom`

---

### 🎨 **Visual Metaphor to Remember It**

> 🧍‍♀️ **You = Content**
> 🧥 **Clothes = Padding**
> 🧢 **Silhouette = Border**
> ⛔ **Personal space = Margin** (Don’t stand so close, Karen.)

---

### 🧙‍♂️ **Pro Developer Wisdom**

* The **box model** is *how browsers understand layout*. Every damn thing you see is a box. A box in a box in a box. It’s like CSS Inception.
* Shorthand properties like `margin` and `padding` can save your life (and your keyboard).

---

## 🧱 **Document Flow & Element Display**

### 💡 **What Is Document Flow?**

* It’s how the browser *naturally* places elements on the screen — like Tetris, but for tags.
* Two main categories of HTML elements:

  * **Block-level elements**: Full-width, new line before & after, stack vertically like pancakes.
  * **Inline elements**: Only as wide as their content, no line breaks — they chill side-by-side.

---

## 🧱 **Block-Level Elements**

* Take up **entire horizontal width** of the parent.
* Cause **line breaks** before and after.
* Examples:

  * `<div>`, `<form>`, `<h1>`–`<h6>`, `<p>`

---

## 🧵 **Inline Elements**

* Only as big as their **content**.
* Do **not** force a line break.
* Fit like puzzle pieces in the flow.
* Examples:

  * `<span>`, `<a>`, `<img>`, `<input>`, `<label>`, `<b>`, `<i>`, `<em>`

---

## 🔄 **Switching Between Block & Inline**

* Use the **`display` property** in CSS:

  * `display: block;` → Forces full-width and new line.
  * `display: inline;` → Flow with text, no break.
  * You can *change an element’s display* type anytime with CSS.

---

## 🧪 **Example Recap**

* Replacing `<span>` with `<div>` moves content to a new line.
* Set `display: inline;` in CSS to revert `<div>` to inline behavior.

```css
#middle {
  display: inline;
}
```

---

## ✍️ **Text Alignment**

* Use `text-align` for aligning **text** inside elements:

  ```css
  p {
    text-align: center; /* left, right, center, justify */
  }
  ```

* Default:

  * `left` for LTR languages (like English)
  * `right` for RTL languages (like Arabic)

---

## 🧲 **HTML Element Alignment**

> Now we’re in the **"align me like a pro"** section.

### ✅ **Centering Block-Level Elements**

1. **Set a width** on the element.
2. Use `margin: auto;` to center it horizontally.

```css
.child {
  width: 50%;
  padding: 20px;
  margin: auto;
  display: block;
}
```

### ✅ **Centering Inline Elements (e.g., `<img>`)**

* Convert to block:

  ```css
  .child {
    display: block;
    width: 50%;
    margin: auto;
  }
  ```
* Or just set:

  ```css
  margin-left: auto;
  margin-right: auto;
  ```

---

## 🧭 **Left / Right Alignment with Float**

* Use the `float` property to pin elements to the left or right.

### Example:

```html
<div class="parent">
  <img src="photo.png" class="child">
  Lorem ipsum dolor...
</div>
```

```css
.child {
  float: right;
}
```

* Result: Image goes to the right, text wraps around it like a clingy ex.

---

## 🏆 TL;DR – Golden Nuggets

| Concept             | What It Means                                      |
| ------------------- | -------------------------------------------------- |
| **Document Flow**   | Default order & positioning of HTML elements       |
| **Block Element**   | Full-width, new line (e.g., `<div>`)               |
| **Inline Element**  | Fits content, same line (e.g., `<span>`)           |
| **display: block**  | Forces full-width behavior                         |
| **display: inline** | Keeps element inline with text                     |
| **text-align**      | Aligns text (`left`, `right`, `center`, `justify`) |
| **margin: auto**    | Horizontally centers block-level elements          |
| **float: right**    | Pushes element right, wraps text around it         |

---

