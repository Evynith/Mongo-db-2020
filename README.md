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
13. ```sh
    db.players.updateMany(
        {},
        { $set: { "teamId": ObjectId("63040dd36d3f1d036815d94d") } }
    )
    ```
14. ```sh
    db.games.updateOne(
        { "name": "final" }, 
        {$set: { "teams": [ObjectId("63040dd36d3f1d036815d94d")] }}
    )
    ```
15. ```sh
    db.teams.updateMany(
        { },
        { $unset: { "players": "" } }
    )
    ```
16. ```sh
        db.games.find().limit(1)
    ```
17. ```sh
        db.games.findOne()
    ```
18. ```sh
        db.games.updateMany(
            { },
            { $set: {"duration": 20}}
        )
    ```
19. ```sh
    db.games.insertMany([
        {
        "name": "prefinal",
        "duration": 30
        },
        {
        "name": "quarterfinals",
        "duration": 35
        },
        {
        "name": "beginning",
        "duration": 25
        }
    ])
    ```
20. ```sh
        db.games.find({
            "duration": {$gt: 20, $lt: 35}
        }, {"name": 1})
    ```
21. ```sh
        db.games.find({
            $or: [{"duration": 20}, {"duration": { $gt: 30}} ]
        })
    ```
22. ```sh
        db.games.deleteMany({
            "duration": { $gt: 30}
        })
    ```

### Notes
*var myDate = new Date("YYYY-mm-dd");* <br>
*var myDate = new Date("YYYY-mm-ddTHH:MM:ss");* <br>
*db.collection.updateMany(filter, update, options)* <br>
*{ $or: [ { <expression1> }, { <expression2> }, ... , ]}*
