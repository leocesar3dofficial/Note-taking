# Market Research

## Uses

- Answers to questions about customers and competitors
- Identify market opportunities
- Measure customer satisfaction
- Assess market shares

## Process

1. **Identify and formulate the problem**

   - Based on symptoms like negative or unexpected results

2. **Determine the research design type**

   - _Exploratory_: for ambiguous problems
     - **Uses**
       - Understand structure
       - Formulate problems precisely
       - Generate hypotheses
       - Develop measurement scales
       - Establish research priorities
     - **Methods**
       - Focus groups
       - In-depth interviews
       - Projective techniques: present people with pictures, words, or other stimuli
       - Observational studies
       - Ethnographic studies
   - _Descriptive_: for somewhat defined problems
     - **Uses**
       - Describe customers or competitors
       - Understand market size
       - Segment markets
       - Measure performance
   - _Causal_: for clearly defined problems
     - **Uses**
       - Uncover causality: but correlation does not automatically imply causation or spurious correlation
       - Understand the performance effects of marketing mix
     - **Methods**
       - Lab experiments
       - Field experiments
         - Shelf tests
       - Analysis of variance
       - Regression analysis
       - Structural equation modeling

3. **Design the sample and method of data collection**

   - **Data Types**
     - Quantitative
     - Qualitative
     - **Variables**
       - Dependent: its outcome depends on one or more variables
       - Independent: controllable
       - Measurement scaling
         - Nominal
         - Ordinal
         - Interval
         - Ratio
     - Constants
     - Cases: all the variables that belong to an object
     - Constructs: a variable that is not directly observable
       - Reflective: use multiple items to increase the measurement stability and accuracy
       - Formative: ex. socioeconomic status
     - Index: sets of variables (causes)
   - **Sampling**
     - _Probability_
       - Simple random
       - Systematic
       - Stratified
       - Cluster
     - _Non-probability_
       - Judgmental
       - Snowball
       - Quota

4. **Collect the data (generate primary data)**

   - **Data quality**
     - Validity: measure what we want
     - Reliability: what is measured is free from random error
   - **Survey design process**
     1. Set the goal
     2. Determine the type of questionnaire and method of administration
     3. Design the items
     - **Item content**
       - Open-ended questions (verbatim items)
       - Closed-ended questions
     - **Item wording**
       - Grammar and sentences
     4. Set the scale
     - **Types**
       - Likert
       - Semantic differential
       - Rank order
       - Balanced or unbalanced
       - Forced or not forced choice (Inclusion of a “Don’t know” option)
     5. Design the questionnaire
     - Layout and format
     - Order of the questions
     6. Pretest the questionnaire
     7. Apply the questionnaire

5. **Analyze the data (generate secondary data)**
   - **Workflow of data**
     1. Create structure
     2. Enter data
     3. Clean data
     - Interviewer fraud
       - Contact a random number of respondents afterwards
     - Suspicious response patterns
       - Straight-lining: the same response in almost all the items
       - Inconsistent answers
     - Data entry errors
     - Outliers
       - **Definition**
         - Values situated far from all the other observations
         - That may influence results substantially
         - Should be deleted, determine the correct values or kept as is
       - **Types**
         - Data collection or entry errors
         - Exceptionally high, rare or low values are a part of reality
           - Must not be deleted, but discussed
       - **Detection techniques**
         - _Univariate_
           - Cases falling outside the range of the “usual” values
           - Chart: Box plot
         - _Bivariate_
           - Examine pairs of variables to identify observations whose combinations of variables are exceptionally rare
           - Chart: Scatter plot
           - Drawback: the need to plot several chart combinations
     - Missing data
       - **Levels**
         - Entire surveys are missing (survey non-response): 75-95%
         - Respondents have not answered all the items (item non-response): 2-10%
       - **Types**
         - Missing completely at random (paradise)
         - Missing at random (purgatory)
         - Non-random missing (hell)
       - **Process**
         - Listwise deletion
           - Delete incomplete responses
         - Multiple imputation
           - Replace with a set of possible values (inference)
     4. Describe data
     - **Descriptive statistics**
       - _Univariate_
         - **Graphs & tables**
           - Bar chart (nominal and ordinal variables)
           - Histogram (continuous variables)
           - Box plot or box-and-whisker plot (continuous)
             - Outlier, Whisker, 1st quartile, Median, 3rd quartile, Whisker, Outlier
           - Pie chart
           - Frequency table
         - **Statistics**
           - Measures of centrality: Mode, Median, Mean
           - Measures of dispersion: Range, Interquartile Range, Variance, Standard deviation
       - _Bivariate_
         - **Graphs & tables**
           - Scatter plots
           - Crosstabs
         - **Statistics**
           - Covariance
           - Correlation
     5. Transform data (optional)
     - **Types**
       - Variable respecification
         - Create new or modify existing ones
       - Scale transformation
         - Change the value(s) to compare with other variable(s)
         - Make the data suitable for analysis
         - Z-standardization (range 0 to 1)
       - Log transformation
         - Commonly used to correct skewed data
       - Aggregation: combine variable with other data category
     6. Create a codebook
     - **Structure**
       - Introduction
       - Questionnaire(s)
       - Description of the variables
       - Summary statistics
       - Datasets

## Directory structure

- Project name
  - Data
  - Syntax
    - Missing data analysis
    - Descriptives
    - Factor analysis
    - Regression analysis
  - Output
  - Temporary
  - Related
    - Codebook
    - Survey
    - Initial findings–presentation to client
    - Findings–presentation to client
    - Recommendations rev1
    - Recommendations rev2

## 6. Interpret, Discuss, and Present the Findings

### Hypothesis Testing and ANOVA

#### Steps

1. Formulate the hypothesis

   - Directional hypothesis (right or left-tailed, logical <= or >)
   - Non-directional hypothesis (logical == or !=)

2. Choose the significance level

   - Alpha Level (default α = 0.05)
   - Beta distribution or Probability density (default β = 0.5)

3. Select the appropriate test

   - Steps
     1. Define the testing situation
     2. Determine if samples are paired or independent
     3. Check assumptions and choose the test
     4. Specify the region of rejection
   - Types of test
     - Normality
       - Shapiro-Wilk test
     - Equality of variances
       - Levene’s test (F-test of sample variance)
     - Parametric
       - t-test
         - One-sample
         - Two-samples
           - Independent samples
           - Paired samples
       - Analysis of Variance (ANOVA)
         - One-way
         - Two-way
         - Welch's correction
     - Non-parametric
       - Wilcoxon signed-rank
       - Wilcoxon matched-pairs signed-rank
       - Mann-Whitney U
       - Kruskal-Wallis rank
   - [Tests Comparison table (CSV)](</Tecnologia da Informação/Análise de dados/Market Research - Tests Comparison table.csv>)

4. Calculate the test statistic

5. Make the test decision

   - Compare the Test Statistic with the Critical Value
   - Compare the p-Value with the Significance Level

6. Interpret the results

### Regression Analysis

#### Types

- Simple (one independent variable)
- Multiple (two or more independent variables)

#### Steps

1. Check the regression analysis data requirements

2. Specify and estimate the regression model

3. Test the regression analysis assumptions

4. Interpret the regression results

5. Validate the regression results

6. Use the regression model

#### Data Requirements

- Sample size
- Variables need to vary
- Scale type of the dependent variable
- Collinearity
  - When two or more predictor (independent) variables are highly correlated

#### Model

1. Specification (variables selection)

2. Estimation

   - Ordinary Least Squares (OLS)

3. Test the assumptions

   1. The regression model can be expressed linearly
   2. The regression model’s expected mean error is zero
   3. The errors’ variance is constant (homoscedasticity)
      - The opposite: non-constant variance (heteroscedasticity)
   4. The errors are independent (no autocorrelation)
      - Identify autocorrelation with the Durbin-Watson (D-W) test
   5. Error Distribution
      - The regression model errors are approximately normally distributed
      - Non-normally distributed errors include outliers

4. Interpret the Results
   - Overall Model Fit
     - Akaike information criterion (AIC)
     - Bayes information criterion (BIC)

## 7. Follow-up
