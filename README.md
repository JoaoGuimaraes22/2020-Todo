# 2020-Todo / Progress Notes

This is my todo file for what I'll do in 2020. I'm an 18 years old portuguese guy with passions for tech, volleyball and entrepreneurship.
In here, I list what I wish to do. Also, when I say "master" I mean know enought that I can do anything I wish to do with it pretty efficiently, not that I completely memorized every detail / use case;

Here it is:
## Todo:

### Main:

#### Fully master React.js:
- ~~Learn about props and state~~;
- ~~Learning about components and class-based lifecycles methods~~;
- ~~Mastering class based lifecycle methods (ended up not doing, I'm basically only using arrow function components, with hooks)~~;
- ~~Learn React development best practises~~;
- ~~useState and useState (and custom hooks)~~;
- ~~useRef and useCallback~~;
- ~~useReducer~~
- Context, createContext, useContext;
- ~~Memoization and useMemo~~;
- React optimization;
- Check rest of React to see what's left to master;
      
#### Experiment more with Redux and React:
- ~~Learn abbout why use Redux~~;
- ~~Become able to developm quickly and efficiently with redux and react~~;
- ~~Learn about Redux use best practises~~;
- ~~Learn about "global" state (still learning)~~; 
- Optimization techniques with Redux;
- Fully master Redux;
  
#### Master Node.js and Express.js:
- ~~Learn what they are and when to use them~~;
- ~~Learn syntax, check documentation~~;
- ~~Learn about routing~~;
- Learn middleware;
- Master all syntax;
- ~~Learn about db integration~~;
- ~~Learn about integrating with MongoDB~~;
- Learn about integrating with MySQL;
- Master database integration with other databases;

#### Learn Next.js:
- ~~Learn and test the different Next.js concepts using documentation / tutorials~~;
- ~~For being able to do server-side rendering~~;
- Learn about deployment;

#### Learn Firebase:
- ~~Learn about fb integration with web apps~~;
- ~~Learn about fb databases~~;
- ~~Learn about fb cloud~~;
- Learn about rapid deployment with firebase;
- ~~Build and deploy full stack web app React and Firebase (optional) -> Canceled~~;
  
#### Learn MongoDB:
- ~~Install MongoDB~~;
- ~~Use MongoDB CLI~~;
- ~~Use MongoDB Atlas~~;
- ~~Connect to MongoDB atlas database from a web app~~;
- Memorize and learn the syntax for using with JavaScript;
- ~~Know what mongoose is and why use it~~;
- Learn why / how to use mongoose;
- ~~Master MongoDB~~;

#### ~~Learn about simple full-stack deployment~~;

#### Master simple full-stack web application deployment

#### Build and deploty a full stack web app with React, Express, and MongoDB;

#### Start being better at DevOps with Github and Azure DevOps;

#### Master SQL (MySQL):
- Fully understand RDBMS;
- Thoroughly understand SQL;
- Fully master data CRUD with MySQL;
- Learn about db deployment and db integration with client;

#### Make full stack production application with MERN (MongoDB or MySQL);

#### Learn basic to medium concepts about data structures and algorithms:
- Using Udemy free course/freecodecamp youtube video;
  
#### Master C#, .NET, ASP.NET and become better at server-client interaction;
- Learn OOP principles;
- Learn the syntax;
- Learn the principal libraries and how the .NET environment works;
- Learn about integrating backend ASP.NET services with a client (React) application;
- Learn about hangfire;

#### Learn Nginx:
- Learn Nginx Ingress Controllers
  
#### Learn Docker:
- ~~Learn about containerization~~;
- ~~Learn Docker containers~~;
- ~~Learn Docker commands~~;
- ~~Learn Docker production deployment~~;
- Learn about Docker with Azure;

#### Learn Kubernetes:
- ~~Learn about Docker and Kubernetes~~;
- ~~Learn about pods, images, nodes, etc.~~;
- Learn YAML really well;
- Learn about deployment;
- Use on DigitalOcean;
- Use on Azure, with Kubernetes Azure Service;

#### Learn Linux:
- ~~Learn about basic installation (probably using a usb drive)~~;
- ~~Boot and install~~;
- ~~Learn basic Linux~~;
- ~~Use Ubuntu~~;
- Learn intermediate Linux / Unix;
- Learn and use Kubuntu;

#### Build and deploy a full scalable web app with kubernetes, ASP.NET and/or Node.js, MySQL / MongoDB / (Firebase) database and a React front-end:
- A good one;

#### Build a really nice workstation:
- https://nickcraver.com/desktop-build/, one day, I will have something like this, **IF I HAVE THE MONEY** and knowledge I guess;
- Using part builder;

### Side wishes -> not the focus:
- ~~Integrate tensorflow into an augmented application using Unity3D~~;
- React testing / other React hooks;
- Research "safer" investing strategies (dividend yield, dividend growth, others)
- Start generating side-money, aside from current job;
- Plant and harvest tomatoes and spinach (have been into planting and stuff for some reason);
- Eat more and bulk up;
- Get a whiteboard;
- Kali Linux and Ethical Hacking (George Hotz is cool);
- Get a medium quality filming camera/webcam - got my eyes on this(https://www.amazon.es/dp/B01L6L52K4?ref=emc_p_m_9_b&th=1) - + microphone (still checking);
- Learn and use video editing software - Davinci Resolve Probably ;
- Get a raspberry pi and do the equivalent of an "Hello World" with it;
- Learn more about AI and ML;

## Stuff I'm pretty good at:
- HTML5;
- CSS3;
- Modern Javascipt; 
- Sass;
- Adobe XD;
- Azure Fundamentals;
- Microsoft Bot Framework;
- Natural language processing (Microsoft's LUIS and Google's Dialogflow);
- Bash;
- React;
- NPM;
- Webpack;
- Git, Github;

## NOTES 

#### What I use when developing currently:
- Kubuntu + Windows 10 dual boot Laptop
- PyCharm for pyhton developing;
- Visual Studio Code for basically any other language that I currently use;
- Sometimes Visual Studio for C# developing (I use VS Code usually even for C#);
- For Visual Studio Code Extensions, I use:
- Auto Rename Tag;
- ES7 React/Redux/React-Native/JS snippets;
- Live Sass Compiler;
- Live Server;
- Material Icon Theme;
- Material Theme - Palenight High Contrast;
- Prettier;
- SQL Server (mssql);

#### Redux ( (with React) -> assuming you already know React):
- Npm install `redux` and `react-redux`;
- Create /reducers folder, with an index.js where you import all the reducers you create (reducers handle your global state altering in your application);
- Create reducers, for example, by using a function and giving it conditional statements to alter `state`, ex: `function counterReducer(state = x, action){if(action.type == "INCREMENT"){return state++}}`;
- Use `combineReducers` imported from `redux`, in the /reducers' folder index.js, and assign a constant to it (ex: `allReducers = combineReducers()`;
- Still in the /reducers' index.js, pass your reducers as key-value pairs in the `combineReducers()` method, for example, `const allReducers = combineReducers({counter: counterReducer, xReducer: reducer2, yReducer: reducer3})`;
- In root index.js, import `createStore` from `redux`, and import `allReducers` from /reducers/index or just from /reducers;
- In root index.js, assign a constant to `createStore(allReducers)`, for example `const myStore = createStore(allReducers)`; 
- To use Redux DevTools extension, in root index.js, add to code like so `createStore(allReducers, window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__())`;
- In root index.js, import `Provider` from `react-redux`, and wrap your `<App/>` component in the `Provider`, like so, `<Provider> <App/> <Provider/>`;
- In root index.js, add `store` parameter to the `Provider` wrapper, and assign it `createStore` constant, for example, `<Provider store={myStore}> <App/> <Provider/>`;
- **Now we have access to global state in our app!**
- To access global state in a component, import `useSelector` from `react-redux` in that component;
- Assign a constant, for example `counter`, to `useSelector()`, like `counter = useSelector()`, in the component;
- Add your state altering function within useSelector, where you pass your state as a paremeter and return the type of state you want to alter, for example, `counter = useSelector(state => state.counter)` or `const x = useSelector(state = state.x)`;
- **That´s how you access your global state!**
- To alter global state, create an /actions folder;
- In the /actions folder, create an index.js, in which you can create all your actions;
- Your actions are functions that return the `type` of the action you activated, for example, an action for handling increments in a component could be: `export const increment = () => { return {type: "INCREMENT"}}`;
- Now in your component, import your action from /actions, like `import {increment} from "../actions"`;
- Then import `useDispatch` from `react-redux`, and assign a constant to the `dispatch()` method, for example `const dispatch = dispatch()`;
- To alter the global state in your componet, just use `dispatch()` with an imported function action as a parameter and it will alter global state, for example: `<button onClick={()=>{dispatch(increment())}}>` --> in each click, increments counter by one;
- **And now you can alter your global state**;
  
#### Express (mainly with MongoDB):
- Run `npm init -y`;
- Run `npm i express`;
- Optional: if using express with a client application, run `npm i -D nodemon concurrently`;
- Optional: if using express with react, make a seperate /server folder for the express node.js backend, with a main file named  server.js or index.js , and another /client folder for the create-react-app, both in the same root directory if you want;
- Optional: create the following npm scripts for faster development, on the root package.json, like so: `{server: "cd server && nodemon server.js", client: "cd client && npm start", dev: "concurrently \"npm run server\" "\npm run client\" "}`;
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
  
#### Axios w/ Express :
- First check the initial Express notes to follow along;
- This if for data handling with Axios;
- First, run `npm i axios` to install axios to your project;
- Import axios, with `const axios = require("axios")`;
- For example, to make GET requests, use `axios.get()`, and for POST, use `axios.post()`;
- A request in axios looks something like (ex: GET):
```
const express = require("express");
const axios = require("axios");
const router = express.Router();
const getData = () => {
  return axios.get("https://jsonplaceholder.typicode.com/posts");
};
// @route GET api/movies
// @desc Fetches all of the movies from external API
// @access Public
router.get("/", async (req, res, next) => {
  try {
    const response = await getData();
    console.log(response);
    const formatData = [];
    await response.data.map((post) => {
      formatData.push(post.title);
    });
    console.log(formatData);
    await res.send(formatData);
  } catch (err) {
    console.log(err);
  }
});
module.exports = router;
```
- The `params` are the query strings for the request;


  
#### Next.js:
- Run `npm init -y`;
- Run `npm i next react react-dom isomorphic-unfetch @zeit/next-css`;
- Add the following scripts to your package.json, `dev: "next", build: "next build", start: "next start"`
- Create a next.config.js file in the root directory and add to it `const withCSS = require("@zeit/next-css"); module.exports = withCSS({});`, to setup styling in the project;
- Then create the following folders:
- /scss (for making .scss files for styling);
- /styles (where the .scss files go when compiled by live sass compiler);
- /pages (where you put your applicattion's pages);
- /layout (where you create your layout components, ones you use in multiple pages);
- /components (for creating components)
- In a page, you can fetch data in the server side using `getInitialProps` and, `fetch` imported from `isomorphic-unfetch`, for example, if you wanted to get data from an api to the Home page, you could do this:  
```
const Home = ({stars}) => {
return (
<Layout>
<div style={{ padding: "4rem", background: "lightblue" }}>
  <h1>Hello World</h1>
  <h2>Next starts: {stars}</h2>
</div>
</Layout>
);
};

Home.getInitialProps = async () => {
const res = await fetch("https://api.github.com/repos/zeit/next.js");
const data = await res.json();
return { stars: data.stargazers_count };
};
```
- **That's the basic Next.js setup!**
- If you want the data fetched on the client-side and not server rendered, run `npm i swr`, then import `useSWR` from `swr` in the page you want to fetch the data, and finnaly fetch data like so:
- Make an asyncronous generic fetch function, like you would do with react;
- Use `useSWR` inside the page-generating function, like so, `const { data, error } = useSWR('/repos/zeit/next.js', fetcher)`;
- **Now you can fetch data on-page-render, on the client side!** 
- If you want, you can have your api routes in the next.js app, by adding a /api folder into the  /pages folder, making it /pages/api;
