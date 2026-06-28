# Chapter 1 - Introduction to Burp Suite

[![Burp Suite](Images/burpsuite.png)]


---

# What is Burp Suite?

Burp Suite is one of the most popular Web Application Security Testing tools.

It is developed by PortSwigger.

Official website:

https://portswigger.net

Burp Suite is used by:

* Penetration Testers
* Bug Bounty Hunters
* Security Researchers
* CTF Players
* Web Application Security Engineers

---

# Why do we need Burp Suite?

Normally:

```text
Browser  ------------->  Server
```

The browser sends a request directly to the server.

The server immediately sends a response.

We cannot see what is happening.

---

Burp Suite places itself between the browser and the server.

```text
Browser
     │
     ▼
Burp Suite
     │
     ▼
Server
```

Now every request passes through Burp first.

This gives us full control.

---

# What can Burp Suite do?

Burp can:

✔ View every request

✔ View every response

✔ Modify requests

✔ Modify headers

✔ Modify parameters

✔ Replay requests

✔ Scan applications

✔ Test vulnerabilities

---

# Burp Suite Editions

There are two versions.

## Community Edition

Free.

Suitable for:

* Learning
* CTF
* Basic Pentesting

---

## Professional Edition

Paid.

Includes:

* Scanner
* Automation
* Advanced Features

For learning Community Edition is enough.

---

# First Launch

When Burp starts we selected

```text
Temporary Project
```

Reason:

We don't need to save a project while learning.

Then:

```text
Next

↓

Start Burp
```

---

# Burp Interface

The main tabs are:

```text
Dashboard

Proxy

Intruder

Repeater

Logger

Extensions
```

Each tab has a different purpose.

---

# Dashboard

Shows:

* Events
* Alerts
* Logs
* Running Tasks

Usually beginners don't spend much time here.

---

# Proxy

This is the most important module for beginners.

Everything starts here.

Path

```text
Proxy

↓

Intercept
```

---

# What is a Proxy?

A proxy is a computer that sits between two computers.

Instead of talking directly:

```text
Browser

↓

Server
```

Communication becomes:

```text
Browser

↓

Proxy

↓

Server
```

Burp acts as that Proxy.

---

# Intercept

This feature stops every HTTP request.

Example:

Browser wants to visit

```text
https://portswigger.net
```

Instead of sending it directly

Burp says:

"Wait.

Let me inspect this request first."

---

When Intercept is ON

Every request stops inside Burp.

We have four choices.

---

## Forward

Send the request.

---

## Drop

Delete the request.

The server never receives it.

---

## Edit

Modify the request.

For example:

Headers

Cookies

Parameters

Values

Everything can be edited.

---

## View

Simply inspect the request.

No changes.

---

# Our First Request

After opening Firefox

We visited

```text
https://portswigger.net
```

Burp intercepted a request.

Surprisingly

The Host was

```text
fonts.googleapis.com
```

instead of

```text
portswigger.net
```

---

# Why?

Because modern websites use many external resources.

For example

Fonts

JavaScript

Images

CSS

Analytics

The browser sends many HTTP requests.

Not just one.

This was our first important observation.

---

# Lesson Learned

One webpage

≠

One request

A modern webpage may generate

10

50

100

or even more HTTP requests.

Understanding this is extremely important for Web Security.

---

# Summary

After this chapter we learned

✔ What Burp Suite is

✔ Why Burp Suite is important

✔ How a Proxy works

✔ What Intercept does

✔ Why browsers generate multiple requests

✔ How Burp intercepts browser traffic

---

# Next Chapter

Understanding HTTP Requests


# Chapter 2 - Understanding HTTP Requests

---

# What is HTTP?

HTTP stands for:

```text
HyperText Transfer Protocol
```

It is the language used by browsers and web servers to communicate.

When you open a website, your browser sends an HTTP Request.

The server receives it and sends back an HTTP Response.

---

# Communication Model

```text
Browser
     │
     │ HTTP Request
     ▼
Server
     ▲
     │ HTTP Response
     │
Browser
```

Everything you do on a website follows this model.

Examples:

* Open a page
* Login
* Search
* Upload a file
* Download a file

Everything is an HTTP Request.

---

# Our First Request

The first intercepted request looked similar to:

```http
GET / HTTP/1.1

Host: fonts.googleapis.com

User-Agent: Mozilla/5.0

Accept: text/css,*/*;q=0.1

Accept-Language: en-US,en;q=0.9

Accept-Encoding: gzip, deflate, br

Cookie: session=...
```

Now we will analyze every line.

---

# GET

```http
GET
```

GET is an HTTP Method.

Methods describe what we want to do.

Examples:

GET

Read information.

POST

Send information.

PUT

Update information.

DELETE

Delete information.

For now we only focus on GET.

---

Example

```http
GET / HTTP/1.1
```

Meaning:

"Please send me the main page."

---

# HTTP/1.1

```http
HTTP/1.1
```

This is the HTTP protocol version.

Common versions:

HTTP/1.0

HTTP/1.1

HTTP/2

HTTP/3

Modern websites usually use HTTP/2 or HTTP/3.

---

# Host

```http
Host: fonts.googleapis.com
```

Host tells the server which website we want.

One server can host many websites.

Without the Host header the server may not know which website should answer.

---

# User-Agent

```http
User-Agent: Mozilla/5.0
```

This identifies the browser.

It may include:

* Browser name
* Browser version
* Operating system
* CPU architecture

Many websites behave differently depending on the User-Agent.

Example:

Desktop version

Mobile version

Different browsers

Different operating systems

---

# Accept

```http
Accept: text/css,*/*;q=0.1
```

This tells the server what type of content we want.

Examples:

HTML

CSS

Images

JSON

XML

Our request expected CSS.

That makes sense because it came from Google Fonts.

---

# Accept-Language

```http
Accept-Language: en-US,en;q=0.9
```

This tells the server our preferred language.

We performed an experiment.

Changed:

```http
Accept-Language: fa-IR
```

Result:

Nothing changed.

Lesson:

This header is only a suggestion.

The server chooses whether to use it.

---

# Accept-Encoding

```http
Accept-Encoding:
gzip,
deflate,
br
```

This tells the server:

"You may compress the response."

Compression reduces bandwidth and improves loading speed.

---

# Cookie

```http
Cookie:
```

Cookies contain information stored by the browser.

Most websites use Cookies for:

* Login
* Session Management
* User Preferences

Cookies are automatically sent with every request.

---

# Important Observation

Headers are not random.

Every header has a purpose.

When learning Web Security we should always ask:

Why does this header exist?

Can it be modified?

Does the server trust it?

---

# Summary

After this chapter I learned:

✔ What HTTP is

✔ Browser ↔ Server communication

✔ HTTP Methods

✔ GET

✔ HTTP Version

✔ Host

✔ User-Agent

✔ Accept

✔ Accept-Language

✔ Accept-Encoding

✔ Cookie

---

# Next Chapter

HTTP Responses

Status Codes

Set-Cookie

Server Headers

Content-Type


# Chapter 3 - HTTP Response

---

# What is an HTTP Response?

After receiving an HTTP Request, the server sends an HTTP Response.

The Response contains:

* Status Code
* Headers
* Body (Data)

Communication:

```text
Browser
      │
      │ HTTP Request
      ▼
Server
      ▲
      │ HTTP Response
      │
Browser
```

---

# HTTP Response Structure

A typical response looks like this:

```http
HTTP/1.1 200 OK

Content-Type: text/html

Content-Length: 3156

Server: nginx

Set-Cookie: session=xxxxxxxx

<html>

...

</html>
```

---

# Status Code

The first line is always the Status Code.

Example

```http
HTTP/1.1 200 OK
```

Meaning:

Everything worked successfully.

---

# Common Status Codes

## 200

```text
200 OK
```

The request succeeded.

---

## 301

```text
301 Moved Permanently
```

The page has permanently moved.

Example

```text
http://example.com

↓

https://example.com
```

---

## 302

```text
302 Found
```

Temporary redirect.

Usually used after login.

---

## 304

```text
304 Not Modified
```

The browser already has the file.

No need to download it again.

---

## 400

```text
400 Bad Request
```

The request is invalid.

---

## 401

```text
401 Unauthorized
```

Authentication required.

---

## 403

```text
403 Forbidden
```

The server understood the request.

But access is denied.

Example:

Trying to access an admin page.

---

## 404

```text
404 Not Found
```

The page does not exist.

---

## 500

```text
500 Internal Server Error
```

The server crashed.

Sometimes this reveals useful information.

CTF players love these errors. 😈

---

# Response Headers

Headers also exist in Responses.

Examples:

```http
Server

Content-Type

Content-Length

Set-Cookie

Cache-Control
```

---

# Content-Type

Example

```http
Content-Type: text/html
```

Meaning:

The server is sending an HTML page.

Other examples:

```text
application/json

image/png

text/css

application/pdf
```

The browser decides how to display the response using this header.

---

# Content-Length

Example

```http
Content-Length: 5421
```

Meaning:

Response size.

Measured in bytes.

---

# Server

Example

```http
Server: nginx
```

Possible values:

Apache

nginx

IIS

Caddy

Sometimes this reveals useful information about the target.

---

# Set-Cookie

This is one of the most important headers.

Example

```http
Set-Cookie:

session=abf29dk3...
```

The server is saying:

"I created a session for you."

The browser stores it automatically.

Then...

Every future request sends:

```http
Cookie:

session=abf29dk3...
```

---

# Difference

Server →

```http
Set-Cookie
```

Browser →

```http
Cookie
```

This difference is extremely important.

---

# Session

Think of a Session like a temporary ID card.

Example:

You login.

The server creates:

```text
Session ID

↓

83f91ad2...
```

The browser stores it.

Then sends it with every request.

Without it

The server would think you are a new visitor.

---

# Why Sessions Matter

Most authentication systems depend on Sessions.

If an attacker steals your Session

He may become you.

This is called:

```text
Session Hijacking
```

We will study it later.

---

# What I Learned

✔ Request

✔ Response

✔ Status Codes

✔ Response Headers

✔ Content-Type

✔ Content-Length

✔ Server

✔ Set-Cookie

✔ Session

✔ Difference between Cookie and Set-Cookie

---

# Mission

Open Burp Suite.

Find a Response.

Answer these questions:

1.

What Status Code did the server return?

2.

Which Server is being used?

3.

Does the Response contain Set-Cookie?

4.

What Content-Type is returned?

Do NOT modify anything.

Just observe.

---

# Next Step

After completing the Burp Suite fundamentals, the next phase of learning will be through real-world labs from **PortSwigger Web Security Academy**.

## SQL Injection Lab

[![SQL Injection Lab](Images/sql-injection.png)](https://portswigger.net/web-security/sql-injection/lab-login-bypass)

**Lab Link:**

https://portswigger.net/web-security/sql-injection/lab-login-bypass

### Learning Objectives

* Understand how SQL Injection works.
* Learn how web applications communicate with databases.
* Analyze HTTP Requests and Responses using Burp Suite.
* Practice modifying requests to identify SQL Injection vulnerabilities.
* Solve the lab step by step while understanding every concept instead of memorizing payloads.

### Status

* ✅ Linux Basics
* ✅ Burp Suite Fundamentals
* ✅ HTTP Requests
* ✅ HTTP Responses
* ✅ Cookies & Sessions
* ⏳ SQL Injection (Current Mission)
