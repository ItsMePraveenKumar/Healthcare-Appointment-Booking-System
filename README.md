# Healthcare Appointment Booking System

A Python-based Selenium automation testing project for automating the appointment booking workflow of a healthcare web application.

The project uses Selenium WebDriver, Python, Pytest, and the Page Object Model (POM) design pattern.

## Project Overview

The Healthcare Appointment Booking System automates and validates a healthcare appointment booking process.

The automation performs actions such as:

- Opening the healthcare website
- Navigating to the appointment page
- Logging into the application
- Selecting a healthcare facility
- Selecting the healthcare program
- Entering appointment-related information
- Booking an appointment

The project uses the Page Object Model (POM) to separate webpage elements and actions from test logic.

## Objectives

- Automate the healthcare appointment booking workflow.
- Reduce repetitive manual testing.
- Validate important user interactions.
- Separate test logic from webpage-specific code.
- Create reusable Page Object classes.
- Execute automated tests using Pytest.
- Improve maintainability when the UI changes.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Selenium WebDriver | Browser automation |
| Pytest | Test execution and reporting |
| Page Object Model | Automation design pattern |
| Google Chrome | Browser used for automation |

## Project Structure

```text
Healthcare-Appointment-Booking-System/
│
├── HealthCare_Project/
│   ├── __init__.py
│   ├── conftest.py
│   └── test_healthcare.py
│
├── PageObjects/
│   ├── __init__.py
│   ├── Appointmentpage.py
│   ├── Homepage.py
│   └── Loginpage.py
│
└── README.md
```

## Folder and File Description

### `HealthCare_Project/`

Contains the Pytest configuration and test cases.

### `conftest.py`

Contains the Pytest fixture used for test setup.

It is responsible for tasks such as:

- Creating the Selenium WebDriver.
- Opening the browser.
- Opening the healthcare application.
- Making the driver available to the test class.
- Performing required cleanup.

### `test_healthcare.py`

Contains the main automated test case.

Main test:

```text
test_healthPro
```

The test coordinates the different Page Object classes and performs the appointment workflow.

## PageObjects

The `PageObjects` directory contains the Page Object Model classes.

### `Homepage.py`

Represents the healthcare application's home page.

It contains webpage locators and actions required to navigate from the home page to the appointment/login workflow.

### `Loginpage.py`

Represents the login page.

It contains locators and actions required for:

- Username entry
- Password entry
- Login

### `Appointmentpage.py`

Represents the appointment booking page.

It contains the elements and actions required for the appointment workflow, including:

- Selecting the healthcare facility
- Selecting the healthcare program
- Entering appointment information
- Booking the appointment

## Page Object Model

This project follows the Page Object Model (POM) design pattern.

Instead of writing all Selenium code inside the test file, webpage-specific elements and actions are placed inside separate classes.

```text
Test Case
   |
   +----> Homepage
   |
   +----> Loginpage
   |
   +----> Appointmentpage
```

### Benefits of POM

- Reduces duplicate code.
- Makes tests easier to read.
- Keeps locators in one place.
- Makes UI changes easier to maintain.
- Allows page actions to be reused.

## Test Execution Flow

```text
Start Pytest
     ↓
Load conftest.py
     ↓
Create WebDriver
     ↓
Open Chrome
     ↓
Open healthcare website
     ↓
Start test_healthPro
     ↓
Open HomePage
     ↓
Click Make Appointment
     ↓
Open LoginPage
     ↓
Enter username
     ↓
Enter password
     ↓
Click Login
     ↓
Open AppointmentPage
     ↓
Select facility
     ↓
Select healthcare program
     ↓
Enter appointment information
     ↓
Click Book Appointment
     ↓
Test completes
     ↓
Browser cleanup
     ↓
Pytest reports result
```

## Test Automation

The current project contains one automated test.

Test file:

```text
HealthCare_Project/test_healthcare.py
```

Test function:

```text
test_healthPro
```

The test validates the main appointment booking workflow.

## Installation

### 1. Install Python

Install Python on your system.

Check the installation:

```bash
python --version
```

Example:

```text
Python 3.14.5
```

### 2. Install Dependencies

Open a terminal in the project directory and run:

```bash
python -m pip install pytest selenium
```

### 3. Verify Pytest

```bash
python -m pytest --version
```

### 4. Verify Selenium

```bash
python -c "import selenium; print(selenium.__version__)"
```

## Browser Requirements

The automation uses Google Chrome.

Make sure Google Chrome is installed.

Modern Selenium versions can normally manage the required browser driver automatically through Selenium Manager.

## Running the Project

Navigate to the project root:

```text
Healthcare-Appointment-Booking-System
```

Run the complete Pytest suite:

```bash
python -m pytest
```

The current project contains one test, so this currently runs one test.

## Running a Specific Test File

```bash
python -m pytest HealthCare_Project/test_healthcare.py
```

## Running a Specific Test

```bash
python -m pytest HealthCare_Project/test_healthcare.py::test_healthPro
```

## Verbose Execution

For detailed Pytest output:

```bash
python -m pytest -v
```

## Quiet Execution

For compact output:

```bash
python -m pytest -q
```

## Running from PyCharm

### Run the test file

1. Open `HealthCare_Project/test_healthcare.py`.
2. Right-click inside the file.
3. Select the Pytest run option.

### Run an individual test

Find:

```text
test_healthPro
```

Click the green Run icon beside the test.

### Run from PyCharm Terminal

```bash
python -m pytest
```

## Successful Test Result

A successful run looks similar to:

```text
collected 1 item

HealthCare_Project\test_healthcare.py .    [100%]

1 passed
```

Meaning:

- `collected 1 item` → Pytest found one test.
- `.` → The test passed.
- `[100%]` → All collected tests completed successfully.
- `1 passed` → One test passed.

## Framework Architecture

```text
                 Pytest
                    |
                    ↓
             Test Layer
                    |
                    ↓
          Page Object Layer
                    |
          ┌─────────┼─────────┐
          ↓         ↓         ↓
       Homepage  Loginpage  Appointmentpage
          |
          ↓
     Selenium WebDriver
          |
          ↓
      Chrome Browser
          |
          ↓
 Healthcare Web Application
```

## Test Data

The current implementation does not contain a separate `/data` directory or external data-driven test-data file.

The required test values are handled directly by the existing test/page implementation.

## Configuration

The current implementation does not contain a separate `/config` directory.

Browser and test setup are handled through:

```text
HealthCare_Project/conftest.py
```

## Current Test Coverage

The current project focuses on the healthcare appointment booking workflow.

The implemented flow includes:

- Website navigation
- Appointment navigation
- User login
- Facility selection
- Healthcare program selection
- Appointment information entry
- Appointment booking

The current project contains one main automated test.

## Troubleshooting

### `pytest` command is not recognized

If:

```bash
pytest
```

shows that pytest is not recognized, use:

```bash
python -m pytest
```

### Selenium is not installed

```bash
python -m pip install selenium
```

### Pytest is not installed

```bash
python -m pip install pytest
```

### Both packages are missing

```bash
python -m pip install pytest selenium
```

### Check installed packages

```bash
python -m pip list
```

### Update Selenium

```bash
python -m pip install --upgrade selenium
```

## Useful Commands

Check Python:

```bash
python --version
```

Install dependencies:

```bash
python -m pip install pytest selenium
```

Check Pytest:

```bash
python -m pytest --version
```

Check Selenium:

```bash
python -c "import selenium; print(selenium.__version__)"
```

Run complete project:

```bash
python -m pytest
```

Run test file:

```bash
python -m pytest HealthCare_Project/test_healthcare.py
```

Run specific test:

```bash
python -m pytest HealthCare_Project/test_healthcare.py::test_healthPro
```

Run with detailed output:

```bash
python -m pytest -v
```

Run with minimal output:

```bash
python -m pytest -q
```

## Future Improvements

The automation framework can be extended with:

- More appointment test scenarios.
- Negative login tests.
- Invalid input validation.
- Appointment cancellation testing.
- Appointment rescheduling testing.
- Multiple test data sets.
- Data-driven testing.
- Stronger assertions for booking confirmation.
- Better logging.
- Screenshot capture on failures.
- HTML test reports.
- Separate configuration files.
- Environment-specific settings.
- CI/CD integration.

## Important Project Note

The original project description mentions folders such as:

```text
/tests
/pages
/data
/config
```

However, those folders are not present in the actual project structure.

The actual implementation uses:

```text
HealthCare_Project/
PageObjects/
```

This README describes the actual implementation present in the project.

## Project Summary

The Healthcare Appointment Booking System is a Selenium-based web automation framework written in Python.

It uses Pytest for test execution and follows the Page Object Model to separate test scenarios from webpage-specific Selenium interactions.

The current automation opens the healthcare application, navigates through the appointment workflow, performs login and appointment-related actions, and executes the test through Pytest.

The framework provides a foundation that can be extended with additional test cases, test data, validations, reporting, and CI/CD automation.
