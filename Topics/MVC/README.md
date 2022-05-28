# Azure Dev Ops
## What is Azure DevOps?
"Azure DevOps provides developer services for allowing teams to plan work, collaborate on code development, and build and deploy applications. Azure DevOps supports a collaborative culture and set of processes that bring together developers, project managers, and contributors to develop software. It allows organizations to create and improve products at a faster pace than they can with traditional software development approaches."

Azure DevOps provides integrated features that you can access through your web browser or IDE client. You can use one or more of the following standalone services based on your business needs:

+ Azure Repos provides Git repositories or Team Foundation Version Control (TFVC) for source control of your code. For more information about Azure Repos, see What is Azure Repos?.
+ Azure Pipelines provides build and release services to support continuous integration and delivery of your applications. For more information about Azure Pipelines, see What is Azure Pipelines?.
+ Azure Boards delivers a suite of Agile tools to support planning and tracking work, code defects, and issues using Kanban and Scrum methods. For more information about + Azure Boards, see What is Azure Boards?.
+ Azure Test Plans provides several tools to test your apps, including manual/exploratory testing and continuous testing. For more information about Azure Test Plans, see Overview of Azure Test Plans
+ Azure Artifacts allows teams to share packages such as Maven, npm, NuGet, and more from public and private sources and integrate package sharing into your pipelines. For more information about Azure Artifacts, see Overview of [Azure Artifacts](https://docs.microsoft.com/en-us/azure/devops/pipelines/artifacts/artifacts-overview?view=azure-devops&tabs=nuget).

---
# MVC Basics
## What is MVC?
MVC is a design pattern or architecture which helps in developing the web application in a most efficient way when compared with the traditional ASP.NET Web Application.

### Model layer:
Represents the objects in our Application. Model is also a class which has all the objects and its properties and methods defined in it.

### View Layer:
It has all the html controls which define the UI of the application. Here in MVC, we don’t have drag and drop option for controls as we don’t use server controls. Instead we use Razor Engine available with Visual Studio by default which helps in rendering the View. Views are files with .cshtml extensions. .cshtml contain both html and server code. And also, using ‘@’, we can access C# code so that in our page which can access server side dynamic data.

### Controller Layer:
Controller basically handles the request from user. It is the heart of the MVC application as everyone say. It is responsible to handle the request and return a response to user by loading appropriate View with data from Model.

Controller is nothing but a class with a group of methods called actions. And Every action method returns view. A View can be anything like it can be xml or html or JSON etc.

Controller maps the incoming user requests to appropriate Controller actions with the help of process called Routing.

---
# Tag Helpers
## What are Tag Helpers?
"Tag Helpers enable server-side code to participate in creating and rendering HTML elements in Razor files. For example, the built-in ImageTagHelper can append a version number to the image name. Whenever the image changes, the server generates a new unique version for the image, so clients are guaranteed to get the current image (instead of a stale cached image). There are many built-in Tag Helpers for common tasks - such as creating forms, links, loading assets and more - and even more available in public GitHub repositories and as NuGet packages. Tag Helpers are authored in C#, and they target HTML elements based on element name, attribute name, or parent tag. For example, the built-in LabelTagHelper can target the HTML <label> element when the LabelTagHelper attributes are applied. If you're familiar with HTML Helpers, Tag Helpers reduce the explicit transitions between HTML and C# in Razor views. In many cases, HTML Helpers provide an alternative approach to a specific Tag Helper, but it's important to recognize that Tag Helpers don't replace HTML Helpers and there's not a Tag Helper for each HTML Helper. Tag Helpers compared to HTML Helpers explains the differences in more detail."

## What Tag Helpers provide?
+ An HTML-friendly development experience: for the most part, Razor markup using Tag Helpers looks like standard HTML. Front-end designers conversant with HTML/CSS/JavaScript can edit Razor without learning C# Razor syntax.

+ A rich IntelliSense environment for creating HTML and Razor markup: this is in sharp contrast to HTML Helpers, the previous approach to server-side creation of markup in Razor views. Tag Helpers compared to HTML Helpers explains the differences in more detail. IntelliSense support for Tag Helpers explains the IntelliSense environment. Even developers experienced with Razor C# syntax are more productive using Tag Helpers than writing C# Razor markup.

+ A way to make you more productive and able to produce more robust, reliable, and maintainable code using information only available on the server, for example, historically the mantra on updating images was to change the name of the image when you change the image. Images should be aggressively cached for performance reasons, and unless you change the name of an image, you risk clients getting a stale copy. Historically, after an image was edited, the name had to be changed and each reference to the image in the web app needed to be updated. Not only is this very labor intensive, it's also error prone (you could miss a reference, accidentally enter the wrong string, etc.) The built-in ImageTagHelper can do this for you automatically. The ImageTagHelper can append a version number to the image name, so whenever the image changes, the server automatically generates a new unique version for the image. Clients are guaranteed to get the current image. This robustness and labor savings comes essentially free by using the ImageTagHelper.

---

# Bootstrap
## What is Bootstrap?
"Bootstrap is a free and open source front end development framework for the creation of websites and web apps. The Bootstrap framework is built on HTML, CSS, and JavaScript (JS) to facilitate the development of responsive, mobile-first sites and apps." Bootstrap is the most popular CSS Framework for developing responsive and mobile-first websites.

## How to install Bootstrap?
Using package manager:
```
npm install bootstrap@5.2.0-beta1
```
```
gem install bootstrap -v 5.2.0-beta1
```


## 1 Hour tutorial Bootstrap:
Click on [this](https://scrimba.com/learn/bootstrap4) link to view the full tutorial for Bootstrap.

---
Resources: [Microsoft technical documentation](https://docs.microsoft.com/en-us/).








