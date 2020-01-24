# 2020-Todo

This is my todo file for what I'll do in 2020. I'm an 18 years old portuguese guy with passions for tech, volleyball and entrepreneurship.

Here it is:

## Todo:

**Main:**

- Fully master React.js:
  - ~~Learn about props and state~~;
  - ~~Learning about components and class-based lifecycles methods~~;
  - ~~Mastering class based lifecycle methods (ended up not doing, I'm basically only using arrow function components, with hooks)~~;
  - ~~Learn React development best practises~~;
  - ~~useState and useState (and custom hooks)~~;
  - ~~useRef and useCallback~~;
  - ~~useReducer and useContext~~;
  - Check rest of React to see what's left to master;
      
- Experiment more with Redux:
  - ~~Learn abbout why use Redux~~;
  - Master Redux syntax and be able to development quick and efficiently;
  - Learn about Redux use best practises;
  - ~~Learn about "global" state (still learning)~~; 
  
- Master Express.js:
  - Learn what is express and when to use express;
  - Learn syntax, check documentation;
  - Learn about routing;
  - Learn middleware;
  - Learn about db integration;
 
- Master Node.js:

- Learn Next.js:
  - For being able to do server-side rendering,

- Learn Firebase:
  - Learn about fb integration with web apps;
  - Learn about fb databases;
  - Learn about fb cloud;
  - Learn about rapid deployment with firebase;
  
- Learn Nginx;
  
- Build and deploy full stack web app with Node, Express, React and Firebase; 
  
- Learn MongoDB:
  - (I know nothing of mongoDB, only that it's used a lot with node, express, react);

- Master SQL (MySQL):
  - Fully understand RDBMS;
  - Thoroughly understand SQL;
  - Fully master data CRUD with MySQL;
  - Learn about db deployment and db integration with client;
  
- Make full stack production appplication with MERN;

- Learn basic-medium concepts about data structures and algorithms:
  - Using udemy free course/freecodecamp youtube video;
  
- Master C#, .NET, ASP.NET and become better at server-client interaction;
  - Learn OOP principles;
  - Learn the syntax;
  - Learn the principal libraries and how the .NET environment works;
  - Learn about integrating backend ASP.NET services with a client (React) application;
  - Learn about hangfire
  
- Learn Docker and Kubernetes;

- Build and deploy a full scalabale web app using Digital Ocean with kubernetes, ASP.NET and or Node.js, MySQL / MongoDB / (Firebase) database and a React front-end; 

**Side wishes:**

- Learn more about AI and ML;
- ~~Integrate tensorflow into an augmented application using Unity3D~~;
- React testing / other React hooks;
- Research "safer" investing strategies (dividen yield, dividend growth, others)
- Start generating side-money, aside from current job;
- Plant and harvest tomatoes and spinach (have been into planting and stuff for some reason);
- Eat more and bulk up;
- Get a whiteboard;
- Get a medium quality filming camera/webcam + microphone;
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

- For Redux (with React):
  - Wrap App in root `index.js` with `Provider` from `react-redux`;
  - Create reducers folder, with an index.js where you import all reducers;
  - Reducers are created by using a function and giving it conditional statements to alter state, ex: `function(state = x, action){if(action.type == "INCREMENT"){return state++}}`
  - Use `combineReducers` from `redux` in the reducers' folder index.js and assign a constant to it, and give `combineReducers` an object with your reducers;
  - In root index.js, import `createStore` from `redux` and the constant assigned to `combineReducers` from /reducers;
  - In root index.js, assign a constant to `createStore(constant from combineReducers)`; 
  - To use Redux DevTools extension, in createStore from root index.js, do `createStore(constant from combineReducer, window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__())`;
  - In the `<Provider> <App/> </Provider>` in root index.js, add `store = {constant assigned to createStore}` as a paremetr to the Provider, like `<Provider store = {constant assigned to createStore}> <App/> </Provider>`
