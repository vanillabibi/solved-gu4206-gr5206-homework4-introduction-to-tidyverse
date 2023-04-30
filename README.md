Download Link: https://assignmentchef.com/product/solved-gu4206-gr5206-homework4-introduction-to-tidyverse
<br>



Please submit both pdf and Rmd files (or html and Rmd files).

<h1>Part II: Split/Apply/Combine and tidyverse warm-up</h1>

This famous (Fisher’s or Anderson’s) iris data set gives the measurements in centimeters of the variables sepal length and width and petal length and width, respectively, for 50 flowers from each of 3 species of iris. The species are Iris setosa, versicolor, and virginica.

Consider the following <strong>loop </strong>that computes the mean of each quantitative variable split by species and stores the computed means in a matrix named <strong>MeanFlowers</strong>.

<table width="632">

 <tbody>

  <tr>

   <td width="632"><em># define a matrix of zeros</em>MeanFlowers &lt;- <strong>matrix</strong>(0,nrow=4,ncol=3)<em># define a character vector corresponding to the numeric variable names </em>measurements &lt;- <strong>c</strong>(“Sepal.Length”,”Sepal.Width”,”Petal.Length”,”Petal.Width”)<em># name the rows and columns of the matrix MeanFlowers </em><strong>rownames</strong>(MeanFlowers) &lt;- measurements <strong>colnames</strong>(MeanFlowers) &lt;- <strong>c</strong>(“setosa”,”versicolor”,”virginica”)<em># Loop</em><strong>for </strong>(j <strong>in </strong>measurements) {<em>#– R code goes here —-</em>MeanFlowers[j,] &lt;- <strong>round</strong>(<strong>tapply</strong>(iris[,j],iris[,”Species”],mean),4)}MeanFlowers</td>

  </tr>

 </tbody>

</table>

##                                          setosa versicolor virginica

<table width="300">

 <tbody>

  <tr>

   <td width="195">## Sepal.Length 5.006</td>

   <td width="70">5.936</td>

   <td width="35">6.588</td>

  </tr>

  <tr>

   <td width="195">## Sepal.Width             3.428</td>

   <td width="70">2.770</td>

   <td width="35">2.974</td>

  </tr>

  <tr>

   <td width="195">## Petal.Length 1.462</td>

   <td width="70">4.260</td>

   <td width="35">5.552</td>

  </tr>

  <tr>

   <td width="195">## Petal.Width             0.246<strong>Problem 1</strong></td>

   <td width="70">1.326</td>

   <td width="35">2.026</td>

  </tr>

 </tbody>

</table>

Replicate the above loop using the <strong>Split/Apply/Combine </strong>model with base R commands.

<strong>Solution goes below</strong>

<em>## solution goes here —</em>

<h2>Problem 2</h2>

Repeat question 1 by constructing a pipe, including the <strong>split() </strong>function from base R and <strong>map_df() </strong>from the <strong>purrr </strong>package.

<strong>Solution goes below</strong>

<em>## solution goes here —</em>

<h1>Part II: More tidyverse with CDC cancer data</h1>

Consider the Center of Disease Control data set <strong>BYSITE_new.csv</strong>, which describes the incidence and mortality counts of several types of cancer over time. The variables of interest are: <strong>YEAR</strong>, <strong>RACE</strong>, <strong>SITE</strong>,

<strong>EVENT_TYPE</strong>, <strong>COUNT </strong>and <strong>POPULATION</strong>.

<h2>Problem 3</h2>

Load in the dataset <strong>BYSITE_new.csv </strong>using the appropriate function from the <strong>readr </strong>package. Display the dimension of the cancer tibble.

<h3>Solution goes below</h3>

<em>## solution goes here —</em>

Base R code for reference.

<em># Base R code for reference </em>cancer &lt;- <strong>read.csv</strong>(“BYSITE_new.csv”,header=T) <strong>dim</strong>(cancer)

## [1] 44982                  7

<h2>Problem 4</h2>

Using Base R or tydyverse functions, identify any strange symbols that are recorded in the <strong>COUNT </strong>variable. Once you have identified the symbols, use functions from the <strong>dplyr </strong>package to remove any rows in the cancer tibble containing these symbols and then convert <strong>COUNT </strong>to a numeric mode.

<em>## solution goes here —</em>

<h2>Problem 5</h2>

For a specific tumor and population, a crude rate is calculated by dividing the number of new cancers observed during a given time period by the corresponding number of people in the population at risk. For cancer, the result is usually expressed as an annual rate per 100,000 persons at risk. <a href="https://ci5.iarc.fr/ci5plus/pages/glossary.aspx">https://ci5.iarc.fr/ci5plus/pages/ </a><a href="https://ci5.iarc.fr/ci5plus/pages/glossary.aspx">glossary.aspx</a>

In reference to our data, this quantity can be calculated by:

COUNT

CRUDE RATE = 100000 <em>∗</em>

POPULATION

Using relevant functions from the <strong>dplyr </strong>package, create a new variable in your dataframe (or tibble) called <strong>CRUDE_RATE</strong>. Then using base R graphics or ggplot, create a histogram of <strong>CRUDE_RATE</strong>. Note that the crude rates are not bounded between [0,1] because they are calculated per 100,000 persons at risk.

<em>## solution goes here —</em>

<h2>Problem 6</h2>

Compute the average incidence rate of prostate cancer for each level of <strong>RACE</strong>. To solve this problem, students must build a pipe (<strong>magrittr </strong>package) and utilize the appropriate functions from the <strong>dplyr </strong>package. Also compare your results to a base R solution. Include both the tidyverse and base R solutions in your final write-up. <strong>Note: </strong>before computing the average incidence rates, students should filter the data as follows:

<ol>

 <li>Extract the rows corresponding to <strong>EVENT_TYPE </strong>level <strong>Incidence </strong>ii. Extract the rows corresponding to <strong>SITE </strong>level <strong>Prostate </strong>iii. Extract the rows corresponding to <strong>SEX </strong>level <strong>Male </strong>iv. Remove the rows corresponding to <strong>YEAR </strong>level <strong>2010-2014</strong></li>

 <li>Remove the rows corresponding to <strong>RACE </strong>level <strong>All Races</strong></li>

</ol>

<h3>Solution goes below</h3>

First filter the dataset:

<em>## solution goes here —</em>

Compute the average incidence rate of prostate cancer for each level of <strong>RACE</strong>.

<em>## solution goes here —</em>

<h2>Problem 7</h2>

Create a plot in base R or ggplot that shows the incidence rate (<strong>CRUDE_RATE</strong>) as a function of time (<strong>YEAR</strong>), split by the levels of <strong>RACE</strong>. Make sure to include a legend and label the graphic appropriately. Before constructing the graphic, perform the data wrangling tasks using a pipe and functions from the <strong>dplyr </strong>package, i.e., the same filtering tasks from problem 6. Students can use some base R functions in the pipe if needed and the plotting code can be included inside or outside the pipe.

<strong>Solution goes below</strong>

<em>## solution goes here —</em>

<h2>Problem 8</h2>

Fit five simple linear regression models, one for each level of <strong>RACE</strong>, relating the incidence rate

(<strong>CRUDE_RATE</strong>) as a function of time (<strong>YEAR</strong>). Collect the estimated slopes, t-statistics and p-values of your estimated models. The collection of slopes describe whether cancer has increased or decreased over the selected time period and the p-values describe if the increase or decrease is statistically significant. Solve this problem using a pipe and functions from the <strong>dplyr </strong>and <strong>purrr </strong>packages. <strong>Note: </strong>use the same filtered data from problem 4 and problem 4 in this analysis.

<strong>Some hints: </strong>(i) this exercise is a natural extension of problem 7; (ii) if needed, students can also define their own functions used in the pipe; (iii) students are not required to use a single pipe to solve this question but it’s a fun challenge if interested.

<h3>Solution goes below</h3>

<em>## solution goes here —</em>