## Data management for the paper:
Hidden Power of the Big Three? Passive Index Funds, Re-Concentration of Corporate Ownership, and New Financial Risk by Jan  Fichtner, Eelke M. Heemskerk, Javier  Garcia-Bernardo  http://papers.ssrn.com/sol3/papers.cfm?abstract_id=2798653

The raw data was downloaded from Orbis, containing the following fields for all US listed companies:
- 'Company name'
- 'Country ISO Code',
- 'NACE Rev. 2 Core code (4 digits)',
- 'Operating revenue (Turnover) th USD Last avail. yr',
- 'Number of employees Last avail. yr', 
- 'GUO - Name', 
- 'Ticker symbol',
- 'Stock exchange(s) listed', 
- 'Shareholder - BvD ID number',
- 'Shareholder - Direct %', 
- 'Shareholder - Total %', 'BvD ID number',
- 'Current market capitalisation th USD', 
- 'Shareholder - Name',
- 'Total assets (last value) th USD', 
- 'Type of entity'

### We excluded:
- Non-US exhanges and private US exchanges. The exchanges that were remaining were:  "'NYSE MKT','NYSE ARCA','NASDAQ/NMS (Global Market)','NASDAQ National Market', 'New York Stock Exchange (NYSE)'
- Private equity firms and Funds. We added JPMORGAN CHASE & CO (BvD ID US132624428) by hand since Orbis has mistakenly classified this very large US bank as a Private Equity firm.
- US041867445 (State Street Bank and Trust Co) because this subsidiary of State Street acts as a custodian, holding the shares for the ultimate owners. 
- Public ownership (many small ownership combines) and owners whose ID start by ZZ (no people or companies).

### We kept
- The largest ownership percentage between direct and total ownership (null values considered zero).
- The sum of the ownership percentages of the Big Three
- The position of that sum among all the shareholder, with the code 1 = largest, 2 = second largest, 3 = third largest, 4 = rest.

#### IMPORTANT: This data is not provided, only the end result. big3_position.csv, that can be used to replicate all figures (step 3-5).  big3_position.csv has the following data:
- Company_name:
- Company_ID: Orbis ID
- Big3Share: Share of the big3 together
- Position: Position of the big 3 among all shareholders
- Revenue: Firm's revenue
- Assets: Firm's assets
- Employees: Firm's number of employees
- MarketCap: Firm's market capitalization
- Exchange: Firm's exchange
- TypeEnt: Firm's type of entity

#### Files provided:
- Big 3.ipynb: ipython notebook containing the code used
- big3_position.csv: see above
- nodes.csv and edges.csv: Files with the network of ownership (threshold = 3%)
- big3.gephi: Gephi file with the previous information
