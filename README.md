# 📚 Datenbank Modul Lernportfolio

Dieses Lernportfolio dokumentiert die wesentlichen Inhalte und gelernten Konzepte des Datenbank Moduls.

---

## 📅 Lektion vom 13.05.2025: Grundlagen & Datenmodellierung

Einführung in SQL und relationale Datenbanken. Fokus auf die Konzepte der Datenmodellierung (ERM, ERD, Physisches Modell) und die Bedeutung der Normalisierung (1NF, 2NF, 3NF) zur Reduzierung von Redundanzen und Sicherung der Datenqualität. Erste Schritte mit Tools wie MySQL Workbench.

---

## 📅 Lektion vom 20.05.2025: DDL, DBMS & Physikalische Modellierung

Vertiefung der Datenmodellierung mit Generalisierung/Spezialisierung und Beziehungsarten (Identifying vs. Non-Identifying Relationships). Einführung in Datenbank Management Systeme (DBMS) und ihre Funktionen. Praktische Anwendung der Data Definition Language (DDL) zur Erstellung und Änderung von Datenbankschemata und Tabellen.

**Wichtige DDL-Befehle:**

| Befehl           | Beschreibung                                   | Beispiel                       |
| :--------------- | :--------------------------------------------- | :----------------------------- |
| `CREATE SCHEMA`  | Erstellt eine neue Datenbank                   | `CREATE SCHEMA mydb;`          |
| `CREATE TABLE`   | Erstellt eine neue Tabelle                     | `CREATE TABLE users (...);`    |
| `DROP TABLE`     | Löscht eine Tabelle                            | `DROP TABLE users;`            |
| `ALTER TABLE`    | Ändert die Struktur einer Tabelle              | `ALTER TABLE users ADD col;`   |
| `INSERT INTO`    | Fügt Daten in eine Tabelle ein (DML-Grundlage) | `INSERT INTO users VALUES(...);` |

---

## 📅 Lektion vom 27.05.2025: Komplexe Beziehungen & DML/DQL Grundlagen

Behandlung fortgeschrittener Beziehungstypen wie rekursive Hierarchien und das Stücklistenproblem. Wiederholung und Anwendung der Data Manipulation Language (DML) für Dateneingabe, -aktualisierung und -löschung sowie der Data Query Language (DQL) für grundlegende Datenabfragen.

## Darstellung von Datenbankbeziehungen
![Datenbank](https://github.com/user-attachments/assets/99269833-8e38-41a2-8e25-cfcb1c2d52b6)


**Wichtige Befehle/Konzepte:**

-   **Rekursive Beziehungen:** Abbildung von Hierarchien innerhalb einer Tabelle.
-   **DML:**
    ```sql
    INSERT INTO table_name (col1) VALUES (val1);
    UPDATE table_name SET col1 = new_val WHERE condition;
    DELETE FROM table_name WHERE condition;
    ```
-   **DQL:**
    ```sql
    SELECT col1, col2 FROM table_name WHERE condition ORDER BY col1;
    ```

---

## 📅 Lektion vom 03.06.2025: Referentielle Integrität & JOINs

Fokus auf die Implementierung von Constraints (`NOT NULL`, `UNIQUE`, `FOREIGN KEY`) zur Sicherstellung der referentiellen Integrität. Verbindung zur Mengenlehre für ein tiefes Verständnis von `JOIN`-Operationen und deren Anwendung zur Abfrage über mehrere Tabellen.

**Wichtige Konzepte & JOIN-Typen:**

-   **Referentielle Integrität:** Sicherstellung der Konsistenz von Referenzen zwischen Tabellen.
-   **Constraints:**
    -   `PRIMARY KEY` (PK)
    -   `FOREIGN KEY` (FK)
    -   `NOT NULL` (NN)
    -   `UNIQUE` (UQ)
-   **JOINs:**
    -   `INNER JOIN`: Schnittmenge (nur übereinstimmende Zeilen)
    -   `LEFT JOIN`: Alle Zeilen von links, passende von rechts
    -   `RIGHT JOIN`: Alle Zeilen von rechts, passende von links

---

## 📅 Lektion vom 10.06.2025: Datenintegrität & Aggregatsfunktionen

Behandlung von Datenlöschstrategien in professionellen Datenbanken (`ON DELETE` Regeln) und deren Einfluss auf die Datenintegrität. Vertiefung fortgeschrittener `SELECT`-Operationen, insbesondere Aggregatsfunktionen, Gruppierung (`GROUP BY`) und Filterung aggregierter Ergebnisse (`HAVING`).

**Wichtige Befehle/Konzepte:**

-   **`ON DELETE` Optionen:** `NO ACTION`, `RESTRICT`, `CASCADE`, `SET NULL`
-   **Aggregatsfunktionen:** `COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`
-   **Datenaggregation:**
    ```sql
    SELECT category, COUNT(*) AS total_items
    FROM products
    GROUP BY category
    HAVING COUNT(*) > 10;
    ```
-   **SELECT-Klausel Reihenfolge (MERKSATZ):** `SELECT > FROM > JOIN > WHERE > GROUP BY > HAVING > ORDER BY > LIMIT`

---

## 📅 Lektion vom 17.06.2025: Subqueries & Datenimport

Einsatz von Subqueries (skalare und nicht-skalare Unterabfragen) zur dynamischen Datenfilterung. Effizienter Massenimport von Daten mit `LOAD DATA INFILE`, inklusive Anpassungen für CSV-Daten (Datumsformate, Spaltenmanagement). Erste Schritte zur Normalisierung einer importierten Datenbank (z.B. `db_adressen`) in 3NF.

**Wichtige Befehle/Konzepte:**

-   **Subqueries:**
    -   Skalar: `WHERE col = (SELECT ...)`
    -   Nicht-skalar: `WHERE col IN (SELECT ...)`
-   **Datenimport:**
    ```sql
    LOAD DATA LOCAL INFILE 'path/file.csv'
    INTO TABLE my_table
    FIELDS TERMINATED BY ','
    LINES TERMINATED BY '\r\n'
    IGNORE 1 ROWS;
    ```
-   **Datenübertragung:** `INSERT INTO target_table SELECT ... FROM source_table;`

---

## 📅 Lektion vom 24.06.2025: Datensicherung & Projektarbeit

Umfassende Konzepte der Datensicherung (logisch/physisch, Voll-/Differentiell/Inkrementell) und praktische Anwendung von Tools wie `mysqldump` für Backups und Restores. Anwendung aller bisher gelernten Konzepte zur Normalisierung einer komplexeren Datenbank (`db_freifaecher`) und deren Befüllung/Validierung.

**Wichtige Befehle/Konzepte:**

-   **Logisches Backup:** `mysqldump -u user -p db_name > backup.sql`
-   **Restore:** `mysql -u user -p < backup.sql`
-   **Datenexport:**
    ```sql
    SELECT col1, col2
    INTO OUTFILE 'path/outfile.csv'
    FIELDS TERMINATED BY ','
    LINES TERMINATED BY '\r\n';
    ```

---

## 📅 Lektion vom 01.07.2025:
