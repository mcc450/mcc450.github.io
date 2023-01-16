# Olympic Rowing Athlete Analysis in SQL and Tableau

###Project description: 
<p>Using Olympic athlete data sourced from Maven Analytic, I decided to answer some questions about trends in winning boat crews in the sport of Rowing using SQL and Tableau. There are common beliefs in the community about what type of athlete performs best in certain events and this analysis will seek to see if there is any validity to those claims along with other questions that arise during the process.
</p>

###All SQL Code used can be found on GitHub <a href="https://github.com/mcc450/Olympic-Rowing-Analysis">HERE</a>.

### 1. Guiding Questions
<ol>
  <li>Do specific events have an athlete build (height and weight) that is more common?</li>
  <ul>
      <li>For example, 8’s might have taller and heavier athletes whereas doubles and pairs may have slightly smaller athletes.</li>
      <li>Separate older data from newer (last 20 years).</li>
  </ul>
  <li>How has the build of athletes of winning boats changed over time?</li>
  <li>Is there a pattern in a country’s performance or athlete demographics and winning events?</li>
</ol>

###Preparing the Data
<p>The raw data was sourced from Maven Analytics’ “120 Years of Olympic History” dataset. This dataset is large and contained more events than needed.</p>

<p>In order to prepare the data for use in data.world.com, I filtered out all non-Rowing event data using Power Query in Excel and created a new worksheet. This reduced the file size from about 21MB to 880KB. This will allow the data to be easily stored and accessed in GitHub for use in data.world.com. Data.world.com is being used so I can access the project from multiple devices.
</p>

<p>After filtering, the data was cleaned and validated before being exported. The only  abnormalities were found except for extremely young ages for rowing athletes which went as low as 11. All of these young ages, under 17, were coxswains in their team event. Almost all of the events with an athlete under the age of 17 are from at least 40 years ago and the trend has not continued. This is partially due to the sport requiring a minimum weight for both men's and women's coxswains.
</p>

###1. Height and Weight Trends
<p>The initial analysis is average height and weight by event, split between medalists and non-medalists. Calculations are inaccurate. They include the heights and weights of coxswains (typically much smaller than athletes). We will assume any athlete that is over 68kg is a rower, not a coxswain. This weight was chosen to not exclude lightweight events.
</p>

<table>
  <tr>
    <td><img src="images/Incorrect Winner HW.png"></td>
    <td><img src="images/Incorrect Loser HW.png"></td>
  </tr>
</table>

<p>Filtering out coxswains, the average height and weight increased. Height does not seem to be a major factor in winning or losing boats.
</p>

<table>
  <tr>
    <td><img src="images/Correct Winner HW.png"></td>
    <td><img src="images/Correct Loser HW.png"></td>
  </tr>
</table>

<table>
  <tr>
    <td><img src="images/Winner HW SQL.png"></td>
    <td><img src="images/Loser HW SQL.png"></td>
  </tr>
</table>

<p>The largest difference is the 1x: 5.32cm or 2.1 inches. This is a sizeable difference, especially when combined with the weight difference of 7.87kg or 17.35 lbs. The resulting table was created using a FULL OUTER JOIN between the two tables created above. The only other notable difference is the Coxed Fours even though this event no longer exists in the Olympics.
</p>

<img src="images/Winner Loser HW Diff.png">

<p>As seen below, there is also no discernable trend in Height and Weight over time. This data will be visualized in Tableau as well to make it easier to view subsets (by year and event) of this data as well.
</p>

<img src="images/HW Winner Over Time.png">

###2. Age Trends
<p>Rowing at a high level demands an extremely high level of cardiovascular capacity combined with a flawless technique developed over many years. 
</p>

####2.1 Age by Event
<p>Separated by boat, the general assumptions in the rowing community are:
</p>
<ul>
  <li>Coxed Eights: younger athletes, strong and raw power, not as refined technique.</li>
  <li>Coxless Fours: a combination of strength, extreme cardiac capacity, time competing, and great technique.</li>
  <li>Single Scull: experienced rowers, similar to marathon runners that are older with massive cardiac capacity, flawless technique, and typically taller.</li>
</ul>

<p>Below is the code and result of finding the average winner’s age by the event. Events outside those listed above don’t have strong stereotypes.
</p>

<table>
  <tr>
    <td><img src="images/Winner Avg Age By Event.png"></td>
    <td><img src="images/Winner Avg Age By Event SQL.png"></td>
  </tr>
</table>

<p>Single sculls are by far the oldest athlete on average at 28.5 while Eights rowers are an average of 2.2 years younger at 26.3 years. 
</p>

####2.2 Age by Country
<p>When calculating the average age of each country’s medalists, it is clear there is a large disparity between countries with few medals. Countries that have more medals tend to have more similar ages in the center of the spectrum. Country names were included in the resulting table by using a LEFT JOIN on the country abbreviations.
</p>

<table>
  <tr>
    <td><img src="images/Excel Age By Country Viz.png"></td>
    <td><img src="images/Avg Age by Country And Medal SQL.png"></td>
  </tr>
</table>

<p>As seen in the Excel visualization, the medal count is distributed in the center with few countries at the extremes. This SQL query counts each athlete in the boat as a new medal, so a country with 9 medals could have won only one event, the Coxless Eight and the Single Scull since coxswains are excluded. This could be changed with a different query to only count one event win as one medal, but I believe counting each athlete is a better representation of the country’s prowess in the sport and average age as it not only takes multiple high-level athletes but the skills to combine them into one cohesive boat.
</p>

###Country Event Wins
<p>Historically, some countries have been dominant in rowing and the most dominant have been England and Germany. The following query contains the number of Men’s event medals for each team and each competition. For example, if England won the Coxless Four, it would count as one medal instead of 4, one for each rower.
</p>

<p>Nested subqueries were used to first filter out athletes and coxswains that did not meet our criteria. Below is a sample of the final table created. It was also necessary to use the DISTINCT function on the Event column as this would only count one medal for that team and year since the query was also using GROUP BY Team and Year.
</p>

<img src="images/Country Event Wins By Year And Team.png">













