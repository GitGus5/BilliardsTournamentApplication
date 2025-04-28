**Funcitionality**
Start with one billiards table and allow to add more

Two people per billiards table

Count wins and loses

Assign chips based on APA skill level with APA API

Send notification when persons turn

Make a queue of people in line to play allow to move people in queue drag and drop

When someone loses they lose a chip and go to the beginning of the queue

Count position in queue

Mobile application and Desktop views

**Roles**
Admin (manage tables, queues, validate results, and user data)
User (Control match results, join queues, view status, and receive notifications)

**Authentication**
Email based and optionally allow to link to APA account if supported by API

**Technology Stack**
Database/Backend: Firebase
Frontend: React Native

How to tie in APA account with user account on application?

APIs: https://api.poolplayers.com/
Free Cloud Hosting: AWS, Firebase
SQL Database / frontend 

**Secondary Priorities**:
Allow for link to live game (in app streaming via YouTube)

**Tables Collection**
This collection stores information about each billiards table, including its queue of players:
Document ID: tableId (string, unique identifier)
Fields:
name: Array of strings, the table's names
championId: String, the user ID of the current champion (nullable if no champion)
queue: Array of strings, ordered list of user IDs waiting to play

**Users Collection**
This collection holds user profiles, including statistics and admin status:
Document ID: userId (string, from Firebase Authentication)
Fields:
name: String, user's name
email: String, user's email
phone: Numeric, user's phone 
apaSkillLevel: Number, user's APA skill level for chip assignment
chips: Number, user's current chip count
wins: Number, total wins
losses: Number, total losses
isAdmin: Boolean, indicates if the user is an admin


**Game collection**
tableId: String, the ID of the table where the game was played
player1Id: String, first player's user ID
player2Id: String, second player's user ID
winnerId: String, the user ID of the winner
timestamp: Timestamp, when the game was completed

