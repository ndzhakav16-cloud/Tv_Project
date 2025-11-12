SELECT* FROM workspace.default.bright_tv_viewership_1;

 SELECT
 
 --EXTRACTING THE TABLE TO SEE ALL THE COLUMN AND ROWS 
 
 SELECT* bright_tv_viewership_1;

----HAVING 2 COLUMN AND YOU WANT TO CHECT IT EFFECIENCY.

SELECT bright_tv_viewership_1
       WHERE userid IS NULL;

SELECT bright_tv_viewership_1
      WHERE USERID IS NULL;

----CHECKING IF SQL IS READING IT THE SAME WAY

SELECT  
	USERID,
    userid
     
FROM bright_tv_viewership_1;

---Checking the Rows if Are Equall

SELECT COUNT*
			FROM bright_tv_viewership_1;


--Then now checking if any of this column (USERID OR userid) has NULL value, then it must exract the other userid with no NULL.

SELECT COALESCE(USERID,userid) AS userid
	 FROM workspace.default.bright_tv_viewership_1;
	 

----Remember we have a RecordDate2- that is not in a DATE Formant Is in a STRING, then we must convert it to a Date by coding a TIMESTAMP 
and Create a new column called Watch Time, by extrcting the time from the RecordDate2	 

1.---Converting to TIMESTAMP
SELECT 
	USERID,
	Channel2,
	Duration2,
	RecordDate2 ,
	
	TO_TIMESTAMP(RecordDate2,'MM/DD/YYYY HH24:MI') AS RecordDate (SQL Planform)
	
	FROM workspace.default.bright_tv_viewership_1;

-----Extracting onnly the Time Part

SELECT
	USERID,
	Channel2,
	Duration2,
	RecordDate2 

     TO_CHAR(TO_TIMESTAMP(RecordDate2,'MM/DD/YYYY HH24:MI:SS'),'HH24:MI:SS') AS Watch_STARTING_TIME(SQL Planform)
	  
	---- Converting to TIMESTAMP Extracting onnly the Time Part (DATABRICKS Planform)
	 
SELECT 
  *,
  try_to_timestamp( RecordDate2, 'yyyy/MM/dd HH:mm' ) RecordDate,
  date_format(
  try_to_timestamp (RecordDate2, 'yyyy/MM/dd HH:mm' ),'HH:MM,SS') AS Wacth_Staring_Time

FROM workspace.default.bright_tv_viewership_1;

----Checking each column and Cleaning DATA OF Viewership

SELECT

    CASE 
        WHEN channel2 = 'None' THEN 'Unknown' 
        WHEN channel2 IS NULL THEN 'Unknown' 
        ELSE channel2
    END AS Channel2
 FROM workspace.default.bright_tv_viewership_1;
 
 
 SELECT   
    CASE 
        WHEN RecordDate2 IN ('None', 'other') THEN 'Unknown' 
        WHEN RecordDate2 IS NULL THEN 'Unknown' 
        ELSE  RecordDate2
    END AS RecordDate2
 FROM workspace.default.bright_tv_viewership_1;
 

 
 SELECT
    CASE  
        WHEN Duration2 IS NULL THEN 'Unknown' 
        ELSE Duration2
    END AS Duration2
  
 FROM workspace.default.bright_tv_viewership_1;
