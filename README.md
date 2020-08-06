# Find_stock_pairs_by_sector
Find cointegrated stock pairs in Russell 3000, by sector.

  1. Generate ticker_list by sector (using Russell 3000 stock list). 
  2. Get Yahoo Finance daily data. Loop through Yahoo Finance daily data to find cointegration in longer term, e.g 3 months. Narrow down the pairs list.
  3. Read in pairs list generated in step 2, get IEX minute data, then check the cointegration in shorter time frame using IEX minute data. e.g 1 month of minute data. Then return the final dataframe for pairs found.

In this way, we are able to reduce the running time. Miniute data is very computative expensive. Also, I used two ways to check contegration. For daily data, I use ADF test. For miniute data, use coint() function in statsmodel, which utilize the augmented Engle-Granger two-step cointegration test. Only pairs that passes both test can be added to our list.
