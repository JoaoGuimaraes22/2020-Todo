## NextJS

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
- If you want, you can have your api routes in the next.js app, by adding a /api folder into the /pages folder, making it /pages/api;
