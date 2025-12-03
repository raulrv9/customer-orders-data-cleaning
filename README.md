# 📊 Customer Orders Data Cleaning Project

**Tools:** Excel (TRIM, PROPER, SUBSTITUTE, VALUE, Text to Columns, Remove Duplicates, formatting)

## 📌 Project Overview  

This project demonstrates my ability to clean and prepare messy real-world data.  
The dataset contained inconsistent names, cities, dates, numeric values, and broken email formats.  
I applied standard data-cleaning techniques in Excel to produce a structured, analysis-ready dataset.

---

## 🧹 Raw Data Issues  

The original dataset (in `raw_customer_orders.xlsx`) contained multiple types of problems:

### 1. Customer Names  
- Inconsistent capitalization: `JOSE   albeRt`, `CARLOS    JUAREZ`  
- Extra spaces  
- Mixed casing and hyphen use (`ana-maria`, `Jose   ALBERT`)  

### 2. City Values  
- Case inconsistencies: `houSton`, `san antonio`, `houston`  
- Leading/trailing spaces  

### 3. Order Dates  
- Multiple date formats mixed in one column:  
  - `01/5/24`  
  - `1/6/2024`  
  - `1/07/2024`  
  - `2024/01/08`  
  - `january 9 2024`  
- Some values stored as text instead of true date values  

### 4. Amounts  
- `$` symbols included  
- Spaces around values  
- Mixed decimal formats (`$75.5` vs `$120.00`)  
- Values stored as text  

### 5. Email Addresses  
- Double `@` symbols: `@@`  
- Double dots: `..`  
- Comma instead of dot: `outlook,com`  
- Missing `.com` in domains: `gmailcom`  
- Extra spaces  

---

## 🛠 Cleaning Techniques Used  

All cleaning was performed in Excel using:

- `TRIM()` to remove extra spaces  
- `PROPER()` to standardize capitalization of names and cities  
- `LOWER()` to normalize email case  
- `SUBSTITUTE()` to fix invalid characters (`..`, `@@`, `,com`)  
- `VALUE()` and `Text to Columns` to convert text dates/amounts to numeric and date types  
- Date formatting to standardize dates as `YYYY-MM-DD`  
- **Remove Duplicates** to check for duplicate records  

Examples of formulas used:

```excel
=PROPER(TRIM(A2))        // Clean and standardize names
=PROPER(TRIM(B2))        // Clean and standardize cities
=VALUE(SUBSTITUTE(TRIM(D2),"$",""))   // Clean and convert amounts
=LOWER(TRIM(SUBSTITUTE(SUBSTITUTE(SUBSTITUTE(E2,",","."),"..","."),"@@","@")))
