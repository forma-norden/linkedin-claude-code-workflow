# linkedin-ad-bidding-optimization

Use this skill to configure LinkedIn Ads bidding strategies, allocate budgets,
and optimize cost efficiency.

## Bidding Strategies

### Manual Bidding (Recommended Default)
Set maximum CPC/CPM directly. Full control over costs.
Use when: starting new campaigns, budget-constrained, testing creative.

### Maximum Delivery (Auto-Bid)
LinkedIn optimizes spend for maximum results.
Use when: you have proven creative and need to scale volume.

### Target Cost
LinkedIn targets a specific cost per result.
Use when: you have 2+ months of data and know your target CPL.

## Budget Allocation Framework

| Funnel Stage | % of Budget | Objective |
|-------------|-------------|-----------|
| Top of Funnel (awareness) | 30% | Brand awareness, reach |
| Mid Funnel (consideration) | 20% | Website visits, engagement |
| Bottom Funnel (conversion) | 50% | Lead gen, conversions |

### ABM Budget Split

| Component | % of ABM Budget |
|-----------|----------------|
| Account warming | 40% |
| Direct conversion | 30% |
| Retargeting | 30% |

## Cost Benchmarks

| Metric | Range | Context |
|--------|-------|---------|
| CPC (manual bid) | $5-15 | Varies by audience size and competition |
| CPM | $30-80 | Varies by geo and targeting specificity |
| Cost per Lead (form) | $30-100 | Depends on offer and targeting |
| Cost per MQL | $100-300 | After lead qualification |

## Optimization Checklist

### Week 1-2:
- Set manual bids at market rate
- Daily budget = minimum $50/campaign
- Monitor delivery rate (should be 80%+ of budget)

### Week 3-4:
- Identify top-performing audiences and creatives
- Shift budget toward best performers
- Increase bids on low-delivery campaigns by 10-20%

### Month 2+:
- A/B test bid strategies (manual vs target cost)
- Scale winners, pause underperformers
- Adjust budgets based on pipeline contribution

## Execution Sequence

1. Select bidding strategy based on campaign maturity.
2. Set initial budgets by funnel stage.
3. Configure daily budget minimums.
4. Monitor delivery and cost metrics weekly.
5. Optimize bids every 2 weeks based on performance data.

## Output Contract

Return:

- bidding strategy recommendation with rationale
- budget allocation by campaign/funnel stage
- initial bid settings by format and audience
- optimization schedule with adjustment criteria
- cost projections for 30/60/90 days
