---
comments: True
layout: default
title: Review Ticket - Tri 1
description: Student Lesson
type: tangibles
courses: {'compsci': {'week': 11}}
---

# Overview

## Issues Recaps:
Used GitHub issues along with my partner Advik to organize work:
- [Sprint Plans](https://github.com/APCSP-RAGS/awsRAGS_flask/issues/2): We used GitHub issue plans to track our progress and plan out future work.
- [Commit Summaries](https://github.com/APCSP-RAGS/awsRAGS_flask/issues/3): These summaries were updated for major commits and helped organize our commits so that if something broke, we could fix it. Also helped us keep track of our work. 
- We also communicated heavily through Slack and Discord and organized voice calls to work on the project.

## PP Peer Reviews:
[Period 5: Personal Review](https://github.com/APCSP-RAGS/pp-frontend/issues/6) - peer grades for our projects

[Period 5: Stocks](https://github.com/Imaad08/stocksFrontend/issues/1#issuecomment-1795851980) - during dress rehearsal

[Period 5: Frogs](https://github.com/IshanCornick/FrontendRepo/issues/1#issuecomment-1795546656) - during dress rehearsal


[Period 5: Lung Cancer](https://github.com/EshikaP1/frontend/issues/1#issuecomment-1795573532) - during dress rehearsal

## Skills gained:
- GitHub collaboration
- AGILE collaboration method
- SCRUM meetings for ideation

## Tools learned:
- Git
- VSCode
- VSCode extension marketplace
- WSL/Linux usage
- AWS

## Languages Covered:
- Python
  - object oriented programming
  - libraries
  - ...more
- Javascript
- HTML/CSS

# Team Teach:
I was responsible for the creation of curriculum up until the first Popcorn hack based on Advik's wireframe that he created

This consisted of for loops, while loops, and iteration through dictionaries/lists

Through this team teach, I learne

# Passion Project Lyrics Create API

- Main focus for the create function is that it provides lyrics for you after you provide artist, song name, etc.

``` python
class Song(db.Model):
    __tablename__ = "Song"
    id = db.Column(db.Integer, primary_key=True)  # Define a primary key column
    character = db.Column(db.String, nullable=False) # Breaking bad character
    song_name = db.Column(db.String, nullable=False)
    artist = db.Column(db.String, nullable=False)
    genre = db.Column(db.String, nullable=False)
    lyrics = db.Column(db.String, nullable=False)
    def __init__(self, character, song_name, artist, genre, lyrics): # Constructor 
        self.character = character
        self.song_name = song_name
        self.artist = artist
        self.genre = genre
        self.lyrics = lyrics
    # Convert db data to a dictionary in order to return easily using JSON
    def to_dict(self):
        return {"character": self.character, "song_name": self.song_name, "artist": self.artist, "genre": self.genre, "lyrics": self.lyrics}
    # Create method to let users add a song to the DB
    def create(self):
        try:
            try:
                self.lyrics = genius.search_song(self.song_name, self.artist).lyrics.split("Lyrics")[1]
            except:
                self.lyrics = "Check that the artist name and song name are spelled correctly"
            db.session.add(self)  # add prepares to persist object to table
            db.session.commit()  # SQLAlchemy requires a manual commit
            return self
        except: 
            db.session.remove() # remove object from table if invalid
            return None
    # Read method to return every part of the table
    def read(self):
        return {
            "id": self.id,
            "character": self.character,
            "song_name": self.song_name,
            "artist": self.artist,
            "genre": self.genre,
            "lyrics": self.lyrics
        }

# Initialize songs

def initSongs():
    # Adds each song + its metadata to the db
    song1 = Song(character="Walter White", song_name="Changes", artist="David Bowie", genre="Art Pop", lyrics=genius.search_song("Changes", "David Bowie").lyrics.split("Lyrics")[1]); db.session.add(song1)
    song2 = Song(character="Walter White", song_name="Back in Black", artist="AC/DC", genre="Hard Rock", lyrics=genius.search_song("Back in Black", "AC/DC").lyrics.split("Lyrics")[1]); db.session.add(song2)
    song3 = Song(character="Walter White", song_name="Baby Blue", artist="Badfinger", genre="Rock", lyrics=genius.search_song("Baby Blue", "Badfinger").lyrics.split("Lyrics")[1]); db.session.add(song3)
    db.session.commit()
```


### Issue #1
- when frontend reloaded and backend ran, the Genius API called for all songs once again which caused the website to run very slowly
- Fixed by moving lyricgenius initial fetch to initSongs function that initializes the database in instances/volumes/sqlite.db

### Issue #2
- Extra junk text was displayed from the lyricgenius 
- Fixed by splitting at the extra characters and displaying that

# PP Frontend Integration

```js
....
    <div class="table-container">
      <div class="add-container">
        <h2>Add a song</h2>
        <label for="songName">Song Name:</label>
        <input type="text" id="songName" placeholder="Enter song name">

        <label for="artistName">Artist Name:</label>
        <input type="text" id="artistName" placeholder="Enter artist name">

        <label for="genre">Genre:</label>
        <input type="text" id="genre" placeholder="Enter genre">

        <label for="character">Person:</label>
        <input type="text" id="character" placeholder="Enter name">
      
        
        <button onclick="addSong()">Add</button>
      </div>
      <!-- HTML table for displaying data -->
      <table class="hacker-theme">
        <h2>Songs</h2>
        <thead>
          <tr>
            <th>Character</th>
            <th>Song Name</th>
            <th>Artist</th>
            <th>Genre</th>
            <th>Lyrics</th>
            <th>Lyrics Toggle</th>
          </tr>
        </thead>
        <tbody id="result">
          <!-- Data will be populated here -->
        </tbody>
      </table>
    </div>
  </div>
.....
function addSong() {
      const songName = document.getElementById("songName").value;
      const artistName = document.getElementById("artistName").value;
      const genre = document.getElementById("genre").value;
      const character = document.getElementById("character").value;

      const apiUrl2 = `http://localhost:8069/api/song/create`
      var body = {
        "song_name": songName,
        "artist": artistName,
        "genre": genre,
        "character": character,
      }
      fetch("http://localhost:8069/api/song/create", {method:'POST', body: JSON.stringify(body), headers: {
      'Content-type': 'application/json',
      }})
        .then(response => response.json())  
        .then(json => {
          console.log(json)
          fetchSongs()
      })
    }
```

- I was also responsible for the integration of the create method between backend and frontend
- I encountered a few CORS erros when switching from the AWS backend to the locally hosted backend but fixed them by hosting it through terminal instead of docker and adding the http:// prefix to the localhost address 

# Scrum-ming

- As the scrum master of my team I had the responsibility of work division
- From this I learned:
  - Efficient work management
  - How to actively facilitate conversation
  - Ensuring people are on task
  - 

# College Board MCQ
- REALLY long
- Pacing
- 60/66 :(

### - Problem 14:
- one such mistake in which I didn't read one of the answers
- On the problem, it asked us to compare two loops and analyze what is different between the two programs
- I selected that they display different number values but didn't select that the values themselves are different because I didn't see that as an option

### - Problem 30 :
- Another mistake in which I didn't thoroughly read the program at question
- I think this was due to how long the test was
- Something I can do to fix this for the future will be to slow down a bit in the beginning since I went rather fast in the beginning and got a bit tired

### - Problem 40:
- I thought the problem was talking about only the data given.
- I didn't realize that the data provided was only an example from two of the students

### - Problem 41:
- I did not account for the case in which the final exam was lower than the midterm

### - Problem 43:
- Is a time complexity of n^2 reasonable, I don't think so.

### - Problem 46:
- The reason that it's not possible to determine, given any program and program input, whether or not the program will go into an infinite loop for that input is because there are infinitely many edge-cases to account for
- This is simply unreasonable

Towards the end of the test I began losing focus and because of that, I got <b>4</b> questions wrong in a row for misreading and misunderstanding questions.

The main takeaway for me from this test is to pace myself during future tests

# Tri 1 Review:
As the first trimester of the school year concludes, it's important to reflect on the notable progress and skills acquired during this period. Utilizing GitHub issues for efficient project organization, mastering AGILE collaboration, and embracing various tools such as Git, VSCode, WSL/Linux, and AWS have enriched our technical expertise. In our passion project, the Lyrics Create API, we developed a robust class for song data management and overcame challenges like API optimization and CORS issues. Serving as a Scrum master provided invaluable experience in effective work management and facilitation. College Board MCQ tests highlighted the need for pacing and maintaining focus. Moving forward, we aim to build upon these lessons, strengthen collaboration, and further excel in the upcoming trimesters.