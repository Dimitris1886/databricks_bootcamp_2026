# Customer Dimension – Silver Layer Plan

## 1. Basic Transformations

Status: ✅ Done

* [x] Read Bronze table
* [x] Trim string columns
* [x] Rename columns
* [x] Cast data types
* [x] Standardize categorical columns

---

## 2. Business Key Enforcement

### 2.1 Validate Not Null

Status: ✅ Done

* [x] Reject NULL customer_key
* [x] Reject empty "" customer_key
* [x] Write invalid rows to quarantine (MERGE)
* [x] Return clean dataframe

---

### 2.2 Validate Format

Status: 🔄 In Progress

* [ ] Validate allowed prefix
* [ ] Validate expected length
* [ ] Validate numeric suffix
* [ ] Write invalid rows to quarantine (MERGE)
* [ ] Return clean dataframe

---

## 3. Duplicate Resolution

Status: ⬜ Not Started

* [ ] Detect duplicate customer_key
* [ ] Create completeness_score
* [ ] Rank using window
* [ ] Keep best record
* [ ] Quarantine duplicate records (MERGE)
* [ ] Return clean dataframe

---

## 4. Final Validation

Status: ⬜ Not Started

* [ ] Ensure no duplicate keys remain
* [ ] Fail pipeline if duplicates exist

---

## 5. Write Silver Table

Status: ⬜ Not Finalized

* [ ] Write clean data to workspace.silver.crm_customers
* [ ] Use overwrite mode (current dimension)

---

# Current Focus

➡ Next task: Implement `validate_business_key_format()`

