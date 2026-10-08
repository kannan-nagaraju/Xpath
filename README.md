# Xpath


## Program:
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import Select
import time

# -----------------------------------------
# Start Chrome
# -----------------------------------------

driver = webdriver.Chrome()

# TC01 - Open registration/form page
driver.get("https://www.selenium.dev/selenium/web/web-form.html")

driver.maximize_window()

# -----------------------------------------
# TC02 - Locate Text Input
# Attribute XPath
# -----------------------------------------

text_input = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']"
)

text_input.send_keys("Sivakumar")


# -----------------------------------------
# TC03 - Enter Password
# Attribute XPath
# -----------------------------------------

password = driver.find_element(
    By.XPATH,
    "//input[@name='my-password']"
)

password.send_keys("Siva@123")


# -----------------------------------------
# TC04 - Locate Submit
# text()
# -----------------------------------------

submit = driver.find_element(
    By.XPATH,
    "//button[text()='Submit']"
)

print("Submit button found")


# -----------------------------------------
# TC05 - Locate textbox dynamically
# contains()
# -----------------------------------------

text_box = driver.find_element(
    By.XPATH,
    "//input[contains(@name,'my-text')]"
)

print("Textbox found using contains()")


# -----------------------------------------
# TC06 - Locate element with prefix
# starts-with()
# -----------------------------------------

text_box = driver.find_element(
    By.XPATH,
    "//input[starts-with(@name,'my-')]"
)

print("Element found using starts-with()")


# -----------------------------------------
# TC07 - Two attributes
# and
# -----------------------------------------

password_box = driver.find_element(
    By.XPATH,
    "//input[@type='password' and @name='my-password']"
)

print("Password found using AND")


# -----------------------------------------
# TC08 - Alternatives
# or
# -----------------------------------------

text_box = driver.find_element(
    By.XPATH,
    "//input[@name='my-text' or @type='text']"
)

print("Element found using OR")


# -----------------------------------------
# TC09 - Find parent
# -----------------------------------------

parent = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']/parent::*"
)

print("Parent element found")


# -----------------------------------------
# TC10 - Find form using ancestor
# -----------------------------------------

form = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']/ancestor::form"
)

print("Form found using ancestor")


# -----------------------------------------
# TC11 - Find child inputs
# -----------------------------------------

child_inputs = form.find_elements(
    By.XPATH,
    ".//child::input"
)

print("Child input count:", len(child_inputs))


# -----------------------------------------
# TC12 - Find next element
# following
# -----------------------------------------

next_element = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']/following::input[1]"
)

print("Following element found")


# -----------------------------------------
# TC13 - Find Checkbox
# Attribute + XPath
# -----------------------------------------

checkbox = driver.find_element(
    By.XPATH,
    "//input[@type='checkbox']"
)

checkbox.click()

print("Checkbox selected")


# -----------------------------------------
# TC14 - Find Radio Button
# Attribute + XPath
# -----------------------------------------

radio = driver.find_element(
    By.XPATH,
    "//input[@type='radio']"
)

radio.click()

print("Radio button selected")


# -----------------------------------------
# TC15 - Select Dropdown
# XPath + Select
# -----------------------------------------

dropdown = driver.find_element(
    By.XPATH,
    "//select[@name='my-select']"
)

select = Select(dropdown)

select.select_by_visible_text("Two")

print("Dropdown selected")


# -----------------------------------------
# TC16 - Find second textbox
# XPath index
# -----------------------------------------

second_textbox = driver.find_element(
    By.XPATH,
    "(//input[@type='text'])[2]"
)

print("Second textbox found")


# -----------------------------------------
# TC18 - Find all input fields
# find_elements()
# -----------------------------------------

all_inputs = driver.find_elements(
    By.XPATH,
    "//input"
)

print("Total input fields:", len(all_inputs))


# -----------------------------------------
# TC19 - Find dynamic element
# contains()
# -----------------------------------------

dynamic_element = driver.find_element(
    By.XPATH,
    "//input[contains(@name,'my-')]"
)

print("Dynamic element found")


# -----------------------------------------
# TC20 - Complete form
# -----------------------------------------

print("Completing form...")

# Text
text_input.clear()
text_input.send_keys("Kannan")

# Password
password.clear()
password.send_keys("Kannan@123")

# Checkbox
if not checkbox.is_selected():
    checkbox.click()

# Radio
if not radio.is_selected():
    radio.click()

# Dropdown
select.select_by_visible_text("Two")

# Submit
submit.click()

print("Form submitted successfully!")

time.sleep(3)

driver.quit()
```















## Output:
<img width="1678" height="981" alt="image" src="https://github.com/user-attachments/assets/4e68ad02-403d-43ff-8508-fe5b811c1169" />
