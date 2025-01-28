
|
Model	Fields	Description
User	id, username, password, email, first_name, last_name	

## User Model

| **Field**    | **Type**                    | **Description**                                    |
|--------------|-----------------------------|----------------------------------------------------|
| `id`         | AutoField (Primary Key)     | Unique identifier for each user.                   |
| `username`   | CharField(max_length=150)   | The username of the user.                          |
| `password`   | CharField(max_length=128)   | The password of the user.                          |

## Lyric Model

 **Field**    | **Type**                    | **Description**                                    |
|--------------|-----------------------------|----------------------------------------------------|
| `id`         | AutoField (Primary Key)     | Unique identifier for each song/lyrics.            |
| `title`      | CharField(max_length=255)   | The title of the song/lyrics.                      |
| `content`    | TextField                   | The lyrics content.                                |
| `author`     | ForeignKey(User)            | The user who created the lyrics.                   |
| `published`  | BooleanField(default=False) | Whether the lyrics are published (True/False).     |
| `updated_at` | DateTimeField(auto_now=True) | Timestamp for when the lyrics were last updated. |


## Explanation:

* User: Represents a user in your system.

* id: Unique identifier for each user.

* username: The username of the user.

* password: The password of the user.
<hr>

* Lyrics: Represents the lyrics or songs created by users.

* id: Unique identifier for each song/lyrics.

* title: The title of the song/lyrics.

* content: The lyrics content.

* author_id: Foreign key that links to the User table.

* published: Indicates whether the lyrics are published.

* created_at: Timestamp when the lyrics were created.

* updated_at: Timestamp when the lyrics were last updated.


## Entity Realtionship Models
```
+------------+         +------------+
|   User     |         |   Lyrics   |
|------------|         |------------|
| id         |         | id         |
| username   |         | title      |
| password   |---------| content    |
|            |         | author_id  |
|            |         | published  |
|            |         | created_at |
|            |         | updated_at |
+------------+         +------------+
```
Realtionship
One-to-Many: Each user can have multiple lyrics, but each piece of lyrics belongs to one user. This is represented by the foreign key author_id in the Lyrics table.