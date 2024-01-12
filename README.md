-- Create gift_recipients table
CREATE TABLE gift_recipients (
    recipient_id INT PRIMARY KEY,
    recipient_name VARCHAR(255),
    recipient_address VARCHAR(255),
    -- Add other relevant columns as needed
);

-- Create gifts table
CREATE TABLE gifts (
    gift_id INT PRIMARY KEY,
    gift_name VARCHAR(255),
    gift_category VARCHAR(50),
    -- Add other relevant columns as needed
);

-- Add sample data to gift_recipients table
INSERT INTO gift_recipients VALUES
(1, 'John Doe', '123 Main St'),
(2, 'Jane Smith', '456 Oak Ave'),
(3, 'Bob Johnson', '789 Elm Blvd'),
(4, 'Alice Brown', '321 Pine Rd'),
(5, 'Charlie Wilson', '654 Cedar Ln');

-- Add sample data to gifts table
INSERT INTO gifts VALUES
(101, 'Toy Robot', 'Toys'),
(102, 'Book Set', 'Books'),
(103, 'Perfume Set', 'Beauty'),
(104, 'Tool Kit', 'Tools'),
(105, 'Chocolates', 'Sweets');

 ## Left Outer Join:
SELECT
    gift_recipients.recipient_id,
    gift_recipients.recipient_name,
    gifts.gift_id,
    gifts.gift_name
FROM
    gift_recipients
LEFT OUTER JOIN
    gifts ON gift_recipients.recipient_id = gifts.recipient_id;

## Right Outer Join:
-- Display list of all gifts and the recipients for each gift
SELECT
    gift_recipients.recipient_id,
    gift_recipients.recipient_name,
    gifts.gift_id,
    gifts.gift_name
FROM
    gift_recipients
RIGHT OUTER JOIN
    gifts ON gift_recipients.recipient_id = gifts.recipient_id;

Full Join:
-- Get a comprehensive list of both gift recipients and gifts
SELECT
    gift_recipients.recipient_id,
    gift_recipients.recipient_name,
    gifts.gift_id,
    gifts.gift_name
FROM
    gift_recipients
FULL OUTER JOIN
    gifts ON gift_recipients.recipient_id = gifts.recipient_id;


# Instructions:

## Create Tables:

## Create two tables: gift_recipients and gifts.
The gift_recipients table should include columns such as recipient_id, recipient_name, and any other relevant information.
The gifts table should include columns like gift_id, gift_name, and gift_category.
Add Data:

Add at least five rows of sample data to each table. Ensure that there is a common column (e.g., recipient_id or gift_id) that can be used for joining.
## Left Outer Join:

Write a query using Left Outer Join to retrieve a list of all gift recipients and the gifts they are receiving for Christmas. Include recipients who are not receiving any gifts.
Provide a brief explanation of the results obtained from the query.
## Right Outer Join:

Write a query using Right Outer Join to display a list of all gifts and the recipients for each gift. Include gifts that have no assigned recipients.
Explain the results obtained from the query.
## Full Join:

Write a query using Full Join to get a comprehensive list of both gift recipients and gifts. Include recipients without gifts and gifts without assigned recipients.
Discuss the outcomes of the query and when such results might be useful in a Christmas context.


