## 1. PSQL
1. Navigate to Projects.
2. Initialise dbt to create project file structure: ```dbt init```
3. Navigate to folder.
4. Start SQL: ```sql_start```
5. Create a database: ```createdb db_name```
-- 6. Potentially here you will create a profile to work on this project?

## 2. DBeaver
1. Open DBeaver and create a new connection.
2. Select: ```PostgreSQL```
3. Set: 
    * Database = <name_of_database>
    * Username = <username_for_database ie. dorian>
    * Password = <if_you_need>
4. Finish.

## 3. Terminal
1. Go to internal project file: ```cd filename```
2. Open ```dbt_project.yml``` and set ```seed-paths: ["data"]```.
3. Setup poetry: ```poetry init```.
4. Add any required packages: ```poetry add numpy pandas```
5. ```~/.dbt``` Go into dbt folder? 
6. Open the dbt profiles file: ```open profiles.yml```
    * Add a profile for the database that you already created in DBeaver.
```terminal
testproj2:
  outputs:

    dev:
      type: postgres
      threads: 4
      host: localhost
      port: 5432
      user: dorian
      pass: ''
      dbname: testproj2
      schema: dbt_dorian

    prod:
      type: postgres
      threads: 4
      host: localhost
      port: 5432
      user: dorian
      pass: ''
      dbname: testproj2
      schema: dbt_dorian

  target: dev
```

6. Navigate back to project folder.
7. Put data into project data folder?
8. Seed with dbt: ```dbt seed```
9. Navigate to models folder and create a folder for models:  ```mkdir models_folder```
10. Create SQL file within new folder:  ```touch new_file.sql```
11. Setup the SQL file as a table: 
```SQL
{{ config(materialized='table') }}
```
Then type your query and save.  Use ```{{ ref('name_of_dataset') }}``` as the FROM location.

13. Run dbt: ```dbt run```
14. Now refresh in DBeaver and you should be able to view your models :)
