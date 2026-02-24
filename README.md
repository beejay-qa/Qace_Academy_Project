📌 API Manual & Automation Project

By: Bolaji Ebun

📖 Project Overview

This project demonstrates end-to-end API testing including:

Manual API testing using Postman

Automated API testing with JavaScript assertions

Data-driven testing (CSV/JSON)

Command-line execution using Newman

CI integration using GitHub Actions

The project covers real-world API testing practices such as authentication, variable chaining, response validation, and continuous integration.

📂 Modules Tested

The following API modules were tested:

Users

Brands

Carts

Categories

Invoices

Payment

Products

Reports

TOTP

Each module includes:

Status code validation

Response body validation

Response time validation

Authentication handling (Bearer token)

Environment variable usage

🛠 Tools Used

Postman

Newman CLI

Node.js

GitHub

GitHub Actions

🔐 Authentication Handling

Authentication is implemented using:

Login endpoint

Token saved as environment variable

Bearer token used for protected routes

Example:

pm.environment.set("token", jsonData.token);

Protected requests use:

Authorization: Bearer {{token}}
🔄 Variable Chaining

Dynamic values are passed between requests.

Example:

Create Cart → Save cart_id

pm.environment.set("cart_id", jsonData.id);

Used in Payment request:

"cart_id": "{{cart_id}}"
📊 Data-Driven Testing

Data-driven testing was implemented using a CSV/JSON file.

Example:

products.csv

name,price
Bag,2000
Shoe,5000
Watch,8000

Collection was executed using:

newman run collection.json -e environment.json -d products.csv
🚀 Running Tests with Newman

Install Newman:

npm install -g newman

Run collection:

newman run Project.postman_collection.json -e project.postman_environment.json

Generate HTML report:

newman run Project.postman_collection.json -e project.postman_environment.json -r html --reporter-html-export report.html
🔄 CI Integration (GitHub Actions)

GitHub Actions workflow automatically:

Installs Node.js

Installs Newman

Runs the collection

Fails pipeline if tests fail

Workflow file location:

.github/workflows/test.yml

The pipeline ensures continuous validation of API stability.

📁 Project Structure
API-Exam-Project
│
├── Project.postman_collection.json
├── project.postman_environment.json
├── products.csv
├── report.html
├── .github/workflows/test.yml
└── README.md
✅ Evaluation Coverage

This project demonstrates:

Structured test organization

Strong assertion implementation

Dynamic variable handling

Data-driven testing

Automation via Newman

CI/CD integration

Professional documentation# Qace_Academy_Project
