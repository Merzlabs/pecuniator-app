# Pecuniator App

> Pecuniator is project that wants to improve access to financial data for you.

Pecuniator App is a work in progress tool which let's you analyze your financial data like you want to. It's basically a data sandbox. Pecuniator wants to become a privacy focused way of looking at your bank transactions and Pecuniator app is one part of the project.

The core of Pecuniator App is to provide a sandbox with imported financial data and a programming API, that lets you work with that data.

Just a quick example:

```javascript
var budget = new Budget({name: "My car budget", interval: "yearly"});
const accountQuery = new AccountQuery();
accountQuery.iban.equals("MYGIROIBAN");
const account = Accounts.query(accountQuery);

const insuranceQuery = new TransactionsQuery();
insuranceQuery.subject.contains("Insurance Payment Car");
//insuranceQuery.subject.regex(..
insuranceQuery.iban.equals("DE....");

const insuranceTransactions = account.query(insuranceQuery);
budget.add("Insurance", insuranceTransactions);

console.log(budgte.name, budget.summary());
```

### MVP

We want to start the Pecuniator journey with a minimum viable product that is Pecuniator App. For this we need to start with the most basic features to show the capabilities and vision of this idea:

* No customer data on external servers. Everything local
* Import CAMT transaction data
* Store data in a local SQLite database
* Write a basic synchronous API with objects and typings to access data
* (Monaco editor for building scripts)

### Planned features

There are some ideas with their own challenges and work needed. In no particular order:

* Component style UI dashboards for custom visualization and interfaces
* Script/Component marketplace for sharing
* Encryption at rest
* Scheduled scripts
* Notifications
* Webhooks
* Access to live data via PSD2 XS2A. PoC [here](https://github.com/Merzlabs/pycuniator) and [here](https://github.com/Merzlabs/pecuniatordotgo)
* Mobile and desktop Sync

## Development

### Running the electron app

Clone this repo and run this script `npm run build:electron`.