---
toc: True
comments: True
title: News Fetcher
layout: base
description: Fetch World News from API (github .env secrets)
tags: [javascript]
courses: { compsci: {week: 3} }
type: hacks
---

<html lang="en">
   <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>News for the Day</title>
      <style>
      body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #9A4CE6;
            color: white;
            text-align: center;
            padding: 10px;
        }
        #news-container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
        }
        .article {
            margin-bottom: 20px;
            border: 1px solid #ddd;
            padding: 10px;
        }
        .article h2 {
            font-size: 20px;
            margin-bottom: 5px;
        }
        .article p {
            font-size: 14px;
            margin-top: 5px;
        }
        #country-input {
            width: 100%;
            padding: 10px;
            margin-bottom: 10px;
        }
        #fetch-button {
            width: 100%;
            padding: 10px;
            margin-top: 20px;
            background-color: #9A4CE6;
            color: white;
            cursor: pointer;
        }
        #fetch-button:hover {
            background-color: #5F3574;
        }
    </style>
   </head>
   <body>
      <header>
         <h1>News for the Day</h1>
         <label for="country-select">Select Country:</label>
         <select id="country-select">
            <option value="us">United States</option>
            <option value="gb">United Kingdom</option>
            <option value="it">Italy</option>
            <option value="ae">United Arab Emirates</option>
            <option value="ar">Argentina</option>
            <option value="at">Austria</option>
            <option value="au">Australia</option>
            <option value="be">Belgium</option>
            <option value="bg">Bulgaria</option>
            <option value="br">Brazil</option>
            <option value="ca">Canada</option>
            <option value="ch">Switzerland</option>
            <option value="cn">China</option>
            <option value="co">Colombia</option>
            <option value="cr">Costa Rica</option>
            <option value="cz">Czech Republic</option>
            <option value="de">Germany</option>
            <option value="eg">Egypt</option>
            <option value="fr">France</option>
            <option value="gr">Greece</option>
            <option value="hk">Hong Kong</option>
            <option value="hu">Hungary</option>
            <option value="id">Indonesia</option>
            <option value="ie">Ireland</option>
            <option value="il">Israel</option>
            <option value="in">India</option>
            <option value="jp">Japan</option>
            <option value="kr">South Korea</option>
            <option value="lt">Lithuania</option>
            <option value="lv">Latvia</option>
            <option value="ma">Morocco</option>
            <option value="mx">Mexico</option>
            <option value="my">Malaysia</option>
            <option value="ng">Nigeria</option>
            <option value="nl">Netherlands</option>
            <option value="no">Norway</option>
            <option value="nz">New Zealand</option>
            <option value="ph">Philippines</option>
            <option value="pl">Poland</option>
            <option value="pt">Portugal</option>
            <option value="ro">Romania</option>
            <option value="rs">Serbia</option>
            <option value="ru">Russia</option>
            <option value="sa">Saudi Arabia</option>
            <option value="se">Sweden</option>
            <option value="sg">Singapore</option>
            <option value="si">Slovenia</option>
            <option value="sk">Slovakia</option>
            <option value="th">Thailand</option>
            <option value="tr">Turkey</option>
            <option value="tw">Taiwan</option>
            <option value="ua">Ukraine</option>
            <option value="ve">Venezuela</option>
            <option value="za">South Africa</option>
        </select>
        <input type="text" id="api-key" class="api-key" placeholder="Enter API Key">
        <button id="fetch-button">Fetch News</button>
      </header>
      <div id="news-container">
         <!-- News articles will be displayed here -->
      </div>
      <script>
    //   const apiKey = '814764f1663046a09341b1264b9bca5d';
        document.getElementById('fetch-button').addEventListener('click', () => {
            const selectElement = document.getElementById('country-select');
            const apiKey = document.getElementById('api-key').value
            console.log(apiKey)
            const selectedCountry = selectElement.value.toLowerCase();
            if (selectedCountry) {
                getNews(selectedCountry, apiKey);
            } else {
                alert('Please select a country');
            }
        });
        async function getNews(country, apiKey) {
            const apiUrl = `https://newsapi.org/v2/top-headlines?country=${country}&apiKey=${apiKey}`;
            try {
                const response = await fetch(apiUrl);
                const data = await response.json();
                if (data.status === 'ok') {
                    displayNews(data.articles);
                } else {
                    console.error('Error fetching news:', data.message);
                }
            } catch (error) {
                console.error('Error:', error);
            }
        }
        function displayNews(articles) {
            const newsContainer = document.getElementById('news-container');
            newsContainer.innerHTML = '';
            articles.forEach((article) => {
                const articleDiv = document.createElement('div');
                articleDiv.classList.add('article');
                const title = document.createElement('h2');
                title.textContent = article.title;
                const description = document.createElement('p');
                description.textContent = article.description;
                articleDiv.appendChild(title);
                articleDiv.appendChild(description);
                newsContainer.appendChild(articleDiv);
            });
        }
        window.onload = () => {
            const defaultCountry = document.getElementById('country-select').value.toLowerCase();
            // getNews(defaultCountry);
        };
        </script>
   </body>
</html>
