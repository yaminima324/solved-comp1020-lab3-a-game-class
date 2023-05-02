Download Link: https://assignmentchef.com/product/solved-comp1020-lab3-a-game-class
<br>
<ul>

 <li>Objects which refer to other objects</li>

</ul>

Notes:

<ul>

 <li>Make sure your TA has recorded your mark before leaving.</li>

 <li>The three questions are sequential – each builds on the previous one.</li>

 <li>Only one of the three exercises is required, but try to do two. The Gold exercise is more difficult, as usual.</li>

 <li>The Gold exercise will require more lines of code, and will probably be impractical to complete in a one hour lab. Try to complete it at home as an extra exercise instead. You will learn a lot from it if you do.</li>

</ul>

<h1>Supplied code</h1>

This lab builds on a modified version of the <strong>HockeyTeam</strong> class from Lab 2. It has been split into two classes

(<strong>HockeyTeam</strong> and <strong>TeamList</strong>), which is the correct way to do it. (It was done in one class in Lab 2 only to give practice with class/static variables.) A few additional methods have also been provided. Download the <strong>HockeyTeam.java</strong> and <strong>TeamList.java</strong> files which provide two classes with the following methods:




<strong>HockeyTeam</strong> methods:

<strong>HockeyTeam(String name, int wins, int losses, int overtimeLosses)</strong> – constructor    <strong>void won()</strong> – record a win for the team   <strong>void lost()</strong> – record a loss for the team

<strong>void lostOvertime()</strong> – record an overtime loss for the team

<strong>int points()</strong> – find the number of points that the team has in the standings

<strong>String toString()</strong> – obtain a printable String for the team                         <strong>String getName()</strong> – find the name of the team

<strong>int compareTo(HockeyTeam)</strong> – compare the points for two teams     <strong><sub>TeamList</sub> </strong>methods:

<strong>TeamList()</strong> – constructor (makes an empty list of teams)                 <strong>void addTeam(HockeyTeam)</strong> – add a team to the end of the list

<strong>String toString()</strong> – obtain a multi-line printable String for the list of teams                    <strong>void SortTeams()</strong> – Sort the teams into descending order by points

<strong>HockeyTeam findTeam(String name)</strong> – find a team by name

Background information on winning, losing, and overtime: For those unfamiliar with NHL games, it works like this. After the third period (the normal end of the game), if the score isn’t tied the game is over – one team gets a win (2 points), the other gets a loss (0 points). If the score is tied, then it becomes an overtime game and they keep playing. Eventually one team will be credited with a goal, and get a win (2 points), and the other team gets an “overtime loss” (1 point).










<ol>

 <li>Create a file <strong>Game</strong><strong><sub>.java</sub></strong> which will implement a class of objects that will store some information about one hockey game. In your file, implement the following variables and methods.

  <ol>

   <li><strong>private</strong> instance variables that will store references to two <strong>HockeyTeam </strong>objects representing the teams that are playing in this game (the “home” team and the “away” team).</li>

   <li><strong>private</strong> instance variables that will store the current score (one <strong><sub>int</sub> </strong>per team).</li>

   <li>a constructor that will accept two <strong>HockeyTeam </strong>parameters, “home” team first. The score should be initialized to 0-0.</li>

   <li>the usual <strong>public</strong> method <strong>String toString()</strong> which will return a <strong>String</strong> giving the status of the game, in the format <strong>“Winnipeg(2) at Chicago(1)”</strong> where the “away” team is listed first and the “home” team is listed second, and the score is given as shown. Note that only the team names are shown, not the records of the teams.</li>

   <li>a public method <strong>void goal(HockeyTeam)</strong> which will update the score due to a goal being scored by the indicated team. If that team isn’t one of the two that are playing in this game, it should use <strong>out.println</strong> to print the error message <strong>“That team isn’t playing in this game!”</strong></li>

  </ol></li>

 <li>Run the supplied file <strong>java</strong> to test your <strong>Game</strong> class. Look at this file to see how it is using your Game objects. If your class is working correctly the output should be:</li>

</ol>

<strong>Creating Chicago at Winnipeg game. </strong>

<strong>Chicago(0) at Winnipeg(0) </strong>

<strong>Creating Colorado at St. Louis game. </strong>

<strong>St. Louis(0) at Colorado(0) </strong>

<strong>Chicago scores </strong>

<strong>Chicago(1) at Winnipeg(0) </strong>

<strong>Winnipeg scores </strong>

<strong>Chicago(1) at Winnipeg(1) </strong>

<strong>St. Louis scores </strong>

<strong>St. Louis(1) at Colorado(0) Colorado scores </strong>

<strong>St. Louis(1) at Colorado(1) Chicago scores in the wrong game: </strong>

<strong>That team isn’t playing in this game! St. Louis scores in the wrong game: </strong>

<strong>That team isn’t playing in this game! </strong>

<strong>Winnipeg scores </strong>

<strong>Chicago(1) at Winnipeg(2)</strong>







<ol>

 <li>Save your <strong>java</strong> file as <strong>GameV2.java</strong>. Change the name of the class and the constructor to match. The supplied main program will expect games to be named this way for the Silver exercise.</li>

 <li>Modify your <strong><sub>GameV2</sub></strong> class by adding the following additional instance variables and methods:

  <ol>

   <li><strong>private</strong> <strong>boolean</strong> instance variables to keep track of whether a game has ended, and whether it went into overtime (regardless of whether the game is over or not).</li>

   <li>a <strong>public</strong> method <strong>void overtime()</strong> which will change the game to show that it has gone into overtime. You do not have to do any error checking. (In a real situation, you would check to see that the game was tied, and wasn’t already over before this.)</li>

   <li>a <strong>public</strong> method <strong>void ended()</strong> which will change the game to indicate that the game has ended. (Again, you do not have to do any error checking. Assume that the game hadn’t ended before, and isn’t tied.) In addition to modifying the object appropriately, this method should send the appropriate <strong>won()</strong>, <strong>lost()</strong>, or <strong>lostOvertime()</strong> messages to the two <strong>HockeyTeam</strong> objects, so that they properly adjust their records in the standings.</li>

   <li>Make appropriate modifications to the existing methods as follows.

    <ol>

     <li>Modify the constructor so that the new game is not over, and not in overtime.</li>

     <li>Modify the <strong>toString</strong> method so that it adds <strong>“OT” </strong>or <strong>“Final”</strong> or both to the end of the <strong>String</strong>, to indicate that the game went into overtime, is over, or both. See the sample output below. iii. Modify the <strong><sub>goal</sub></strong> method so that it automatically ends the game if the goal was scored in overtime.</li>

    </ol></li>

   <li>Run the <strong>java</strong> file to test your modified class. If your <strong>GameV2</strong> class is working properly, the output should be:</li>

  </ol></li>

</ol>

<strong>Standings: </strong>

<strong>Chicago(28,13,2=58) </strong>

<strong>St. Louis(27,13,3=57) Winnipeg(22,14,8=52) </strong>

<strong>Colorado(18,17,8=44) </strong>

<strong> </strong>

<strong>Creating Chicago at Winnipeg game. </strong>

<strong>Creating Colorado at St. Louis game. </strong>

<strong> </strong>

<strong>After goals are scored: </strong>

<strong>Chicago(1) at Winnipeg(2) </strong>

<strong>St. Louis(1) at Colorado(1) </strong>

<strong> </strong>

<strong>Winnipeg-Chicago game ends </strong>

<strong>Chicago(1) at Winnipeg(2) Final </strong>

<strong>St. Louis-Colorado game goes into overtime </strong>

<strong>St. Louis(1) at Colorado(1) OT </strong>

<strong>St. Louis scores </strong>

<strong>St. Louis(2) at Colorado(1) OT Final </strong>

<strong> </strong>

<strong>Standings: </strong>

<strong>St. Louis(28,13,3=59) Chicago(28,14,2=58) Winnipeg(23,14,8=54) Colorado(18,17,9=45)</strong>




In this exercise, you will not create any new classes, but you will modify all of the existing classes (<strong>HockeyTeam</strong>, <strong>GameV2</strong>, and <strong>TeamList</strong>) in order to implement the following method.

<ol>

 <li>Add a <strong>HockeyTeam bestBet()</strong> method to the <strong>TeamList</strong> This method is looking for the team that is most likely to win its game. This method should look at all of the teams in the list, and return the one which 1) is currently playing a game, which 2) is not over yet, and 3) is farther ahead of its opponent in the <strong><em>standings</em></strong> than any other team that is currently playing. The current score in the games doesn’t matter, only the points difference in the standings. If no teams at all are playing right now, return <strong><sub>null</sub></strong>. If two teams are equally far ahead of their opponent in the standings, return either one of them.</li>

 <li>This cannot be done without adding additional instance variables and/or methods to the existing classes. Add whatever you need to solve the problem. It’s up to you to decide what you need. This is a Gold exercise, after all. There will have to be some additional interactions between the three classes.</li>

 <li>The rules:

  <ol>

   <li>You cannot create any other classes.</li>

   <li>You cannot use an additional list or array of games anywhere. The only list should be the existing list of teams.</li>

   <li>You cannot add any class/static variables or methods, only instance variables or methods. d. Good luck.</li>

  </ol></li>

 <li>Run the <strong>java</strong> file to test your modified classes. If everything is working properly, the output should be:</li>

</ol>

<strong>Standings: </strong>

<strong>Nashville(29,9,4=62) </strong>

<strong>Chicago(28,13,2=58) </strong>

<strong>St. Louis(27,13,3=57) </strong>

<strong>Winnipeg(22,14,8=52) </strong>

<strong>Dallas(19,16,7=45) </strong>

<strong>Colorado(18,17,8=44) </strong>

<strong>Minnesota(18,19,5=41) </strong>

<strong> </strong>

<strong>Test 1: Best Bet now should be null – there are no games. </strong>

<strong>league.bestBet() gives:null </strong>

<strong> </strong>

<strong>Creating Nashville at Winnipeg game. </strong>

<strong>Creating Minnesota at St. Louis game. </strong>

<strong>Creating Dallas at Colorado game. </strong>

<strong> </strong>

<strong>Test 2: Best Bet now should be St. Louis (16 points better) league.bestBet() gives:St. Louis(27,13,3=57)  </strong>

<strong>Minnesota(0) at St. Louis(1) Final </strong>

<strong>Test 3: Best Bet now should be Nashville (10 points better) league.bestBet() gives:Nashville(29,9,4=62) </strong>

<strong> </strong>

<strong>Dallas(0) at Colorado(1) Final </strong>

<strong>Nashville(0) at Winnipeg(1) Final </strong>

<strong>Test 4: No active games. Best Bet now should be null league.bestBet() gives:null </strong>


