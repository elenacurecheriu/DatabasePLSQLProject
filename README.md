# Music Player App Database Manager - Oracle Database PL/SQL Project

This project is a relational database implementation for a music streaming service, similar to Spotify, Apple Music, or YouTube Music. The database efficiently manages users, subscriptions, playlists, songs, albums, artists, and record labels, ensuring data integrity and efficient querying.

Advanced SQL and PL/SQL features used: stored procedures and functions, triggers, cursors, collections, custom exceptions, etc.

- ERD Diagram:

![image](https://github.com/user-attachments/assets/10a9bf44-e3a3-4b93-ae7a-a531ea4e03da)

- Conceptual diagram:

![image](https://github.com/user-attachments/assets/7810598b-1f99-494c-aab7-cd38759c280a)

## Entities and relationships:

- SUBSCRIPTION, which can be owned by a single user, and each user can have only one subscription.
- USER, who can own multiple playlists, with each playlist being managed by a single user.
- PLAYLIST, which can contain multiple songs.
- SONG, which can be included in multiple playlists, belong to multiple genres, be part of a single album, and be performed by at least one artist.
- ALBUM, which can belong to multiple genres and be associated with a single artist.
- GENRE, which can contain multiple albums and songs.
- ARTIST, who can have multiple albums and belong to a single record label.
- RECORD_LABEL, which can contract multiple artists.
- Intermediate tables (GENRE_ALBUM, GENRE_SONG, ARTIST_SONG, SONG_PLAYLIST) to resolve many-to-many relationships.

## Stored procedures and triggers:

- Retrieves user subscriptions and playlists with detailed song information.
- Identifies record labels with the fewest artists.
- Finds the longest playlist for a user and counts its songs.
- Removes multi-genre songs from playlists.
- Prevents albums with future release dates.
- Restricts playlists to a maximum of 5 songs.
- Logs all schema modifications (CREATE, ALTER, DROP).
