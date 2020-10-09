# Wage

This is an initial analysis performed on a data set obtained on [Kaggle](https://www.kaggle.com/nsharan/h-1b-visa) and containing over 3 million rows. More data can be obtained from the *Office of Foreign Labor Certification* which outputs yearly data sets. See this [link](https://www.dol.gov/agencies/eta/foreign-labor/performance) for more performance indices.

For this section, we load the data set with 4 columns: case status, full time position, prevailing wage and year. The case status is one of

- CERTIFIED-WITHDRAWN
- WITHDRAWN
- CERTIFIED
- DENIED
- REJECTED (only 2 rows)
- INVALIDATED (only 1 row)
- PENDING QUALITY AND COMPLIANCE REVIEW - UNASSIGNED (only 15 rows)
- Not available (nan)

The full time position indicates whether or not a position is full time. The year ranges from 2011 to 2016.

Our final goal is to estimate the probability of having an H-1B visa application rejected. In order to demonstrate viability, we show that there is sufficient data to obtain meaningful results. In this notebook, we focus on the relationship between wages and applications. In particular, we compute a chi-square statistic to show that the is a clear relationship between wages and the probability of seeing and H-1B application denied.

## Wage Distribution

We plot wage distribution for full time and non full time positions. The plots are presented for the totality of the data, as well as by year.

Notes: We remove rows with wages of of 0 as well as those whose wages are above $250 000 (we consider very high wages to be outliers.). Doing so, we omit an insignificant amount of data (about 0.1%).


## Observations

We observe that the separation between full time and not full time does not make sense for the year 2016. In fact, it seems that the data was simply divided between wages above and below \$70 000.

Moreover, we can see that most applications that are not full time appeared in the year 2016. Indeed, see the following table.

| 2011   | 2012   | 2013  | 2014  | 2015  |  2016 | 
| :----- | :----: | :---: | :---: | :---: | -----: |
|  16579 |	15617 |	13557 |	14182 |	15093 | 351128 |

This is probably due to some error in the data collection. We therefore will not separate between full time and non full time positions in the year 2016.
