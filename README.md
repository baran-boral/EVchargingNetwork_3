# ⚡ EV Charging Network

A Java application for managing an EV Charging Network, developed **BDD style** with Cucumber as part of the **Requirements Engineering Project (REQEP)** at FH Technikum Wien (WS 2026, Group 3).

The Owner of a growing network of electric charging Stations needs software to manage Stations and Charging Points, set Prices, handle prepaid Customer Accounts and bill Charging Sessions.

## ✨ Features

* 🏢 **Stations:** create and view Stations with name and address
* 🔌 **Charging Points:** AC or DC Charging Mode, status Available / Occupied / Out of Order
* 💶 **Prices:** Energy Price (EUR per kWh) and Time Price (EUR per minute) per Station and Charging Mode, changeable at any time
* 👤 **Customer Accounts:** registration before charging
* 💳 **Prepaid Balance:** Top-Ups in EUR; the balance never becomes negative
* 🚗 **Charging Sessions:** start and stop charging, Charging Cost deducted automatically
* 📊 **Network Status:** Charging Point Status and current Prices of all Stations at any time
* 📜 **Transaction History:** date-sorted list of Top-Ups and Charging Sessions with balance

## 🧮 Billing Rule

```
Charging Cost = Charged Energy (kWh) × Energy Price + Charging Duration (min) × Time Price
```

The Price valid at the Station and Charging Mode **when the session started** always applies.

## 🗺️ Requirements

The requirements are developed with **User Story Mapping** (Jeff Patton) for two personas, **Owner** and **Customer**:

| Epic | Feature File | Persona | Release |
|---|---|---|---|
| E1 Station | `station.feature` | Owner | MVP Part 1 |
| E2 Charging Point | `charging_point.feature` | Owner | MVP Part 1 |
| E3 Price | `price.feature` | Owner | MVP Part 2 |
| E4 Customer Account | `customer_account.feature` | Customer | MVP Part 1 |
| E5 Prepaid Balance | `prepaid_balance.feature` | Customer | MVP Part 2 |
| E6 Charging Session | `charging_session.feature` | Customer | MVP Part 2 |
| E7 Network Status | `network_status.feature` | Owner and Customer | MVP Part 2 |
| E8 Transaction History | `transaction_history.feature` | Owner and Customer | MVP Part 2 |

📋 All 38 User Stories are tracked on the **[Kanban board](https://github.com/users/baran-boral/projects/4)**.

## 🧪 BDD Approach

1. 📝 **Feature files:** requirements written in Gherkin (`Given` / `When` / `Then`)
2. 🔗 **Step definitions:** acceptance tests that call the business objects
3. 🧱 **Business objects:** Java classes with manager classes for create, read, update and delete
4. ▶️ **Main program:** shows the business logic running without any test code

## 📁 Project Structure

```
src/
├── main/java/org/example/
│   └── ElectricChargingStationNetwork.java   ← main class
└── test/
    ├── java/org/example/
    │   ├── RunCucumberTest.java              ← Cucumber test runner
    │   └── StepDefinitions.java              ← acceptance test code
    └── resources/org/example/
        └── *.feature                         ← requirements in Gherkin
```

## 🔀 Development Workflow

* 🌿 Feature branch for every User Story
* 🔃 Pull request before merging into `main`
* ✅ Only tested code goes into `main`
* 🔒 `main` is the stable branch used for feedback and grading

## 🛠️ Technologies

* ☕ Java
* 📦 Maven (`io.cucumber:cucumber-archetype`)
* 🥒 Cucumber with Gherkin
* 🧪 JUnit Platform
* ✔️ AssertJ (fluent assertions)
* 💡 IntelliJ IDEA

## 🔨 Build

Clone the repository and run all acceptance tests:

```
mvn test
```

Build the project:

```
mvn package
```

## 👨‍💻 Contributors

* baran-boral
* Durmaz-jpg
* pascall0204
* SHUBRU

## 📜 License

This project was created for educational purposes as part of the Requirements Engineering Project at FH Technikum Wien.
