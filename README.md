-- Project: Customer Discount Database Logic
-- Goal: Querying customer data to identify who gets a discount

-- Creating a sample table (Imagining a real company database)
CREATE TABLE Customers (
    CustomerID INT,
    Name VARCHAR(50),
    TotalSpend DECIMAL(10, 2)
);

-- Inserting some data
INSERT INTO Customers VALUES (1, 'Adiba', 650.00);
INSERT INTO Customers VALUES (2, 'Reya', 120.50);
INSERT INTO Customers VALUES (3, 'Sadia', 350.00);

-- The Magic Query: Deciding Discount Status
SELECT Name, TotalSpend,
    CASE 
        WHEN TotalSpend >= 500 THEN '20% VIP Discount'
        WHEN TotalSpend >= 200 THEN '10% Gold Discount'
        ELSE 'No Discount'
    END AS DiscountStatus
FROM Customers;
