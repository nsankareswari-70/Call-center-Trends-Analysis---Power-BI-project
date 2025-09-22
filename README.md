### Call-center-Trends-Analysis---Power-BI-project
### Project Introduction

This project focuses on analyzing call center performance using Power BI. A raw call center dataset was imported, transformed, and cleaned to ensure accuracy and consistency. Data types for all columns were verified, and a new DateTime column was created by combining the existing Date and Time fields, enabling more precise time-based analysis.

To gain deeper insights into call center operations, several DAX measures were created, including:

Total Calls to track overall call volume.

Calls Resolved / Not Resolved to measure service effectiveness.

Calls Answered vs. Not Answered for operational efficiency.

Average Talk Duration and Response Time to evaluate service speed.

Calls Resolved % and Satisfaction Ratio to assess customer experience.

Number of Calls per Hour to identify peak activity periods.

By combining these KPIs, the dashboard provides a comprehensive view of call center performance, highlighting efficiency, responsiveness, and customer satisfaction. This enables data-driven decision-making to improve overall service quality and optimize resource allocation.

Import Call center Data set to Power BI
Transform and clean the data - Check all the columns and their data types. 
Add a custom column DateTime by combining the two column Date and Time    
Creating Measures:     
Totalcalls = DISTINCTCOUNT('Call-Center-Dataset'[Call ID])        
CallsResolved = CALCULATE(count('Call-Center-Dataset'[Call ID]),'Call-Center-Dataset'[Resolved]="Y")     
Callsnotresolved = divide([callsNotAnswered],[Totalcalls])*100   
AvgTalkDuration = divide([Totaltalkduration],[TotalcallsAnswered],0)   
callsNotAnswered = calculate(count('Call-Center-Dataset'[Call ID]),'Call-Center-Dataset'[Answered (Y/N)]="N")    
Callsresolved% = divide([CallsResolved],[TotalcallsAnswered],0)*100    
NumberofcallsperHour = divide([TotalcallsAnswered],[SumofHour],0)   
ResponseTime = AVERAGE('Call-Center-Dataset'[Speed of answer in seconds])    
SatRatio = divide([sumsat],count('Call-Center-Dataset'[Satisfaction rating])*5,0)*100   
SumofHour = sum('Call-Center-Dataset'[Hour])   
sumsat = sum('Call-Center-Dataset'[Satisfaction rating])    
TotalcallsAnswered = calculate(count('Call-Center-Dataset'[Call ID]),'Call-Center-Dataset'[Answered (Y/N)]="Y")   
Totaltalkduration = sum('Call-Center-Dataset'[Talkduration])
Here is the screenshot of the Dashboard. For more details and to experience the interactive view, please check out my CallCenterTrendAnalysis.pbix file.
![img alt](https://github.com/nsankareswari-70/Call-center-Trends-Analysis---Power-BI-project/blob/8feb68c9a8710658255e539a7cc693ce17c0ea75/calla1.png)
