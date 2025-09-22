### Call-center-Trends-Analysis---Power-BI-project
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

