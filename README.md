# postwork4
(none)> show databases;
+--------------------+
| Database           |
+--------------------+
| ANDREA             |
| Adrii_Merlin       |
| FranciscoGarcia_DB |
| Jazmin             |
| Lilia              |
| ROSS               |
| Rosalia            |
| Rosalia_TP         |
| Sam                |
| Sergio             |
| Zamby              |
| information_schema |
| janet              |
| maria              |
| mysql              |
| performance_schema |
+--------------------+

16 rows in set
Time: 0.184s

SE SELECCIONA LA BASE DE DATOS DONDE SE VA A TRABAJAR


(none)> use Rosalia_TP;
You are now connected to database "Rosalia_TP" as user "root"
Time: 0.080s
Rosalia_TP> show tables;
+----------------------+
| Tables_in_Rosalia_TP |
+----------------------+
| VANILLA_TP           |
| ranking              |
+----------------------+
2 rows in set
Time: 0.176s
Rosalia_TP> load data local infile "C:/Users/USER/Desktop/Mi_Proyecto/sesion03/
            Mis_Datos/cwurData.csv" into table ranking fields terminated by ","
            ;
Query OK, 1001 rows affected
Time: 2.743s
Rosalia_TP> select
(1064, "You have an error in your SQL syntax; check the manual that corresponds
to your MariaDB server version for the right syntax to use near '' at line 1")
Rosalia_TP> select *from ranking;
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+
| world_rank | institution                    | country              | national_
rank | quality_of_education | alumni_employment | quality_of_faculty | publicati
ons | influence | citations | broad_impact | patents | score | year_ |
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     |
| 1          | "Harvard University"           | USA                  | 1
     | 7                    | 9                 | 1                  | 1
    | 1         | 1         | 0            | 5       | 100   | 2012  |
| 2          | "Massachusetts Institute of Te | USA                  | 2
     | 9                    | 17                | 3                  | 12
    | 4         | 4         | 0            | 1       | 92    | 2012  |
| 3          | "Stanford University"          | USA                  | 3
     | 17                   | 11                | 5                  | 4
    | 2         | 2         | 0            | 15      | 90    | 2012  |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  |
| 5          | "California Institute of Techn | USA                  | 4
     | 2                    | 29                | 7                  | 37
    | 22        | 22        | 0            | 18      | 85    | 2012  |
| 6          | "Princeton University"         | USA                  | 5
     | 8                    | 14                | 2                  | 53
    | 33        | 26        | 0            | 101     | 83    | 2012  |
| 7          | "University of Oxford"         | United Kingdom       | 2
     | 13                   | 28                | 9                  | 15
    | 13        | 19        | 0            | 26      | 82    | 2012  |
| 8          | "Yale University"              | USA                  | 6
     | 14                   | 31                | 12                 | 14
    | 6         | 15        | 0            | 66      | 79    | 2012  |
1001 rows in set
Time: 0.950s
Rosalia_TP> select *from ranking where country="USA" LIMIT 10;
Reconnecting...
+------------+--------------------------------+---------+---------------+-------
---------------+-------------------+--------------------+--------------+--------
---+-----------+--------------+---------+-------+-------+
| world_rank | institution                    | country | national_rank | qualit
y_of_education | alumni_employment | quality_of_faculty | publications | influen
ce | citations | broad_impact | patents | score | year_ |
+------------+--------------------------------+---------+---------------+-------
---------------+-------------------+--------------------+--------------+--------
---+-----------+--------------+---------+-------+-------+
| 1          | "Harvard University"           | USA     | 1             | 7
               | 9                 | 1                  | 1            | 1
   | 1         | 0            | 5       | 100   | 2012  |
| 2          | "Massachusetts Institute of Te | USA     | 2             | 9
               | 17                | 3                  | 12           | 4
   | 4         | 0            | 1       | 92    | 2012  |
| 3          | "Stanford University"          | USA     | 3             | 17
               | 11                | 5                  | 4            | 2
   | 2         | 0            | 15      | 90    | 2012  |
| 5          | "California Institute of Techn | USA     | 4             | 2
               | 29                | 7                  | 37           | 22
   | 22        | 0            | 18      | 85    | 2012  |
| 6          | "Princeton University"         | USA     | 5             | 8
               | 14                | 2                  | 53           | 33
   | 26        | 0            | 101     | 83    | 2012  |
| 8          | "Yale University"              | USA     | 6             | 14
               | 31                | 12                 | 14           | 6
   | 15        | 0            | 66      | 79    | 2012  |
| 9          | "Columbia University"          | USA     | 7             | 23
               | 21                | 10                 | 13           | 12
   | 14        | 0            | 5       | 79    | 2012  |
| 11         | "University of Chicago"        | USA     | 9             | 15
               | 26                | 8                  | 34           | 20
   | 28        | 0            | 101     | 74    | 2012  |
| 12         | "Cornell University"           | USA     | 10            | 21
               | 42                | 14                 | 22           | 21
   | 16        | 0            | 10      | 74    | 2012  |
| 13         | "University of Pennsylvania"   | USA     | 11            | 31
               | 16                | 24                 | 9            | 10
   | 8         | 0            | 9       | 74    | 2012  |
+------------+--------------------------------+---------+---------------+-------
---------------+-------------------+--------------------+--------------+--------
---+-----------+--------------+---------+-------+-------+

10 rows in set
Time: 0.180s
Rosalia_TP> select count(*)from ranking where country="USA";
+----------+
| count(*) |
+----------+
| 204      |
+----------+
1 row in set
Time: 0.176s
Rosalia_TP> show tables;
+----------------------+
| Tables_in_Rosalia_TP |
+----------------------+
| VANILLA_TP           |
| ranking              |
+----------------------+
2 rows in set
Time: 0.106s




SE CREA UNA NUEVA TABLA CON LOS DATOS OROGINALES DEL ARCHIVO CSV DEL DATA SET DESCARGADO SOBRE RANKINGS DE UNIVERSIDADES 


Rosalia_TP> create table timesData(
            world_rank int primary key,
            university_name varchar (30),
            country varchar (20),
            teaching int,
            international int,
            research int,
            citations int,
            income int,
            total_score int,
            num_students int,
            student_staff_ratio int,
            international_students int,
            female_male_ratio int,
            year_ int);

Rosalia_TP> load data local infile "C:/Users/USER/Desktop/Mi_Proyecto/sesion03/
            Mis_Datos/timesData.csv" into table ranking fields terminated by ",
            ";
 SE COMOIENZAN HACER FILTARDOS CON LA FUNCION 
 SELECT FROM 
 
 
 
Rosalia_TP> select * from ranking order by patents asc;
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+
| world_rank | institution                    | country              | national_
rank | quality_of_education | alumni_employment | quality_of_faculty | publicati
ons | influence | citations | broad_impact | patents | score | year_ |
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     |
| 10         | "University of California      |  Berkeley"           | 0
     | 8                    | 16                | 52                 | 6
    | 6         | 5         | 3            | 0       | 16    | 79    |
| 19         | "University of California      |  Los Angeles"        | 0
     | 13                   | 62                | 59                 | 23
    | 3         | 11        | 6            | 0       | 13    | 64    |
| 20         | "University of California      |  San Diego"          | 0
     | 14                   | 61                | 101                | 15
    | 10        | 8         | 10           | 0       | 22    | 63    |
| 24         | "University of California      |  San Francisco"      | 0
     | 17                   | 101               | 101                | 21
    | 19        | 3         | 13           | 0       | 33    | 60    |
| 34         | "University of Michigan        |  Ann Arbor"          | 0
     | 24                   | 68                | 60                 | 101
    | 2         | 17        | 7            | 0       | 8     | 54    |
| 40         | "University of California      |  Santa Barbara"      | 0
     | 29                   | 101               | 101                | 28
    | 68        | 72        | 36           | 0       | 101   | 52    |
| 42         | "Purdue University             |  West Lafayette"     | 0
     | 30                   | 95                | 70                 | 49
    | 61        | 101       | 58           | 0       | 19    | 52    |
| 45         | "University of California      |  Davis"              | 0
     | 33                   | 79                | 101                | 92
    | 23        | 40        | 25           | 0       | 32    | 51    |
| 47         | "University of California      |  Irvine"             | 0
     | 35                   | 101               | 101                | 38
    | 59        | 57        | 52           | 0       | 65    | 51    |
| 49         | "University of Minnesota       |  Twin Cities"        | 0
     | 36                   | 101               | 101                | 85
    | 18        | 31        | 17           | 0       | 84    | 50    |
| 52         | "Ohio State University         |  Columbus"           | 0
     | 38                   | 101               | 101                | 83
    | 30        | 50        | 35           | 0       | 54    | 50    |
| 64         | "Pennsylvania State University |  University Park"    | 0
     | 45                   | 101               | 94                 | 101
    | 38        | 60        | 27           | 0       | 99    | 48    |
| 68         | "University of Maryland        |  College Park"       | 0
     | 47                   | 85                | 101                | 50
    | 47        | 55        | 41           | 0       | 101   | 48    |
| 73         | "Texas A&M University          |  College Station"    | 0
     | 50                   | 101               | 101                | 46
    | 58        | 101       | 80           | 0       | 101   | 47    |
| 2          | "Massachusetts Institute of Te | USA                  | 2
     | 9                    | 17                | 3                  | 12
    | 4         | 4         | 0            | 1       | 92    | 2012  |
1001 rows in set
Time: 0.861s


SE COMINEZA  A REALIZAR SELECCIONES DE DOS TIPOS DE TABLAS 

Rosalia_TP> select * from ranking inner join `timesData` on ranking.country=tim
            esData.country;
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+-------+
| world_rank | institution                    | country              | national_
rank | quality_of_education | alumni_employment | quality_of_faculty | publicati
ons | influence | citations | broad_impact | patents | score | year_ | world_ran
k | university_name                | country              | teaching | internati
onal | research | citations | income | total_score | num_students | student_staf
f_ratio | international_students | female_male_ratio | year_ |
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+-------+
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0     |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  | 6
  | University of Cambridge        | United Kingdom       | 91       | 78
     | 94       | 94        | 57     | 91          | 0            | 812
        | 12                     | 34                | 46    |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  | 9
  | Imperial College London        | United Kingdom       | 89       | 90
     | 95       | 88        | 93     | 91          | 0            | 60
        | 12                     | 51                | 37    |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  | 22
  | University College London      | United Kingdom       | 74       | 91
     | 82       | 81        | 39     | 78          | 0            | 607
        | 11                     | 46                | 56    |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  | 40
  | University of Edinburgh        | United Kingdom       | 60       | 67
     | 62       | 87        | 42     | 69          | 0            | 774
        | 14                     | 36                | 58    |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
    | 16        | 11        | 0            | 50      | 86    | 2012  | 68
  | University of Bristol          | United Kingdom       | 50       | 67
     | 53       | 81        | 36     | 61          | 0            | 906
        | 14                     | 25                | 53    |
| 4          | "University of Cambridge"      | United Kingdom       | 1
     | 10                   | 24                | 4                  | 16
4488 rows in set
Time: 5.364s
Rosalia_TP> select * from ranking left join `timesData` on ranking.national_ran
            k=timesData.teaching;
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+--------+
| world_rank | institution                    | country              | national_
rank | quality_of_education | alumni_employment | quality_of_faculty | publicati
ons | influence | citations | broad_impact | patents | score | year_ | world_ran
k | university_name                | country              | teaching | internati
onal | research | citations | income | total_score | num_students | student_staf
f_ratio | international_students | female_male_ratio | year_  |
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+--------+
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 10         | "University of California      |  Berkeley"           | 0
     | 8                    | 16                | 52                 | 6
    | 6         | 5         | 3            | 0       | 16    | 79    | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 19         | "University of California      |  Los Angeles"        | 0
     | 13                   | 62                | 59                 | 23
    | 3         | 11        | 6            | 0       | 13    | 64    | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 20         | "University of California      |  San Diego"          | 0
     | 14                   | 61                | 101                | 15
    | 10        | 8         | 10           | 0       | 22    | 63    | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 24         | "University of California      |  San Francisco"      | 0
     | 17                   | 101               | 101                | 21
    | 19        | 3         | 13           | 0       | 33    | 60    | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 34         | "University of Michigan        |  Ann Arbor"          | 0
     | 24                   | 68                | 60                 | 101
    | 2         | 17        | 7            | 0       | 8     | 54    | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0      |
| 40         | "University of California      |  Santa Barbara"      | 0
     | 29                   | 101               | 101                | 28
2319 rows in set
Time: 2.824s
Rosalia_TP> select * from ranking inner join `timesData` on ranking.country=tim
            esData.num_stdents;
(1054, "Unknown column 'timesData.num_stdents' in 'on clause'")

SE UTILIZA LAS FUNCIONES JOIN PARA TRAER RSULTADOS DE 2 TABLAS



Rosalia_TP> select * from ranking inner join `timesData` on ranking.country=tim
            esData.num_students;
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+-------+
| world_rank | institution                    | country              | national_
rank | quality_of_education | alumni_employment | quality_of_faculty | publicati
ons | influence | citations | broad_impact | patents | score | year_ | world_ran
k | university_name                | country              | teaching | internati
onal | research | citations | income | total_score | num_students | student_staf
f_ratio | international_students | female_male_ratio | year_ |
+------------+--------------------------------+----------------------+----------
-----+----------------------+-------------------+--------------------+----------
----+-----------+-----------+--------------+---------+-------+-------+----------
--+--------------------------------+----------------------+----------+----------
-----+----------+-----------+--------+-------------+--------------+-------------
--------+------------------------+-------------------+-------+
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 0
  | university_name                | country              | 0        | 0
     | 0        | 0         | 0      | 0           | 0            | 0
        | 0                      | 0                 | 0     |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 1
  | Harvard University             | United States of Ame | 100      | 72
     | 99       | 99        | 35     | 96          | 0            | 152
        | 9                      | 25                | 0     |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 2
  | California Institute of Techno | United States of Ame | 98       | 55
     | 98       | 100       | 84     | 96          | 0            | 243
        | 7                      | 27                | 33    |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 3
  | Massachusetts Institute of Tec | United States of Ame | 98       | 82
     | 91       | 100       | 88     | 96          | 0            | 74
        | 9                      | 33                | 37    |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 4
  | Stanford University            | United States of Ame | 98       | 30
     | 98       | 99        | 64     | 94          | 0            | 596
        | 8                      | 22                | 42    |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
    | 0         | 0         | 0            | 0       | 0     | 0     | 5
  | Princeton University           | United States of Ame | 91       | 70
     | 95       | 100       | 0      | 94          | 0            | 929
        | 8                      | 27                | 45    |
| 0          | institution                    | country              | 0
     | 0                    | 0                 | 0                  | 0
-- Más  --


0 rows in set
Time: 0.159s
Rosalia_TP>
Goodbye!

(base) C:\Users\USER>



