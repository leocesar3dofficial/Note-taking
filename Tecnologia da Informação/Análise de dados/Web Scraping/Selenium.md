# Selenium

## Install
```bash
pip install selenium
```
Download Chromium and choose the proper version [here](https://chromedriver.chromium.org/downloads). Put it inside the scraping project.

## Documentation
[https://www.selenium.dev/documentation](https://www.selenium.dev/documentation)

## Hardcoded location of Chromium
```python
from selenium.webdriver.chrome.service import Service
from selenium import webdriver

service = Service(executable_path="/path/to/chromedriver")
driver = webdriver.Chrome(service=service)
```

## Run it Headless
```python
options = webdriver.ChromeOptions()
options.add_argument("--headless")
driver = webdriver.Chrome(options=options)
# Automation / scraping code...
```

## Maximize current browser window
```python
driver.manage().window().maximize();  # or options.add_argument("start-maximized");
```

## Set browser window size
```python
from selenium.webdriver.common.by import By

dimension = (300, 1080)
driver.manage().window().setSize(dimension)
```

## Do not download images
```python
options.add_argument('--blink-settings=imagesEnabled=false')
```

## Steps

### 1. Start the session
```python
driver = webdriver.Chrome()
```

### 2. Take action on the browser
```python
driver.get("<url-to-automate-scrape>")
```

### 3. Request browser information
```python
title = driver.title
```

### 4. Establish Waiting Strategy

#### Global wait
```python
driver.implicitly_wait(0.5)  # The default setting is 0, meaning disabled
```

#### Conditional wait
```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By

WebDriverWait(driver, 30).until(
    EC.text_to_be_present_in_element(
        (By.CLASS_NAME, 'progress-label'),  # element filtration
        'Complete'  # the expected text
    )
)
```

### 5. Find an element(s)

#### By name
```python
text_box = driver.find_element(by=By.NAME, value="my-text")
```

#### By CSS selector
```python
submit_button = driver.find_element(by=By.CSS_SELECTOR, value="button")
```

#### By CSS class name
```python
fruit = fruits.find_element(By.CLASS_NAME, "tomatoes")
```

#### All matching elements
```python
plants = driver.find_elements(By.TAG_NAME, "li")
elements = driver.find_elements(By.TAG_NAME, 'p')
```

#### Find Elements From Element
```python
element = driver.find_element(By.TAG_NAME, 'div')
elements = element.find_elements(By.TAG_NAME, 'p')
```

#### Get Active Element
```python
attr = driver.switch_to.active_element.get_attribute("title")
```

### 6. Take action on the element

#### Edit element input text
```python
from selenium.webdriver.common.keys import Keys

text_box.send_keys("<inputted-text>")
driver.find_element(By.NAME, "q").send_keys("webdriver" + Keys.ENTER)
```

#### Button click
```python
submit_button.click()
```

#### Clear input element
```python
text_box.clear()
```

#### Selectable elements
##### Setup
```python
select_element = driver.find_element(By.NAME, 'select-dropdown')
select = Select(select_element)
```
##### List options
```python
option_list = select.options
```
##### Selected options
```python
selected_option_list = select.all_selected_options
```
##### Select option
```python
select.select_by_visible_text('Four')
select.select_by_value('two')
select.select_by_index(3)
```
##### De-select option
```python
select.deselect_by_value('eggs')
```

### 7. Request element information

#### Text Content
```python
text = driver.find_element(By.CSS_SELECTOR, "h1").text
```

#### Is Displayed (to avoid a honeypot: invisible elements in the DOM that lead to a trap to identify the scraper)
```python
is_email_visible = driver.find_element(By.NAME, "email_input").is_displayed()
```

#### Is Enabled
```python
value = driver.find_element(By.NAME, 'btnK').is_enabled()
```

#### Is Selected
Used on Checkboxes, radio buttons, input, and option elements.
```python
value = driver.find_element(By.CSS_SELECTOR, "input[type='checkbox']:first-of-type").is_selected()
```

#### Tag Name
```python
attr = driver.find_element(By.CSS_SELECTOR, "h1").tag_name
```

#### Size and Position
```python
res = driver.find_element(By.CSS_SELECTOR, "h1").rect
```

#### Get CSS Value
```python
cssValue = driver.findElement(By.LINK_TEXT, "More information...").value_of_css_property('color')
```

#### Fetching Attributes or Properties
```python
value_info = email_txt.get_attribute("value")
```

### 8. End the session
```python
driver.quit()
```

## Simple Example
```python
import os
from selenium.webdriver.chrome.service import Service
from selenium import webdriver
from selenium.webdriver.common.by import By

def test_eight_components():
    service = Service(executable_path=os.environ['PATH'] += r"/path/to/chromedriver")
    # set path from CLI: set PATH%PATH%;<chromium folder path>
    driver = webdriver.Chrome(service=service)
    driver.implicitly_wait(10)  # wait just the necessary time until the max value
    driver.get("https://www.selenium.dev/selenium/web/web-form.html")
    title = driver.title
    assert title == "Web form"
    text_box = driver.find_element(by=By.NAME, value="my-text")
    submit_button = driver.find_element(by=By.CSS_SELECTOR, value="button")
    text_box.send_keys("Selenium")
    submit_button.click()
    message = driver.find_element(by=By.ID, value="message")
    value = message.text
    assert value == "Received!"
    driver.quit()

test_eight_components()
```