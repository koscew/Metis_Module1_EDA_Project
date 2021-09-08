### Project Proposal of EDA project
Chien Yuan Chang
#### Question/need:
We're going to identify the busiest subway entrances and hours among MTA stations in New York City with the highest entires and exits between March and May in 2021 for the client, WomenTechWomenYes (WTWY), to place street teams at entrances to subway stations to promote their gala at the beginning of the summer to fill the event space with individuals passionate about increasing the participation of women in technology, and also to concurrently build awareness and reach efficiently.

>* What is the framing question of your analysis, or the purpose of the model/system you plan to build? 
>* Who benefits from exploring this question or building this model/system?

#### Data Description:
* Dataset: Using python pandas to obtain public [MTA turnstile data](http://web.mta.info/developers/turnstile.html) to ingest the raw data from 2/27/2021 to 6/4/2021.

* An individual sample/unit (total 11 columns):
C/A,UNIT,SCP,STATION,LINENAME,DIVISION,DATE,TIME,DESC,ENTRIES,EXITS  
A002,R051,02-00-00,59 ST,NQR456W,BMT,03/01/2021,03:00:00,REGULAR,0007537860,0002570718
TEXT,TEXT,TEXT,TEXT,TEXT,TEXT,TEXT,TEXT,TEXT,INTERGER,INTERGER

* Expected characteristics/features to work with:
  * C/A: Control Area
  * UNIT: Remote Unit for a station
  * SCP: Subunit Channel Position, an specific address for a device
  * STATION: The station name the device is located at
  * DATE: The date (MM-DD-YY)
  * TIME: The time for a scheduled audit event by every 4 hours
  * ENTRIES: The cumulative entry register value for a device
  * EXIST: The cumulative exit register value for a device

>* What dataset(s) do you plan to use, and how will you obtain the data?
>* What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

#### Tools:
* Pandas for ingesting the raw data from [MTA turnstile data](http://web.mta.info/developers/turnstile.html) into csv file
* SQLite3 for creating database and table and importing csv into table
* Python SQLAlchemy for querying from the database into Python
* Python Pandas for exploratory data analysis
* Python matplotlib and seaborn for data visualization
* Other Python libraries if needed

>* How do you intend to meet the tools requirement of the project? 
>* Are you planning in advance to need or use additional tools beyond those required?

#### MVP Goal:
* Top 10 stations with the highest sum of entires and exits
* The hours with the sum of entires and exits 

>* What would a minimum viable product (MVP) look like for this project?