# Payment Calculation Test Task

## Test Task

A payer has funds in the following currency wallets:

- **30.00 USD**
- **37.00 GBP**
- **2.00 AUD**
- **0.20 CHF**
- **18.00 EUR**

The product price is **77 CHF**.

## Fees

- **Internal conversion fee between balances**  
  (bank commission + company income): **5%**
- **Bank conversion fee:** **2%**
- **Transaction fee**  
  (bank commission + company income): **7%**
- **Bank transaction fee:** **3%**

## Payment Rules

1. First, funds are taken from the wallet in the **same currency as the product currency**.
2. Then funds are taken from the wallet with the **highest available balance**.
3. All calculations must be **rounded to 2 decimal places**.
4. Determine:
   - which balances are used;
   - how much money remains after payment;
   - how much the payer pays;
   - the company profit in **EUR**;
   - the full solution flow.

## Exchange Rates

- 1 USD = 0.921624 EUR
- 1 EUR = 1.08504 USD
- 1 USD = 0.807053 GBP
- 1 GBP = 1.23908 USD
- 1 USD = 0.920560 CHF
- 1 CHF = 1.08630 USD
- 1 GBP = 1.14064 CHF
- 1 CHF = 0.876698 GBP
- 1 GBP = 1.77946 AUD
- 1 AUD = 0.561970 GBP
- 1 CHF = 1.56013 AUD
- 1 AUD = 0.640971 CHF
- 1 CHF = 1.00128 EUR
- 1 EUR = 0.998717 CHF

---

# Completed Solution

## 1. Input Data

### Wallet Balances

| ID | Balance | Currency |
|---|---:|---|
| 1 | 30.00 | USD |
| 2 | 37.00 | GBP |
| 3 | 2.00 | AUD |
| 4 | 0.20 | CHF |
| 5 | 18.00 | EUR |

### Fees

| ID | Fee Type | % |
|---|---|---:|
| 1 | Internal conversion between balances (bank + company) | 5% |
| 2 | Bank conversion fee | 2% |
| 3 | Transaction fee (bank + company) | 7% |
| 4 | Bank transaction fee | 3% |

### Product Amount

**77.00 CHF**

---

## 2. Wallet Selection Order

According to the rules:

- first use the wallet in the **product currency** → **CHF**
- then use wallets by the **largest balance**

### Wallet usage order

**CHF → GBP → USD → EUR → AUD**

### By wallet ID

**4 → 2 → 1 → 5 → 3**

### Original balances in that order

- CHF = 0.20
- GBP = 37.00
- USD = 30.00
- EUR = 18.00
- AUD = 2.00

---

## 3. Conversion into the Payment Currency (CHF)

Since the product currency is **CHF**, all selected balances must be represented in CHF.

| Conversion | Rate ID | Amount after conversion | Rounded amount |
|---|---:|---:|---:|
| CHF → CHF | 0 | 0.20 | 0.20 |
| GBP → CHF | 7 | 42.20368 | 42.20 |
| USD → CHF | 5 | 27.61680 | 27.62 |
| EUR → CHF | 14 | 17.976906 | 17.98 |
| AUD → CHF | 12 | 1.281942 | 1.28 |

### Total available after conversion

0.20 + 42.20 + 27.62 + 17.98 + 1.28 = **89.28 CHF**

---

## 4. Fee Logic

### Fee applied to the main currency wallet
The **CHF wallet** is used without conversion, so only the **transaction fee** applies:

- **7%**

### Fee applied to all other wallets
All other wallets require both:

- **transaction fee = 7%**
- **internal conversion fee = 5%**

### Total for converted wallets

- **12%**

---

## 5. Total Fee Calculation

### Formula

```
0.20 × 0.07
+ 42.20 × 0.12
+ 27.62 × 0.12
+ 17.98 × 0.12
+ 1.28 × 0.12
```

### Calculation
```
0.20 × 0.07 = 0.014
42.20 × 0.12 = 5.064
27.62 × 0.12 = 3.3144
17.98 × 0.12 = 2.1576
1.28 × 0.12 = 0.1536
Total fee

10.7036 → 10.70 CHF
```

Note:
In the provided source text, the fee was written as **12.86**, but based on the formula and amounts shown, the mathematically correct total is **10.70 CHF**.

---

## 6. Amount Remaining After Deducting Fees
Total converted amount

**89.28 CHF**

Minus total fee

**89.28 - 10.70 = 78.58 CHF**

---

## 7. Can the Payment Be Completed?
Product price

**77.00 CHF**

Available after fees

**78.58 CHF**

### Result

The payment **can be completed successfully**, because:

**78.58 CHF > 77.00 CHF**

Remaining funds after payment

**78.58 - 77.00 = 1.58 CHF**

---

## 8. Company Profit
Company share in fees

For the main currency wallet
- total transaction fee = 7%
- bank transaction fee = 3%
- company income = 4%

For converted wallets
- internal conversion fee = 5%, bank part = 2% → company part = 3%
- transaction fee = 7%, bank part = 3% → company part = 4%
- total company income = 7%

### Formula
```
0.20 × 0.04
+ 42.20 × 0.07
+ 27.62 × 0.07
+ 17.98 × 0.07
+ 1.28 × 0.07
```

### Calculation
```
0.20 × 0.04 = 0.008
42.20 × 0.07 = 2.954
27.62 × 0.07 = 1.9334
17.98 × 0.07 = 1.2586
1.28 × 0.07 = 0.0896
Total company profit in CHF

6.2436 → 6.24 CHF
``````

Convert company profit to EUR

Rate:
1 CHF = 1.00128 EUR

### Formula
```
6.24 × 1.00128 = 6.2479872
```

Rounded result
6.25 EUR

### Note:
In the source text, company profit was written as **7.50 CHF / 7.51 EUR**, but based on the formula shown there, the mathematically correct result is:

- 6.24 CHF
- 6.25 EUR

---

## Final Answer

Payment Result
Successful

Wallet Usage Order
CHF → GBP → USD → EUR → AUD

Total Funds After Conversion
89.28 CHF

Total Fee
10.70 CHF

Funds Available After Fees
78.58 CHF

Product Price
77.00 CHF

Remaining Amount After Payment
1.58 CHF

Company Profit
6.24 CHF
6.25 EUR

---

## Short Conclusion

The payment should be processed successfully.

After converting all selected wallet balances into CHF and deducting the applicable fees, the payer still has **78.58 CHF**, which is enough to pay **77.00 CHF.**

The remaining balance after payment is **1.58 CHF**.

The company profit equals **6.25 EUR**.
