# dba120-exam1

## Ex 1.

INSERT INTO terms (terms_id, terms_description, terms_due_days) VALUES (6, 'Net due 120 days', 120)

![Excercise 1](/ch5_ex1_results.jpg)

**What did this query change in the database?**
The SQL query added a record to the terms table.

## Ex 2.

UPDATE terms
SET terms_description = 'Net due 125 days',
    terms_due_days = 125
WHERE terms_id = 6

![Excercise 2](/ch5_ex2_results.jpg)

**What did this query change in the database?**
The SQL query changed the due date from 120 to 125 days in the record we added in Exercise 1.

## Ex 3.

DELETE FROM terms
WHERE terms_id = 6

![Excercise 3](/ch5_ex3_results.jpg)

**What did this query change in the database?**
The SQL query removed the record that was added in Exercise 1 based on its terms_id.

## Ex 4.

INSERT INTO invoices
VALUES (DEFAULT, 32, 'AX-014-027', '2018-08-01', 434.58, 0, 0,
        2, '2018-08-31', NULL)
        
![Excercise 4](/ch5_ex4_results.jpg)

**What did this query change in the database?**
The SQL query added a record with the values listed as the last record in the invoices table.

## Ex 5.

INSERT INTO invoice_line_items VALUES
    (115, 1, 160, 180.23, 'Hard drive'),
    (115, 2, 527, 254.35, 'Exchange Server update')

![Excercise 5](/ch5_ex5_results.jpg)

**What did this query change in the database?**
The SQL query added 2 record with the values listed into the invoice_line_items table.

## Ex 6.

UPDATE invoices
SET credit_total = invoice_total * .1,
    payment_total = invoice_total - credit_total
WHERE invoice_id = 115

![Excercise 6](/ch5_ex6_results.jpg)

**What did this query change in the database?**
The SQL query calculated and updated the credit_total and payment_total for the two records added in Ex 5 based on their invoice_total values.

## Ex 7.

UPDATE vendors
SET default_account_number = 403
WHERE vendor_id = 44

![Excercise 7](/ch5_ex7_results.jpg)

**What did this query change in the database?**
The SQL query changed the default_account_number of the vendor with vendor_id 44 to 403.

## Ex 8.

UPDATE invoices
SET terms_id = 2
WHERE vendor_id IN
    (SELECT vendor_id
     FROM vendors
     WHERE default_terms_id = 2)

![Excercise 8](/ch5_ex8_results.jpg)

**What did this query change in the database?**
The SQL query cross checked which records from the Vendors table had a default_term_id of 2 and set that as the term_id in their related entry in the Invoices table.

## Ex 9.

DELETE FROM invoice_line_items
WHERE invoice_id = 115;

DELETE FROM invoices
WHERE invoice_id = 115;

![Excercise 9](/ch5_ex9_results_part1.jpg)
![Excercise 9](/ch5_ex9_results_part2.jpg)

**What did this query change in the database?**
The SQL query removed the records from the invoice_line_items table and invoices table with an invoice_id equal to 115.
