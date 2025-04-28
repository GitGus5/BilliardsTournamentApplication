<h1>**Funcitionality**</h1><br>
Start with one billiards table and allow to add more<br>
Two people per billiards table<br>
Count wins and loses<br>
Assign chips based on APA skill level with APA API<br>
Send notification when persons turn<br>
Make a queue of people in line to play allow to move people in queue drag and drop<br>
When someone loses they lose a chip and go to the beginning of the queue<br>
Count position in queue<br>
Mobile application and Desktop views<br>

<h1>**Roles**</h1><br>
Admin (manage tables, queues, validate results, and user data)<br>
User (Control match results, join queues, view status, and receive notifications)<br>

<h1>**Authentication**</h1><br>
Email based and optionally allow to link to APA account if supported by API<br>

<h1>**Technology Stack**</h1><br>
Database/Backend: Firebase<br>
Frontend: React Native<br>

How to tie in APA account with user account on application?

APIs: https://api.poolplayers.com/<br>
Free Cloud Hosting: AWS, Firebase<br>

<h2>**Secondary Priorities**:</h2><br>
Allow for link to live game (in app streaming via YouTube)<br>
<h1>Database Schema</h1>
<h2>**Tables Collection**</h2>
This collection stores information about each billiards table, including its queue of players:<br>
Document ID / Primary Key: tableId (string, unique identifier)<br>
Fields:<br>
name: Array of strings, the table's names<br>
championId: String, the user ID of the current champion (nullable if no champion)<br>
queue: Array of strings, ordered list of user IDs waiting to play <br>

<h2>**Users Collection**</h2>
This collection holds user profiles, including statistics and admin status:<br>
Document ID Primary Key: userId (string, from Firebase Authentication)<br>
Fields:<br>
name: String, user's name<br>
email: String, user's email<br>
phone: Numeric, user's phone <br>
apaSkillLevel: Number, user's APA skill level for chip assignment<br>
chips: Number, user's current chip count<br>
wins: Number, total wins<br>
losses: Number, total losses<br>
isAdmin: Boolean, indicates if the user is an admin<br>


<h2>**Game collection**</h2>
auto-generated uuid for game
tableId: String, the ID of the table where the game was played<br>
player1Id: String, first player's user ID<br>
player2Id: String, second player's user ID<br>
winnerId: String, the user ID of the winner<br>
timestamp: Timestamp, when the game was completed<br>

