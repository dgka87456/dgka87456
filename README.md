- 👋 Hi, I’m @dgka87456
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
dgka87456/dgka87456 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
const axios = require('axios');
const { parse } = require('node-html-parser');

async function getData(selector, url) {
  const response = await axios.get(url);
  const root = parse(response.data);
  const elements = root.querySelectorAll(selector);
  elements.forEach((element) => {
    console.log('text', element.text);
    console.log('src', element.getAttribute('src'));
    console.log('href', element.getAttribute('href'));
  });
}

getData('div.sc-b7fb630d-2 img', 'https://www.gemini.com/activetrader');

