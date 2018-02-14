# Function-Sql-Server
Fungsi Fungsi Sql server yang sangat penting


Pencarian SQL SP 

**Pencarian SP Berdasarkan Nama TABLE**

`SELECT 
    '-------------------------------------'  + CHAR(13) + CHAR(10) +
    'DROP ' + IIF(o.type = 'P', 'PROCEDURE', 'VIEW') + ' [' + s.name + '].[' + o.name + ']'  + CHAR(13) + CHAR(10) +
    'GO' + CHAR(13) + CHAR(10) +
    REPLACE(REPLACE([definition],'HOST_PROD','HOST_1'),'LOYALTY_PROD','LOYALTY_1') + CHAR(13) + CHAR(10) +
    'GO' + CHAR(13) + CHAR(10)
FROM sys.sql_modules m
INNER JOIN sys.objects o ON m.object_id = o.object_id
INNER JOIN sys.schemas s ON o.schema_id = s.schema_id
WHERE o.[type] IN ('P','V')
AND [definition] LIKE '%NAME TABLE%' OR [definition] LIKE '%NAME TABLE%'`


** Pencarian SP Berdasarkan Tanggal **

`SELECT 
    '-------------------------------------'  + CHAR(13) + CHAR(10) +
    'DROP ' + IIF(o.type = 'P', 'PROCEDURE', 'VIEW') + ' [' + s.name + '].[' + o.name + ']'  + CHAR(13) + CHAR(10) +
    'GO' + CHAR(13) + CHAR(10) +
    REPLACE(REPLACE([definition],'HOST_PROD','HOST_1'),'LOYALTY_PROD','LOYALTY_1') + CHAR(13) + CHAR(10) +
    'GO' + CHAR(13) + CHAR(10)
FROM sys.sql_modules m
INNER JOIN sys.objects o ON m.object_id = o.object_id
INNER JOIN sys.schemas s ON o.schema_id = s.schema_id
WHERE o.[type] IN ('P','V')
AND create_date LIKE '%2018%' OR create_date LIKE '%2018%'`
