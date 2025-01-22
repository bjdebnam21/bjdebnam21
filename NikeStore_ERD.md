```mermaid

erDiagram
    CUSTOMER || --}| PRODUCT : buys
    PRODUCT || -- || INVENTORY : "is in"
    PRODUCT {
        integer productID PK
        string  productName
        string  productDesc
    } 
    CUSTOMER {
        integer custNumber PK
        string firstname
        string lastname
  }
    SALE || -- || CUSTOMER : "associated with"
  SALE {
        integer saleID  PK
        integer custNumber FK
        string  transType
        integer amount
  }
  INVENTORY {
        integer  inventoryID PK
        integer productID FK
        integer quantity
  }
  SALE ||--|{ PRODUCT : contains

  ```


  ## Documentation
  > This diagram represents the relationships between the tables needed for the Nike Store to track products, customers, sales, and inventory.
  * Customer to Product - To be an actual customer, a customer must have purchased at least one product.  Storing customer information and 
  the products they have purchased will help the store identify customer preferences and market to their customers accordingly. For example, the store may
  send out special advertising campaign based on the customer purchases. 
  * Product to Inventory - Each product will be found in the inventory tables.  The products must be in the inventory table to track the amount of products available to sell. Inventory information will help the owner determine when he/she needs to buy more products.
  * Sale to Customer - Each sale is associated with a customer.
  * Sale to Product - Each sale consists of one or more products sold.
