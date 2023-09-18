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


## Getting the data

NASDAQ makes this information available via FTP and they update it every night. Log into ftp.nasdaqtrader.com anonymously. Look in the directory SymbolDirectory. You'll notice two files: nasdaqlisted.txt and otherlisted.txt. These two files will give you the entire list of tradeable symbols, where they are listed, their name/description, and an indicator as to whether they are an ETF. 

```bash
# Download nasdaqlisted.txt
curl -o nasdaqlisted.txt ftp://ftp.nasdaqtrader.com/SymbolDirectory/nasdaqlisted.txt

# Download otherlisted.txt
curl -o otherlisted.txt ftp://ftp.nasdaqtrader.com/SymbolDirectory/otherlisted.txt

echo "Files downloaded successfully.
```

| Name                      | Ticker | Exchange | Sector                                               | Industry      | Principal Competitor | Close Price | Median Target | Forward EPS | Forward P/E | Beta | Market Cap | PEG Ratio |
|---------------------------|--------|----------|------------------------------------------------------|---------------|----------------------|-------------|---------------|-------------|-------------|------|------------|-----------|
| Verizon                   | VZ     | NYSE     | Communication Services                               |               | AT&T                 | 33.79       | 39            | 5           | 6.76        | 0.33 | 142.055B   | -0.63     |
| Molson Coors              | TAP    | NYSE     | Alcoholic Beverages                                  | Food & Drink  | Anheuser Busch       | 63.59       | 70            | 0.19        | 334.68      | 0.9  | 13.757B    | 2.42      |
| Bristol-Myers Squibb      | BMY    | NYSE     | Discovery, development, licensing, manufacture, marketing, distribution, and sale | Pharma   | AbbVie                | 59.03       | 73.95         | 3.76        | 15.7        | 0.41 | 123.32B    | 1.58      |
| Dr Pepper                 | KDP    | NASDAQ   | Beverages                                            | Food & Drink  | Coca-Cola             | 33.3        | 40            | 1.13        | 29.47       | 0.58 | 46.529B    | 3.19      |
| Plains All American Pipeline | PAA  | NASDAQ   | Energy Infrastructure                                | Energy       | Energy Transfer      | 15.15       | 17            | 1.62        | 9.35        | 1.65 | 10.62B     | 0.1       |


## Column Aligned 


|                         | Verizon  | Molson Coors | Bristol-Myers Squibb | Dr Pepper | Plains All American Pipeline |
|-------------------------|----------|--------------|----------------------|-----------|-----------------------------|
| Ticker                  | VZ       | TAP          | BMY                  | KDP       | PAA                         |
| Exchange                | NYSE     | NYSE         | NYSE                 | NASDAQ    | NASDAQ                      |
| Sector                  | Communication Services | Alcoholic Beverages | Discovery, development, licensing, manufacture, marketing, distribution, and sale | Beverages | Energy Infrastructure  |
| Industry                |          | Food & Drink | Pharma               | Food & Drink | Energy                     |
| Principal Competitor    | AT&T     | Anheuser Busch | AbbVie              | Coca-Cola | Energy Transfer             |
| Close Price             | 33.79    | 63.59        | 59.03                | 33.3      | 15.15                       |
| Median Target           | 39       | 70           | 73.95                | 40        | 17                          |
| Forward EPS             | 5        | 0.19         | 3.76                 | 1.13      | 1.62                        |
| Forward P/E             | 6.76     | 334.68       | 15.7                 | 29.47     | 9.35                        |
| Beta                    | 0.33     | 0.9          | 0.41                 | 0.58      | 1.65                        |



