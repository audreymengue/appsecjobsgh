# AWA 2

## DES232 Migrating OWASP 2021 Injection
An injection attack refers to a class of techniques in which an atacker manipulates an application through malicious input.

### The course will focus on cross-site injection, SQL injection, OS command injections, code injection

* Cross-site scripting (XSS) Attackers will inject code into the web page that other people will view. The script will steal sensitive information from 
  sessions and cookies and redirect users to a site that has similar content but is malicious. Occurs when applications fail to filter user inputs and 
  display that content withat proper encoding. Can me mitigated by:
	1. Input validation ( set limites on what inputs your applications can allow) Always perform it on the server, never on the client-side, browser. Centralise validation. Use an allow list. Validate form data, HTTP headers, Form data, environment variables and cookie data. Use well tested libraries and frameworks.
	2. Output encoding (Ensure proper encoding of all outputs sent to the browser )
	3. Content security policy (Standard that determines how browsers handle request)
	- Normalizing data is the ability to covert data nto a predictable format to ensure proper comarisons and other imput validation. It includes:
	1. Converting to a consistent character set/code page
	2. Considering Unicode character equivalents
	3. Converting all encoded characters to decoded value
	4. Removing all redundant characters
	5. Removing white space
	6. Cating data to the expected data type
	7. removing HTML tags and other metadata
	- Output encoding to ensure browser properly intterprets output as content and not markup. Without it, people can inject any content within the script element. You must use different strategies depending on the context:
	1. HTML content
	2. HTML elements
	3. Elements attributes
	4. JavaScript
	5. CSS
	on the side: OWASP DOM-based XSS Prevention cheat cheet
	- Content Security Policy(The most effective one): Allows developers to set an allow list-based content policy for each resourc-type, directory, and file on the same origin. Here :
	1. Mitigate cross-site scripting and other attacks
	2. Enforces HTTPS connections
	3. Allow lists for each resource type
	4. Restricts content to specific directories or files
	5. Resricts by content
	6. Origin policies for different APIs
	7. Iframe sandbox policies
	8. Blocks eval, inline scripts, inline CSS, data URIs
	9. Reports policy violations back to the server
* SQL injections uses web application input to change the behavior of a query sent to the database.
	. 1=1 always evaluates to true so the query will always return all records