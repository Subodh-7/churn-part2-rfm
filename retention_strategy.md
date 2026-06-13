# Retention Strategy by Customer Segment — Part 2
**Snapshot:** 2025-09-30 | **Customers:** 2,400 | **Student:** Subodh Raut

## Segment Sizes & Definitions
| Segment | Rule | Count |
|---------|------|-------|
| Champions | R≥4, F≥4, M≥4 | 51 |
| Loyal | RFM score ≥10, R≥3 | 582 |
| At-Risk | R≤2 and F≥2 | 224 |
| Dormant | All others (low RFM) | 1,543 |

## Champions 🏆 (51)
**Who:** Most recent, frequent, high-spend buyers.
**Actions:** VIP tier, early access to new launches, referral program activation, personalised thank-you. No discounts needed.
**Avoid:** Generic promotions — degrades relationship.

## Loyal 💚 (582)
**Who:** Consistent buyers, often loyalty members, RFM ≥10.
**Actions:** Loyalty tier upgrade nudges, recommendations based on `preferred_category`, double-points bonus on next 2 orders.
**Avoid:** Treating like new customers.

## At-Risk 🔴 (224)
**Who:** Previously active, now quiet (recency >90d but had 2+ orders).
**Actions:**
- Day 1: Personalised win-back email, 15% off in preferred category
- Day 7: SMS with urgency
- Day 14: Free shipping/sample as final offer
- Check `manual_priority_bucket`="high" → escalate to personal outreach
- Resolve open tickets BEFORE promotional contact

## Dormant 😴 (1,543) — largest segment, split into:
**Sub-group A — New & Inactive:** signed up recently, never reordered → onboarding email + loyalty enrollment incentive
**Sub-group B — Long-term Dormant:** signed up >6mo ago, no activity → low-cost re-engagement only, suppress after 2 attempts

## Budget Allocation (₹1,00,000 example)
| Priority | Segment | Budget | Rationale |
|----------|---------|--------|-----------|
| 1 | At-Risk | ₹40,000 | Highest revenue at risk, recoverable |
| 2 | Dormant (new) | ₹25,000 | Cheap to re-engage |
| 3 | Loyal | ₹20,000 | Protect reliable base |
| 4 | Dormant (long-term) | ₹10,000 | Email only |
| 5 | Champions | ₹5,000 | VIP perks minimal cost |

## Key Principle
> Segment-specific communication beats blanket discounts. A 20% coupon to a Champion erodes margin; a generic email to an At-Risk customer with an unresolved complaint wastes the last chance to retain them.
