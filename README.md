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
  - [ ] ~~Upsample data to a quarterly interval~~
  - [x] Save as "~~pickle file "stock_index.pkl"~~ sqlite database "data.db"
  - [x] ~~Create multiple smaller SQL tables for efficiency~~ Its faster to query entire df than multiple smaller queries.

#### __Research__
- [ ] Research Stock Clustering
  - [ ] Dependent Variable/s

#### __PCA & Clustering__
- [x] [PCA_Clustering](...)
  - [x] MinMax Scale data
  - [x] PCA
  - [x] Create clusters (K-Mean)

  #### __PCA & t-SNE__
  - [ ] [PCA_Clustering](...)
    - [ ] Apply t-SNE on PCA components

#### __Visualization (Plotly)__
Dash Python
**[x] [Dash - Plotly Express](...)**
  - [x] App 1 Prototype
      - [x] 2D PCA Scatter plot
      - [x] 3D PCA Scatter plot - colour: Sectors
      - [x] 3D PCA Scatter plot - colour: Clusters

  - [x] App 2 More visually expressive
      - [x] Sector represented by symbols
      - [x] Size of symbol represted by Returns
      - [x] 3D PCA Scatter plot - colour: Clusters

**[x] [Dash - Plotly Graphical Objects (GO)](...)**
  - [x] App 3 Plotly GO
      - [x] 3D PCA Scatter plot - colour: Clusters

  - [X] App 4&5 User customization
      - [X] Slider with time (Years)
        __Axis names dont appear from layout__

  - [x] App 6 User customization    
      - [x] Quarter Dropdown
        __Dropdown limited to selected year range (not_all)__
      - [x] Sector CheckList
      - [x] Size of symbol represted by Returns
      - [x] Fix Layout
      - [x] Fix Drag and Axis
      - [ ] Year Tabs (1yrs, 2yrs, 3yrs, all)

**[ ] Advanced Dash (GO)](...)**
  - [ ] App 7 More User customization %  
      - [ ] [Soft Clustering](https://plot.ly/python/v3/3d-point-clustering/)
      - [ ] Timechange
      - [ ] Cross Filtering
          - [ ] Tabs for different data: [Fundamental, Economic, Technical]
          - [ ] Hover over table to get PCA explained variance by feature



  - [t-SNE + PCA](https://dash-gallery.plotly.host/dash-tsne/)
  - [Yield Curve](https://dash-gallery.plotly.host/dash-yield-curve/)


[ ] R - Shinny

#### __Issues__
S1
- The reporting frequency is not daily ( probably quarterly ). Each date (daily) should have values for all companies ( must be subsampled ?).
  - order by unique year-quarter
- Pivoting portfolio of stocks with multiple features. Multi-Index df. How to cluster high dimensional data ?

__PCA & Clustering__
- PCA can be used to visualize data, but there are better methods for this task, for example, t-SNE. But PCA has less computational complexity.
- MinMax scaling the input features results in extremely small PCA values that are not visualised well
  --> Issue: df["y_return"] scale

__Visualization (Dash)__
- For the visualisation, does a 3D scatter plot limit enforce a 3 feature limit on the analysis at any one point in time?
  - can PCA resolve this ?
- Performance issues with Dash (Solved with MinMax Scaling) ~~( MAINLY DUE TO MULTIPLE TABS)~~
  - more efficient code examples https://dash.plot.ly/performance

#### Additional Ideas
- Use classification model to highlight Predicted Classes for specific period
  (Manual evaluation)
    - Will likely use price data model
