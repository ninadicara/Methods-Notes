
Transmits data between two pieces of software. 
A way to provide or consume data via web apps. 

A web app makes a request via the api to a server, which retrieves the data from a database, and passes it back. 


## API Security

Check the [OWASP API Security Top 10 2023](https://owasp.org/API-Security/editions/2023/en/0x11-t10/). 

### 1. Broken Object Level Authorisation (BOLA)

- Very common exploit. 
- There should object level authorisation checks for performing all requests to check that users have permission to access or modify that object. 
- Can lead to unauthorised information disclosure, or unauthorised data amendment or deletion. 
#### How to avoid
- User hierarchies should be clear (admins different to users for example).
- Authorisation mechanism should be used to check a user has access for an action.
- Use random and unpredictable values for record IDs. 
- Tests to evaluate vulnerability. 

### 2. Broken Authentication

- Vulnerabilities within the API authentication process.
- May allow people to gain control of user accounts. 

- Permits weak password/vulnerable to password attacks
- Unencrypted or weakly hashed credentials
- Credentials are in the URL
- No or inadequate JSON Web Token validation (e.g. expiration date invalid)
#### How to avoid
- Use multifactor authentication
- Use weak password checks
- Auto lock-out mechanisms to avoid brute force password attacks

### 3. Broken Object Property Level Authorisation (BOPLA)

- Users gain access to a _property_ of an object that they should not be able to read. 
- API responds with more information than is needed (excessive data exposure). 
- Even more problematic if the user is able to change the object - mass assignment.
- Can lead to account take over. 

#### How to avoid
- Only disclose minimum amount of data
- Ensure users have access to the specific property being requested

### 4. Unrestricted resource consumption

- No limit on client use of the API
- Creates a risk of DOS/DDOS attacks
- Affects the quality of the API for those making legitimate requests. 

#### How to avoid
- Using containers or serverless code makes it easy to limit memory or server processes.
- Enforce maximum data size on incoming payloads
- Rate limiting - HTTP 429 response

### 5. Broken Function Level Authorisation (BFLA)

- Regular users are able to access admin endpoints or perform sensitive actions by changing the HTTP method (e.g. from GET to DELETE). 
- Users can perform actions by guessing end point parameters. 

#### How to avoid
- Deny all access by default - only those with specific roles can perform specific tasks. 

### 6. Unrestricted access to sensitive business flows

- Threat actor being able to identify and disrupt business flows. For example:
	- Scalping, produce purchasing - can buy all items at once and resell them. This happened with Taylor Swift tickets! 
	- Another example is being able to create comments and posts, e.g. bots spamming social media. 
	- Reserving all time-slots available. 

#### How to avoid
- CAPTCHA 
- Non-human behaviour pattern analysis
- Block anonymous IP addresses (if you reguarly use a VPN you probably see Captcha's more often for this reason). 

### 7. Server-Side Request Forgery (SSRF)

- API fetches remote resources without validating then they can gain access to sensitive data. 
- They can use the target server to process any requests. 

#### How to avoid
- Isolate the resource fetching mechanism from your network
- Use allow lists
- Disable HTTP redirection
- Validate and sanitise all use supplied input data

### 8. Security Misconfiguration

- Applies to the supporting systems of the API, rather than the API itself. 
- For example, missing security patches, outdated systems, improperly configured permissions.
- Unnecessary features are enabled.
- Error messages expose sensitive information. 

#### How to avoid
- Continually review and update security

### 9. Improper Inventory Management

- Outdated or unpatched API versions
- Using test or beta versions
- Outdated documentation or documentation missing spots
- Make sure we know what data we have - inventory management

#### How to avoid
- Keep an up to date inventory of API endpoints and data etc.
- Ensure documentation is updated and maintained all the time. 
- Ensure proper documentation is available to all authorised users.
- Don't use production data in non-production versions (which often have weaker security).
- Any beta versions should have the same security controls as a production version.

### 10.  Unsafe Consumption of APIs

- Focuses on vulnerability of the API consumer - e.g. if you are a developer who uses public APIs. 
- Developers tend to trust APIs more than user input. 

#### How to avoid
- Adopt a zero trust policy for ANY third-party data. Don't assume it's safe just because it came from a trusted source.  
- Validate or sanitise API data. 
- Assess the security posture of third-party APIs
- Use encrypted communication channels e.g. TLS
- Don't blindly follow re-directs - you can keep a list of allowed URLs. 

