## 📊 Data-Driven Testing

This project uses data-driven testing with `products.csv` containing 5 test products:
- Laptop
- Wireless Mouse
- USB Keyboard
- HD Monitor
- Webcam

## 📸 Screenshots

The `/screenshots` folder contains:
1. `newman-command.png` - Local Newman test execution
2. `html-report.png` - Generated HTML test report
3. `ci-pipeline.png` - GitHub Actions pipeline run

## 🚀 Running with Data File

```bash
newman run Project.postman_collection.json -e Project.postman_environment.json -d products.csv
text

### **Step 7: Push Everything to GitHub**
```bash
# Check what we have
git status
# You should see: products.csv, screenshots/, README.md

# Add all new files
git add products.csv screenshots/ README.md

# Commit
git commit -m "Add products.csv, screenshots, and update README"

# Push
git push origin master
✅ Final Check on GitHub:
Go to: https://github.com/beejay-qa/Qace_Academy_Project
You should see:

📁 screenshots/ folder

📄 products.csv file

Updated README

Take the screenshots now and let me know when you're done! 💛

I'm done with the screenshots, give the updated readme.md
Perfect! Here's your complete, professional README.md file ready to copy and paste:

📝 Complete README.md Content
markdown
# API Exam Project - Qace Academy

![API Tests](https://github.com/beejay-qa/Qace_Academy_Project/actions/workflows/api-tests.yml/badge.svg)

## 📋 Project Overview
This project demonstrates a complete API test automation suite built using **Postman**, **Newman**, and **GitHub Actions**. It covers functional testing, advanced automation techniques, and CI/CD integration.

### 🎯 Objectives
- Manual API testing using Postman
- Automated testing with JavaScript assertions
- Data-driven testing with CSV
- Command-line execution via Newman
- Continuous Integration with GitHub Actions

## 🧩 Modules Tested
The following API modules were tested based on the provided documentation:
- ✅ Users
- ✅ Brands
- ✅ Carts
- ✅ Categories
- ✅ Invoices
- ✅ Payment
- ✅ Products
- ✅ Reports
- ✅ TOTP

## 🛠️ Tech Stack
| Tool | Purpose |
|------|---------|
| Postman | API testing and collection management |
| Newman | Command-line test runner |
| Node.js | Runtime environment |
| GitHub Actions | CI/CD pipeline automation |
| htmlextra | HTML report generation |

## 📁 Project Structure
Qace_Academy_Project/
├── .github/
│ └── workflows/
│ └── api-tests.yml # GitHub Actions workflow
├── screenshots/
│ ├── newman-command.png # Local Newman execution
│ ├── html-report.png # HTML test report
│ └── ci-pipeline.png # GitHub Actions pipeline
├── products.csv # Data-driven test data
├── Project.postman_collection.json # Postman collection
├── Project.postman_environment.json # Postman environment
├── test-report.html # Generated HTML report
└── README.md # Project documentation

text

## 🔐 Authentication
Authentication is handled using Bearer tokens:
1. Login endpoint saves token to environment
2. Token is automatically used for protected routes
3. Variable chaining ensures seamless test execution

```javascript
// In Login request Tests tab
let jsonData = pm.response.json();
pm.environment.set("token", jsonData.token);
🔄 Variable Chaining
Dynamic values are passed between requests:

Create User → Save User ID

Create Cart → Save Cart ID

Use IDs in subsequent requests (Get/Update/Delete)

📊 Data-Driven Testing
The project implements data-driven testing using products.csv:

csv
name,price,category,stock
Laptop,999.99,Electronics,10
Wireless Mouse,25.50,Accessories,50
USB Keyboard,45.00,Accessories,30
HD Monitor,299.99,Electronics,15
Webcam,89.99,Electronics,25
Run with data file:

bash
newman run Project.postman_collection.json -e Project.postman_environment.json -d products.csv
🚀 Running Tests Locally
Prerequisites
Node.js installed

Newman installed globally

Installation
bash
# Install Newman and HTML reporter
npm install -g newman newman-reporter-htmlextra
Run Tests
bash
# Basic run
newman run Project.postman_collection.json -e Project.postman_environment.json

# With HTML report
newman run Project.postman_collection.json -e Project.postman_environment.json -r htmlextra --reporter-htmlextra-export test-report.html

# With data-driven testing
newman run Project.postman_collection.json -e Project.postman_environment.json -d products.csv -r htmlextra
🔄 CI/CD Integration (GitHub Actions)
The GitHub Actions workflow (.github/workflows/api-tests.yml) automatically:

Triggers on push to master branch

Sets up Node.js environment

Installs Newman and reporters

Runs the entire Postman collection

Generates HTML reports

Fails the pipeline if any tests fail

Uploads test results as artifacts

Workflow Status
https://github.com/beejay-qa/Qace_Academy_Project/actions/workflows/api-tests.yml/badge.svg

📸 Screenshots
The /screenshots folder contains:

Screenshot	Description
newman-command.png	Local Newman test execution in terminal
html-report.png	Generated HTML test report with results
ci-pipeline.png	GitHub Actions successful pipeline run
✅ Test Assertions Implemented
Each request includes:

✅ Status code validation (200, 201, 404, etc.)

✅ Response body validation (JSON structure)

✅ Response time checks (< 500ms)

✅ JavaScript assertions using pm.test()

Example:

javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

pm.test("Response has user ID", function () {
    let jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property("id");
});
📦 Deliverables
This project includes all required deliverables:

✅ Postman Collection file

✅ Postman Environment file

✅ Data file (products.csv)

✅ Newman command screenshot

✅ Generated HTML report

✅ GitHub repository with Actions

✅ CI pipeline screenshot

✅ README with setup instructions

🏆 Evaluation Criteria Met
Criteria	Status
Structure & Organization	✅
Assertion Quality	✅
Data-driven Testing	✅
Automation via Newman	✅
CI Integration	✅
Documentation	✅
📬 Submission
Repository URL: https://github.com/beejay-qa/Qace_Academy_Project

Submitted by: [Your Name]

Date: February 25, 2026

🙏 Acknowledgments
Qace Academy for the comprehensive API testing project

Postman for the excellent API testing tool

GitHub Actions for free CI/CD integration