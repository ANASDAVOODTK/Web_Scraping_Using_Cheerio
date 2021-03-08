# BUILD A WEB SCRAPER WITH NODE
  You will need Node 8+ installed on your machine.
  Web scraping refers to the process of gathering information from a website through automated scripts. This eases the process of gathering large amounts of data from websites       where no official API has been defined.

  The process of web scraping can be broken down into two main steps:

  Fetching the HTML source code of the website through an HTTP request or by using a headless browser.
  Parsing the raw data to extract just the information you're interested in.
  We'll examine both steps during the course of this tutorial. At the end of it all, you should be able to build a web scraper for any website with ease.
 # Prerequisites
  
  To complete this tutorial, you need to have Node.js (version 8.x or later) and npm installed on your computer. This page contains instructions on how on how to install or         upgrade your Node installation to the latest version.
  
 # Getting started
  Create a new scraper directory for this tutorial and initialize it with a package.json file by running npm init -y from the project root.

  Next, install the dependencies that we'll be needing too build up the web scraper:
  
        npm install axios cheerio puppeteer --save
  
  Here's what each one does:

  Axios: Promise-based HTTP client for Node.js and the browser
  Cheerio: jQuery implementation for Node.js. Cheerio makes it easy to select, edit, and view DOM elements.
  Puppeteer: A Node.js library for controlling Google Chrome or Chromium.
  You may need to wait a bit for the installation to complete as the puppeteer package needs to download Chromium as well.
# Scrap a static website with Axios and Cheerio

To demonstrate how you can scrape a website using Node.js, we're going to set up a script to scrape the Premier League website for some player stats. Specifically, we'll scrape the website for the top 20 goalscorers in Premier League history and organize the data as JSON.

Create a new pl-scraper.js file in the root of your project directory and populate it with the following code:

    
    const axios = require('axios');

    const url = 'https://www.premierleague.com/stats/top/players/goals?se=-1&cl=-1&iso=-1&po=-1?se=-1';

    axios(url)
      .then(response => {
        const html = response.data;
        console.log(html);
      })
      .catch(console.error);
If you run the code with node pl-scraper.js, a long string of HTML will be printed to the console. But how can you parse the HTML for the exact data you need? That's where Cheerio comes in.

Cheerio allows us to use jQuery methods to parse an HTML string and extract whatever information we want from it. But before you write any code, let’s examine the exact data that we need through the browser dev tools.

## Thankyou

 
  
