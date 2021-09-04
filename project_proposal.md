### Project Proposal of EDA project

#### Question/need:
* What is the framing question of your analysis, or the purpose of the model/system you plan to build? 
  * identifing the busiest stations and hours
* Who benefits from exploring this question or building this model/system?
  * Clients who would like to place street teams at entrances to subway stations

#### Data Description:
* What dataset(s) do you plan to use, and how will you obtain the data?
  *  [MTA turnstile data](http://web.mta.info/developers/turnstile.html) from 5/29/2021 to 9/3/2021
  *  Ingesting the raw data into a SQL database by provided file "get_mta.py"
* What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?
  * 
* If modeling, what will you predict as your target?

#### Tools:
* How do you intend to meet the tools requirement of the project? 
  * Ingesting the raw data into a SQL database by provided file "get_mta.py"
  * Using required libraries which are sqlalchemy, pandas, matplotlib and seaborn
* Are you planning in advance to need or use additional tools beyond those required?
  * No, I may dicover the need during the project 

#### MVP Goal:
* What would a minimum viable product (MVP) look like for this project?
  * The busiest stations and hours
