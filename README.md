# 2020-Todo / Progress Notes

This is my todo file for what I'll do in 2020. I'm an 18 years old portuguese guy with passions for tech, volleyball and entrepreneurship.

Here it is:

## Todo:

## Main:

### Fully master React.js:
- ~~Learn about props and state~~;
- ~~Learning about components and class-based lifecycles methods~~;
- ~~Mastering class based lifecycle methods (ended up not doing, I'm basically only using arrow function components, with hooks)~~;
- ~~Learn React development best practises~~;
- ~~useState and useState (and custom hooks)~~;
- ~~useRef and useCallback~~;
- ~~useReducer~~
- Context, createContext, useContext;
- Memoization and useMemo;
- React optimization;
- Check rest of React to see what's left to master;
      
- Experiment more with Redux and React:
  - ~~Learn abbout why use Redux~~;
  - ~~Become able to developm quickly and efficiently with redux and react~~;
  - ~~Learn about Redux use best practises~~;
  - ~~Learn about "global" state (still learning)~~; 
  - Fully master Redux;
  
- Master Node.js and Express.js:
  - ~~Learn what they are and when to use them~~;
  - Learn syntax, check documentation;
  - Learn about routing;
  - Learn middleware;
  - Learn about db integration;
 
- Learn Next.js:
  - ~~Learn and test the different Next.js concepts using documentation / tutorials~~;
  - ~~For being able to do server-side rendering~~;
  - Learn about deployment;

- Learn Firebase:
  - ~~Learn about fb integration with web apps~~;
  - ~~Learn about fb databases~~;
  - ~~Learn about fb cloud~~;
  - Learn about rapid deployment with firebase;
  
- Build and deploy full stack web app React and Firebase (optional); 
  
- Learn MongoDB:
  - (I know nothing of mongoDB, only that it's used a lot with node, express, react);

- Learn about simple full-stack deployment, maybe with Heroku;

- Build and deploty a full stack web app with React, Express, and MongoDB;

- Master SQL (MySQL):
  - Fully understand RDBMS;
  - Thoroughly understand SQL;
  - Fully master data CRUD with MySQL;
  - Learn about db deployment and db integration with client;
  
- Make full stack production application with MERN;

- Learn basic-medium concepts about data structures and algorithms:
  - Using Udemy free course/freecodecamp youtube video;
  
- Master C#, .NET, ASP.NET and become better at server-client interaction;
  - Learn OOP principles;
  - Learn the syntax;
  - Learn the principal libraries and how the .NET environment works;
  - Learn about integrating backend ASP.NET services with a client (React) application;
  - Learn about hangfire;

- Learn Nginx;
  
- Learn Docker;

- Learn Kubernetes;

- Build and deploy a full scalable web app with kubernetes, ASP.NET and/or Node.js, MySQL / MongoDB / (Firebase) database and a React front-end; 

- Build a really nice workstation;

**Side wishes:**

- Learn more about AI and ML;
- ~~Integrate tensorflow into an augmented application using Unity3D~~;
- React testing / other React hooks;
- Research "safer" investing strategies (dividend yield, dividend growth, others)
- Start generating side-money, aside from current job;
- Plant and harvest tomatoes and spinach (have been into planting and stuff for some reason);
- Eat more and bulk up;
- Get a whiteboard;
- Get a medium quality filming camera/webcam + microphone;
- Learn and use video editing software - Davinci Resolve;
- Get a raspberry pi and do the equivalent of an "Hello World" with it;

## Stuff I'm pretty good at:

- HTML5;
- CSS3;
- Modern Javascipt; 
- Sass;
- Adobe XD;
- Natural language processing (Microsoft's LUIS and Google's Dialogflow);
- Bash;
- NPM;
- Webpack;
- Git, Github;

## NOTES 

- **What I use when developing currently:**
  - Windows 10 Laptop (looking to change ti Linux OS -> probably Kubuntu);
  - Visual Studio for .NET applications;
  - PyCharm for pyhton developing;
  - Visual Studio Code for basically any other language that I currently use;
  - For Visual Studio Code Extensions, I use:
    - Auto Rename Tag;
    - ES7 React/Redux/React-Native/JS snippets;
    - Live Sass Compiler;
    - Live Server;
    - Material Icon Theme;
    - Material Theme - Darker High Contrast;
    - Prettier;
    - SQL Server (mssql);
    - Sublime Importer;

- **Redux ( (with React) -> assuming you already know React):**
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
  
- **Express**:
  - Run `npm init -y`;
  - Run `npm i express`;
  - Optional: if using express with a client application, run `npm i -D nodemon concurrently`;
  - Optional: if using express with react, make a seperate /server folder for the express node.js backend, with a main file named  server.js or index.js , and another /client folder for the create-react-app, both in the same root directory if you want;
  - Optional: create the following npm scripts for faster development, on the root package.json, like so: `{server: "cd server && nodemon server.js", client: "cd client && npm start", dev: "concurrently \"npm run server\" "\npm run client\" "}`;
  - Now, on server.js, import `express` and assign it to a constant like `const express = require("express");`;
  - Use `const app = express();`;
  - Make a middleware section, like `// Middleware`, on server.js;
  - On `// Middleware`, use the body parser middleware to parse requests comming through express to json, like so `app.use(express.json());`;
  - Make an express section, like `// Express`, on server.js.
  - Use `const port = process.env.PORT || 5000`, on server.js, setting the port that will be used for the express API;
  - **Now you can run an express server, using npm run server!**;
  - Create a /routes folder;
  - Create a /api folder inside the /routes folder, making it /routes/api;
  - 
  
- **Next.js:**
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
- **That's the basic Next.js setup!**
- If you want the data fetched on the client-side and not server rendered, run `npm i swr`, then import `useSWR` from `swr` in the page you want to fetch the data, and finnaly fetch data like so:
- Make an asyncronous generic fetch function, like you would do with react;
- Use `useSWR` inside the page-generating function, like so, `const { data, error } = useSWR('/repos/zeit/next.js', fetcher)`;
- **Now you can fetch data on-page-render, on the client side!** 
- If you want, you can have your api routes in the next.js app, by adding a /api folder into the  /pages folder, making it /pages/api;
