# 📘 Postman API Testing Project – Simple Book API

This repository contains an **API automation framework** built with **Postman + Newman** for testing the [Simple Book API](https://simple-books-api.glitch.me).  
It demonstrates **functional testing, data-driven testing, CI/CD integration, reporting, and mock APIs** – a complete QA portfolio project.

---

## 🔧 Tools & Technologies
- **Postman** – API test creation & execution  
- **Newman** – CLI runner for Postman collections  
- **Newman HTML Extra Reporter** – beautiful HTML test reports  
- **GitHub Actions** – CI/CD pipeline for automated test runs  
- **JavaScript** – for dynamic test scripts & validations  

---

## 📂 Project Structure

├── collections/
│ └── simple-book-api.postman_collection.json # Main test collection
│
├── environment/
│ └── simple-book-api-env.postman_environment.json # Environment variables
│
├── data/
│ └── testdata.csv # Data-driven testing input
│
├── reports/
│ └── newman-report.html # Test execution report
│
├── .github/workflows/
│ └── postman-tests.yml # GitHub Actions CI/CD pipeline
│
└── README.md

---

## ✅ Test Coverage
The project covers **Books & Orders APIs** with:
- **Positive scenarios**
  - Get all books
  - Get a single book by ID
  - Place a new order
  - Get order details
  - Update order
  - Delete order
- **Negative scenarios**
  - Invalid/expired token
  - Invalid book ID
  - Unauthorized order update
- **Data-driven testing**
  - Multiple customers & book IDs from `testdata.csv`
- **Mock APIs**
  - Sample mock collection included for demo purposes

---

## 🚀 How to Run Locally

1️⃣ Install [Node.js](https://nodejs.org/)  
2️⃣ Install Newman & HTML reporter:

npm install -g newman newman-reporter-htmlextra

newman run collections/simple-book-api.postman_collection.json \
  -e environment/simple-book-api-env.postman_environment.json \
  -d data/testdata.csv \
  -r htmlextra \
  --reporter-htmlextra-export reports/newman-report.html

⚙️ CI/CD – GitHub Actions

This project includes a workflow (.github/workflows/postman-tests.yml) that:

Runs on every Push or Pull Request to the main branch

Installs Node.js + Newman

Executes all API tests

Uploads the HTML report as an artifact

🔗 You can download the report from the GitHub Actions run page.

🌍 Environment Setup

The environment file (simple-book-api-env.postman_environment.json) includes:

baseUrl → API base URL

accessToken → Authentication token

👉 You can extend this for QA/Staging/Prod environments.

📈 Future Enhancements

 Add JSON Schema validation for responses

 Expand negative test cases (invalid payloads, boundary values)

 Parameterize environment variables for multi-env testing

 Add Newman Slack/Email notification integration
