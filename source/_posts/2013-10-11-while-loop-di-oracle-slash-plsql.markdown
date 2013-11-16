---
layout: post
title: "While Loop di Oracle/PLSQL"
date: 2013-10-11 12:11
comments: true
categories: ["oracle","pl/sql"]
---

Sintaks untuk `while loop` di oracle seperti ini:

```sql
WHILE condition
LOOP
   {.statements.}
END LOOP;
```

Kita menggunakan `while loop` ketika kita tidak yakin berapa kali kita akan meng-eksekusi `loop body`. Karena `while condition` di evaluasi sebelum masuk ke dalam `loop`, ini memungkinkan `loop body` tidak akan di eksekusi sama sekali.

Contoh: kita akan membuat function yang berfungsi untuk mencari posisi terakhir dari karakter `x` dari suatu `String`.

```sql
CREATE OR REPLACE FUNCTION LAST_INDEX(P_STRING IN VARCHAR2, P_CHAR IN VARCHAR2)
    RETURN NUMBER DETERMINISTIC
  AS
    V_INDEX         NUMBER;
    V_START         NUMBER;
  BEGIN

    V_START :=1;
    SELECT INSTR(P_STRING, P_CHAR, V_START) 
      INTO V_INDEX
    FROM DUAL;

    WHILE V_INDEX <> 0
    LOOP
      V_START := V_INDEX;
      SELECT INSTR(P_STRING, P_CHAR, V_START+1) 
        INTO V_INDEX
      FROM DUAL;      
    END LOOP;

    RETURN V_START;
  END;
```

test:

```sql
SELECT LAST_INDEX('123X567X89X123','X') FROM DUAL;
```

result:

```
11
```