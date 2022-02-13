## 1. DBeaver
1. Open DBeaver and create a new connection.
2. Select: ```PostgreSQL```
3. Set: 
    * Database = <name_of_database>
    * Username = <username_for_database ie. dorian>
    * Password = <if_you_need>
4. Finish.

## 2. Terminal
1. Go to project file: ```cd filename```
2. Setup poetry: ```poetry init``` and enter packages required.
3. Add anymore packages with ```poetry add numpy pandas```
4. ```~/.dbt``` Go into dbt folder? 
5. Open the dbt profiles file: ```open profiles.yml```
    * Add a profile for the database that you already created in DBeaver.
    ```terminal
    brendan2:
      outputs:

        dev:
          type: postgres
          threads: 4
          host: localhost
          port: 5432
          user: dorian
          pass: ''
          dbname: brendan2
          schema: dbt_dorian
    
        prod:
          type: postgres
          threads: 4
          host: localhost
          port: 5432
          user: dorian
          pass: ''
          dbname: brendan2
          schema: dbt_dorian
    
      target: dev
    ```
5. Navigate back to project folder.
6. Put data into project data folder?
7. Seed with dbt: ```dbt seed```
8. Navigate to models folder and create a folder for models:  ```mkdir models_folder```
9. Create SQL file within new folder:  ```touch new_file.sql```
10. Run dbt: ```dbt run```
11. Now refresh in DBeaver and you should be able to view your models :)
