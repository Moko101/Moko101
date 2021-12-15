- 👋 Hi, I’m @Moko101
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Moko101/Moko101 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.

--->
SQL Querys
--delined accounts 
SELECT * 
FROM WORKFLOW.ADVERSE_ACTION_REASONS
WHERE LOCATORID = 'USU459Y53'

--limbo accounts 
SELECT
CASE
WHEN lcd.CREATEBYUSERID = 164 THEN 'Bradley'
WHEN lcd.CREATEBYUSERID = 172 THEN 'Luke'
WHEN lcd.CREATEBYUSERID = 155 THEN 'Mikael'
WHEN lcd.CREATEBYUSERID = 154 THEN 'Albert'
WHEN lcd.CREATEBYUSERID = 169 THEN 'Remmie L'
WHEN lcd.CREATEBYUSERID = 175 THEN 'Patrick'
WHEN lcd.CREATEBYUSERID = 13 THEN 'Jorjia'
WHEN lcd.CREATEBYUSERID = 165 THEN 'Alisha'
WHEN lcd.CREATEBYUSERID = 163 THEN 'Samuel'
WHEN lcd.CREATEBYUSERID = 177 THEN 'Lewis'
WHEN lcd.CREATEBYUSERID = 179 THEN 'Diamond'
WHEN lcd.CREATEBYUSERID = 181 THEN 'Tennisha'
WHEN lcd.CREATEBYUSERID = 1 THEN 'Superadmin'
WHEN lcd.CREATEBYUSERID = 121 THEN 'Rebecca'
END AS OpsAgent,
lcd.locatorID,
lcd.CREATEDATE,
lcd.createbyuserID
FROM ANALYTICS.LATESTCREDITDECISION lcd
WHERE lcd.decision = 'In Progress'
AND lcd.automateddecision = 'FALSE'
AND lcd.starrating IS NULL
AND lcd.everapproved = 1

--accounts approved and industry
SELECT
LOCATORID,
APPLICATIONDATE,
AMOUNTAPPROVED,
INDUSTRYCATEGORY FROM ANALYTICS.APPLICATIONMASTER
WHERE offer = 'Approved'
AND INDUSTRYCATEGORY = 'Adult Entertainment, Gambling & Nightclubs'
