# Actual Budget API Reference

## Base URL
http://localhost:5000/api

## 📘 Budget Endpoints

### `GET /budgets`
**Description:**  
Retrieve a list of all budgets.
**Response Example:**
```json
[
  {
    "id": "budget-1",
    "name": "Personal Budget",
    "total": 15000000
  }
]
```
Status Codes:
  - 200 OK – Successfully retrieved list of budgets.
  - 500 Internal Server Error – Server error.


### `POST /budgets`
**Description:**  
Create a new budget.
**Request Body :**
```json
{
  "name": "Monthly Expenses",
  "total": 2000000
}
```
**Response Example :**
```json
{
  "id": "budget-2",
  "name": "Monthly Expenses",
  "total": 2000000
}
```
Status Codes:
  - 201 Created – Budget created successfully.
  - 400 Bad Request – Invalid input.
**Error Response Example :**
```json
{
  "error": "Name and total are required"
}
```

    
### `GET /budgets/:id`
**Description:**
Retrieve a specific budget by its ID.
**Response Example:**
```json
{
  "id": "budget-1",
  "name": "Personal Budget",
  "total": 15000000
}
```
Status Codes:
  - 200 OK – Budget retrieved successfully.
  - 404 Not Found – Budget not found.
**Error Response Example :**
```json
{
  "error": "Budget not found"
}
```


### `POST /budgets/:id`
**Description:**  
Update a budget by its ID.
**Request Body :**
```json
{
  "name": "Updated Budget",
  "total": 18000000
}
```
**Response Example :**
```json
{
  "id": "budget-1",
  "name": "Updated Budget",
  "total": 18000000
}
```
Status Codes:
  - 200 OK – Budget updated successfully.
  - 400 Bad Request – Invalid update data.
  - 404 Not Found – Budget not found.
**Error Response Example :**
```json
{
  "error": "Budget not found"
}
```


### `DELETE /budgets/:id`
**Description:**
Delete a budget by its ID.
**Response Example:**
```json
{
  "message": "Budget deleted successfully"
}
```
Status Codes:
  - 200 OK – Budget deleted.
  - 404 Not Found – Budget not found.
**Error Response Example :**
```json
{
  "error": "Budget not found"
}
```
/
/
/
/
/
## 📘 Transaction Endpoints
### `GET /transactions`
**Description:**  
Retrieve all transactions.
**Response Example:**
```json
[
  {
    "id": "tx-1",
    "amount": 50000,
    "budgetId": "budget-1",
    "description": "Groceries"
  }
]
```
Status Codes:
  - 200 OK – Successfully retrieved transactions.
  - 500 Internal Server Error – Server error.


### `POST /transactions`
**Description:**  
Create a new transaction.
**Request Body:** 
```json
{
  "amount": 50000,
  "budgetId": "budget-1",
  "description": "Groceries"
}
```
**Response Example:**
```json
{
  "id": "tx-2",
  "amount": 50000,
  "budgetId": "budget-1",
  "description": "Groceries"
}
```
Status Codes:
  - 201 Created – Transaction created successfully.
  - 400 Bad Request – Invalid input.
**Error Response Example :**
```json
{
  "error": "Amount and budgetId are required"
}
```   


### `GET /transactions/:id`
**Description:**
Retrieve a specific transaction by its ID.
**Response Example:**
```json
{
  "id": "tx-1",
  "amount": 50000,
  "budgetId": "budget-1",
  "description": "Groceries"
}
```
Status Codes:
  - 200 OK – Transaction retrieved.
  - 404 Not Found – Transaction not found.
**Error Response Example :**
```json
{
  "error": "Transaction not found"
}
```


### `POST /transactions/:id`
**Description:**  
Update a transaction by its ID.
**Request Body :**
```json
{
  "amount": 60000,
  "description": "Updated groceries"
}
```
**Response Example :**
```json
{
  "id": "tx-1",
  "amount": 60000,
  "budgetId": "budget-1",
  "description": "Updated groceries"
}
```
Status Codes:
  - 200 OK – Transaction updated.
  - 400 Bad Request – Invalid data.
  - 404 Not Found – Transaction not found.
**Error Response Example :**
```json
{
  "error": "Transaction not found"
}
```


### `DELETE /transactions/:id`
**Description:**
Delete a transaction by its ID.
**Response Example:**
```json
{
  "message": "Transaction deleted successfully"
}
```
Status Codes:
  - 200 OK – Transaction deleted.
  - 404 Not Found – Transaction not found.
**Error Response Example :**
```json
{
  "error": "Transaction not found"
}
```
