# Testing and Swagger and Deployment
---
## Testing Controller
Controller tests attempt to test the controller in isolation, so we test whether a controller action returns a particular view, returns a particular set of data, or returns a different type of action result.

Here we have our controller, The ProductController contains two action methods named Index() and Details(). Both action methods return a view. Notice that the Details() action accepts a parameter named Id. We will test if a controller returns a different type of action result.


**Code:**

```
using System;
using System.Web.Mvc;
namespace Store.Controllers
{
     public class ProductController : Controller
     {
          public ActionResult Index()
          {
               // Add action logic here
               throw new NotImplementedException();
          }
          public ActionResult Details(int Id)
          {
               if (Id < 1)
                    return RedirectToAction("Index");
               var product = new Product(Id, "Laptop");
               return View("Details", product);

          }
     }
}
```

This will test the Action Result returned by a Controller,  If you pass an invalid product Id -- an Id with a value less than 1 -- then you are redirected to the Index() action. You can test the behavior of the Details() action with the unit test in Listing 6. The unit test verifies that you are redirected to the Index view when an Id with the value -1 is passed to the Details() method.

**Code:**
```
using System.Web.Mvc;
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Store.Controllers;
namespace StoreTests.Controllers
{
     [TestClass]
     public class ProductControllerTest
     {
          [TestMethod]
          public void TestDetailsRedirect()
          {
               var controller = new ProductController();
               var result = (RedirectToRouteResult) controller.Details(-1);
               Assert.AreEqual("Index", result.Values["action"]);

          }
     }
}
```


Explanation: 
when you call the RedirectToAction() method in a controller action, the controller action returns a RedirectToRouteResult. The test checks whether the RedirectToRouteResult will redirect the user to a controller action named Index.

---

## Swagger / OpenAPI
### What is Swagger?
It is a language-agnostic specification for describing REST APIs. Swagger allows you to describe the structure of your APIs so that machines can read them. 

### OpenApi vs. Swagger
+ OpenAPI is a specification.
+ Swagger is tooling that uses the OpenAPI specification. For example, OpenAPIGenerator and SwaggerUI.

#### It's main goals are to:

+ Minimize the amount of work needed to connect decoupled services.
+ Reduce the amount of time needed to accurately document a service.

#### Here's an example of an OpenAPI specification that describes the capabilities of your API:

```
{
  "openapi": "3.0.1",
  "info": {
    "title": "API V1",
    "version": "v1"
  },
  "paths": {
    "/api/Todo": {
      "get": {
        "tags": [
          "Todo"
        ],
        "operationId": "ApiTodoGet",
        "responses": {
          "200": {
            "description": "Success",
            "content": {
              "text/plain": {
                "schema": {
                  "type": "array",
                  "items": {
                    "$ref": "#/components/schemas/ToDoItem"
                  }
                }
              },
              "application/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "$ref": "#/components/schemas/ToDoItem"
                  }
                }
              },
              "text/json": {
                "schema": {
                  "type": "array",
                  "items": {
                    "$ref": "#/components/schemas/ToDoItem"
                  }
                }
              }
            }
          }
        }
      },
      "post": {
        …
      }
    },
    "/api/Todo/{id}": {
      "get": {
        …
      },
      "put": {
        …
      },
      "delete": {
        …
      }
    }
  },
  "components": {
    "schemas": {
      "ToDoItem": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int32"
          },
          "name": {
            "type": "string",
            "nullable": true
          },
          "isCompleted": {
            "type": "boolean"
          }
        },
        "additionalProperties": false
      }
    }
  }
}
```

---

Click on this link to view [Swagger UI](https://docs.microsoft.com/en-us/aspnet/core/tutorials/web-api-help-pages-using-swagger?tabs=visual-studio&view=aspnetcore-2.1) to generate interactive API documentation that lets your users try out the API calls directly in the browser.

When unit testing controller logic, only the contents of a single action are tested, not the behavior of its dependencies or of the framework itself. Click on [this](https://docs.microsoft.com/en-us/aspnet/core/mvc/controllers/testing?view=aspnetcore-2.1) link to view an example of testing the controller's logic.







