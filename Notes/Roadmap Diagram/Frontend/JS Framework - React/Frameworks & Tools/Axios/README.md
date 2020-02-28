## Axios

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
