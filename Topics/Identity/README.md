# Introduction to Identity on ASP.NET Core
---
## What is ASP.NET Core Identity?
Is an API that supports user interface (UI) login functionality, manages users, passwords, profile data, roles, claims, tokens, email confirmation, and more. Users can create an account with the login information stored in Identity or they can use an external login provider such as Facebook, Google, Microsoft Account, and Twitter. ASP.NET Core Identity adds user interface (UI) login functionality to ASP.NET Core web apps.

![img](https://digitalmccullough.com/blog/aspnetcore-auth-system-demystified/aspnetcore-auth-system-demystified_auth-flow.svg)

---
## How do we configure it?
Identity is typically configured using a SQL Server database to store user names, passwords, and profile data. Alternatively, another persistent store can be used, for example, Azure Table Storage.

---
## How to secure web APIs and SPAs?
To secure web APIs and SPAs, use one of the following:
+ [Azure Active Directory](https://docs.microsoft.com/en-us/azure/api-management/api-management-howto-protect-backend-with-aad).
+ [Azure Active Directory B2C](https://docs.microsoft.com/en-us/azure/active-directory-b2c/secure-rest-api?tabs=windows&pivots=b2c-user-flow) (Azure AD B2C).
+ [IdentityServer4](https://duendesoftware.com/).

---
## Identity Components
All the Identity-dependent NuGet packages are included in the ASP.NET Core shared framework.

The primary package for Identity is [Microsoft.AspNetCore.Identity](https://www.nuget.org/packages/Microsoft.AspNetCore.Identity/). This package contains the core set of interfaces for ASP.NET Core Identity, and is included by Microsoft.AspNetCore.Identity.EntityFrameworkCore.

---
## Create a Web app with authentication
Follow these steps provided by Microsoft docs to create a web app with authentication by click on [this](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity?view=aspnetcore-5.0&tabs=visual-studio) link.
