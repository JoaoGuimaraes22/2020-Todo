# 2020-Todo / Progress Notes

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

- For Redux (with React -> assuming you already know React):
  - Npm install `redux` and `react-redux`;
  - Create reducers folder, with an index.js where you import all the reducers you create (reducers handle your global state altering in your application);
  - Create reducers, for example, by using a function and giving it conditional statements to alter `state`, ex: `function counterReducer(state = x, action){if(action.type == "INCREMENT"){return state++}}`;
  - Then, use `combineReducers` imported from `redux`, in the reducers' folder index.js, and assign a constant to it (ex: `allReducers`, and assign it `combineReducers()`;
  - Still in the reducers' index.js, pass your reducers as key-value pairs in the `combineReducers()` method, for example, `const allReducers = combineReducers({counter: counterReducer, xReducer: reducer2, yReducer: reducer3})`;
  - In root index.js, import `createStore` from `redux` and `allReducers` from /reducers/index or just from /reducers;
  - In root index.js, assign a constant to `createStore(allReducers)`, for example `const myStore = createStore(allReducers)`; 
  - To use Redux DevTools extension, in root index.js, add to code like so `createStore(allReducers, window.__REDUX_DEVTOOLS_EXTENSION__ && window.__REDUX_DEVTOOLS_EXTENSION__())`;
  - In root index.js, import `Provider` from `react-redux`, and wrap your `<App/>` component in the `Provider`, like so, `<Provider> <App/> <Provider/>`;
  - In root index.js, add `store` parameter to the `Provider` wrapper, and assign it `myStore`, for example, `<Provider store={myStore}> <App/> <Provider/>`;
  - Now we have access to global state in our app!
  - To access global state in a component, `useSelector` from `react-redux`;
  - Then assign a constant, example `counter`, to `useSelector()`;
  - Then add state altering function in useSelector, in which you pass your state as a paremeter and return the specific type of state you which to alter, for example, `counter = useSelector(state => state.counter)` or `const x = useSelector(state = state.x)`;
  - To alter global state, create an actions folder;
  - In the actions folder, create an index.js, in which you can create all your actions;
  - Your actions are functions that return the `type` of the action you activated, for example, an action for handling increments in a component could be: `export const increment = () => { return {type: "INCREMENT"}}`;
  - Now in your component, import your action from actions, like `import {increment} from "../actions"`;
  - Then import `useDispatch` from `react-redux`, and assign a constant to the `dispatch()` method, for example `const dispatch = dispatch()`;
  - To alter the global state in your componet, just use `dispatch()` with an imported function action as a parameter and it will alter global state, for example: `<button onClick={()=>{dispatch(increment())}}>` --> in each click, increments counter by one;
  - That's pretty much it to use redux in a simple way in a create-react-app application!;
  
