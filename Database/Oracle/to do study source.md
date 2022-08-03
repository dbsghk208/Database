
## 2022.08.03

```sql
  SELECT TO_CHAR(SYSDATE, 'YYYY') - LEVEL + t.max_yaer AS code
        ,TO_CHAR(SYSDATE, 'YYYY') - LEVEL + t.max_yaer AS name
        FROM (
            SELECT TO_NUMBER(NVL(lv.meaning, 2012)) AS start_year
                  ,TO_NUMBER(NVL(lv.attribute1, 5)) AS max_yaer
              FROM ad_lookup_values lv
             WHERE lv.lookup_type  = 'YEAR_COMBO'
               AND lv.lookup_code  = 'YEAR'
               AND lv.enabled_flag = 'Y'
             UNION   
           
           /* 기본 설정 정보가 없을 경우 */             
            SELECT 2012 AS start_year   
                  ,5    AS max_yaer
              FROM dual
             WHERE 1 = 1
               AND NOT EXISTS ( SELECT 1
                                  FROM ad_lookup_values lv
                                 WHERE lv.lookup_type  = 'YEAR_COMBO'
                                   AND lv.lookup_code  = 'YEAR'
                                   AND lv.enabled_flag = 'Y')
             ) t
        CONNECT BY LEVEL <= ((TO_CHAR(SYSDATE, 'YYYY') + t.max_yaer) - t.start_year) 
        ;
```



```sql

SELECT
    to_char(add_months(SYSDATE, (LEVEL - 1) * 12 * -1), 'yyyy') code
    FROM dual CONNECT BY LEVEL  <= 3 
    ;

```
