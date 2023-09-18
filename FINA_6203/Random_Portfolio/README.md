# Reasons for Randomly Choosing Stocks for a Long-Term Portfolio

## Theoretical Reasons:

### 1. Efficient Market Hypothesis (EMH):
- All known information is already priced into stocks, implying no one has an advantage when picking stocks.
- Randomly selecting stocks might be as effective as any well-researched strategy.

### 2. Random Walk Theory:
- Stock prices are unpredictable and follow a random path.
- Future stock movements are independent of past patterns, making random choices potentially successful.

### 3. Diversification:
- Random selection can lead to an unplanned diversified portfolio.
- Reduces risk from a single stock or sector underperforming.

### 4. Overcoming Analysis Paralysis:
- Bypass the paralysis from over-analyzing data with random selections.

## Practical Reasons:

### 1. Cost-Effective:
- Reduces costs associated with research, tools, or advisory fees.

### 2. Avoiding Emotional Bias:
- Emotions can lead to suboptimal stock choices.
- Random selection minimizes emotional decision-making.

### 3. Simplicity:
- Random stock selection combined with a long-term strategy is straightforward.

### 4. Performance Benchmarks:
- Compare an actively managed portfolio against a random selection to measure effectiveness.

### 5. Novelty and Learning:
- Learn about new companies or sectors.

### 6. Avoiding Common Pitfalls:
- Avoid the pitfalls of herd behavior in stock choices.

## Reasons for Not Randomly Choosing Stocks for a Long-Term Portfolio (or mixing a random approach with vetted equties)

### Corporate Social Responsibility (CSR) & Environment, Social, and Governance (ESG) Concerns:

### 1. Ethical Investing:
- **Importance of Values**: Investors may want to ensure their investments align with their personal or institutional values. Blindly picking stocks doesn't allow for this alignment.
- **Avoiding Harmful Industries**: Some investors may want to avoid companies involved in industries like tobacco, firearms, or fossil fuels due to ethical concerns.

### 2. Long-Term Value Creation:
- **Sustainable Practices**: Companies committed to sustainable practices are often seen as less risky in the long term.
- **Better Long-Term Returns**: Research has indicated that firms with strong CSR or ESG scores might outperform in the long run.

### 3. Stakeholder Relationships:
- **Public Image & Reputation**: Companies that prioritize CSR often have better public relations, which can translate to brand loyalty and trust.
- **Employee Morale & Retention**: Ethical companies often have higher employee satisfaction rates, leading to reduced turnover and improved productivity.

### 4. Regulatory & Legal Considerations:
- **Avoiding Regulatory Scrutiny**: Companies that disregard ESG considerations might face stricter regulatory scrutiny, leading to potential fines or legal troubles.
- **Meeting Investment Mandates**: Certain institutional investors have mandates to invest only in companies meeting specific ESG criteria.

### 5. Vetting for Ethical Companies:
- **In-Depth Analysis Required**: Vetting companies for ethical practices requires thorough analysis and isn't feasible with random selection.
- **Meeting Moral Obligations**: Investors may feel a moral obligation to invest in companies that contribute positively to society.


## Randomly Picking Stocks
### Pseudocode:

1. Fetch the latest NASDAQ and Non-NASDAQ (NYSE/AMEX) lists from the NASDAQ FTP server.
2. Annotate the files for common stocks.
3. Randomly select 'n' stocks:
   - 50% chance from NASDAQ
   - 50% chance from Non-NASDAQ
   - Ensure they are common stocks, not ETFs
   - Ticker symbols between 1-5 characters long
4. Use the Yahoo finance API to gather relevant financial information.
5. Fill in missing data using search tools like Google and ChatGPT.

**Complete code and data** can be found at [this GitHub repository](https://github.com/nikbearbrown/Computational_Finance_with_Python/tree/main/FINA_6203/Random_Portfolio).
