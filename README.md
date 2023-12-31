# Welcome to flight Service
## Project Setup
- clone the project on your local
- Excecute `npm install` on the same path as of your root directory
-  Create a `.env` file in the root directory and add the following  environment variable
    - PORT=<3000>
- Inside the `src\config` folder create a new file `config.json` and then add the following piece of json
    ```{
        "development": {
            "username": "root",
            "password": <Password>
            "database": "Flights_Search_DB_Dev",
            "username": <root/Your db login name>,
            "password": <Password>
            "database": "database name",
            "host": "127.0.0.1",
            "dialect": "mysql"
            }
        }
    ```
- Once you have added your db config as listed above, go to src folder and  excecute `npx sequelize db:create`\

## DB design
    - Airplane table
    - Flight table
    - Airport table
    - City table

    - A flight belongs to an airplane but one airplane can have many flights
    - A city has many airports but one airport belongs to one city
    - One airport can have many flights but a flight belongs to one airport

## Tables

### City -> id, name, created_at, updated_at
## Airport -> id, name, address, city_id, created_at, updated_at
   Relationship -> city has many airports and Airport belong to a city(one to many)
   ```npx sequelize model:generate --name:Aiport --attributes name:String,address:String,cityId:integer
      npx sequelize db:migrate
   ```