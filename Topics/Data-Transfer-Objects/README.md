# Data Transfer Objects
---
A Data Transfer Object (commonly known as a DTO) is usually an instance of a POCO (plain old CLR object) class used as a container to encapsulate data and pass it from one layer of the application to another. You would typically find DTOs being used in the service layer to return data back to the presentation layer. 

**Note:** DTO is only used to pass data and does not contain any business logic. They only have simple setters and getters.

![img](https://www.baeldung.com/wp-content/uploads/2021/08/layers-4.svg)

---
### When to use DTOs?
+ Use DTOs for abstraction.
+ Hide particular properties that clients are not supposed to view.
+ Remove circular references (see previous section).
+ Omit some properties in order to reduce payload size.
+ Flatten object graphs that contain nested objects, to make them more convenient for clients.
+ Avoid "over-posting" vulnerabilities. 
+ Decouple your service layer from your database layer.
---
## Example:
A DTO is an object that defines how the data will be sent over the network.

![img](https://tarikmahmood.com/wp-content/uploads/2021/02/DTO-mapping.png)

Code from [MicrosoftDocs](https://docs.microsoft.com/en-us/).
```
namespace BookService.Models
{
    public class BookDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public string AuthorName { get; set; }
    }
}

namespace BookService.Models
{
    public class BookDetailDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public int Year { get; set; }
        public decimal Price { get; set; }
        public string AuthorName { get; set; }
        public string Genre { get; set; }
    }
}
```

**Note:** we're converting to DTOs manually in code. Another option is to use a library like [AutoMapper](http://automapper.org/) that handles the conversion automatically.

Resources: [MicrosoftDocs](https://docs.microsoft.com/en-us/).