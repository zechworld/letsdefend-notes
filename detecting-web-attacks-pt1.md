# What are web attacks?

A web application is an application that provides some kind of services through Internet using a browser interface. This applications make up a large parte of the Internet usage today (e.g. Google, Facebook, YouTube, etc). This acts as an interface between the user's machine and the Internet, which makes it vulnerable for exploits, and as consequence, attackers can gain access to devices and all sorts of personal data or organizational data.

## Web Application Defined
The Web is a highly programmable environment that allows mass customization through the deployment of a large and diverse range of applications to millions of global users. Modern websites are constructed from **"Web Browser"** and **"Web Application"**.

- Web Browser is a software that allows users to retrieve data and interact with content located within a website.Through this, websites allow the *capture, processing, storage and transmission* of sensitive customer data for immediate and recurrent use, all of this is done through *web applications*.

- Web Applications are computer programs allowing website visitors to submit and retrieve data to/from a database over the Internet. This data is presented to the user within their browser as information generated dynamically by the web application. 


Some of the attacks methods used to infiltrate web applications are:
- SQL Injection
- Cross Site Scripting
- Command Injection
- IDOR
- RFI & LFI
- File Upload (Web Shell)

## Why Detecting Web Attacks 
Web applications are consider as gateways for attackers, mainly because these apps contain critical data. Organizations have multiple web application that are highly complex and have numerous attack vectors, making it difficult to control. Around 75% of cyber attacks are done through web apps, this is why we need to have strong security measures that aim at preventing and detecting threats that exploit Web Apps (WAF, IPS, SIEM rules).

## OWASP
O = Open
W = Worldwide
A = Application
S = Security
P = Project

Non profit foundation dedicated to improving software security. It publishes a list of the 10 web app vulnerabilities that post the most critical security risks. The 2021 list was as follows:

1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Insecure Design
5. Security Misconfig
6. Vulnerable and Outdated Components
7. Identification and Authentication Failures
8. Software and Data Integrity Failures
9. Security Logging and Monitoring Failures
10. Server-side Request Forgery (SSRF)

## How Web Applications Work
Web apps communicate using the **HTTP Protocol** (Layer 7 in the OSI model).

This communication protocol is between the server and the client, that wants to request a specific resource from the server. A _HTTP Request_ is sent to the server, and the server answer with an _HTTP Response_ back to the client after activating certain controls and processes:

- Client ask for "index.html" file
- Server answers with the "index.html" file

### HTTP Request
Requests are used to retrieve specific resource from a web server. The web server's job is to process the response received and present that resource to the user. The request must have a specific format, otherwise it will not be recognize and it will be perceived as an error.

The request structure consist of 3 main parts: Request line, Request Headers, and Request Message Body. 

- `**Request Line**`: Consists in a *HTTP Method (GET, POST, UPDATE, etc)* and the resource requested from the web server: ` GET / HTTP /1.1` (The / means that the main page is being requested).
- `**Request Headers**`: List of different parameters used to identify the request. 
	- Host Header: Modern web apps usually belong to more than one domain, therefore the *"Host"* header to identify which domain requested the resource. `(letsdefend.io)`
	- Cookie Header: Web applications often store information on the client's device using "cookies", these typically store session information to make the user's flow much smoother.
	- Upgrade-Insecure-Requests Header: Indicates if the client wants to communicate using encryption (SSL).`(Usually 1)`
	- User-Agent Header: Information about the client's browser and OS. Web server will use this information to send specific HTTP responses to the client.`(Mozilla/5.0 (Windows NT 10.0; Win64; x64)Chrome/97.0.4692.71)`
	- Accept Heaeder: Here the type of data requested is specified `(text/html,application/xhtml+xml,application/xml;q=0.9,image/avif)`
	- Accept-Encoding Header: The type of encoding supported by the client, specified as compression algorithms. `(gzip, deflate)`
	- Accept-Language Header: It's the client's language information, this will affect how the web server displays the prepared content in that specific language. `(en-US, en;q=0.9)`.
	- Connection Header: This header shows how the HTTP connection is made. If is "close", the TCP connection will be closed after receiving the HTTP resonse. If is "keep-alive", the connection will be maintained. `(close)`
  - Closing the *Request Headers* is done with an empty line to separate sections.
- `**Request Message Body**`: Remaining data to be sent will be specified in the Request Message Body. If the method POST is used, its parameters can be found here.

### HTTP Response
