# Mongo-db-2020

## Commands list

1. ```bash
    mongosh
    ```
2. ```sh
    use futbolfifa
    ```
3. ```sh
    db.createCollection("players")
    ```
4. ```sh
    db.players.insertMany([
        {
        "name": "Lionel",
        "surname": "Messi",
        "birth": new Date(1987-06-24),
        "position": "Center Forward"
        },
        {
        "name": "Emiliano",
        "surname": "Martinez",
        "birth": new Date(1992-09-02),
        "position": "Goalkeeper"
        },
        {
        "name": "Nicolas",
        "surname": "Otamendi",
        "birth": new Date(1988-02-12),
        "position": "Center Back"
        },
        {
        "name": "Paulo",
        "surname": "Dybala",
        "birth": new Date(1993-11-15),
        "position": "Central Midfielder"
        },
        {
        "name": "Franco",
        "surname": "Armani",
        "birth": new Date(1986-10-16),
        "position": "Goalkeeper"
        }
    ])
    ```

5. ```sh
    db.players.find()
    ```
6. ```sh
    db.createCollection("teams")
    ```
7. ```sh
    db.createCollection("games")
    ```
8. ```sh
    db.teams.insertMany([
        {
        "name": "Team 1",
        "players": null
        }
    ])
    ```
9. ```sh
    db.games.insertMany([
        {
        "name": "final",
        "teams": null
        }
    ])
    ```
10. ```sh
    db.teams.updateOne(
        { "name": "Team 1" },
        {
            $set: {"name": "Argentina"},
            $currentDate: { lastModified: true }
        }
    )
    ```
11. ```sh
    show collections
    ```
12. ```sh
    db.teams.find()
    ```

### Notes
*var myDate = new Date("YYYY-mm-dd");* <br>
*var myDate = new Date("YYYY-mm-ddTHH:MM:ss");* <br>
*db.collection.updateMany(filter, update, options)*