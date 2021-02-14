# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis
### Project Description

Our first module in DSI covers:
- Basic statistics and probability
- Many Python programming concepts
- Programmatically interacting with files and directories
- Visualizations
- EDA
- Working with Jupyter notebooks for development and reporting

---
### Overview
For our first project, we're going to take a look at aggregate SAT and ACT scores and participation rates in the United States. We'll seek to identify trends in the data and combine our data analysis with outside research to address our problem statement.

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

---
## Project 1. Standardized Test Analysis of aggregate SAT and ACT scores and participation rates in the United States.

---
### Problem Statement
>  According to Kranse Institute, in the year 2016, the SAT scores were the lowest in the last 20 years! ([*source*](https://www.kranse.com/blogs/news/2016-sat-scores-were-the-lowest-in-the-last-20-years)). In March 2016, the College Board - the company that owns and administers the SAT test, - released the new, significantly modified, format for the SAT. Since then, levels of participation in multiple states have changed with varying legislative decisions. 

> The goal of this project is to analyze the average SAT scores on the national and state levels in the 3 years, following the adoption of the new version of the SAT test, and to discover and review the major trends in order to answer the following questions:

> * Has the new, improved and enhanced, format of the SAT test solved the performance problems, that have accumulated by 2016? Is the situation improving?

> * The SAT test has long been considered to be the most accurate indicator of future academic success. Should the state and college administrations continue to require students to pass this test or should they become more flexible and consider other ways of measuring students preparedness? Which states will it benefit the most?

> * The main alternative to the SAT is the ACT test. Have the modifications, made to the SAT test in the year 2016, made it easier than ever for the students to prepare for both SAT and ACT tests concurrently and to earn competitive scores on both tests?

---

### Data Dictionary

#### Dataset 1: [`sat_2019.csv`](./data/sat_2019.csv): 2019 SAT Scores by State ([source](https://blog.prepscholar.com/average-sat-scores-by-state-most-recent))

|**Feature**|**Type**|**Dataset**|**Description**|
|---|---|---|---|
|**State**|object|sat_2019|One of the US states (there are 50 state names, a value representing the District of Columbia, and 2 more values, 'Puerto Rico' and 'Virgin Islands')| 
|**Participation Rate**|object|sat_2019|The percent of the students in a state, who took a SAT test (represented by a string in the following format: '##.#%' - for example, '99.5%'| 
|**EBRW**|int64|sat_2019|The average score for the 'Evidence-Based Reading and Writing' section of the SAT test per state| 
|**Math**|int64|sat_2019|The average score for the 'Math' section of the SAT test per state| 
|**Total**|int64|sat_2019|The average total score for the SAT test per state. It is a sum total of 'EBRW' and 'Math' scores| 

#### Dataset 2: [`act_2019.csv`](./data/act_2019.csv): 2019 ACT Scores by State ([source](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows))

|**Feature**|**Type**|**Dataset**|**Description**|
|---|---|---|---|
|**State**|object|act_2019|One of the US states (there are 50 state names, a value representing the District of Columbia, and 1 more value representing the total, 'National' | 
|**Participation**|object|act_2019|The percent of the students in a state, who took an ACT test (represented by a string in the following format: '##.#%' - for example, '99.5%'| 
|**Composite**|float64|act_2019|The average total score for the ACT test per state.| 

#### Dataset 3: [`sat_2017.csv`](./data/sat_2017.csv): 2017 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))

|**Feature**|**Type**|**Dataset**|**Description**|
|---|---|---|---|
|**State**|object|sat_2017|One of the US states (there are 50 state names, and a value representing the District of Columbia)| 
|**Participation**|object|sat_2017|The percent of the students in a state, who took a SAT test (represented by a string in the following format: '##.#%' - for example, '99.5%'| 
|**Evidence-Based Reading and Writing**|int64|sat_2017|The average score for the 'Evidence-Based Reading and Writing' section of the SAT test per state| 
|**Math**|int64|sat_2017|The average score for the 'Math' section of the SAT test per state| 
|**Total**|int64|sat_2017|The average total score for the SAT test per state. It is a sum total of 'Evidence-Based Reading and Writing' and 'Math' scores| 

#### Dataset 4: [`sat_2018.csv`](./data/sat_2018.csv): 2018 SAT Scores by State ([source](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/))

|**Feature**|**Type**|**Dataset**|**Description**|
|---|---|---|---|
|**State**|object|sat_2018|One of the US states (there are 50 state names, and a value representing the District of Columbia)| 
|**Participation**|object|sat_2018|The percent of the students in a state, who took a SAT test (represented by a string in the following format: '##.#%' - for example, '99.5%'| 
|**Evidence-Based Reading and Writing**|int64|sat_2018|The average score for the 'Evidence-Based Reading and Writing' section of the SAT test per state| 
|**Math**|int64|sat_2018|The average score for the 'Math' section of the SAT test per state| 
|**Total**|int64|sat_2018|The average total score for the SAT test per state. It is a sum total of 'Evidence-Based Reading and Writing' and 'Math' scores| 

---

### Discovered Trends

>1. Even though the SAT was significantly redesigned in March 2016, the **average SAT scores** continued to **decline**, as participation continued to grow. The trend is **negative** and, most likely, the scores will continue to decline, especially in 2020-2021, due to Covid lockdowns.

> 2. Out of the 8 states with a **100% participation** in the SAT test, **not even one had a total SAT score above the national average** (which in 2019 was 1113.078). The same is true for the states with a 100% participation in the ACT test (average = 21.465). Most likely, it can be explained by the fact that in the states with mandatory 100% test participation, a significant share of participants were not planning to continue their education and did not really prepare for their tests.

> 3. The reverse is also true: the states with the **best performance in SAT/ACT** all showed **low participation** in those tests. In these states, participation in SAT/ACT is obviously voluntary and brings very good results. The students who voluntarily take tests, as they prepare to continue their education, tend to have higher scores, significantly raising the state's average.
---
### Conclusions and Recommendations
> 1. Even though the SAT was significantly redesigned in March 2016, the **average SAT scores** continued to **decline**, as participation continued to grow. Apparently, redesigning the SAT in 2016 has not solved the problems, which have been accumulating for years. Most likely, it created some additional issues, so it would be beneficial for the College Board to review this new version of the SAT test - to make sure that all issues are solved and that it does not create any unnecessary problems.

"The College Board... decided to make major structural changes to the math section, shifting to more “real world” scenarios. The addition of these word-based math problems took longer for students good at math to complete, and far longer for those who struggle with English to finish, if they finished at all. Though there are still traditional “solve for x” and numeric questions, the word problems are likely dragging down the math score for anyone with a learning disability (diagnosed or not) as well as those who speak English as a second language. For a test that claims to be an excellent indicator of analytical skill and knowledge, this is a major problem... the fact remains that the SAT has become a more difficult test, requiring more preparation and a solid strategy going into it in order to obtain the best score." ([source](https://www.kranse.com/blogs/news/2016-sat-scores-were-the-lowest-in-the-last-20-years))

> 2. The states with the **best performance in SAT/ACT** all showed **low participation** in those tests. In these states, participation in SAT/ACT is obviously voluntary and brings very good results. The students who voluntarily take tests, as they prepare to continue their education, tend to have higher scores, significantly raising the state's average. It would probably be more beneficial for the states to **remove requirements for a 100% participation in SAT/ACT tests** and to allow students and their parents to choose a different test or no test at all.

> 3. College admissions officers should be relying more on high school GPA, the classes, which students took in high school, letters of recommendation from teachers or mentors, admissions interviews, etc - without relying completely on SAT or ACT test scores.

Since March 2020, "more than 500 colleges, including every school in the Ivy League, have joined the growing “test optional” movement. All told, more than 1,600 four-year schools will not require scores for admission in 2021, and a growing number are becoming “test blind,” meaning they won’t consider scores at all... Institutions eliminating or de-emphasizing standardized tests often cite a lack of confidence in the SAT’s and ACT’s ability to predict college success as well as a desire to improve campus diversity. The preponderance of research regarding the predictive power of the SAT supports the test-optional pathway, as high school performance is a better indicator of collegiate success." ([source](https://www.forbes.com/sites/susanadams/2020/09/30/the-forbes-investigation-how-the-sat-failed-america/?sh=35b0cdf753b5))

---
 
