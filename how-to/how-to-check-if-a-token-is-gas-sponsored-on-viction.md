---
description: This guide will show you how to check if a token is gas sponsored on Viction
---

# How to check if a token is gas sponsored on Viction

### **Step 1: Check if the Token is in the Sponsor List** <a href="#step-1-check-if-the-token-is-in-the-sponsor-list" id="step-1-check-if-the-token-is-in-the-sponsor-list"></a>

* **Objective:** Verify if the token is eligible for gas sponsorship.
* **Function:** Use the `tokens` function from the [Issuer Contract](https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee#code).

**Steps:**

1. Call the `tokens` function with the token address or identifier.
2. If the token exists in the sponsor list, proceed to Step 2. Otherwise, it is **not sponsored**.

### **Step 2: Check Token Capacity** <a href="#step-2-check-token-capacity" id="step-2-check-token-capacity"></a>

* **Objective:** Determine if the token has remaining gas sponsorship capacity.
* **Function:** Use the `getTokenCapacity` function.

**Steps:**

1. Call `getTokenCapacity` with the token address or identifier.
2. Interpret the response:
   * **If > 0:** Token can sponsor gas.
   * **If = 0:** Token sponsorship is exhausted. Transactions will be failed.

#### **Key Functions:** <a href="#key-functions" id="key-functions"></a>

Simple flow:

1. Call `tokens` to check sponsorship eligibility.
2. If eligible, call `getTokenCapacity` to validate capacity:
   * 0: Sponsored.
   * \= 0: Not sponsored.
3. Cache results for faster future checks.
