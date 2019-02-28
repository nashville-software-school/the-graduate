# Server side validation

Once the data passes the client side validation, it moves on to interact (`POST`/`DELETE`, etc) with the database. You’ll get a server side validation error if you try to do something to the database that isn’t allowed (based off of the models you create in your Django app). So, if on the model, you said that the max length of a name is 50 characters, and someone enters a name at 55 characters, it will pass the client side, but it will fail on the server side.

![ServerSideValidation](../images/server-side-validation.jpg)
