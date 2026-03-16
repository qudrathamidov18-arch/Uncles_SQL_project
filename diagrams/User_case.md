# Shopping Mall Management System

## Use Case Diagram

```mermaid
flowchart LR

Customer((Customer))
Cashier((Cashier))
Admin((Admin))
InventoryManager((Inventory Manager))

BrowseProducts([Browse Products])
SearchProducts([Search Products])
PurchaseItems([Purchase Items])
ProcessPayment([Process Payment])
ManageInventory([Manage Inventory])
TrackStock([Track Stock])
GenerateReports([Generate Sales Reports])
ManageEmployees([Manage Employees])

Customer --> BrowseProducts
Customer --> SearchProducts
Customer --> PurchaseItems

Cashier --> ProcessPayment
Cashier --> SearchProducts

InventoryManager --> ManageInventory
InventoryManager --> TrackStock

Admin --> GenerateReports
Admin --> ManageEmployees
Admin --> ManageInventory
```
