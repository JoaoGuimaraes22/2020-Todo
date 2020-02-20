#### Data Scraping w/ NodeJS, Express and Puppeteer

- Optional: use with Express, set up a basic express template project (see Express Notes);
- Run, `npm i puppeteer` to install puppeteer (will install Chromium);
- Import puppeteer into your .js file, with `const puppeteer = require("puppeteer")`;
- Create `const scrapeProduct = async (url) => {}`, an asynchronous function to get the data, with `url` as it's argument;
- Now, inside the functiom, use `const browser = await puppeteer.launch()` to start puppeteer with Chromium;
- Use `const page = await browser.newPage()` to start a new page in the browser;
- Then use `await page.goto(url)` to go to your desired url;
- **You are now on your page, and can start fetching data**;
- To get a single component of page you know, you can use it's XPath;
- Copy the item's XPath using your browser's DevTools (I'm using Chrome, works great);
- Do this by running, `const [item] = await page.$x('put-x-path-here')`;
- To get a propert of the item you fetched, for example it's `src`, run `const src = await item.getProperty("src")`;
- Finnaly, format the info to JSON, with `const itemSrc = await src.jsonValue()`;
- If this doesn't work, copy the full XPath and ty again;
- In the end of all of the srcaping and manipulation, run `browser.close()` to close the browser;
- **With this you can scrape any item**;
- To fetch all of the data with the same tag / class, do the following;
- Get the data using `const data = page.$$eval('JS path', (items) => {items.map( (item) => {item.textContent} )})`;
- For example:

```
  const movieTitles = await page.$$eval(
    ".Slide > .PosterContent > a > h3",
    (a) => a.map((title) => title.textContent)
  );
```

- An example of a full fledged app with express would be:

```
const puppeteer = require("puppeteer");
const express = require("express");
const router = express.Router();

const scrapeProduct = async (url) => {
  const browser = await puppeteer.launch();
  const page = await browser.newPage();
  await page.goto(url);

  const movieTitles = await page.$$eval(
    ".Slide > .PosterContent > a > h3",
    (a) => a.map((title) => title.textContent)
  );

  const movieImgs = await page.$$eval(".Slide > a > img", (img) =>
    img.map((image) => image.src)
  );

  const releasedDates = await page.$$eval(
    ".Slide > .PosterContent > .Headline--eyebrow > p > .MoviePosters__released-month",
    (dat) => dat.map((date) => date.textContent)
  );

  await browser.close();

  return { movieTitles, movieImgs, releasedDates };
};

router.get("/", async (req, res, next) => {
  const scrapedData = await scrapeProduct("https://www.amctheatres.com/movies");
  res.send(scrapedData);
});

module.exports = router;


```
