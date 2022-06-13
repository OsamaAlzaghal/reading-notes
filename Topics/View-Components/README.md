# View Components
## What is a View?
A view contains the HTML markup and content that is sent to the browser. A view is the equivalent of a page when working with an ASP.NET MVC application. In general, if you want to return a view for a controller action, then you need to create a subfolder in the Views folder with the same name as your controller.
## What is a view component?
A view component consists of two parts, the class (typically derived from ViewComponent ) and the result it returns (typically a view). Like controllers, a view component can be a POCO, but most developers will want to take advantage of the methods and properties available by deriving from ViewComponent .

---

## What is the difference between partial view and view component?
View components are similar to partial views, but they're much more powerful. View components don't use model binding, they depend on the data passed when calling the view component. View components work with Razor Pages.

---

## View properties
### A view component:

+ Renders a chunk rather than a whole response.
+ Includes the same separation-of-concerns and testability benefits found between a controller and view.
+ Can have parameters and business logic.
+ Is typically invoked from a layout page.

**Note:** View components are intended anywhere reusable rendering logic that's too complex for a partial view, such as:

+ Dynamic navigation menus.
+ Tag cloud, where it queries the database.
+ Sign in panel.
+ Shopping cart.
+ Recently published articles.
+ Sidebar content on a blog.
+ A sign in panel that would be rendered on every page and show either the links to sign out or sign in, depending on the sign in state of the user.

---

### Tutorials for View Components in ASP.NET Core MVC
+ [Tutorial by Marius Schulz](https://docs.microsoft.com/en-us/aspnet/core/mvc/views/view-components?view=aspnetcore-6.0&viewFallbackFrom=aspnetcore-2.1)
+ [Microsoft Docs Tutorial](https://mariusschulz.com/blog/view-components-in-asp-net-core-mvc)

---

### Resources
+ https://docs.microsoft.com/en-us/aspnet/core/mvc/views/view-components?view=aspnetcore-6.0
+ https://docs.microsoft.com/en-us/aspnet/mvc/overview/older-versions-1/overview/understanding-models-views-and-controllers-cs
