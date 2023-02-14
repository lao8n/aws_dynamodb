
Raw attributes
OrderId (only if Delivered), AccountId, Status, CreateTimestamp, ItemSKU

Partition key - sort key - attributes
Base = AccountID - Status:CreateTimestamp:ItemSKU - ItemSKU, Status, CreateTimestamp, OrderId
GSI = AccountID:ItemSKU - Status:CreateTimestamp - AccountId, ItemSKU, Status, CreateTimestamp

Base = AccountID - Status:CreateTimestamp:ItemSKU - ItemSKU, Status, CreateTimestamp, OrderId
GSI = ItemSKU - Status - AccountId, ItemSKU, Status, CreateTimestamp

View Active records by most recent
* accountId -> active -> create timestamp - sorted on starts with status + create timestamp
View Saved products by most recent
* accountId -> !active -> create timestamp - sorted on starts with status + create timestamp

View Purchased products by most recent
* GSI = AccountId - Status:OrderId
What item attribute scales in volume with higher access?
• Combination of User & ItemSKU
What is the natural organization for the related data items?
• 


AccountID:Status:CreateTimestamp ItemSKU

accountid - status
1 - 
2

