#### Express (mainly with MongoDB):

- Run `npm init -y`;
- Run `npm i express`;
- Optional: if using express with a client application, run `npm i -D nodemon concurrently`;
- Optional: if using express with react, make a seperate /server folder for the express node.js backend, with a main file named server.js or index.js , and another /client folder for the create-react-app, both in the same root directory if you want;
- Optional: create the following npm scripts for faster development, on the root package.json, like so: `{server: "cd server && nodemon server.js", client: "cd client && npm start", dev: "concurrently \"npm run server\" "\npm run client\" "}`;
- Optional: in the package.json file of your client app, add `"proxy": "http://localhost:5000"` to it, to better use your api backend server;
- Now, on server.js, import `express` and assign it to a constant like `const express = require("express");`;
- Use `const app = express();`;
- For this, we want to handle our responses and requests as JSON, but we could use express with other things other than JSON;
- Make a middleware section, like `// Middleware`, on server.js;
- On `// Middleware`, use the body parser middleware to parse requests comming through express to json, like so `app.use(express.json());`;
- Make an express section, like `// Express`, on server.js.
- Use `const port = process.env.PORT || 5000`, on server.js, setting the port that will be used for the express API;
- Then, make your app listen on that port, with `app.listen(port, ()=>{console.log("App listening on port ${port}")})`;
- **Now you can run an express server, using npm run server!**;
- Create a /routes folder;
- Create a /api folder inside the /routes folder, making it /routes/api;
- In this /api folder, you will put all your HTTP method calls (GET, POST, DELETE, PUT);
- For each api in the api folder, use `const express = require("express")`, importing express;
- Use routing to make this file, /api/:api_name, a route for the express server;
- To use routing, use `const router = express.Router()`;
- For each HTTP request, be it GET, POST, PUT or DELETE, make a commented description about what route (@route) is that method going towards, the description (@desc) of the service, and the access (@access) level of the api (public or private), for example, when documenting a GET request, do this `// @route GET api/items; // @desc Gets All Items; // @access Public`;
- The routing for each api will be /websitename(when developing will be localhost:5000/api/:api_name;
- **GET** To set a route for GET methods (to fecth items from source), use something like:

```
router.get('/', auth (// optional) , (req, res) => {
  Item.find()
    .sort({ date: -1 })
    .then(items => res.json(items));
});
```

- **POST** To set a route for POST methods (to create items on your source), use something like:

```
router.post('/', auth (// optional), (req, res) => {
  const newItem = new Item({
    name: req.body.name
    (// here we are setting the new item's name through our request's body)
  });

  newItem.save().then(item => res.json(item));
});
```

- **DELETE** To set a route for DELETE methods (to delete items from your source), use something like:

```
router.delete('/:id(// here we are finding our item by id)', auth (// optional), (req, res) => {
  Item.findById(req.params.id)
    .then(item => item.remove().then(() => res.json({ success: true })))
    .catch(err => res.status(404).json({ success: false }));
});
```

- **PUT** To set a route for PUT methods (to alter items from your source), do some research, because I haven't really been using it; :P;
- To use these routes in your express applicaton, use `module.exports = router` on your /api/:api_name file;
- Finnaly, import them in your server.js, like so, for example: `app.use('/api/items', require('./routes/api/items'));`;
- **Now you can use all your routes APIs in your application**;
