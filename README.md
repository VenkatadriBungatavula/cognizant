#RaboCustomerStatementProcessor is spring boot application REST service which receives the customer statement JSON as a POST data, Perform the below validations
1. All transaction references should be unique
2. The end balance needs to be validated ( Start Balance +/- Mutation = End Balance )

URL: http://localhost:8080/validateStatement
Method: POST

Design used:
==============
Maintain layered structure as below
Controller -- RaboStatementProcessController: to hadle the requrests and map to methods
Util -- ValidationUtil: to validate the transaction statement 
                          1. Method to check duplication transaction reference
                          2. Method to validate End Balance in transactions
Model -- ErrorRecord, Request, ResponseStatus, Transaction: model classes
Exception -- Gloabal exception handling
