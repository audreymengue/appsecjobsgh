# AWA 2 14-06-2022

## DES232 Migrating OWASP 2021 Injection (14-06-2022)
An injection attack refers to a class of techniques in which an atacker manipulates an application through malicious input.

## The course will focus on cross-site injection, SQL injection, OS command injections, code injection

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
    . hyphens and semicolons are treated as comment so everything after that is ignored
    To mitigate SQL injections:
    1. Use parametarised queries
    2. Parameterized stored procedures (Avoid dynamically concatinating user inputs and SQl statements, avoid sensitive system stored procedures)
    3. Sparing use of deny lists
    4. Exception handling
    5. Minimal privileges
    6. Harden OS and Platforms
    7. Disable stacked queries
    8. Avoid SELECT *
    9. Use the LIMIT clause

* OS command injection is a vulnerability that allows an attacker to execute arbitrary commands on a web, database, or backend server. Here is how to mitigate it:
    1. Avoid the shell for commands
    2. Careful input validation
    3. Parameterization
    4. Identify risky functions
    5. Use command abstraction
    6. Run web server with low privilege
    7. File permission
    8. Use full path
    9. Run Web server in virtualized or sandbox environment

* Code Injection is where the attacker targets the programming language and the code the application uses.
    . This vulnerability is most common in interpreted scripting languages like python, PHP, Ruby, JS etc... 
    . Still possible in compiled languages
    . Vulnerability if using functions such as eval
    To mitigate code injection:
    1. Never evaluate code based on user inputs

## DES234 Mitgating OWASP 2021 cryptographic failure (14.06.2022)

### Cryptography
Can be hard to implement but very secure. Many liraries wwere  created to solve that problem.
It's failure can resulte in exposure of sensitive data and then make the compnay loose their reputation.
It was meant to achieave three goals: authenticity(guaranties the origine of the data), integrity(the data has not been modified) and confidentiality(discretion in viewing the data). Let's focus on confidentiality.

* Confidentiality consists of securing the data at rest and in transit.
Data at rest ca be encrypted using the following:
	- Transparent disk encryption
	- Database encryption
	- Application level encryption
	- Storing password hashes
Selecting the strong algorythms (keylength.com for more information)
Storing password (Hash function with password)
Brute force attacks(best practice: strong algo, password policy, multi-factor authentication, use Salt and Pepper)
Best to use a salt when storing passwords a salt is a long number added to the hashed password
Pepper is a salt kept secret

Data in transit(TLS is not SSL, Some of them interchangeably, SSL is insecur, use TLS v1.2 or less)



    

