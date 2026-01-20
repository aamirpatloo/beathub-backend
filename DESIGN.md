# BeatHub Design Document

## 1. Data Relationships

Artist is the parent entity.
Album references Artist.
Song references Album and Artist.
User is independent.
Playlist references User and contains an array of Song references.

## 2. Design Decisions

### Why did you reference Songs in the Playlist instead of embedding them?

Referencing allows playlists to always show updated song details. If a song name changes, all playlists automatically reflect the update. Embedding would require updating every playlist manually.

### Why did you reference the Artist in the Song model?

This allows faster queries like "find all songs by Daft Punk" without needing to search through albums first.
