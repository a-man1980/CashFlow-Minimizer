# CashFlow-Minimizer

A React application to help users visualize and minimize cash flow among multiple transactions.

---

## Introduction

The **CashFlow-Minimizer** is an intuitive solution designed to optimize the settlement of debts among a group of individuals or entities. By minimizing the total cash flow required for settlements, the application streamlines the debt resolution process efficiently. Built using React, this application offers an easy-to-use interface and employs advanced algorithms to ensure a smooth and accurate calculation of transactions.

### Problem Statement
Imagine a scenario where a group of friends, say **Aman**, **Ashish**, and **Pratyai**, share expenses during a trip. At the end of the trip, there is a need to settle debts so that everyone has either given or received the exact amount they owe. However, with multiple transactions involved, manually calculating who owes whom and how much can be tedious and error-prone. 

The CashFlow-Minimizer solves this problem by:
- Automatically calculating net balances for each individual.
- Categorizing participants into creditors and debtors.
- Minimizing the total number of transactions required for settlement.

---

## How Does It Work?

The CashFlow-Minimizer follows a systematic approach to resolve debts:

1. **Input Transactions:**
   Users input all transactions among the group. For instance, if **Aman pays ₹100 to Pratyai**, this transaction is recorded, and their balances are updated accordingly.

2. **Calculate Net Balances:**
   The application calculates each individual’s net balance by summing up their credits and debits:
   - **Credit:** A person’s net balance is **positive** if they are owed money.
   - **Debit:** A person’s net balance is **negative** if they owe money.

   For example:
   - If **Ashish pays ₹50 to Aman**, Ashish’s balance becomes **-50** (debtor), and Aman’s balance becomes **+50** (creditor).
   - If **Pratyai pays ₹100 to Aman**, Pratyai’s balance becomes **-100**, while Aman’s balance increases to **+150**.

3. **Categorize Participants:**
   Based on net balances, participants are divided into two groups:
   - **Creditors**: Those who are owed money.
   - **Debtors**: Those who owe money.

   Individuals with a zero balance are considered settled and excluded from further calculations.

4. **Optimize Transactions:**
   The application uses a **Max Heap** data structure to efficiently settle debts:
   - Identify the participant with the **largest credit** (e.g., Aman) and the one with the **largest debit** (e.g., Pratyai).
   - Settle the smaller of the two balances. For instance, if Aman is owed ₹150 and Pratyai owes ₹100, Pratyai pays Aman ₹100, leaving Aman with a balance of ₹50 and Pratyai with a balance of 0.
   - Repeat this process until all participants have a net balance of zero.

5. **Visualize Settlements:**
   The optimized transactions are displayed in a clear and concise manner, showing who pays whom and how much. This ensures transparency and simplicity in the settlement process.

---

## Example Walkthrough

Consider a group of three friends: **Aman**, **Ashish**, and **Pratyai**.

1. **Initial Transactions:**
   - Aman pays Pratyai ₹200.
   - Ashish pays Aman ₹100.
   - Pratyai pays Ashish ₹50.

2. **Net Balances:**
   - Aman: ₹100 (creditor)
   - Ashish: ₹50 (debtor)
   - Pratyai: ₹100 (debtor)

3. **Settlement Process:**
   - Pratyai (₹100 debtor) pays Aman (₹100 creditor): Pratyai’s balance becomes 0, Aman’s balance becomes 0.
   - Ashish (₹50 debtor) pays Pratyai (₹50 creditor): Ashish’s balance becomes 0, Pratyai’s balance becomes 0.

   Final Outcome: All balances are settled with only two transactions.

---

## Key Features

- **Algorithmic Efficiency:**
  Uses a **greedy algorithm** with a **Max Heap** for optimizing transactions, ensuring minimal cash flow and fewer transactions.

- **Interactive UI:**
  Built with React, the application provides a user-friendly interface for inputting transactions and visualizing optimized results.

- **Real-World Applicability:**
  Perfect for resolving group expenses such as trips, office events, or shared household costs.

---

## Installation Guide

Follow these steps to run the application locally:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/a-man1980/CashFlow-Minimizer
   cd CashFlow-Minimizer
   ```

2. **Install Dependencies:**
   Ensure Node.js is installed, then run:
   ```bash
   npm install
   ```

3. **Start the Application:**
   ```bash
   npm start
   ```

4. **Access the Application:**
   Open your browser and go to `http://localhost:3000`.

---

## Conclusion

The **CashFlow-Minimizer** simplifies complex group settlements by providing an optimized, algorithm-driven solution. Whether it’s managing trip expenses or resolving shared costs, this application ensures fairness and efficiency with minimal effort. With its intuitive design and powerful algorithms, it’s an indispensable tool for anyone looking to streamline financial settlements.

