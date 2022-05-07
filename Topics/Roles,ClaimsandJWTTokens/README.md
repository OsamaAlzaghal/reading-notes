# Roles, Claims and JWT Tokens

## Authentication in ASP.NET Core
Authentication is the process of determining who you are, while Authorisation revolves around what you are allowed to do, i.e. permissions. Obviously before you can determine what a user is allowed to do, you need to know who they are, so when authorisation is required, you must also first authenticate the user in some way.

### Claims-based authentication
Claims in code specify claims which the current user must possess, and optionally the value the claim must hold to access the requested resource. Claims requirements are policy based, the developer must build and register a policy expressing the claims requirements.

Identities in ASP.NET Core are a ClaimsIdentity. A simplified version of the class might look like this (the actual class is a lot bigger!):

```
public class ClaimsIdentity: IIdentity
{
    public string AuthenticationType { get; }
    public bool IsAuthenticated { get; }
    public IEnumerable<Claim> Claims { get; }

    public Claim FindFirst(string type) { /*...*/ }
    public Claim HasClaim(string type, string value) { /*...*/ }
}

```
+ Claims which consists of all the claims associated with an identity. 
+ The AuthenticationType property is fairly self-explanatory. In our practical example previously, this might be the string Passport or DriversLicense, 
+ IsAuthenticated indicates whether an identity is authenticated or not.

Note: in ASP.NET Core if you create a ClaimsIdentity and provide an AuthenticationType in the constructor, IsAuthenticated will always be true. So an authenticated user must always have an AuthenticationType, and, conversely, you cannot have an unauthenticated user which has an AuthenticationType.

---
## JWT Tokens
### What is JWT?
JSON Web Token (JWT) is a means of representing claims to be transferred between two parties. The claims in a JWT are encoded as a JSON object that is digitally signed using JSON Web Signature (JWS) and/or encrypted using JSON Web Encryption (JWE). In simple terms, it is just another way of encoding JSON object and use that encoded object as access tokens for authentication from the server.


![img](https://miro.medium.com/max/1400/1*0SEbHdFcVpaejejGA-1DDw.png)

There are generally three parts in JWTs as shown in the above picture. 
1. 1st part is HEADER:

	```
		{
 			"alg": "HS256",
 			"typ": "JWT"
		}
		
	```
2. 2nd part is PAYLOAD:
	```
		{
 			"email": "John Doe",
 			"xyz": "abc"
		}
	```
3. 3rd part is SIGNATURE:
	```
		key           = 'secretkey';
		unsignedToken = encodeBase64Url(header) + '.' + 			encodeBase64Url(payload);
		signature     = HMAC-SHA256(key, unsignedToken) // 		As mentioned in header section.
	```
	
There are two parties involved, one party who gives a service, and the other party who uses the service.

Producer is the one who gives a service. It will be the provider(Server) of the API(s) which are JWT protected.

Consumer is the one who uses it. It will be the customer(Server/Mobile App/ Web App/ Client) who will be providing the valid JWT token to consume the API(s) being provided by the Producer.

![img](https://miro.medium.com/max/1400/1*44waelPu4JvYALzkvoh8zw.png)	

Resources: [Microsoft Docs](https://docs.microsoft.com/en-us/aspnet/core/security/authorization/claims?view=aspnetcore-6.0&viewFallbackFrom=aspnetcore-2.1) and [Code Burst](https://codeburst.io/jwt-to-authenticate-servers-apis-c6e179aa8c4e).