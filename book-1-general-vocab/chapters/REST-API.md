# REST API 
[Resource](https://mlsdev.com/blog/81-a-beginner-s-tutorial-for-understanding-restful-api)

[Another Resource](https://en.wikipedia.org/wiki/Representational_state_transfer) (in particular, the architectural properties)

[Seriously, another resource](https://simpleisbetterthancomplex.com/tutorial/2018/02/03/how-to-use-restful-apis-with-django.html) ;) - Python specific, but great for anyone to read 

In short, a REST API an intuitive way for clients to access the data on a server. REST is not a standard or protocol, this is an approach to or architectural style for writing API.

There are 6 different guiding restraints for an API to be considered truly ReSTful. [More reading](https://restfulapi.net/).

RESTful APIs depend on the HTTP CRUD methods.

![rest](../images/rest_http.png)

All resources in REST are entities. They can be independent like:
* GET /users - get all users;
* GET /users/123 - get a particular user with id = 123;
* GET /posts - get all posts.
There are also dependent entities, that rely on their parent models:
* GET /users/123/projects - get all the projects that a user with id = 123 has.