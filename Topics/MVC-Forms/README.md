# Views in ASP.NET Core MVC
---
## What is a view?
A view is an HTML template with embedded Razor markup. Razor markup is code that interacts with HTML markup to produce a webpage that's sent to the client.

In ASP.NET Core MVC, views are .cshtml files that use the C# programming language in Razor markup. Usually, view files are grouped into folders named for each of the app's controllers. The folders are stored in a Views folder at the root of the app.

---
## What are the benefits of using views?
+ The app is easier to maintain because it's better organized. Views are generally grouped by app feature. This makes it easier to find related views when working on a feature.
+ The parts of the app are loosely coupled. You can build and update the app's views separately from the business logic and data access components.
+ You can modify the views of the app without necessarily having to update other parts of the app.
+ It's easier to test the user interface parts of the app because the views are separate units.
+ Due to better organization, it's less likely that you'll accidentally repeat sections of the user interface.

---
## How to create views?
Views that are specific to a controller are created in the Views/[ControllerName] folder. Views that are shared among controllers are placed in the Views/Shared folder. To create a view, add a new file and give it the same name as its associated controller action with the .cshtml file extension. 

---
## Example:
We have a view called "List.cshtml" inside "Home" folder. The view shows the item's name on the web page, and if the user clicks on it, it will redirect the user to the Home controller with the Index action.

```
@using Class26Demo.Models
@model List<Person>
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

    <ul>
        @foreach(var item in Model)
    {
        <li>
            <a asp-controller="Home" asp-action="Index" asp-route-name=@item.Name asp-route-job=@item.Job>@item.Name</a> 
        </li>  
    }
</ul>
```

**Note:** for more info about the views, click [here](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/overview?view=aspnetcore-5.0).

Resources: [Microsoft Docs](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/overview?view=aspnetcore-5.0).

---

### Ways to create forms in ASP.NET MVC:

1. FORMS - WEAKLY TYPED.
2. FORMS - STRONGLY TYPED.
3. FORMS - STRONGLY TYPED AJAX (ASYNCHRONOUS).
4. PURE HTML FORMS WITH AJAX AND JQUERY.

Click [here](https://www.completecsharptutorial.com/asp-net-mvc5/4-ways-to-create-form-in-asp-net-mvc.php) to view the whole tutorial.