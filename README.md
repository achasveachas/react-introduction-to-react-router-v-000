# Introduction to React Router
## Objectives

1. How client-side routing works
2. What the trade-off are for client-side routing
3. What `pushState` is



### Client-Side Routing

So we've have learned about building components, changing state, moving state to a store using redux, actions, reducers, etc..., but you are probably wondering how you can make a page with different components. I mean not every app is a todo list, tic-tac-toe or a spreadsheet, so how do we build an app that allows us to have unique pages for the user to see? This is where `Client-Side` routing comes in.  

Client-Side routing is a different beast then what we used with Rails, because we aren't actually making HTTP GET requests anymore.

Lets say that our Client-Side app is going to have these routes

https://www.movie-maker-2016/movies/new

https://www.movie-maker-2016/movies

https://www.movie-maker-2016/about

https://www.movie-maker-2016/login

well the `server` is only going to render the same `HTML`. Which will look like this.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Movie Maker 2016</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
  </head>
  <body>
    <div id="container"></div>
    <script src="./bundle.js" charset="utf-8"></script>
  </body>
</html>
```

It is now the responsibility of the Client-Side app to handle the finding, fetching and displaying of the data in the browser instead of the server.

We do get some great benefits though. The major one is *Speed*. Since we are only making one request to the server we don't have to wait for a round trip server call. We have everything stored on the Client-Side already so we just notify our Client-Side code to display this info for us as we need it.

### Single Page App (SPA)

In React we will most likely be building a `SPA`. This means there will never be a new page being loaded just the original GET request to the server to load the initial HTML, CSS and JS files. So we need to figure out how to make the experience of Client-Side routing work for us.

There are a couple of things that we need to take into consideration:

* We want to make sure that we have a URL that displays what the user is doing at that moment. So if they are viewing a bio page it might look like this https://worlds-best-app/bio instead of this https://worlds-best-app.

* We want a user to be able to use the browser's back and forward buttons with ease.

* We want a user to be able to input a URL into the address bar and navigate to the view they need to see.

This was easy with server side rendering most MVC frameworks come with this for free, because we just defined the routes, added the actions needed to the controller and then made a call to the model to get the info we desired.


### Limits of Client-Side routing

So this all sounds great, but what are the limitations? 

### Push it, Push it

## Resources

* [React Router Tutorial](https://github.com/reactjs/react-router-tutorial/tree/master/lessons/01-setting-up)