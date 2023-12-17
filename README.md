# send
- Add Tax planning to the budget
- ```mermaid
  erDiagram
  
  USER {
  	string id PK
      string fname
      string lname
  }
  
  INCOMESOURCE {
  	string id PK
  	string label
  }
  
  INCOMEFLOW {
  	string id PK
  	string owner FK
      string source FK
      int amount
      string pool FK
      string stream FK
      datetime date
  }
  
  INCOMEPOOL {
  	string id PK
      string label
      int amount
  }
  
  INCOMESTREAM {
  	string id PK
  	string owner FK
      string source FK
      String pool FK
      bool recurs
      int freq
      int interval
      int[] byweekday
      datetime dtstart
      datetime until
  }
  
  BUDGETFLOW {
  	string id PK
      int amount
      string pool FK
      string stream FK
      string fund FK
      string category FK
      datetime date
  }
  
  BUDGETSTREAM {
  	string id PK
      string pool FK
      string fund FK
      string category FK
      datetime date
  }
  
  FUNDCATEGORY {
  	string id PK
      string label
  }
  
  FUND {
  	string id PK
      string category FK
  }
  
  EXPENSECATEGORY {
  	string id PK
      string fund FK
      int amount
  }
  
  INCOMEFLOW }o--|| INCOMESOURCE: source
  INCOMEFLOW }o--|| USER: owner
  INCOMESTREAM }o--|| USER: owner
  INCOMESTREAM }o--|| INCOMESOURCE: source
  
  INCOMESTREAM }o--|| INCOMEPOOL: pool
  INCOMEFLOW }o--|| INCOMEPOOL: pool
  INCOMEFLOW }o--o| INCOMESTREAM: stream
  
  FUND }o--|| FUNDCATEGORY: category
  
  BUDGETSTREAM }o--|| INCOMEPOOL: pool
  BUDGETSTREAM }o--|| FUND: fund
  BUDGETSTREAM }o--|| EXPENSECATEGORY: category
  
  BUDGETFLOW }o--|| INCOMEPOOL: pool
  BUDGETFLOW }o--o| BUDGETSTREAM: stream
  BUDGETFLOW }o--|| EXPENSECATEGORY: category
  BUDGETFLOW }o--|| FUND: fund
  
  EXPENSECATEGORY }o--|| FUND: fund
  ```
-
- ## Income
	- ### Income Record
		- An individual payment that represents a single inflow.
	- ### Income Source
		- A source of income, to which income records can be automatically or manually added.
	- ### Income Stream
		- A recurrence rule for automatically creating `IncomeFlow`s for an `IncomeSource`
		- Automatically added income will require a confirmation from the owner, before it is added.
			- The value of the income can
	- ### Income Pool
		- Multiple incomes can be collected into income pools.
	- ### Income Outflows
		- Represent outflows from an `IncomePool` into `Fund` and `ExpenseCategory`
	-
	- Automatically redirect income from `Pools` into `Funds` based on **rules**:
		- **Percentage rule**: A certain % of the Pool is added to a selected fund every assessment period.
		- **Fixed amount rule**: A certain fixed amount is added every period.
		- **Top-up rule**: A certain prescribed amount is maintained in a fund. A transfer is only made if the amount in the fund is less than the prescribed amount, and the transfer fills the difference between the prescribed amount and the current amount.
	- ## Fund
	- ### Fund Category
		- Represents the type of a fund.
		- By default `Expenses` and `Savings` are created
	- ## Fund options
		- Danger levels
		- Warning levels
		-
	- Funds can be Budget funds or Savings funds.
		- When an expense is recorded, it has to be categorized. This category is linked to a fund from which the money is deducted and added to the **Expense Records**.
	- The **expense entry screen** has the following inputs:
		- **Amount**: the money amount to be paid.
		- **Category**: A searchable input for the fund-linked category.
			- When a category is selected, the fund it belongs to is displayed as a bar with the current expense,  `warning` and `danger` levels.
		- **Date**: Defaults to current datetime.
		- **Notes**: Searchable text.
		- **Tags**: Tags like `Avoidable`, `To reduce`, `Unplanned` or `Emergency`
	- ## [[Text editor]]
-
