# E-Commerce Purchase Flow Automation

A web automation testing project built using **Python, Selenium, and PyTest**.

The project automates important user flows of an e-commerce website, including product selection, cart/checkout navigation, form submission, and purchase confirmation.

The project follows the **Page Object Model (POM)** design pattern to keep the automation code organized, reusable, maintainable, and scalable.

---

## 📌 Project Overview

This project demonstrates how Selenium WebDriver can be used with Python and PyTest to automate web application testing.

The automation covers two major test scenarios:

### 1. E-Commerce Purchase Flow

The test automates a complete shopping flow:

```text
Open Website
     ↓
Navigate to Shop
     ↓
Find Product
     ↓
Select Blackberry
     ↓
Add Product to Cart
     ↓
Proceed to Checkout
     ↓
Select Country
     ↓
Accept Terms/Checkbox
     ↓
Complete Purchase
     ↓
Verify Success Message
```

### 2. Home Page Form Submission

The project also automates the registration/form submission flow:

```text
Open Website
     ↓
Enter First Name
     ↓
Enter Email
     ↓
Select Checkbox
     ↓
Select Gender
     ↓
Submit Form
     ↓
Verify Success Message
```

---

# 🛠️ Technologies Used

- **Python**
- **Selenium WebDriver**
- **PyTest**
- **OpenPyXL**
- **Page Object Model (POM)**
- **PyTest Fixtures**
- **Explicit Waits**
- **Logging**
- **Excel Data-Driven Testing**
- **Git & GitHub**

---

# 📂 Project Structure

```text
E-Commerce-Purchase-Flow-Automation/
│
├── PageObjects/
│   ├── CheckoutPage.py
│   ├── ConfirmPage.py
│   ├── HomePage.py
│   └── __init__.py
│
├── TestData/
│   ├── Exceldataproject.py
│   ├── Homepagedata.py
│   ├── exceldemo.py
│   └── __init__.py
│
├── Tests/
│   ├── assets/
│   │   └── style.css
│   ├── conftest.py
│   ├── report.html
│   ├── test_e2e.py
│   ├── test_homePage.py
│   ├── uploadlec_112.py
│   └── __init__.py
│
├── Utilities/
│   ├── baseclass.py
│   └── __init__.py
│
├── ReportsJenkins/
│   └── __init__.py
│
├── pythondemo.xlsx
├── E-Commerce-Purchase-Flow-Automation_Run_Guide.txt
└── .gitignore
```

---

# 🧩 Page Object Model

The project uses the **Page Object Model (POM)** design pattern.

Each important page has its own Python class.

### HomePage.py

Contains locators and methods related to the home page.

Examples:

- Name field
- Email field
- Gender dropdown
- Checkbox
- Submit button
- Success message
- Shop navigation

### CheckoutPage.py

Contains functionality related to:

- Product listing
- Product selection
- Cart
- Checkout navigation

### ConfirmPage.py

Contains functionality related to:

- Country selection
- Confirmation
- Purchase submission

This keeps Selenium interaction code separated from test logic.

---

# 🧪 Test Cases

## Test Case 1: E-Commerce Purchase

File:

```text
Tests/test_e2e.py
```

The test:

1. Opens the website.
2. Navigates to the Shop page.
3. Retrieves available products.
4. Searches for the product **Blackberry**.
5. Adds the product to the cart.
6. Proceeds to checkout.
7. Enters/selects India as the country.
8. Accepts the required checkbox.
9. Submits the purchase.
10. Verifies the success message.

Final validation is performed using an assertion against the success message.

---

## Test Case 2: Home Page Form

File:

```text
Tests/test_homePage.py
```

The test:

1. Opens the website.
2. Reads test data from Excel.
3. Enters the first name.
4. Enters the required form data.
5. Selects the checkbox.
6. Selects the gender.
7. Submits the form.
8. Verifies the success message.

---

# 📊 Test Data

The project uses an Excel file:

```text
pythondemo.xlsx
```

The file is located in the project root.

The Excel file is read using the **OpenPyXL** library.

The data is loaded through:

```text
TestData/Homepagedata.py
```

---

# 🔧 PyTest Fixture

The project uses PyTest fixtures to manage browser setup.

File:

```text
Tests/conftest.py
```

The fixture:

- Creates the Chrome WebDriver.
- Opens the application URL.
- Maximizes the browser window.
- Makes the driver available to test classes.

This avoids repeating browser setup code in every test.

---

# ⏳ Selenium Waits

The project uses Selenium waiting mechanisms to handle elements that may not be immediately available.

For example, `WebDriverWait` is used to wait for required elements before continuing with the test.

This helps reduce failures caused by page loading delays.

---

# 📝 Logging

The project uses Python logging to provide information during test execution.

The base class provides reusable logging functionality.

This makes it easier to understand what the test is doing and troubleshoot failures.

---

# 🔄 Test Execution Flow

The overall architecture can be represented as:

```text
PyTest
   │
   ▼
conftest.py
   │
   ▼
Browser Setup
   │
   ▼
Test Class
   │
   ├── HomePage
   │
   ├── CheckoutPage
   │
   └── ConfirmPage
   │
   ▼
Selenium WebDriver
   │
   ▼
Web Application
   │
   ▼
Assertions
   │
   ▼
Test Result
```

---

# ⚙️ Installation

## Prerequisites

Install the following:

- Python
- Google Chrome
- PyCharm (optional)
- Git

Check Python:

```bash
python --version
```

The project was successfully tested with:

```text
Python 3.14.5
```

---

# 📦 Install Dependencies

Open the terminal inside the project directory and run:

```bash
python -m pip install selenium pytest openpyxl
```

### Package purpose

| Package | Purpose |
|---------|---------|
| Selenium | Browser automation |
| PyTest | Test execution |
| OpenPyXL | Excel test data handling |

---

# 📊 Excel Configuration

Make sure:

```text
pythondemo.xlsx
```

exists in the project root.

The project loads it using:

```python
book = openpyxl.load_workbook("pythondemo.xlsx")
```

---

# ▶️ Running the Tests

## Run E-Commerce Test

```bash
python -m pytest Tests/test_e2e.py -v
```

Expected result:

```text
1 passed
```

---

## Run Home Page Test

```bash
python -m pytest Tests/test_homePage.py -v
```

Expected result:

```text
1 passed
```

---

## Run the Complete Project

```bash
python -m pytest -v
```

PyTest automatically discovers the available test files.

Expected result:

```text
collected 2 items

Tests/test_e2e.py::TestOne::test_e2e PASSED
Tests/test_homePage.py::TestHomePage::test_formSubmission[getData0] PASSED

2 passed
```

---

# 🔍 Run a Specific Test

### E-Commerce test

```bash
python -m pytest Tests/test_e2e.py::TestOne::test_e2e -v
```

### Home page test

```bash
python -m pytest Tests/test_homePage.py::TestHomePage::test_formSubmission -v
```

---

# 📋 Test Results

The project contains an HTML test report:

```text
Tests/report.html
```

The report can be opened in a web browser to inspect the generated test results.

---

# 🚀 Key Features

- Automated browser testing using Selenium
- Python-based automation framework
- PyTest test execution
- Page Object Model architecture
- Reusable utility methods
- Excel-based test data
- PyTest fixtures
- Explicit waits
- Logging
- Assertion-based validation
- End-to-end e-commerce testing
- Form validation testing
- Maintainable test structure

---

# 🎯 Learning Objectives

This project demonstrates practical knowledge of:

- Selenium WebDriver
- Python automation
- PyTest
- Page Object Model
- Web element locators
- Explicit waits
- Browser automation
- Test assertions
- Fixtures
- Data-driven testing
- Excel integration
- Logging
- Test organization

---

# 🧪 Current Test Status

The complete project was successfully executed with:

```bash
python -m pytest -v
```

Result:

```text
2 passed
```

Both available automated test scenarios passed successfully.

---

# 👨‍💻 Project Purpose

This project is intended to demonstrate how an automated testing framework can be structured for an e-commerce web application using Python and Selenium.

It focuses on creating reusable page objects, separating test data from test logic, and validating important user workflows through automated end-to-end tests.

---

# 📄 Additional Documentation

A complete project execution guide is available in:

```text
E-Commerce-Purchase-Flow-Automation_Run_Guide.txt
```

It contains setup instructions, dependency installation, test execution commands, and troubleshooting information.

---

# 📜 License

This repository is intended for educational and automation testing purposes.
