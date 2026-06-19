SELECT * FROM analysis_fmcsa.`sms_input_-_crash_20260609`;

SELECT *
FROM analysis_fmcsa.`sms_input_-_crash_20260609`
WHERE fatalities > 1;

SELECT *
FROM analysis_fmcsa.`sms_input_-_crash_20260609`
WHERE Vehicle_License_State = 'IN';

SELECT *
FROM analysis_fmcsa.`sms_input_-_crash_20260609`
WHERE Report_State = 'IN' AND Fatalities > 1 AND Light_Condition_Desc = 'Daylight';

SELECT Report_Number, DOT_Number, Report_Date, Report_State, Fatalities, Injuries, Tow_Away, Vehicle_License_number, Vehicle_License_State 
FROM analysis_fmcsa.`sms_input_-_crash_20260609`
WHERE Vehicle_License_State = 'IL' AND Fatalities >= 1
ORDER BY DOT_Number, Vehicle_License_number, Report_Date;
