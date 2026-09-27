# E-Commerce Purchase Flow Automation

A web automation testing project built using **Python, Selenium, and PyTest**.  
The project automates important user flows of an e-commerce website, including product selection, cart/checkout navigation, form submission, and purchase confirmation.

The project follows the **Page Object Model (POM)** design pattern to keep the automation code organized, reusable, maintainable, and scalable.

---

## Project Overview

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