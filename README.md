# DB_Assignment_03_DWH


## Business case

Our business case is the Vesna café.
Key business questions:

 - Which products sell best?

 - Who are our most active customers?

 - Which month has the highest sales?

 - Which employees have the greatest impact on sales?

## Source data and table creation
```
-- menu

CREATE OR REPLACE TABLE dataset.raw_menu (
    product_id STRING,
    product_name STRING,
    category STRING,
    price STRING 
);

INSERT INTO dataset.raw_menu (product_id, product_name, category, price)
VALUES
    ('1', 'Espresso', 'Coffee', '35.00'),
    ('2', 'Latte', 'Coffee', '55.00'),
    ('2', 'Latte', 'Coffee', '55.00'),
    ('3', 'Green Tea', NULL, '40'),
    ('4', 'Croissant', 'Food', '$65.00'),
    ('5', 'Water', 'Beverage', '25');


-- staff

CREATE OR REPLACE TABLE dataset.raw_staff (
    staff_id STRING,
    staff_name STRING,
    role STRING,
    hire_date STRING 
);

INSERT INTO dataset.raw_staff (staff_id, staff_name, role, hire_date)
VALUES
    ('S01', 'Maria Ivanova', 'Barista', '2023-01-10'),
    ('S02', '  Oleh   ', 'Manager', '2022-11-15'),
    ('S03', 'Anna Petrova', 'Barista', '2023/05/20'),
    ('S01', 'Maria Ivanova', 'Barista', '2023-01-10'),
    ('S04', 'Ivan Kozak', NULL, '2023-08-01');


-- customers

CREATE OR REPLACE TABLE dataset.raw_customers (
    customer_id STRING,
    customer_name STRING,
    phone STRING,
    registration_date STRING
);

INSERT INTO dataset.raw_customers (customer_id, customer_name, phone, registration_date)
VALUES
    ('C100', 'Dmytro', '+38(050)123-45-67', '2023-09-01'),
    ('C101', 'Olena', '097 555 44 33', '2023-09-02'),
    ('C102', 'Andrii', 'Tel: 0631112233', '2023-09-03'),
    ('C100', 'Dmytro', '+38(050)123-45-67', '2023-09-01'),
    ('C103', 'Sofia', NULL, '2023-09-05'),
    ('C104', 'Max', '380440000000', NULL);


-- orders

CREATE OR REPLACE TABLE dataset.raw_orders (
    order_id STRING,
    order_date STRING,
    customer_id STRING,
    staff_id STRING,
    product_id STRING,
    quantity STRING 
);

INSERT INTO dataset.raw_orders (order_id, order_date, customer_id, staff_id, product_id, quantity)
VALUES
    ('1001', '2023-10-01', 'C100', 'S01', '1', '1'),
    ('#1002', '2023-10-01', 'C101', 'S02', '2', '2'),
    ('Ord-1003', '2023-10-01', 'C102', 'S01', '4', '1 pc'),
    ('1001', '2023-10-01', 'C100', 'S01', '1', '1'),
    ('1004', '2023-10-02', 'C102', NULL, '3', '1');
```

## Data lineage

<img width="1606" height="485" alt="image" src="https://github.com/user-attachments/assets/493d929d-af93-4b12-9d74-394b8597cadd" />

## Layers

## Model type
<img width="798" height="638" alt="image" src="https://github.com/user-attachments/assets/f391df5a-a880-4b80-bcfb-2ca5e6a94b10" />

## Fact table

## Dimensions
