# Research papers


## Characterizing Automated Data Insights


https://arxiv.org/pdf/2008.13060.pdf


### Type of insights:

Outliers. Usually provide auto-insights about outliers in a single variable. For example, Insights communicates outliers in a time series that are highlighted in a line chart

Value/derived value. Auto-insights about a value of a single row in a table or a value derived from multiple rows in the table. The multimodal layered storytelling approach reveals prominent values in a timeline IE: the number of unique categories in a categorical variable and ranks bar charts by the unique category count/ the average of a numerical variable  / computes the proportion of categories in a categorical variable. state the derived values (average and proportion) as textual descriptions.

Association. (i.e. quantitative relationship between two numerical variables). tools commonly identify either linear relationship using Pearson correlation or non-linear relationship using more sophisticated measures - computes a Pearson correlation between two variables and presents it as a textual description alongside a scatterplot . ranks scatterplots by least-squares error curvilinear regression and quadracity to identify scatterplots that show a quadratic relationship.

Difference. An auto-insight about difference involves a quantitative comparison between distributions. Ie: users can specify two groups of objects (e.g., cities in China and cities in the US). For each attribute (e.g., population), compares the two groups to determine whether they have different distributions. ranks grouped bar charts by computing the earth movers distance between the two probability distributions depicted in the charts /  oneway ANOVA for charts that show continuous-categorical data and sorts the charts by p-value

Trend. Ie extract upward and downward trends, steady trend, and periodicity. line charts based on the upward trends they show. Temporal summary images add annotations to the flat regions in a time series visualization extracts time series that show seasonality.

Distribution. data facts about the range of a numerical variable, ranks charts based on several measures of distribution including dispersion, skewness, and heavytailedness to reveal charts with a noteworthy distribution .

Extreme. auto-insights about the minimum and maximum values in a stream of values.

Visual motifs. Visual motifs are unique patterns in a chart that do not fall into other auto-insight types. They include the special patterns in scatterplots identified by the scagnostics measures. tools identify visual motifs in scatterplots by utilizing scagnostics or other measures (e.g., uniformity).

Cluster. employs K-means and DBSCAN to find clusters in a scatterplots, It presents the clusters using a textual description and highlights the clusters in the scatterplot

Metadata. Auto-insights about metadata provide information about a dataset. Such information includes missing values and other data quality issues. uses detection routines to identify data quality issues and suggests charts to visualize the issues.

Rank. auto-insights involve sorting categories by a numerical variable. For a dataset of cars, recommends a data fact that says, “Compact, SUV, Midsize are the top 3 categories in the year of 2008”. This fact is generated by ranking different types of cars by the numerical variable sales.

Compound fact. defined a compound fact as a fact that contains two or more facts. recommends a fact by combining auto-insights about derived value and distribution . For example, it generates the fact “Average Retail Price of SUV is 1.76 times Sedan” for a car dataset . The fact includes a derived value (average) and is about the distribution of retail price. 



### Purpose of insights:


Exploratory analysis. The majority of the auto-insight intend to support exploratory data analysis. Several papers argue that data exploration typically involves specifying and examining a large number of charts . They comment that the process is non-trivial because of a large dataset  or a limited expertise of users . Tools rank charts based on the statistical properties of data (e.g., correlation) and show the potentially interesting ones to reduce the number of charts for user review. Aside from surfacing potentially interesting charts, we observed other reasons for providing auto-insights to support data exploration. Analysts might not know where to look at the beginning of data exploration, and automatically revealing interesting charts helps analysts enter the exploratory loop. Visualization systems often leave analysts “uncertain about how to explore their data in an orderly manner.” The HCE system to support a more systematic data exploration . Users often encounter drill-down fallacies and recommends bar charts to protect users from the analysis pitfall.


Communication. More recently, some researchers have developed tools that automatically generate data insights for communication purposes. These tools commonly present textual insights beside visualizations. They utilize textual insights to provide various benefits during communication with visualizations, including visualization interpretation, effective storytelling, and reflection. Some seeks to scaffold visualization interpretation by presenting textual descriptions of charts ]./ data-driven storytelling. generates infographic-like fact sheets to communicate key points in a dataset/ summary images annotate temporal visualizations to point “a viewers attention to regions of interest,” “suggest conclusions,” and “provide data context” . automatically generated annotations of visualizations served educational purposes by encouraging reflection on performance in nursing simulations.


Focused analysis. Analysis exists on a spectrum from exploratory to directed. Data exploration is often more opportunistic and involves a vague goal while focused analysis is directed by more concrete questions, auto-insight tools that were designed to support more focused analysis. They help answer concrete yet high-level questions such as “Why is there a large high-income White population?”  and “What are the differences between New England colleges and Southeast colleges?” While lowlevel questions such as What is the admission rate of University X in 2020? often have a single correct answer, high-level questions may have multiple reasonable answers. Auto-insight tools lend themselves to answering high-level questions by recommending possible answers. Users can then apply their domain knowledge to interpret the relevance of the recommendations.


Data wrangling. Another purpose of automatically extracting data insights is to support data wrangling. It detects anomalies in data and recommends visualizations to show the data quality issues.
