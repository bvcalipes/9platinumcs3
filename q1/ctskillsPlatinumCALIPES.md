# Annex A: Computational Thinking Exercise
**Scenario:** Smart School Canteen Queue  
**Section:** Platinum  
**Name:** Bashaier V. Calipes  
**Date:** Aug 17, 2026

---

## Step 2: Identify Sub-Problems
1. **Decision Delay:** Students take too long to decide what to order while standing at the counter.
2. **Manual Checkout:** The cashier manually calculates order totals and change, slowing down transactions.
3. **Inventory Tracking:** There is no real-time system to monitor food item stock levels as items sell out.

---

## Step 3: Define Computational Thinking Approaches

| Sub-Problem | CT Skill | Example Solution |
| :--- | :--- | :--- |
| **1. Decision Delay** | **Abstraction** | Display digital menu boards in the waiting line showing only essential details (Item Name, Price, Stock Status) so students choose before reaching the counter. |
| **2. Manual Checkout** | **Algorithm Design** | Implement an automated POS (Point of Sale) cashier program that calculates order totals, applies discounts, and computes change instantly. |
| **3. Inventory Tracking** | **Pattern Recognition & Automation** | Create an automated inventory tracker that deducts item quantities per sale and alerts staff when stock falls below a set threshold. |

---

## Step 4: Pseudocode for Sub-Problem 2 (Automated Cashier System)

```text
START
  Set TotalCost = 0
  
  LOOP until ordering is complete:
    INPUT FoodItem, Quantity
    FETCH Price of FoodItem
    ItemSubtotal = Price * Quantity
    TotalCost = TotalCost + ItemSubtotal
  END LOOP

  DISPLAY TotalCost

  INPUT AmountPaid

  IF AmountPaid >= TotalCost THEN
    Change = AmountPaid - TotalCost
    DISPLAY "Transaction Successful"
    DISPLAY "Change: ", Change
    UPDATE Inventory Stock
  ELSE
    DISPLAY "Insufficient Payment. Please provide additional cash."
  END IF
END