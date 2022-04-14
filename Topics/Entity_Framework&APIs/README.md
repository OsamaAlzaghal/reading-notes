# Entity Framework Core
It is an object-relational mapper (O/RM), which enables .NET developers to work with a database using .NET objects and eliminates the need for most of the data-access code that typically needs to be written.  

![img](https://www.entityframeworktutorial.net/Images/efcore/ef-core-dev-approaces.png)

---
## What is an ORM?

![img](https://cdn.educba.com/academy/wp-content/uploads/2020/01/what-is-orm.jpg.webp)

An object-relational mapper provides an object-oriented layer between relational databases and object-oriented programming languages without having to write SQL queries. It standardizes interfaces reducing boilerplate and speeding development time.

ORMs generate objects which map to tables in the database virtually. Once these objects are up, then coders can easily work to retrieve, manipulate or delete any field from the table without paying much attention to language specifically. It supports writing complex long SQL queries in a simpler way.
[Source](https://www.educba.com/what-is-orm/)

---
## The model 
The model is the way that allows us to acess the data. A model is made up of entity classes and a context object that represents a session with the database. The context object allows querying and saving data.

### EF supports the following model development approaches:

+ Generate a model from an existing database.
+ Hand code a model to match the database.
+ Once a model is created, use EF Migrations to create a database from the model. Migrations allow evolving the database as the model changes. [Microsoft docs](https://docs.microsoft.com/en-us/)
---

## Querying 
We can retrieve our entity classes from the database by performing LINQ. Below is an example on how to do a query from Microsoft docs:
```
using (var db = new BloggingContext())
{
    var blogs = db.Blogs
        .Where(b => b.Rating > 3)
        .OrderBy(b => b.Url)
        .ToList();
}
```
---

## Saving data 
We can save data by creating instances of our entity classes. See the code sample from Microsoft docs:
```
using (var db = new BloggingContext())
{
    var blog = new Blog { Url = "http://sample.com" };
    db.Blogs.Add(blog);
    db.SaveChanges();
}
```
---

## Data Seeding 
Data seeding is providing the database with an initial set of data. 

There are several ways this can be accomplished in EF Core:

+ Model seed data: it is used for static data that's not expected to change outside of migrations and does not depend on anything else in the database, for example ZIP codes.

+ Manual migration customization: using this way, you have to provide you call, such as InsertData(), UpdateData(), and DeleteData(). But on the other ways, we can use HasData which is transformed to one of these calls.

+ Custom initialization logic: can be done by using DbContext.SaveChanges() before the main application logic begins execution.

You can check [Microsoft docs](https://docs.microsoft.com/en-us/ef/core/modeling/data-seeding) to view examples for each way with a description for each code line.

---
## APIs

API stands for Application Programming Interface, which is a software intermediary that allows two applications to talk to each other. So by using the APIs, we can have different devices and platforms talking to each other regarding the way they usually do. In .NET, you can create your own API or use any API you want to exchange data between different devices. You can check [Microsoft docs](https://docs.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-6.0&tabs=visual-studio) on how to create a web API with ASP.NET Core and display the data you want to that web page.


What is User secrets? User secrets is a secure way of storing private user information such as API keys, client secrets, and connection strings. Essentially anything that you don’t want others to know about when using your code base. So there is a way to that by following the steps provided in this link.
[Code Fellows](https://codefellows.github.io/code-401-dotnet-guide/resources/user-secrets.html).

