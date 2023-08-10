# data-scouting-for-wingers

Using simple data analysis to find a new winger for Tottenham



**Introduction**

With Ange Postecoglou's arrival at Tottenham, it seemed Spurs would be in the market for a winger to fit Postecoglou's style of play. (At the time of this being written, it appears Spurs are sticking with Heung Min Son and Dejan Kulusevski as the starting wingers.) This project looks to use publicly available data to find a wide creator whose profiles as a ball-to-feet 1v1 dribbler. Postecoglou's in-possesion setup is highly akin to the style of Mikel Arteta and Pep Guardioloa, and Arsenal and Man City wingers like Bukaya Saka and Jack Grealish are perfect examples of the style of winger that would thrive. With Tottenham likely being in rebuild mode, young age was also prioritized. 



**Data Collection**

Public Data from FBRef was used for this project. To find what statistics to focus on, several players' FBRef scouting players were used to see what stands out about them. This included Saka and Grealish as well as Gabriel Martinelli and Kaoro Mitoma. 4 stats in particular seemed to be ones they each excelled in and also matched football logic in terms of what skills would be useful for that type of winger: Shot Creating Actions, Progressive Carries, Successful Take-ons, and Progressive Passes Recieved (all stats are per 90 minutes). _(Note to self: had this been a higher effort project, I would have consulted indsutry experts/professionals to see what stats to focus on)_

The relevant FBRef pages of the 2022-23 season in the Big 5 football leagues (English Premier League, German Bundesliga, French Ligue 1, Italian Serie A, and Spanish La Liga) were then downloaded as CSVs. There were 3 needed pages for each league: Standard Stats, Goal and Shot Creation, and Possession. For each league, the 3 CSVs were concatenating by player name, resulting in 5 CSVs for each league. They were each uploaded into Google Colab and then concatenated into 1 big dataframe (df).


**Data Wrangling**

The type of some of the data was string rather than integers so they needed to be converted. There were alsomany instances of players having empty stats due to them playing very few minutes. However, this was not a problem because the minimum minutes threshold that was later applied filtered out all such players. 

**Methods**

A second dataframe (df2) was then created to contain only the relevant data from df1. As there is no "winger" position on FBRef, it contained all attackers (players listed as FW, FW-MF, or MF-FW). df2 also included the 4 aftormentioned stats as well as other key information like age, minutes, and npxG+xAG p90. npxG+xA per 90 was used as an additional filter to rule out players who have good skills, but lack end-product contribution. 5 new columns were also added to df2, them being the percentile ranks of each players 4 stats and npxG+xAG p90 within this group of attackers.

The final dataframe (df3) was made by applying filters. Only players who played over 10 90s in the 2022-23 domestic season, were above the 60th percentile in each of the 5 stats, and were 25 years old or younger were included. df3 was then ranked in descending order by their average percentile of the 5 stats to obtain a rough ranking of the final players.

**Results**

28 players made the final cut. Many of these players were quite obviously unattainable - Saka, Martinelli, Phil Foden, Rafael Leao, Khvicha Kvaratskhelia, Rodrygo, Vini Jr, Ansu Fati, Ousmane Dembele, Jamal Musiala, and Kylian Mbappe - leaving 17 potential players for Tottenham. (the fact that the likes of Kvaratskhelia and Mbappe were on the list provide a good sanity test for this project.)

The final list for Tottenham ranked in descedning order of their average percentile is the following: Edon Zhegrova, Rayan Cherki, Raphina, Jeremy Doku, Donyell Malen, Allan Saint-Maximin, Ademola Lookman, Jadon Sancho, Moussa Diaby, Randal Kolo Muani, Karim Adeyemi, David Pereira da Costa, Justin Kluivert, Dango Ouattara, Antony, and Ferran Torres.

Because FBRef had no specific winger position, some of these players are not actually primarily wingers. After removing players whose primary position on Transfermarkt is not either LW or RW, we are left with the final list of potential wingers for Tottenham: **Zhegrova, Raphina, Doku, Malen, ASM, Sancho, Diaby, Adeyemi, Kluivert, Ouattara, Antony, and Torres.**

These players are all of varying degrees of attainability. It is also worth noting that the order of this list is not very significant as the average of the used percentiles does not seem highly meaningful. Teams should also obviously never buy a player based on stats alone without first scouting them. Nevertheless, all of these listed players are worth Tottenham looking at. 

