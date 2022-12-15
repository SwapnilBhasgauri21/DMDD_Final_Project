# NBA Players stat


# Team Members: 

Vikrant Pawar (NUID: 002772104)
Swapnil Bhasgauri (NUID : 002752978)

# Project Description: 

This Database Management project is based on basketball reference, that was developed using SQL to make databases and Python to scrape data from a basketball reference website. The project is intended to provide an insight into the data collected from the website and allow users to easily access and analyze the data. It includes a comprehensive statistical database, a directory of basketball teams and players, and a variety of other basketball-related information. The project includes designing and implementing a relational database to store the data from the basketball reference.

The database will include: 

- Players information such as age, position, team name
- Players stats like games played, games won, defensive score, points
- Stadium information
- Coach details
- Team description

We developed a web scraper using Python and which was responsible for scraping data from the website and storing it in the database. The database is built using the SQL programming language and is used to store the data collected from the website BeautifulSoup and requests libraries. Finally, the queries are used to access the data in the database and display the desired results Once the data was successfully scraped, it was stored in a MySQL database using SQL commands. The data was then organised into tables, each containing information about a particular aspect of basketball such as teams, players, and games.The goal of this project is to provide a comprehensive database of basketball-related facts and figures that can be used by different coaches, players, researchers, and other basketball enthusiasts.

## Scope: 
We have selected the 2020 stats which includes all the information about the matches played during this season.

## Plan of Action:
We have used 2 websites to scrape the data: 
-https://www.basketball-reference.com/
-https://en.hispanosnba.com/nba-arenas

## Implementation

### Phase 1: Twitter 

We started with thorough research and collection of existing data pertaining to this project. We sought various sources of data and verified the existing ones. To begin with, we laid out the use cases which we were seeking answers for. As the next steps, we spoke to a bunch of students at Northeastern University to gather information and factor in their points of view. 

Moving forward, we sought broader sources of information which led us to Twitter. Since Twitter as a platform voices many opinions, we thought it would give us a good sense of our project space. We scraped Twitter API, using tweepy for relevant programs, courses, and resources offered by Northeastern university, tweets, information about users, and their posts related to our database. This was a good starting point for our database and it helped us to move in the right direction. 

The performed the following steps for above analysis: 

- Fetched data from twitter 
- Inserted that data in our database using MYSQL
- Performed Queries to view data related to courses, programs, faculty details, events, and users. 
- Aligned and corraborated our usecases with the data collected using Twitter API 

#### Please visit the following link to get a detailed view of our Twitter data analysis
https://github.com/SwapnilBhasgauri21/Twitter_Bot
https://github.com/vikpawar22/Twitter-bot


### Phase 2: Gathering data from multiple resources

After collecting data from twitter, we condenseed our search to three main sources for data collection, described as follows: 

#### Website Scraping: 
We have collated all the above data sources to create a database and established connections between them to provide precise information for the same.

#### Please visit the following link to get a detailed view of Phase 2
https://github.com/SwapnilBhasgauri21/Web_Scraping
https://github.com/vikpawar22/DMDD_Ass3

### Phase 3: Normalization

The data collected in Phase 2 was sufficient but it was not in standard format. Phase 3 of this project involved normalizing this data. We studied all the tables obtained in the second phase extensively and realised that some tables were violating the some normal forms viz. 1NF, 2NF, and 3NF. We have documeneted all these changes in a separate detailed folder. 

#### Please refer to the PDF named DMDD_Assignment_4


### Phase 4: Final Project
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/ER%20Diagram.jpg)


## Data Cleaning:


1. Players Table:

- Removed all the * marks from the fields using replace() in python
- Unwanted columns were removed  
 
2. Player_Stats Table:

- Removed all the * marks from the fields using replace() in python
- Unwanted columns were removed 

3. Team Table:

- Removed all the * marks from the fields using replace() in python
- Unwanted columns were removed 


4. Coach Table:

- Removed all the * marks from the fields using replace() in python
- Unwanted columns were removed 

5. Stadium Table:

- Removed all the * marks from the fields using replace() in python
- Unwanted columns were removed 


## Assignment Execution Steps:

Run the below Queries for the complete code Execution by following the given steps:


## 1. Create PLAYER table

    CREATE TABLE PLAYER(
    PLAYER_ID VARCHAR(50) Primary Key,
    Player_First_Name VARCHAR(50),
    Player_Last_Name VARCHAR(50),
    Position VARCHAR(50),
    Age Integer
    );


## 2. Create TEAM table

    TEAM_ID VARCHAR(50) Primary Key,
    Team_Name VARCHAR(50),
    Win Integer,
    Loss Integer,
    Win_Loss_Percent Integer,
    Points_Per_Game Decimal,
    Opponents_Points_Per_Game Decimal,
    SRS Decimal
    );



## 3. Create PLAYER_STATS table

    CREATE TABLE PLAYER_STATS(
    PLAYER_ID VARCHAR(50), -- Foreign Key
    Game Decimal,
    Game_Started Decimal,
    Minutes_Played Decimal,
    Field_Goals Decimal,
    Field_Goal_Attempts Decimal ,
    Field_Goal_Percentage Decimal,
    3_Points Decimal,
    3_Points_Attempts Decimal,
    3_Points_Percentage Decimal,
    2_Points Decimal,
    2_Points_Attemps Decimal,
    2_Points_Percentage Decimal,
    Effective_Field_Goal_Percentage Decimal,
    Free_Throws Decimal,
    Free_Throws_Attempts Decimal,
    Free_Throws_Percentage Decimal,
    Offensive_Rebounds Decimal,
    Defensive_Rebounds Decimal,
    Total_Rebounds Decimal,
    Assists Decimal,
    Steals Decimal,
    Blocks Decimal,
    Turnover Decimal,
    Personal_Fouls Decimal,
    Points Decimal
    );



## 4. Create STADIUM Table

    STADIUM_ID VARCHAR(50) Primary Key,
    Stadium_Name VARCHAR(50),
    Size Integer,
    Location VARCHAR(50)
    );



## 5. Create COACH table

    CREATE TABLE COACH(
    COACH_ID VARCHAR(50),
    Coach_Name VARCHAR(50),
    Games Integer,
    Win Integer,
    Loss Integer,
    Win_Percentage Decimal
    );



#### Add Foreign Key constraints

    ALTER TABLE PLAYER_STATS
	ADD CONSTRAINT PLAYER_STATS_fk  FOREIGN KEY (PLAYER_NAME)
	REFERENCES PLAYER(PLAYER_NAME);

	ALTER TABLE PLAYER_ID
	ADD CONSTRAINT PLAYER_fk  FOREIGN KEY (TEAM_NAME_ID)
	REFERENCES TEAM(TEAM_NAME_ID)

	ALTER TABLE COACH_ID
	ADD CONSTRAINT COACH_fk  FOREIGN KEY (TEAM_NAME_ID)
	REFERENCES TEAM(TEAM_NAME_ID)
 
	ALTER TABLE STADIUM_ID
	ADD CONSTRAINT STADIUM_fk  FOREIGN KEY (TEAM_NAME_ID)
	REFERENCES TEAM(TEAM_NAME_ID)

## 6. Run the Python Script for scraping Basketball Websites in Jupyter Notebook

#### SQL to insert data in Coach Table

	INSERT INTO COACH VALUES(301,201,'Darvin Ham',11,2,9,0.182);
	INSERT INTO COACH VALUES(302,202,'Chauncey Billups',94,36,58,0.383);
	INSERT INTO COACH VALUES(303,203,'Jacque Vaughn',231,68,163,0.294);
	INSERT INTO COACH VALUES(304,204,'Steve Kerr',640,433,207,0.677);
	INSERT INTO COACH VALUES(305,205,'Erik Spoelstra',1125,665,460,0.591);
	INSERT INTO COACH VALUES(306,206,'Wes Unseld Jr.',94,41,53,0.436);
	INSERT INTO COACH VALUES(308,208,'Steve Clifford',650,295,355,0.454);
	INSERT INTO COACH VALUES(310,210,'Nate McMillan',1381,739,642,0.535);
	INSERT INTO COACH VALUES(311,211,'Stephen Silas',166,39,127,0.235);
	INSERT INTO COACH VALUES(312,212,'Billy Donovan',567,326,241,0.575);

## Use Cases
          

### 1. Which players are playing for the team with the highest srs?

SQL Statement:
	SELECT Player_Name, MAX(SRS)
	FROM Player p
	JOIN Team  ON Team_Name = TEAM
	GROUP BY Team_Name;
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_1%20(1).png)



### 2. Which player has the highest field goal percentage for a season and represents which team?

SQL Statement:
	SELECT PLayer, MAX(Effective_Field_Goal_Percentage), Team_Name
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_2%20(1).png)

	


### 3. Which players have the 3 pointer percentage greater than 0.4 and which team they belong to?

SQL Statement:
	SELECT PLayer, 3_Points_Percentage, Team_Name
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	WHERE 3_Points_Percentage > 0.4;
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_3%20(1).png)



### 4. Which team has players of age group 25 to 30 and what are their particular points?

SQL Statement:
	SELECT PLayer, Age, Team_Name
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	WHERE Age between 25 AND 30;
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_4%20(1).png)



### 5.  Which all players are playing at centre position for the team?

SQL Statement:
	SELECT PLayer, position, Team_Name
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	WHERE position = 'C' 
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_5%20(1).png)



### 6.	Which player has the highest minutes played and for which team?

SQL Statement:
	SELECT PLayer, Team_Name, MAX(Minutes_Played)
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_6%20(1).png)



### 7. Which all players are playing at power forward position for the team with highest srs?

SQL Statement:
	SELECT DISTINCT(PLayer), Team_Name, MAX(SRS) 
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	WHERE position = 'PF' ; 
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_7%20(1).png)




### 8. Which is the youngest player who has played the most games?

SQL Statement:
	SELECT DISTINCT(PLayer), MIN(Age), MAX(Game)
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team;
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_8%20(1).png)



### 9.  Which all teams have srs greater than 3 and who all are playing under them?
 
SQL Statement:
	SELECT DISTINCT(PLayer),SRS
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	WHERE SRS > 3;

![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_9%20(1).png)



### 10.  Which players have the highest points from each team?

SQL Statement:
	SELECT DISTINCT(PLayer),MAX(Points), Team
	FROM Player_Stats 
	JOIN Player ON Player = Player_Name
	JOIN Team  ON Team_Name = Team
	GROUP BY Team
	
	
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/UC_10%20(1).png)

## Views

### 1.Which players are playing for the team with highest srs?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_1.png)

### 2.Which player has the highest field goal percentage for a season and represents which team?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_2.png)

### 3.Which players have a 3 pointer percentage greater than 0.4 and which team they belong to?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_3.png)

### 4.Which team has players of age group 25 to 30 and what are their particular points?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_4.png)

### 5.Which all players are playing at Power Forward position for the team?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_5.png)

### 6.Which player has the highest minutes played and for which team?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_6.png)

### 7.Which all players are playing at Shooting Guard position for the team with highest srs?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_7.png)

### 8.Which is the youngest player who has played the most games?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_8.png)

### 9.Which all teams have srs greater than 3 and who all are playing under them?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_9.png)

### 10.Which players have the highest points from each team?
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/V_10.png)

## Sample data from all tables

### Player table:
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/Player.png)


### Coach Table:
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/Coach.png)


### Player_stats Table:
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/Player_Stats.png)


### Stadium Table:
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/Stadium.png)


### Team Table: 
![image](https://github.com/SwapnilBhasgauri21/DMDD_Final_Project/blob/master/Images/Team.png)
