# Web Scraping

## What are the key differences between scraping static and dynamic websites?

When we scrape static data from a static website we will get results expected when the HTML file is rendered in the browser, because nothing on the page changes dynamically once it renders. 

When we scrape a dynamic website, we want to be able to capture the same result that the browser renders. Sometimes the browser may dynamically change some inner text based on a conditional render.

The key differences betwen scraping a static and dynamic website would be the process of scraping.

For a dynamic website we want to be able to instantiate a webdriver that will load a webpage in our scraping process to be able to capture dynamically changed values on a webpage. 

For a static website, we would just open the html file, find an id we want to extract from and then get that text or value. 

## Explain at least three techniques or best practices that can be employed to avoid getting blocked while scraping websites.

1. Observe website policies and robots.txt: 
Many websites have a robots.txt file that specifies which pages can be crawled and which ones cannot. Make sure to observe the policies outlined in this file and avoid crawling pages that are prohibited. You should also check the website's terms of service and abide by them. Ignoring these policies could lead to being blocked.

2. Limit requests and use delays:
 Sending too many requests to a website within a short period can trigger alarms and lead to being blocked. To avoid this, limit the number of requests you send per second or minute. Additionally, introduce delays between requests to simulate human behavior. You can use tools like sleep() or setTimeOut() to pause your scraping script for a specified amount of time.

3. Use proxies: 
Proxies allow you to change your IP address, which can help you avoid getting blocked. When using proxies, you can rotate through a pool of IP addresses to prevent the website from detecting that a single IP address is making too many requests. However, not all proxies are created equal, and some may not work for web scraping purposes. It's important to choose a reliable and trustworthy proxy provider.

## What is Playwright, and how does it assist in web scraping tasks? Provide an example of a use case where Playwright would be particularly beneficial.

Playwright is an open-source Node.js library developed by Microsoft that provides a high-level API for automating web browsers, including Chrome, Firefox, and Safari. It can be used for a variety of tasks, including testing, monitoring, and web scraping.

Playwright makes web scraping easier and more efficient by automating the process of interacting with web pages. It can simulate user interactions like clicking buttons, filling out forms, and scrolling through pages, making it easier to scrape data that would otherwise be difficult to access. 

A generic use case for playwright would if you want to scrape data from a website that loads content dynamically using AJAX. Traditional web scraping tools may struggle to capture this data, as the content is not present in the initial HTML response. Playwright can help in this scenario by simulating user interactions to trigger the AJAX calls and capture the resulting data

Example Code:
```python
from playwright.sync_api import Playwright, async_playwright

with async_playwright() as p:
    # Launch the Chromium browser and navigate to the website
    browser = await p.chromium.launch()
    page = await browser.new_page()
    await page.goto('https://example.com')

    # Scroll down the page to load more content
    await page.evaluate('''() => {
        window.scrollBy(0, window.innerHeight);
    }''')

    # Wait for the new content to load
    await page.wait_for_selector('.new-content')

    # Extract the data from the page
    data = await page.evaluate('''() => {
        results = []
        items = document.querySelectorAll('.new-content')
        items.forEach((item) => {
            results.append(item.innerText)
        })
        return results
    }''')

    print(data)

    # Close the browser
    await browser.close()
```

## Describe the purpose of using Xpath in web scraping, and provide an example of an Xpath expression to select a specific HTML element from a webpage.

XPath is a language used to navigate through the elements and attributes of an XML document or HTML webpage. It is commonly used in web scraping to extract data from websites by selecting specific HTML elements that contain the desired information. 

By using XPath expressions with Playwright, we can easily navigate through a webpage and extract data from specific HTML elements.

The XPath expression to select all the links on the page is simply `'//a'`, which is passed as an argument to the `page.locator()` method. The `.all()` method is used to return a list of all the links on the page. We can modify the XPath expression to select specific elements based on their attributes. 

```python
h1_tags = page.locator('//h1').all()
```

## Things I want to know more about

- How would one implement robots.txt in their own webpage?



>References
>
>[Scrape a Dynamic Website with Python](https://scrapingant.com/blog/scrape-dynamic-website-with-python)
>
>[Web Scraping](https://en.wikipedia.org/wiki/Web_scraping)
>
>[How to Scrape Websites Without Getting Blocked](https://www.scrapehero.com/how-to-prevent-getting-blacklisted-while-scraping/)
>
>[Login and Scrape Data with Playwright and Python](https://www.youtube.com/watch?v=H2-5ecFwHHQ&t=60s)
>
>[Python Playwright Tutorial For Beginners](https://www.youtube.com/watch?v=yp1o9biMMWU)
>
>[xpath cheatsheet](https://devhints.io/xpath)
>
>[Playwright XPath Selectors](https://www.programsbuzz.com/article/playwright-xpath-selectors)