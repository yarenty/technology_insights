# Time Series Transformer

https://jchiang1225.medium.com/a-new-data-approach-in-time-series-analysis-2d6c97f209cd

References:

https://allen-chiang.github.io/Time-Series-Transformer/introduction.html

https://github.com/allen-chiang/Time-Series-Transformer



----


A New Data Approach in Time Series Analysis
Empower the data structure, Enhance the data process


Photo by Pierre Borthiry on Unsplash
Time Series data is a sequence of data points indexed in time order. The most common example of time series data is the daily closing price of the stock market. Beside the stock market, we do encounter a lot of different time series data, for instance, the climate changes across time or the sales revenue of a company. Time series analysis helps organizations understand the underlying causes of trends or systemic patterns over time.

Today, we want to dive into a fancy and powerful time series data structure engine.

Time-Series-Transformer

The package not only provides functionalities to process the time series data, but it shines when we need to process multi-dimensional time series data. Moreover, the submodule, Stock_Transformer, is able to extract the stock data and calculate the technical indicators in just a few lines of code.

Installation
pip install time-series-transform
Note: Make sure tensorflow and plotly are installed

Data
In this example, we will use the climate time series data in Delhi from Kaggle

https://www.kaggle.com/datasets/sumanthvrao/daily-climate-time-series-data?resource=download

Let’s get started
When we are processing the time series data, we always need to take extra attention on the time order, and it is not easy to do so with solely numpy or even pandas. The Time_Series_Transform makes the task easier than ever.

There are two main modules in the package.

Time_Series_Transformer: the core module and it is compatible with user defined time series data
Stock_Transformer: helps us to extract stock data and provide operation to embed the technical indicator calculation library (pandas-ta)
Time Series Transformer Core
Time_Series_Transformer can helps us to format the time series data and we are able to manipulate the time series data easily.



Figure 1. climate data
From the dataset, we can see there are 4 different features, and we can load the data into our package from pandas.dataFrame. The timeSeriesCol will be the column of the time index, and the mainCategory field allows us to handle multi-dimensional data, we will talk about it later.


ime_Series_Transformer data
data column
-----------
date
meantemp
humidity
wind_speed
meanpressure
time length: 1462
category: None


We can slice the data from the time_series_data as below
{'date': array(['2013-01-01', '2013-01-02', '2013-01-03'], dtype=object),
'meantemp': array([10.        ,  7.4       ,  7.16666667]),
'humidity': array([84.5, 92. , 87. ]),
'wind_speed': array([0.        , 2.98      , 4.63333333]),
'meanpressure': array([1015.66666667, 1017.8, 1018.66666667])}
Data Manipulation
Most of the time, we need to preprocess the data before entering the model. In time series analysis, making lag or lead data (shifting data) is one of the most common methods. The package also provide the function to shift data.

make_lead
make_lag
make_lead_sequence
make_lag_sequence
make_lead and make_lag shift the data

make_lead_sequence and make_lag_sequence shift the data and return a window list data as feature. It is useful in producing Deep learning feature




{'date': array(['2013-01-01', '2013-01-02', '2013-01-03'], dtype=object),
'meantemp': array([10.        ,  7.4       ,  7.16666667]),
'humidity': array([84.5, 92. , 87. ]),
'wind_speed': array([0.        , 2.98      , 4.63333333]),
'meanpressure': array([1015.66666667, 1017.8, 1018.66666667]),
'meantemp_lead_3': array([8.66666667, 6.        , 7.        ]),
'wind_speed_lead_3': array([1.23333333, 3.7       , 1.48      ]),
'meantemp_lead_seq_3': array([[7.4       , 7.16666667, 8.66666667],
[7.16666667, 8.66666667, 6.        ],
[8.66666667, 6.        , 7.        ]]),
'meanpressure_lead_seq_3': array([[1017.8, 1018.6667, 1017.1667],
[1018.66666667, 1017.16666667, 1016.5       ],
[1017.16666667, 1016.5       , 1018.        ]])}
User defined function
It is also possible to use the user defined function. We can use the transform function to customize the data process.

Restriction of the customize function:

the function must take an array
output must be an array with the same size as the original data length
Note: time_series_transform.transform_core_api.util provides some general functions as we imported at the beginning


data column
-----------
date
meantemp
humidity
wind_speed
meanpressure
meantemp_lead_3
wind_speed_lead_3
meantemp_lead_seq_3
meanpressure_lead_seq_3
wind_cust_10
time length: 1462
category: None
Plot
The package also provides function to draw plot and it supports several functions customize the plot.

add_line
remove_line
update_layout
add_marker


Figure 2. plot function
Multi-Dimensional Time Series Data
Sometimes when we are doing Exploratory Data Analysis or preprocessing the time series data before entering the model, we might want to separate the data by their features. Handling multi-dimensional time series data is the strong point of the package.

Time_Series_Transformer can specify the mainCategoryCol parameter to point out the main category. This class only provide one columns for main category because multiple dimensions can be aggregated into a new column as main category.

From the documentation. With the mainCategoryCol, we are able to separate the data by the category and perform same data operations as we did previously.


Next we can further apply the functionality to perform advance preprocessing. To demonstrate the capability of the Time_Series_Transformer, we can separate the data by their month and investigate the behavior of the data.





Moreover, we can also use the plot function on the multi-dimension data, and it will generate several lines and we can select which month we want.



Figure 3. Multi-dimension plot (option to choose category)
Stock Transformer
Speaking of the time series analysis, the stock market must be the interest of most people. Stock_Transformer makes our life easy and simple. Extraction of the stock data can be done in just one line of code, and we can also use the power of the data manipulation like how we did previously.

Stock extraction methods:

from_stock_engine_date
from_stock_engine_period
from_stock_engine_intraday


To calculate the standard technical indicators, we can use the get_technial_indicator with pandas-ta.


Date       Open       High        Low      Close     Volume  \
25  2019-02-07  41.725962  42.098690  41.227381  41.372601  126966800   
26  2019-02-08  41.076051  41.481974  40.937501  41.421207   95280000   
27  2019-02-11  41.576775  41.615667  41.139252  41.183002   83973600   
28  2019-02-12  41.345854  41.564614  41.248625  41.537876   89134000   
29  2019-02-13  41.659413  41.924356  41.302103  41.365299   89960800

    Dividends  Stock Splits  MACD_12_26_9  MACDh_12_26_9  MACDs_12_26_9  \
25     0.0000           0.0      1.952193            NaN            NaN   
26     0.1825           0.0      1.915505            NaN            NaN   
27     0.0000           0.0      1.845929            NaN            NaN   
28     0.0000           0.0      1.798691            NaN            NaN   
29     0.0000           0.0      1.727417            NaN            NaN

       EMA_10        BBL        BBM        BBU  Bandwidth   Percent  
25  40.383502  34.842427  38.655327  42.468227  19.727684  0.856326  
26  40.572176  34.930402  38.865177  42.799952  20.248332  0.824800  
27  40.683235  35.136170  39.081391  43.026611  20.189764  0.766349  
28  40.838624  35.475825  39.343060  43.210295  19.659045  0.783771  
29  40.934383  35.746722  39.558949  43.371175  19.273650  0.736915


Figure 4. Stock candle plot

