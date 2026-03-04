# Week 2: Business Process Modeling (BPM) - MallMaster

## 1. Goal
The objective of this week is to visualize how the shopping mall's core business processes work and how the system automates these tasks.

---

## 2. Core Process: Product Sales Flow
This process describes the interaction between the Customer, Cashier/Store Manager, and the MallMaster System during a purchase.

### Process Steps:
1. **Inquiry:** Customer requests a specific product.
2. **System Search:** Cashier searches for the product in the system.
3. **Availability Check:**
   - If **In Stock**: Proceed to checkout.
   - If **Out of Stock**: Suggest alternative products or inform the customer.
4. **Validation:** System checks the product details (e.g., correct batch or brand if needed).
5. **Transaction:** Customer pays via Cash, Card, or Digital Wallet.
6. **Auto-Update:** System decrements the stock count and logs the transaction.
7. **Receipt:** System prints/generates a digital receipt.

---

## 3. Supplier to Inventory Flow Diagram
```mermaid
graph TD
    subgraph Supplier [Supplier / Yetkazib beruvchi]
        S1([Start: Delivery Arrives]) --> S2[Provide Invoice & Products]
    end

    subgraph Stock_Manager [Inventory Supervisor / Omborchi]
        S2 --> M1[Unpack & Inspect Products]
        M1 --> M2{Are Products Damaged?}
        M2 -- Yes --> M3[Return to Supplier]
        M2 -- No --> M4[Scan Barcodes into System]
        M5[Confirm Product Details & Stock] --> M6[Finalize Entry]
    end

    subgraph System_Lane [MallMaster System]
        M4 --> SY1[Search/Create Product Profile]
        SY1 --> M5
        M6 --> SY2[Increase Stock Quantity]
        SY2 --> SY3[Log Procurement Transaction]
        SY3 --> SY4([End: Inventory Updated])
    end

    style S1 fill:#a2fca2,stroke:#008000
    style SY4 fill:#fca2a2,stroke:#ff0000
    style M2 fill:#fff4dd,stroke:#d4a017
```

---

## 4. Customer Purchase Flow Diagram
```mermaid
graph TD
    %% Roles/Lanes definition
    subgraph Customer_Lane [Customer]
        A([Start: Needs Product]) --> B[Request Product]
        L[Make Payment] --> M([End: Receive Product & Receipt])
    end

    subgraph Cashier_Lane [Cashier / Store Manager]
        B --> C[Search Product in System]
        G[Inform: Out of Stock] --> N([End])
        K[Hand over Product] --> M
    end

    subgraph System_Lane [MallMaster System]
        C --> D{Is Product Available?}
        D -- No --> G
        D -- Yes --> E[Check Product Details]
        E --> F{Is it Correct/Valid?}
        F -- No --> G
        F -- Yes --> H[Display Price & Info]
        H --> L
        L --> I[Update Inventory -1]
        I --> J[Generate Digital Receipt]
        J --> K
    end

    %% Styling
    style A fill:#a2fca2,stroke:#008000
    style N fill:#fca2a2,stroke:#ff0000
    style M fill:#fca2a2,stroke:#ff0000
    style D fill:#fff4dd,stroke:#d4a017
    style F fill:#fff4dd,stroke:#d4a017

    subgraph Mall_System_Process
        direction TB
        subgraph Customer_Lane [CUSTOMER]
            A[Request Product] --> B[Provide Payment]
            G[Receive Product & Receipt]
        end

        subgraph Cashier_Lane [CASHIER]
            B1[Check Stock & Product Details] --> C{Is Available?}
            C -- No --> D[Inform Customer]
            C -- Yes --> E[Process Transaction]
        end

        subgraph Database_Lane [SYSTEM / DATABASE]
            E --> F[Update Inventory & Save Sale]
            F --> G
        end
    end

    %% Styles
    style Customer_Lane fill:#e3f2fd,stroke:#0d47a1
    style Cashier_Lane fill:#fff9c4,stroke:#fbc02d
    style Database_Lane fill:#f1f8e9,stroke:#388e3c
```
