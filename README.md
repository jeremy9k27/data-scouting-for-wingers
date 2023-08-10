# data-scouting-for-wingers

Using simple data analysis to find a new winger for Tottenham




With Ange Postecoglou's arrival at Tottenham, it seemed Spurs would be in the market for a winger to fit Postecoglou's style of play. (At the time of this being written, it appears Spurs are sticking with Heung Min Son and Dejan Kulusevski as the starting wingers.) This project looks to use publicly available data to find a wide creator whose profiles as a ball-to-feet 1v1 dribbler. Postecoglou's in-possesion setup is highly akin to the style of Mikel Arteta and Pep Guardioloa, and Arsenal and Man City wingers like Bukaya Saka and Jack Grealish are perfect examples of the style of winger that would thrive.  



**Data Collection**

Public Data from FBRef was used for this project. To find what statistics to focus on, several players' FBRef scouting players were used to see what stands out about them. This included Saka and Grealish as well as Gabriel Martinelli and Kaoro Mitoma. 4 stats in particular seemed to be ones they each excelled in and also matched football logic in terms of what skills would be useful for that type of winger: Shot Creating Actions, Progressive Carries, Successful Take-ons, and Progressive Passes Recieved (all stats are per 90 minutes). _(Note to self: had this been a higher effort project, I would have consulted indsutry experts/professionals to see what stats to focus on)_

The relevant FBRef pages of the 2022-23 season in the Big 5 football leagues (English Premier League, German Bundesliga, French Ligue 1, Italian Serie A, and Spanish La Liga) were then downloaded as CSVs. There were 3 needed pages for each league: Standard Stats, Goal and Shot Creation, and Possession. For each league, the 3 CSVs were concatenating by player name, resulting in 5 CSVs for each league. They were each uploaded into Google Colab and then concatenated into 1 big dataframe.


**Data Wrangling?**


**Results**
There were 46 players that remained after the applying the filters. Being 60th percentile in npxG+xA per 90 was used as an additional filter to make the list smaller and to rule out players who have good skills, but lack end-product contribution. The list of players was reduced to 27.

Many of these players were quite obviously unattainable - Saka, Martinelli, Phil Foden, Rafael Leao, Khvicha Kvaratskhelia, Rodrygo, Vini Jr, Ansu Fati, Ousmane Dembele, Jamal Musiala, and Kylian Mbappe - leaving 16 potential players for Tottenham. (the fact that the likes of Kvaratskhelia and Mbappe were on the list provide a good sanity test for this project.)

The final list for Tottenham is the following: Jadon Sancho, Allan Saint-Maximin, Kaoru Mitoma, Antony, Ademola Lookman, Ferran Torres, Raphina, Justin Kluivert, Donyell Malen, Randal Kolo Muani, Moussa Diaby, Karim Adeyemi, Edon Zhegrova, Dango Ouattara, Jeremy Doku, and Rayan Cherki.


Unless Tottenham choose to sell Harry Kane, many of these players are still probably out of Tottenham's budget, with the realistic options being ASM, Lookman, Kluivert, Malen, Diaby, Adeyemi, Zhergoca, Ouattara, Doku, and Cherki.



