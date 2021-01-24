I am using Stack overflow Annual Developer survey Data from 2017 to 2020. You can find it [here](https://insights.stackoverflow.com/survey).  
If you are using kaggle then you can find the data [here](https://www.kaggle.com/haakakak/stack-overflow-developer-surveys-20152020#).  
This blog is based on my notebook on kaggle. You can click [here](https://www.kaggle.com/kirankamat/stack-overflow-annual-developer-survey-analysis) for code.  
Github repo of [project](https://github.com/kirankamatmgm/Stack-Overflow-Developer-Survey)

# Business understanding

In this analysis, I want to concentrate/ask 4 Questions, and try to reach to Solution with Data I have.  
Data -> Question -> Solution.


Questions?
1. Is Formal Education necessary to become Professional Developer?
2. As a Software engineer, Is it better to work in India or move to Western countries?
3. Which country has the most number of developers in last 4 years? and where does India stand in terms of total number of developers?
4. Will you earn more salary if you contribute to open source?

# Data Understanding

We have 2 datasets for every year.  
Consider for example year 2020,  
df_2020: It consist entire dataset
df_2020_Schema: It consist of column name from df_2020 and question asked for that column to fill the details in survey

Let us look at what we understand from data for each question in the respective section.

## 1. Is Formal Education necessary to become Professional Developer? 

To make this analysis, required column are present only in 2020 dataset, so I am considering only 2020 dataset for this question.  
Plotting barplot using column 'NEWEdImpt' which tells importance of formal education, and checking count for each answer.

![coutformal.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611472499169/xufwDjUk5.png)


![percentformal.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611472545792/3LWaC9gOc.png)

From above plot it can be understood that
- Almost 85% of the respondents that are professional developers feel that formal education is at least somewhat important, 
- which is contrary to the popular idiom that you don't need formal education to become a developer. 
- However, almost 16% believe that it is not at all important or necessary.

To get to a fare point, we will compare Formal Education importance with Salary they earn. And also we don't want to manipulate our decision with everyone's opinion so I am considering only Professional developer.

For handling with missing values I am droping all the rows which doesnt have NEWEdImpt and Salary.  
Two reason for dropping
- I can afford to do this because I have huge data left after this
- Imputing data for salary may manipulate the opinion about formal education.


![formalsalary.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611489474266/CuI5EbfqW.png)

### Evaluation

- This means that Professional developers with different opinion about formal education earn pretty much the same.  
- Professional developers who think Formal education is not needed earn comparatively higher then professional developers feel that formal education is important, but they are only 16%.  
- Remaining 85% of the respondents that are professional developers feel that formal education is at least somewhat important and earn comparatively same. 
- This doesn't mean people cannot become professional developers and earn competitive salary, certainly is possible but chances are just 16%
- This plot was to see if there is a huge difference in salary of Professional developer with and without formal education. 

Since there is no huge difference, going with majority I conclude that to become Professional developer and earn competitive salary it is better to complete formal education.


## 2. As a Software engineer, Is it better to work in India or move to Western countries?

To make this analysis of this question, required column are present only in 2017 and 2019 dataset, so I am considering 2017,2019 dataset for this question. 

I am considering only employed full-time professional developer.


![2017salary.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611473057444/1B7YTGhz0.png)

![2019salary.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611473066827/uU56zLcd9.png)

### Evaluation

Here you can see a programmer’s salary in the India is much lower than that in the west no matter how many years you are coding.  
Since CareerSatisfaction and JobSatisfaction are only present in 2017, I am making analysis of this based on only 2017 data

![qust2satisfaction.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611473074050/t850W3D0U.png)

After comparing the salary based on Years a programmer has been coded between the India and the western world. 
- I found that the salary of an indian programmer is much lower than that of the western no matter how many years they are coded.
- Career and Job Satisfaction of the western programmers are much higher than those of the indian programmers.

- So if you want to earn good amount of salary with Career and Job Satisfaction as you grow experience it is better to move to Western countries.



## 3. Which country has the most number of developers in last 4 years? and where does India stand in terms of total number of developers

Can you guess where do you find most number of developers in the world from year 2017 to 2020?

We write a function to get a tuple with details of top 2 countries details

Plot top 2 country with most number of developers.

![topdevcountry.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611473308451/_WZTUVrO6.png)

## Evaluation
From above plot it could be understood that
- According to Stackoverflow, most of the developers on its platform are from United States for each year.  US contributes to around 20 percent of developers in the world. 
- And India has second most number of the developers in the world according to Stackoverflow. India contributes to around 10 percent of developers in the world

# 4. Will you earn more salary if you contribute to open source?

To make this analysis of this question, required column are present only in 2019 dataset, so I am considering 2019 dataset for this question.



![opensource.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1611489343487/2ZLIn1VYz.png)

## Evaluation

- As we can see that the more you contribute to open source, Total salary earned is also increasing.

- So it is good idea to contribute to open source.
