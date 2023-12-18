---
external: false
draft: false
title: "Simplifying Option Selection with Selenium's WebDriver"
description: "Confused using select in selenium"
date: 2023-12-18
---
### Introduction:

I am on a series, addressing the most frequently asked questions related to automation, today's focus is on a fundamental task: 
- selecting options using Selenium's WebDriver with Python. 
- Specifically, we'll delve into the intricacies of Chrome version 115 and above, unraveling the process step by step for seamless automation.

### Setting the Stage:

Before diving into the code, it's crucial to ensure that your Chrome browser is ready for automation. For Chrome 115 and above, two essential components are required: the path to the Chrome executable and the Chrome binary driver.

1. **Chrome Executable Path:**
   - Mac users can locate the Chrome executable at "/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome."
   - Windows users can find it typically at "C:\Program Files (x86)\Google\Chrome\Application\chrome.exe." A quick Google search can guide you to the exact location.

2. **Chrome Binary Driver:**
   - Download the Chrome binary driver from [this link](https://googlechromelabs.github.io/chrome-for-testing/#stable).

With these prerequisites in place, let's move to the Integrated Development Environment (IDE) for the next steps.

HTML Structure and IDE Setup:

In our scenario, we've created a simple HTML structure containing a select element with options. The key element is identified as 'fruits.'

Next, ensure you are running a basic live server, initiating a local server on port 5500 (you can substitute your link). The following code snippet showcases the initial setup:

```python
# Finding the dropdown element
dropdown = driver.find_element(By.ID, 'fruits')
```

Selecting Options:

Once the dropdown element is located, you can proceed to select options using various methods:

1. **By Index:**
   ```python
   dropdown.select_by_index(index)
   ```

2. **By Visible Text:**
   ```python
   dropdown.select_by_visible_text("Text")
   ```

3. **By Value:**
   ```python
   dropdown.select_by_value("value")
   ```

Deselecting Options:

Similarly, you can deselect options by employing the same methods used for selection.


1. **By Index:**
   ```python
   dropdown.deselect_by_index(index)
   ```

2. **By Visible Text:**
   ```python
   dropdown.deselect_by_visible_text("Text")
   ```

3. **By Value:**
   ```python
   dropdown.deselect_by_value("value")
   ```

Multi-Select Options:

If the dropdown supports multiple selections, you can utilize the following:

- **Select All:**
  ```python
  dropdown.select_all()
  ```

#### Code :

Sample html code used : 
```html 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <label for="fruits">Choose a fruit:</label>
<select name="fruits" id="fruits">
  <option value="apple">Apple</option>
  <option value="banana">Banana</option>
  <option value="mango">Mango</option>
  <option value="orange">Orange</option>
</select>

</body>
</html>
```


I ran this with live server 


Now coming to automation code 
```python 
import time
from selenium import webdriver
from selenium.webdriver.support.select import Select
from selenium.webdriver.common.by import By
PATH = "/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome"

options = webdriver.ChromeOptions()
options.binary_location = "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"
chrome_driver_binary = "chromedriver"
driver = webdriver.Chrome(chrome_driver_binary, chrome_options=options)

driver.get('http://127.0.0.1:5500/index.html')

time.sleep(2)
dropdown = driver.find_element(By.ID, 'fruits')
select = Select(dropdown)

select.select_by_visible_text('Mango')
# select.deselect_by_visible_text("your text")
# select.deselect_by_value("your text")
# select.select_by_index("your text")
# select.deselect_all("your text")

time.sleep(2)
driver.quit()
```


Certainly! Let's break down the provided Python code line by line:

```python
# Importing the necessary modules
import time
from selenium import webdriver
from selenium.webdriver.support.select import Select
from selenium.webdriver.common.by import By

# Setting the path to the Chrome executable (for Mac in this case)
PATH = "/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome"

# Creating ChromeOptions and specifying the binary location
options = webdriver.ChromeOptions()
options.binary_location = "/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"

# Specifying the ChromeDriver binary
chrome_driver_binary = "chromedriver"

# Creating a Chrome WebDriver instance with the specified options
driver = webdriver.Chrome(chrome_driver_binary, chrome_options=options)

# Navigating to a local server (http://127.0.0.1:5500/index.html)
driver.get('http://127.0.0.1:5500/index.html')

# Introducing a delay of 2 seconds (to allow time for the page to load)
time.sleep(2)

# Locating the dropdown element on the page by its ID ('fruits')
dropdown = driver.find_element(By.ID, 'fruits')

# Creating a Select object from the dropdown element
select = Select(dropdown)

# Selecting an option by its visible text (in this case, 'Mango')
select.select_by_visible_text('Mango')

# Introducing another delay of 2 seconds (to observe the selected option)
time.sleep(2)

# Quitting the WebDriver, closing the browser window
driver.quit()
```

Explanation:

1. **Importing Modules:**
   - The code begins by importing the necessary modules (`time`, `webdriver` from Selenium, `Select` from `selenium.webdriver.support.select`, and `By` from `selenium.webdriver.common.by`).

2. **Setting Chrome Path and Options:**
   - The path to the Chrome executable is set in `PATH`.
   - `webdriver.ChromeOptions()` is used to create an instance of ChromeOptions, and the binary location is specified.

3. **Creating Chrome WebDriver:**
   - The Chrome WebDriver instance is created using `webdriver.Chrome()` with the specified ChromeDriver binary and options.

4. **Navigating to the Web Page:**
   - The WebDriver navigates to the local server running at 'http://127.0.0.1:5500/index.html'.

5. **Locating Dropdown Element:**
   - The dropdown element is located using `driver.find_element()` with `By.ID` and the ID ('fruits') of the dropdown.

6. **Creating Select Object:**
   - A `Select` object is created using the located dropdown element.

7. **Selecting an Option:**
   - An option in the dropdown is selected using `select.select_by_visible_text('Mango')`.

8. **Quitting the WebDriver:**
    - `driver.quit()` is used to quit the WebDriver, closing the browser window.

This script essentially automates the process of opening a web page, selecting a specific option from a dropdown, and then closing the browser.



### Wrapping Up:

Automation becomes a breeze with Selenium's WebDriver in Python, especially when dealing with option selection in Chrome 115 and above. Whether you're choosing by index, visible text, or value, or even deselecting options, the process is streamlined and efficient.

In conclusion, mastering these fundamental Selenium WebDriver functions empowers you to handle dropdowns seamlessly, bringing us to the end of this installment in our series on automation. Bada boom bam, and there you have it—automation made easy!

`github` : 'https://github.com/Bosco98/Automation-Most-asked/tree/main/Series%201'