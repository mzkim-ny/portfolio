# **Min-zi Kim's Portfolio**
Hello. This is a record of questions I had about issues I was curious about, along with answers based on data.

- **Tools**: Excel, MSSQL, Tableau Public, ChatGPT
- **References**: 'My first SQL class', 'Tableau Good Morning Afternoon', 'Data Pre-processing Analysis Tasting in SQL' 
- **Tableau**: [profile](https://public.tableau.com/app/profile/mzkim/vizzes)<br><br/>

## **1. Indicator Analysis**
#### **# Understanding superstore sales performance ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%8A%88%ED%8D%BC%EC%8A%A4%ED%86%A0%EC%96%B4))** (←Click to link)
- **Data**: Superstore Sales (from Tableau)
- **Extract indicator**:<br>
1\) Sales (by date, month, year) <br>
2\) Number of buyers, number of purchases (by date, month, year)<br>
3\) Revenue per person (AMV, Average Member Value) (annual) <br>
4\) Purchase amount per case (ATV, Average Transaction Value) (year by year)<br>
5\) Revenue (by country, city, and region) <br>
6\) Sales Top 5 Cities (West)<br>
7\) Top 10 Sales Items (West, Los Angeles, 2017)<br>
8\) Repurchase rate (by region, by year) <br>
- **Interpretation**: Sales, number of buyers, number of purchases, and sales per person increased annually, but purchases per case fell. We extracted sales rankings by city and item, focusing on the western regions with the highest sales. Repurchase rates did not vary by region, but increased annually.
- **Visualization**: How long it took for the customer to repurchase, expressed in a highlight table. ([Cohort Analysis](https://public.tableau.com/views/240922_/2?:language=ko-KR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)) 
- **Advice**: It appears that customers are increasingly buying more and more affordable products over and over again at wider intervals. If we proceed with the event, we suggest selecting popular items that are relatively affordable in the West, where sales are high.

#### **# How can I issue pizza discount coupons? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%ED%94%BC%EC%9E%90%20%EB%8D%B0%EC%9D%B4%ED%84%B0)) - [Tableau](https://public.tableau.com/shared/4FKB8ZMXH?:display_count=n&:origin=viz_share_link)** (←Click to link.)
- **Data**: Pizza Sales (from Kaggle)
- **Purpose**: As the single-person pizza market grows, it is to understand the current status of S-sized pizza sales and refer to them when issuing discount coupons.
- **Dashboard**: Indicators (total order amount, etc.) were calculated, features by size were expressed as progress graphs, the number of orders by size/hour/day was visualized as a highlight table, and the five most purchased menus were visualized as a tree map chart.
- **Advice**: Even if there is only one order per ID, it seems that S size is not selected first. L size is the highest in both order and sales ratio, followed by M size and S size. As the menu you prefer differs by size, we suggest an event to issue discount coupons only for popular menus at 12 o'clock on Thursday when you order the most S size.
- **Code**: Before I started working on the table, I found that the preferred menu was different for each size and the same size even though the time zone was different, so I organized the dashboard accordingly.

## **2. Dashboard**
#### **# How many moviegoers have returned to cinemas after COVID-19? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%BD%94%EB%A1%9C%EB%82%9819%EC%9D%B4%ED%9B%84%20%EC%98%81%ED%99%94%EA%B4%80%20%EB%A7%A4%EC%B6%9C%EC%95%A1%20%EB%B0%8F%20%EA%B4%80%EA%B0%9D%EC%88%98%20%EC%B6%94%EC%9D%B4)) - [Tableau](https://public.tableau.com/views/19_17186243860350/2_1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)**
- **Data**: Movie theater ticket integrated computer network (2024.06)
- **Purpose**: To see how much the film industry has recovered since COVID-19.
- **Code**: Three tables divided by countries were combined into one table to extract the required column, and if there was no value in the column, text was entered.
- **Dashboard**: It is expressed in cumulative graphs and numbers based on the changes in trends by country (all films, Korean films, foreign films), year, sales, number of audiences, and number of films.
- **Advice**: Compared to 2019 and 2023, the audience recovery rate is lower than sales. It seems necessary to analyze whether the increase in sales is due to higher movie ticket prices or higher purchases of certain goods.
- **Limit**: It is difficult to access personal identification information with public data.


#### **# What books have been most borrowed from the Jeong Yak-yong Library? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%EC%A0%95%EC%95%BD%EC%9A%A9%EB%8F%84%EC%84%9C%EA%B4%80%EC%97%90%EC%84%9C%EB%8A%94%20%EC%96%B4%EB%96%A4%20%EC%B1%85%EC%9D%B4%20%EB%A7%8E%EC%9D%B4%20%EB%8C%80%EC%B6%9C%EB%90%98%EC%97%88%EC%9D%84%EA%B9%8C%3F)) - [Tableau](https://public.tableau.com/views/_17196652852140/1?:language=ko-KR&:sid=&:display_count=n&:origin=viz_share_link)**
- **Data**: Namyangju City Jeong Yakyong Library Book Lending List (2024.05)
- **Purpose**: This is to understand the reading preferences of users of Jeong Yakyong Library.
- **Code**: We updated the decimal classification column based on the subject classification number, created a virtual table, extracted specific columns, and used functions to calculate the required numbers.
- **Dashboard**: A one-graph visualization of decimal classification categories according to the book loan ratio. When each circle is clicked, the list of loans top 10, the number of loans, the total number of loans, and the total number of holdings will be displayed.
- **Advice**: Placing the most borrowed literature and social sciences side-by-side at the entrance to the archives was a choice to increase the total number of loans. When the event book puts a new book in the corner, you may want to consider a category with a large number of books in possession but a low number of loans.


## **3. Visualize data**
#### **# How many dogs will live in Namyangju? (Excel) - [Tableau 1](https://public.tableau.com/app/profile/mzkim/viz/3_17178536456650/1)&nbsp;- [Tableau 2](https://public.tableau.com/shared/35Z4SXZ2H?:display_count=n&:origin=viz_share_link)**
- **Data**: Namyangju's pet registration status (dog) (2024.02) and Namyangju's demographic (2024.05)
- **Purpose**: To understand the current status of Namyangju citizens raising their pets (dogs).
- **Interpretation**: The townships with the highest number of dog registrations in Namyangju are Hwado-eup (10,306), Dasan 1-dong (6,390), and Byeolnae-dong (5,893), similar to the three townships with the highest resident registration population.
- **Advice**: Guri City has set up a pet playground to test the level of satisfaction. If Namyangju City is also going to test it out, I recommend you start at Dasan 1-dong, which has the highest number of dog registrations for the number of areas. You can increase the utilization rate per pet playground and listen to different opinions.

#### **# How popular are tanghulu shops right now? ([SQL](https://github.com/mzkim-ny/portfolio/blob/main/%ED%83%95%ED%9B%84%EB%A3%A8%EB%A7%A4%EC%9E%A5%20%EA%B0%9C%EC%97%85%20%EB%B0%8F%20%ED%8F%90%EC%97%85%20%EC%88%98)) - [Tableau](https://public.tableau.com/views/2024_06_1/1_1?:language=ko-KR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**
- **Data**: Local administration licensing data open (2024.06)
- **Purpose**: To ensure Tanghulu's popularity, which was popular as a popular snack, remains valid.
- ** Interpretation**: A total of 163 Tanghulu stores closed between January and June 2024, more than 72 stores closed last year. The number of Tanghulu stores peaked in Q3 2023, has been declining, and the recent decline has been sharpening.
- **Advice**: A closer analysis should be possible when compared to other industry data on whether Tanghulu stores opened and closed at a particularly fast pace or whether there is a regular cycle.
