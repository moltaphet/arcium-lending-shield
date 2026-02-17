# 🛡️ Arcium Lending Shield

**Confidential Borrowing & Privacy-Preserving Liquidation Engine**

Arcium Lending Shield is a professional-grade DeFi primitive designed to eliminate the transparency risks of traditional lending protocols. By leveraging **Multi-Party Computation (MPC)** via the Arcium Network, this engine ensures that sensitive financial data—such as collateral amounts, credit scores, and exact liquidation thresholds—never leak to the public mempool or predatory bots.

---

## 🔒 The Problem: Liquidation Hunting
In transparent DeFi (like Aave or Solend), user health factors are public. This creates an incentive for **Predatory Liquidation Bots** to:
1. Identify positions near the liquidation threshold.
2. Manipulate oracle prices or congest the network to trigger forced liquidations.
3. Profit at the expense of the user's privacy and assets.

**Lending Shield solves this by moving the logic into a "Black Box" execution layer.**

---

## ✨ Key Features
- **Shielded Health Factors**: All debt-to-collateral ratios are calculated in an encrypted state. 
- **Confidential Credit Multiplier**: Users get a borrowing power boost based on a private credit score that is never revealed to the lender.
- **Bot Resistance**: Since the liquidation trigger is private, bots cannot "snipe" vulnerable positions.
- **MPC Consensus**: Liquidation signals are only broadcasted when the MPC cluster reaches consensus that a breach has occurred.

---

## ⚙️ Technical Architecture

The engine evaluates borrowing capacity using a multi-factor confidential formula:

$$Capacity = \frac{Collateral_{hidden} \times LTV_{limit}}{100} + (CreditScore_{hidden} \times 2)$$

The protocol only returns a boolean `is_liquidatable`, keeping the underlying variables ($Collateral$, $Debt$, $Score$) completely private.

---

## 🛠 Installation & Usage

### Prerequisites
- Rust and Cargo installed.
- Access to Arcium CLI (for deployment simulation).

### Build
```bash
cargo build

```

### Run Simulation Tests

The project includes a robust testing suite to verify confidential logic across different risk scenarios:

```bash
cargo test -- --nocapture

```

---

## 🧪 Verified Scenarios

The following logic is covered in our test suite:

* **Healthy Position**: Verifies that users with high credit scores gain extra borrowing capacity.
* **Liquidation Trigger**: Confirms that the system generates a confidential alert when debt exceeds the shielded capacity.
* **Boundary Conditions**: Ensures fair execution exactly at the liquidation margin.

---

## 🤝 Contributing

This project is part of the Arcium Developer RTG. Feel free to explore the code and suggest improvements to the confidential execution logic.

**Developed with ❤️ for the Arcium Ecosystem.**