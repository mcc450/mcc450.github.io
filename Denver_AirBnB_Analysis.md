#Denver AirBnB Market Analysis in Tableau

###Summary
<p>Using AirBnB data from Denver, Colorado, I performed a cursory market analysis to understand the basics of the rental market. Inspired by friends in Salt Lake City who have successfully ventured into the AirBnB market along with a video from "Alex the Analyst" on YouTube, I downloaded data from AirBnB here: http://insideairbnb.com/get-the-data/ and created a Tabelau visualization to summarize basic market findings and to support further exploration.</p>

<p>Looking for financial opportunities is a great habit in a growing city like Salt Lake. Having renters build equity in a property for you in addition to possibly generating positive cash flow is enticing. This analysis was done to narrow down general search results when looking for the most commonly used AirBnB properties. While there are many differences between Denver and Salt Lake City, similar general assumptions could be made that warrant further analysis or web scraping projects. A similar analysis could also be completed for cities like Salt Lake to see if general trends hold true.</p>

###Initial Questions
1. What type of homes are booked most frequently?
2. What type of homes produce the mose revenue?
3. What locations offer the best prices?
4. What locations are the cheapest / most expensive?
5. What time of year is best to rent out a property?
6. What type of homes most common in certain areas? (Lefter for further analysis)

###Processing Data
<p>Excel was used to download and transfer the data to Tableau. Data was cleaned and validated using both built in Excel features, temporary COUNT functions, find and replace, and IF functions.</p>

###Findings & Recommendations
<p>This is an initial analysis of the Denver AirBnB data. Once narrowing down the market choices when looking for a rental property, further analyses would be needed when considering specific locations and types of property.</p>
<p> Findings show that the vast majority of revenue come from 1 and 2 bedroom rentals, both about $50-51 million per year. Three bedroom rentals create nearly $26.5 million in revenue which would be another great option if looking to use the property for a part time family residence or vacation home as well.</p>
<p>Zip codes in the center of the city have higher prices. This benefit would need to be checked against the probable higher property cost in a secondary cost-benefit analysis.</p>
<p>A general analysis of revenue by time of year did not result in much beneficial information. The number of bookings would likely be a better judge of activity and possible revenue. The location of the property would also be a big factor. Being close to the mountains and ski resorts in the winter versus being close to the city in the summer could yield different benefits and activity throughout the year.</p>

<div class='tableauPlaceholder' id='viz1671668856205' style='position: relative'><noscript><a href='#'><img alt='Denver AirBnB General Information ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;De&#47;DenverAirBnBGeneralAnalysisDashboard&#47;DenverAirBnBGeneralInformation&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='path' value='views&#47;DenverAirBnBGeneralAnalysisDashboard&#47;DenverAirBnBGeneralInformation?:language=en-US&amp;:embed=true' /> <param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;De&#47;DenverAirBnBGeneralAnalysisDashboard&#47;DenverAirBnBGeneralInformation&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /></object></div>                <script type='text/javascript'>                    var divElement = document.getElementById('viz1671668856205');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='100%';vizElement.style.height=(divElement.offsetWidth*0.75)+'px';} else { vizElement.style.width='100%';vizElement.style.height='1827px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
  
  
  
