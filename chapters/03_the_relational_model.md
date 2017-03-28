# The Relational Model

## Definitions

* **Data Definition Language** :

    * Data Definition Language (DDL) features of SQL, the standard language for creating, manipulating, and querying 
    data in a relational DBMS.
    
    * The subset of SQL that supports the creation, deletion, and modification of tables is called the Data 
    Definition Language (DDL).
    
* **Relation** :

    A relation consists of a relation schema and a relation instance. The SQL language standard uses the word table 
    to denote relation, and we often follow this convention when discussing SQL.
    
* **Relation Schema** :

    Relation schema describes the column heads for the table. The schema specifies the relation's name, the name of 
    each field (or column, or attribute), and the domain of each field. A domain is referred to in a relation schema 
    by the domain name and has a set of associated values. Field named sid has a domain named string. It is clear 
    that every student record should satisfy domains constraint.
    
```console
    Students(sid: string, name: string, login: string, age: integer, gpa: real)
```

* **Relation Instance** :

    The relation instance is a table, An instance of a relation is a set of tuples, also called records, in which 
    each tuple has the same number of fields as the relation schema. A relation instance can be thought of as a table
     in which each tuple is a row, and all rows have the same number of fields. (The term relation instance is often 
     abbreviated to just relation) An instance of the Students relation appears in below Figure. 
    \coloredtext{red}{Note that no two rows are identical. This is a requirement of the relational model each 
    relation is defined to be a set of unique tuples or rows.}[^sample-footnote]
    
|**sid** | **name** | **login** | **age** | **gpa** |
|--------|----------|-----------|---------|---------|
| 53666 | منگول | mangul@shangulabad.com | 18 | 3.5 |
| 53686 | شنگول | shangul@shangulabad.com | 17 | 3.2 |
| 53662 | حبه انگور‍ | habbeangura@shangulabad.com | 13 | 2.8 |
| 53659 | مامان بزی | mamanbozi@shangulabad.com | 24 | 3.9 |
| 53646 | بابا بزی | bababozi@shangulabad.com | 28 | 1.4 |

## Unimportant Definitions

**Degree** : The degree, also called arity, of a relation is the number of fields. Degree of Student table is 5.

**Cardinality** : The cardinality of a relation instance is the number of tuples in it. Cardinality of Student table 
is 6.

**Relational Database** : A relational database is a collection of relations with distinct relation names. 

**Relational Database Schema** : The relational database schema is the collection of schemas for the relations in the 
database.
    
**Instance of Relational Database** : An instance of a relational database is a collection of relation instances, one 
per relation schema in the database schema.
    
\coloredtext{red}{TODO: provide example used SQL field number rather than name.}

## Useful SQL Queries

\begin{codelisting}
\codecaption{Creat Table}
\label{code:hello}
```sql
CREATE TABLE Students ( sid CHAR(20), name CHAR(30), login CHAR(20),
                        age INTEGER, gpa REAL )
```
\end{codelisting}

\begin{codelisting}
\codecaption{Insert with list of column names}
\label{code:hello}
```sql
INSERT
INTO Students (sid, name, login, age, gpa)
VALUES (53688, 'Smith', 'smith@ee', 18, 3.2)
```
\end{codelisting}

\begin{codelisting}
\codecaption{Insert without list of column names}
\label{code:hello}
```sql
INSERT 
INTO Students
VALUES (53688, 'Smith', 'smith@ee', 18, 3.2)
```
\end{codelisting}

\begin{codelisting}
\codecaption{Delete all Students tuples with name equal to 'Smith'}
\label{code:hello}
```sql
DELETE
FROM Students S
WHERE S.name = 'Smith'
```
\end{codelisting}

\begin{codelisting}
\codecaption{}
\label{code:hello}
```sql
UPDATE Students S
SET S.age = S.age + 1, S.gpa = S.gpa - 1 
WHERE S.sid = 53688
```
\end{codelisting}

This example illustrate some important points. The WHERE clause is applied first and determines which rows are to 
be modified. The SET clause then determines how these rows are to be modified. If the column being modified is also 
used to determine the new value, the value used in the expression on the right side of equals (=) is the old value, 
that is, before the modification.


\begin{codelisting}
\codecaption{}
\label{code:hello}
```sql
```
\end{codelisting}

[^sample-footnote]: In practice, commercial systems allow tables to have duplicate rows, but we assume that a relation is indeed a set of tuples unless otherwise noted.
