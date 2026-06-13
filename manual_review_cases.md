# Manual Review — 10 Ambiguous Customer Cases — Part 2
**Real customer IDs from rfm_modeling_snapshot.csv**

---

### CUST00871 | At-Risk | Actual: Churned ✓
R=2,F=2,M=4 | Recency=122d, Freq=3, Spend=₹1,704, Returns=0%, Tickets=2, Sessions=3, No loyalty
**Analysis:** 3 orders historically + 2 tickets — investigate ticket content before win-back. At-Risk correct; recommend service-recovery framing in outreach.

### CUST01844 | At-Risk | Actual: Retained ✗ (false alarm)
R=2,F=2,M=5 | Recency=125d, Freq=2, Spend=₹1,934, Sessions=8, Loyalty=Silver
**Analysis:** Despite 125d gap, 8 sessions in 30d shows engagement — customer returned. **Lesson: recency alone misclassifies slow/seasonal buyers with high digital activity.**

### CUST01005 | Dormant | Actual: Churned ✓
R=2,F=1,M=4 | Recency=144d, Freq=1, Spend=₹1,330, Tickets=1, No loyalty
**Analysis:** One-and-done customer, 144d silent, 1 ticket may have been a friction point. Dormant correct — low-cost re-engagement only.

### CUST02103 | Dormant | Actual: Churned ✓
R=4,F=2,M=3 | Recency=44d (very recent!), Freq=2, Spend=₹1,052, Sessions=0, Loyalty=Platinum
**Analysis:** Paradox — recent order (44d) but ZERO sessions and still churned. High recency doesn't guarantee retention when monetary/frequency are low. **Model edge case.**

### CUST02384 | Dormant | Actual: Retained ✗ (false alarm)
R=3,F=2,M=4 | Recency=68d, Freq=2, Spend=₹1,501, Return rate=33%, Sessions=7, Loyalty=Silver
**Analysis:** Retained despite 33% return rate — return handled well. Should be borderline Loyal, not Dormant. **Recommend loyalty programme push — convertible customer.**

### CUST00428 | Dormant | Actual: Retained ✗
R=3,F=2,M=3 | Recency=74d, Freq=2, Spend=₹811, Sessions=1, No loyalty
**Analysis:** Clean history, low spend. Needs spend-activation (bundle/cross-sell), not churn risk treatment.

### CUST00834 | Dormant | Actual: Retained ✗
R=5,F=1,M=3 | Recency=2d (today!), Freq=1, Spend=₹971, Sessions=6, No loyalty
**Analysis:** Very recent activity but Dormant due to low frequency — this is a **NEW customer**, not Dormant. Onboarding + loyalty enrollment is the right action, not churn intervention.

### CUST00851 | Dormant | Actual: Retained ✗
R=5,F=1,M=3 | Recency=0d, Freq=1, Spend=₹823, Return rate=50%, Sessions=8, Loyalty=Gold
**Analysis:** Ordered today but 50% return rate + open ticket. **High-priority manual review — do NOT send promotional message until support issue is resolved.**

### CUST00219 | At-Risk | Actual: Churned ✓
R=1,F=2,M=4 | Recency=154d, Freq=2, Spend=₹1,225, Sessions=3, Loyalty=Silver
**Analysis:** 154d — borderline Dormant. At-Risk correct for final win-back attempt; if fails, move to Dormant suppression.

### CUST00427 | Dormant | Actual: Churned ✓
R=5,F=2,M=1 | Recency=1d, Freq=2, Spend=₹332, Return rate=50%, Sessions=4, Loyalty=Silver
**Analysis:** Active yesterday but predicted AND actually churned. Extremely low spend (₹332/2 orders) + 50% returns shows fundamental product-customer mismatch. Investigate which category was purchased/returned — likely wrong recommendation at acquisition.

---

## Summary
| Finding | Count |
|---------|-------|
| Segment assignment correct | 7/10 |
| Should reclassify | 2/10 (CUST02384→Loyal, CUST00834→New Customer) |
| Special handling (don't contact) | 1/10 (CUST00851 — open complaint) |

**Key insight:** Return rate, ticket status, and session activity override RFM scores in edge cases. A customer with recency=0 but 50% returns and an open ticket should never receive a promotional message based on RFM alone.
