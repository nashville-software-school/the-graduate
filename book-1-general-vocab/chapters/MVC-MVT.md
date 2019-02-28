# Model-View-Template/Model-View-Controller

Both Python and C# use an architectural pattern with similar signal flows to get/post data from your database, prepare/manipulate that data, and then render that data on the browser.  

![MVC_MVT](../images/mvc_mvt.png)

* **Model**: Describes your data - the single source of truth for your data
  * Blueprint of how your data is structured 
* **View** (Python) / **Controller** (C#): Controls what users see 
  * Most of your business logic is going to happen here 
  * This is similar to your API Manager or whatever it was called in frontend to do CRUD and other ways to manipulate/access your data from your database
* **Template** (Python) / **View** (C#): How the user sees it 
  * It’s fancy HTML!
  * You can do simple logic in a template - if statements, loops

Typical flow: 
1. User requests something from the browser (GET request, POST request, etc.)
1. View(Python)/controller(C#) queries the database and gets the requested data
1. View(Python)/controller(C#) returns that data to the template(Python)/view(C#)