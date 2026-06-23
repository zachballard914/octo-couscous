SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn` to `Violation Code`;
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[0]` to `Type`;
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[1]` to `Violation Description`; 
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[2]` to `# of Inspections`;    
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[3]` to `# of Violations`;
    
SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[4]` to `% of Total Violations`;
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[5]` to `# of OOS Violations`;
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
	RENAME COLUMN `MyUnknownColumn_[6]` to `% OOS Percent`;
    
SELECT * FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Code` = 'Violation Code';

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
LIMIT 5;

DESCRIBE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Code` = 'Violation Code';

DELETE FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Code` = 'Violation Code'
	AND `Type` = 'Type'
    AND `Violation Description` = 'Violation Description';
    
SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
LIMIT 5;

SELECT `Violation Description`, COUNT(`Violation Description`)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
GROUP BY `Violation Description`
HAVING COUNT(`Violation Description`) > 1;

SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Description` = 'Weight carried exceeds tire load limit';

SELECT
	`Violation Code`,
    `Violation Description`,
    COUNT(*) AS cnt
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
GROUP BY
	`Violation Code`,
    `Violation Description`
HAVING COUNT(*) > 1;

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Description` IS NULL
	OR `Violation Code` = '';
    
DELETE FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Violation Code` IS NULL
	OR `Violation Code` = '';
    
SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT `# of Inspections`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Inspections` NOT REGEXP '^[0-9]+$';   

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Inspections` NOT REGEXP '^[0-9]+$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Inspections` NOT REGEXP '^[0-9]+$';

DELETE FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Inspections` NOT REGEXP '^[0-9]+$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Inspections` NOT REGEXP '^[0-9]+$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of Violations` NOT REGEXP '^[0-9]+$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `# of OOS Violations` NOT REGEXP '^[0-9]+$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `% of Total Violations` NOT REGEXP '^[0-9]+(\\.[0-9]+)?$';

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `% OOS Percent` NOT REGEXP '^[0-9]+(\\.[0-9]+)?$';

SELECT `% OOS Percent`, `% of Total Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
LIMIT 10;

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE REPLACE(`% OOS Percent`, '%', '') NOT REGEXP '^[0-9]+(\\.[0-9]+)?$' ;

SELECT COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE REPLACE(`% of Total Violations`, '%', '') NOT REGEXP '^[0-9]+(\\.[0-9]+)?$';

UPDATE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
SET `% OOS Percent` = REPLACE(`% OOS Percent`, '%', ''),
    `% of Total Violations` = REPLACE(`% of Total Violations`, '%', '');
    
ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
MODIFY COLUMN `% OOS Percent` DECIMAL(8,3),
MODIFY COLUMN `% of Total Violations` DECIMAL(8,3);

ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
MODIFY COLUMN `# of Inspections` INT,
MODIFY COLUMN `# of Violations` INT,
MODIFY COLUMN `# of OOS Violations` INT;

DESCRIBE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT
    MIN(`Roadside Inspection Violations All Violations`),
    MAX(`Roadside Inspection Violations All Violations`),
    COUNT(*)
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT
    COUNT(*) AS total_rows,
    COUNT(DISTINCT `Roadside Inspection Violations All Violations`) AS unique_ids
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;

SELECT *
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Roadside Inspection Violations All Violations` IS NULL
   OR `Roadside Inspection Violations All Violations` = '';   

ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
MODIFY COLUMN `Roadside Inspection Violations All Violations` INT;

ALTER TABLE oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ADD PRIMARY KEY (`Roadside Inspection Violations All Violations`);

SELECT `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ORDER BY `# of Violations` DESC;

SELECT `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ORDER BY `# of OOS Violations` DESC;

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ORDER BY `# of OOS Violations` DESC;

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ORDER BY `# of Violations` DESC;

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
ORDER BY `# of OOS Violations` DESC;

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Type` = 'Vehicle';

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Type` = 'Driver';

SELECT `Type`, `Violation Description`, `# of Violations`, `# of OOS Violations`
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
WHERE `Type` = 'Other';

SELECT Type,
    SUM(`# of Violations`) AS total_violations
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
GROUP BY Type
ORDER BY total_violations DESC;

SELECT Type,
    SUM(`# of Violations`) AS total_violations,
    SUM(`# of OOS Violations`) AS total_oos_violations
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025
GROUP BY Type;

SELECT * 
FROM oos_violations_in_the_us.roadside_inspection_violations_all_violations_2025;
