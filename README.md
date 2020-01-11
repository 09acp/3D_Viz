# 3D_Vizualisation for Stocks Project
Alex Papa 10/01/2020

#### __Stage 1__
- [x] [Data Wrangling](https://github.com/09acp/3D_Viz/blob/master/data_wrangling.ipynb)
  - [x] Identify dataset
    - Wharton Fundamental Data
  - [x] EDA 1 - missing data
  - [x] Create Date Index
  - [x] Multi Index dataset by Ticker & Year/Quarter
  - [x] Clean dataset
  - [x] Remove duplicates
  - [x] Backfill nan
  - [x] Save as pickle file "stock_index.pkl"  ~~sqlite database "stock_fundamentals"~~

#### __Stage 2__
- [ ] Research Stock Clustering
  - [ ] Dependent Variable/s


#### __Stage 3__
- [ ] PCA
- [ ] Create clusters


#### __Stage 4__
- [ ] Visualization
  - [ ] Python - Dash
  - [ ] R - Shinny

#### __Issues__
- The reporting frequency is not daily ( probably quarterly ). Each date (daily) should have values for all companies ( must be subsampled ?).
  - order by unique year-quarter
- Pivoting portfolio of stocks with multiple features. Multi-Index df. How to cluster high dimensional data ?


#### Additional Ideas
- Use classification model to highlight Predicted Classes for specific period
  (Manual evaluation)
    - Will likely use price data model
