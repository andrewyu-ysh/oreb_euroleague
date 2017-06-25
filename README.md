# oreb_euroleague
Statistical analysis of offensive rebounding in EuroLeague basketball season 2015-16 using play-by-plays

# Questions
1. [Identify the top 5 teams & players in offensive rebounding. Describe the metric(s) used and explain why you used it.](#1)
2. [Identify the top 5 teams & players whose offensive rebounds most effectively yield 2nd chance points.](#2)
3. [What is the 2P%, 3P%, eFG% of shots after offensive rebounds?](#3)
4. [What additional data would you acquire/use to predict likelihood of scoring 2nd chance points?](#4)
5. [What is the FG% of shots after offensive rebounds in each court zone (restricted area, (non-RA) in-the-paint, midrange, corner 3, above break 3)?](#5)
6. [Build a visualization to show FG% of shots after offensive rebounds.](#6)
7. [Additional Notes](#7)
# My Answers

## <a name="1"></a> 1. Identify the top 5 teams & players in offensive rebounding. Describe the metric(s) used and explain why you used it.

### Top 5 Offensive Rebounding Teams

1. Unicaja Malaga [MAL]
2. Anadolu Efes Istanbul [IST]
3. CSKA Moscow [CSK]
4. Olympiacos Piraeus [OLY]
5. Fenerbahce Istanbul [ULK]

### Teams' oreb-related Statistics, Sorted by oreb%

~~~~
team    games    orebs    - shots    oreb%    orebs/game    - shots/game    + shots/game      fg
----  -------  -------  ---------  -------  ------------  --------------  --------------  ------
 MAL       24      313        821   0.3812         13.04           34.21           26.54  0.4369
 IST       24      276        791   0.3489         11.5            32.96           29.96  0.4762
 TEL       10      123        356   0.3455         12.3            35.6            26.6   0.4277
 OLY       24      283        836   0.3385         11.79           34.83           27.33  0.4397
 MAD       27      312        942   0.3312         11.56           34.89           29.19  0.4555
 CSK       29      277        843   0.3286          9.55           29.07           31.17  0.5175
 ULK       29      303        925   0.3276         10.45           31.9            28.21  0.4693
 KHI       24      272        831   0.3273         11.33           34.62           29.96  0.4639
 RED       27      282        864   0.3264         10.44           32              26.85  0.4563
 PAN       27      278        856   0.3248         10.3            31.7            27.37  0.4633
 TIV       31      331       1022   0.3239         10.68           32.97           26.9   0.4494
 DAR       24      237        769   0.3082          9.88           32.04           27.08  0.4581
 BAR       29      283        929   0.3046          9.76           32.03           27.97  0.4661
 CED       24      236        795   0.2969          9.83           33.12           27.38  0.4525
 GSS       10      102        344   0.2965         10.2            34.4            24.5   0.416
 ZAL       24      244        824   0.2961         10.17           34.33           26.08  0.4317
 BAS       29      297       1012   0.2935         10.24           34.9            28.41  0.4488
 MIL       10      107        367   0.2916         10.7            36.7            26.3   0.4175
 STR       10       99        344   0.2878          9.9            34.4            27.4   0.4434
 MUN       10       99        350   0.2829          9.9            35              28.5   0.4488
 LMG       10       87        309   0.2816          8.7            30.9            25.8   0.455
 KSK       10       94        345   0.2725          9.4            34.5            25.4   0.424
 BAM       24      186        716   0.2598          7.75           29.83           27.67  0.4812
 SAS       10       75        346   0.2168          7.5            34.6            24.9   0.4185
~~~~

The top 7 teams in offensive rebounding rate (oreb%) are discussed below. The preceding numbers represent a team's rank in oreb%.

1) __Unicaja Malaga [MAL]__'s numbers are eye-popping; the team's oreb% is the league-high at an absurd 38%, with the next best team falling below 35%. With this statistic alone, _one can comfortably conclude that __MAL is at least one of the top 5 offensive rebounding teams, if not the best.__

6) __CSKA Moscow [CSK]__ is an interesting team. Their oreb% is a respectable 33%, which falls to 6th best in the league. However, they are incredibly efficient on offense. They boast league-best numbers with most shots made and least shots missed per game (which leads to highest field goal percentage (fg%)). It's one thing for a team to jack up a bunch of mediocre shots and get lots of long offensive rebounds (4 of 5 top oreb% teams are at or below league average fg%, while the next 14 teams have above average fg%), but CSK prioritizes offensive shot quality while still maintaining a great oreb%. If CSK were to punt shot quality in favor of offensive rebounds, I would expect their oreb% to surge upward. Despite being outside of the top 5 in oreb%, __I would consider CSK to be one of the 5 best offensive rebound teams.__

3) __~~Maccabi FOX Tel Aviv [TEL]~~__ is the opposite of CSK. Although their oreb% is 34.5%, good for 3rd in the league, they are the only team among the top 14 oreb% teams not to have advanced to the playoffs. In addition, they have the 5th lowest fg% in the league. For TEL, their high oreb% might actually be a side-effect of their awful shot quality rather than their knack for offensive rebounding, as discussed above. If their shot quality improves, their oreb% likely goes down. Not only that, there are only 10 games of data for TEL, containing 123 offensive rebounds from 356 missed shots; such a sample size is too big to ignore altogether, but it is small enough to be susceptible to statistical noise. __In a vacuum, I would not consider TEL to be one of the 5 best offensive rebounding teams.__

2) __Anadolu Efes Istanbul [IST]__ is like CSK, but more well-rounded. Their oreb% is 35%, 2nd best in the league; 48% fg% is 3rd best. Compared to CSK, IST gets on the offensive glass more, while their shot quality is lower. In a vacuum, I would say IST's offensive rebounding prowess is equal to or slightly higher than CSK's. __To me, IST is in the top 5.__

4) __Olympiacos Piraeus [OLY]__ and 5) __~~Real Madrid [MAD]~~__ are very similar in many ways. They get miss shots and get offensive rebounds at about the same rate per game, while MAD makes two more on two more attempts per game. In short, MAD has better shot quality, whereas OLY crashes the offensive glass more. They are probably very close in terms of offensive rebounding as a team, but __I will take OLY based the oreb% numbers.__

7) __Fenerbahce Istanbul [ULK]__ __slips in as my 5th best offensive rebounding team__. In the same vein as CSK and IST, ULK seems to prioritize shot quality, with their fg% at 4th best. However, there is a sizable group of teams that hover around 32.5 and 33.5 oreb%, all of which could be considered for the 5th spot.

### Top 5 Offensive Rebounding Players

1. HUNTER, OTHELLO [P005160]
2. KUZMIC, OGNJEN [P003479]
3. AYON, GUSTAVO [P005927]
4. REYES, FELIPE [PAAX]
5. ZIRBES, MAIK [P004183]

### Players' oreb-related Statistics, Sorted by orebs/game

~~~~
player_id   player_name              orebs    minutes    games    m/g    orebs/g    orebs/40m    adj o/40m
----------  ---------------------  -------  ---------  -------  -----  ---------  -----------  -----------
P005927     AYON, GUSTAVO               81     703.93       27  26.07       3            4.6        1.4708
P005160     HUNTER, OTHELLO             63     463.67       22  21.08       2.86         5.43       1.1433
P004183     ZIRBES, MAIK                72     681.28       27  25.23       2.67         4.23       1.2975
P001438     AUGUSTINE, JAMES            59     640.22       23  27.84       2.57         3.69       1.0684
P000925     VESELY, JAN                 58     631.37       23  27.45       2.52         3.67       1.0459
PAAX        REYES, FELIPE               64     492.18       26  18.93       2.46         5.2        1.1636
P003622     BILAN, MIRO                 52     623.58       24  25.98       2.17         3.34       0.9401
P003048     DUNSTON, BRYANT             50     504.92       24  21.04       2.08         3.96       0.8936
P005800     HONEYCUTT, TYLER            46     452.27       23  19.66       2            4.07       0.8335
P003479     KUZMIC, OGNJEN              50     344.77       25  13.79       2            5.8        0.9144
P006503     UDOH, EKPE                  53     749.7        27  27.77       1.96         2.83       0.9555
P006614     SINGLETON, CHRIS            60     671.53       31  21.66       1.94         3.57       1.0811
PLBJ        STIMAC, VLADIMIR            48     365.32       25  14.61       1.92         5.26       0.8565
P002812     HINES, KYLE                 55     763.07       29  26.31       1.9          2.88       0.9966
P005856     THOMAS, WILL                44     554.87       24  23.12       1.83         3.17       0.7786
P002507     TOMIC, ANTE                 52     589.03       29  20.31       1.79         3.53       0.9581
P002008     KUZMINSKAS, MINDAUGAS       41     489.82       23  21.3        1.78         3.35       0.7293
P000556     CLAVER, VICTOR              54     838.25       31  27.04       1.74         2.58       0.9739
PTFX        VOUGIOUKAS, IAN             41     488.78       24  20.37       1.71         3.36       0.7499
PAQU        BOUROUSIS, IOANNIS          49     727.17       29  25.07       1.69         2.7        0.8819
PJLX        KURBANOV, NIKITA            49     586.58       29  20.23       1.69         3.34       0.8793
P004425     BROWN, DERRICK              40     556.62       24  23.19       1.67         2.87       0.7232
PJDU        RADULJICA, MIROSLAV         45     552.4        27  20.46       1.67         3.26       0.8185
P002744     TILLIE, KIM                 45     650.58       29  22.43       1.55         2.77       0.811
~~~~

__AYON, GUSTAVO [P005927]__ is the league leader in total offensive rebounds (orebs) and orebs per game (orebs/g), though with a lot of games and minutes per game. But even when adjusted for such, he ranks in the top 5 for orebs per 40 minutes (orebs/40m). He is on the fringe of the elite class of offensive rebounders (4.5+ orebs/40m), but his consistency and reliability on the offensive glass gives him an edge. When adjusted for the defensive rebounding rate of his opponents, his oreb numbers on top by a large margin. His raw numbers seem to underrate him, but I think __belongs in the top 5__.

On the other hand, __KUZMIC, OGNJEN [P003479]__ has a lot of potential to be a special offensive rebounder. His league-leading 5.8 orebs/40m is off the charts. He only gets 13 minutes a game, which means his numbers are more susceptible to being fluky, it's all about gambling on upside and potential for prospects from outside the US. In the EuroLeague, I would expect him to dominate as he gets more minutes, __so he is in__.

__~~STIMAC, VLADIMIR [PLBJ]~~__ is very similar to Kuzmic, in fact grabbing the same 1.92 orebs/g with one more minute per game than Kuzmic. He is in the elite class of offensive rebounders, but when adjusted for defensive rebounding rate of his opponents, his numbers fall flat. He also showed troubling trends towards the end of the season, steadily losing orebs, and putting up multiple 0-oreb games in the playoffs. __He's not in my top 5__.

__HUNTER, OTHELLO [P005160]__ is 2nd best in orebs/40m as well as orebs/g, and he has more games, minutes, and total orebs than Kuzmic. His stats say he is very productive and well-rounded; he even logs starter minutes while still upholding his fantastic 5.43 orebs/40m, so __he is my number 1 pick__.

__REYES, FELIPE [PAAX]__'s numbers may seem a bit shaky, and he seems to land somewhere near the top 5. But among the leading offensive rebounders in the EuroLeague, he was one of the only players to show a steady growth in offensive rebounding through the season.

__ZIRBES, MAIK [P004183]__ is Ayon-lite. His offensive rebounding production falls short of Ayon by all metrics, but his consistency is not to be ignored. He puts up starter minutes, with decent per minute numbers, as well as against very strong opposition. __He just barely makes the cut__.

Stats used: orebs, minutes per game, adjusted orebs/40m: when a player grabs an offensive rebound, its value depends on the opponent's defensive rebounding prowess. In the EuroLeague, there is a large gap between the best and worst defensive rebounding teams. Therefore, the raw orebs/40m is adjusted based on opponent defensive rebounding percentage (e.g. an oreb against a team with a dreb% of 80% is worth 0.8 adjusted oreb, instead of a flat 1).

## <a name="2"></a> 2. Identify the top 5 teams & players whose offensive rebounds most effectively yield 2nd chance points.

### Top 5 Teams

1. Zalgiris Kaunas (ZAL)
1. Khimki Moscow Region (KHI)
1. CSKA Moscow (CSK)
1. Real Madrid (MAD)
1. Olympiacos Piraeus (OLY)

### Teams' Offensive Efficiency Statistics, Sorted by (oreb-eFG / eFG)

~~~~
team      orebs    + 2fg    - 2fg    + 3fg    - 3fg     oreb-FG     oreb-eFG     eFG    oreb-eFG / eFG
------  -------  -------  -------  -------  -------  ----------  -----------  ------  ----------------
SAS          54       23       17        6        8      0.537        0.5926  0.4899          1.20958
KSK          69       31       15        5       18      0.5217       0.558   0.4825          1.15649
ZAL         186       76       68       15       27      0.4892       0.5296  0.4762          1.11206
KHI         194       82       48       21       43      0.5309       0.5851  0.5323          1.09919
LMG          63       27       22        6        8      0.5238       0.5714  0.5229          1.09275
MAD         229       88       70       29       42      0.5109       0.5742  0.5312          1.08099
OLY         205       80       81       20       24      0.4878       0.5366  0.4997          1.07389
BAM         124       55       37       12       20      0.5403       0.5887  0.55            1.07038
PAN         192       81       63       17       31      0.5104       0.5547  0.5213          1.06401
ULK         222      104       69       15       34      0.536        0.5698  0.5382          1.05884
DAR         160       73       54       10       23      0.5188       0.55    0.5215          1.05466
MIL          82       30       28        7       17      0.4512       0.4939  0.4738          1.04241
CED         169       84       53        3       29      0.5148       0.5237  0.5079          1.03101
CSK         203       88       55       25       35      0.5567       0.6182  0.6007          1.0291
IST         194       89       72       13       20      0.5258       0.5593  0.5493          1.0181
BAR         190       69       66       22       33      0.4789       0.5368  0.5376          0.998509
MAL         221       89       80       14       38      0.4661       0.4977  0.4997          0.996158
MUN          69       25       23        6       15      0.4493       0.4928  0.5126          0.961286
RED         209       92       69        7       41      0.4737       0.4904  0.5154          0.951519
BAS         210       75       68       18       49      0.4429       0.4857  0.5226          0.929413
TEL          84       27       33        8       16      0.4167       0.4643  0.5032          0.922638
TIV         238       88       82       19       49      0.4496       0.4895  0.5307          0.922339
STR          74       29       31        2       12      0.4189       0.4324  0.4935          0.876207
GSS          64       20       27        4       13      0.375        0.4062  0.4694          0.865393
~~~~

Mostly, a good offensive team also scores efficiently on 2nd chance points, which doesn't say much about whether a team gets offensive rebounds that yield easier scoring opportunities. To discern the difference, the disparity between eFG% after an oreb, and eFG% overall for a team is measured. The sample sizes are too small and noisy to make strong claim.

__Zalgiris Kaunas (ZAL)__ is the first team among the top oreb-eFG%/eFG% ratio teams that don't suffer from unuseably small sample sizes. At 186 orebs, their oreb-eFG is 10% higher than overall-eFG. So to strictly answer the question, ZAL has to be included in the top 5 teams.

__Khimki Moscow Region (KHI)__ is the next up, their oreb-eFG just short of 10% higher than overall-eFG. Their sample size is also good, so one can claim that the 10% disparity is a product of the team's offensive rebounding dynamic, instead of statistical noise.

__CSKA Moscow (CSK)__ is not among the teams whose oreb-eFG numbers are way higher than their overal-eFG. However, they rebound more than both teams above on the list, (ZAL, KHI), and their oreb-eFG in general leads the league at almost 62%, the only team higher than 60%. But as stated above, their high oreb-eFG% is a product of their efficient offense in general.

__~~Dinamo Banco di Sardegna Sassari (SAS)~~__ has to be considered just because of their whopping 20% increase in eFG in 2nd chance points compared to overall eFG, and they get offensive rebounds at a pretty high clip, but they did not play many games, only 54 offensive rebounds in the season. Too noisy to count.

__Real Madrid (MAD)__ is 2nd in the league in raw offensive rebounds, and they get about 8% higher eFG after an oreb than overall, which is 6th best. Very solid all around, with a large sample size.

__Olympiacos Piraeus (OLY)__ is on the fringe, but sneaks in because of their large sample size, good overall oreb numbers, and 7th overall in oreb-eFG%/eFG% ratio. Nothing too flashy about them, but good enough.

### Top 5 Players

### Players' Team Offensive Efficiency after Players' orebs, sorted by oreb-eFG

~~~~
player_id    team      oreb-eFG    oreb-FGA
-----------  ------  ----------  ----------
P002812      CSK       0.72449           49
PJDU         PAN       0.71875           32
P000925      ULK       0.683673          49
P006503      ULK       0.666667          39
PLHI         CSK       0.66              25
PAMM         OLY       0.659091          22
P004425      IST       0.65625           32
PBWI         ZAL       0.653846          26
P002507      BAR       0.644737          38
PJYB         DAR       0.642857          28
P004119      IST       0.642857          21
P005927      MAD       0.640625          64
P005757      TIV       0.637931          29
PAQU         BAS       0.631579          38
P003479      PAN       0.625             32
P004132      BAM       0.625             24
PTFX         ZAL       0.614286          35
P003622      CED       0.612245          49
PJLX         CSK       0.611111          36
PAAX         MAD       0.602041          49
~~~~

* ['HINES, KYLE']
* ['RADULJICA, MIROSLAV']
* ['VESELY, JAN']
* ['UDOH, EKPE']
* ['AYON, GUSTAVO']

These are the top 5 players in terms of eFG% of shots by him or his teammates after his offensive rebounds.

* ['HINES, KYLE']
* ['RADULJICA, MIROSLAV']
* ['VESELY, JAN']
* ['UDOH, EKPE']
* ~~['VORONTSEVICH, ANDREY']~~

I set the limit at 20 shot attempts after a player's offensive rebounds, and the results are decent. 'VORONTSEVICH, ANDREY' is very questionable because of his orebs -> shot attempts numbers at 25. I prefer ['AYON, GUSTAVO'], just because he puts up huge oreb numbers, and the subsequent shot attempt eFG% is 12th best. Not great, but extremely consistent.

## <a name="3"></a>  3. What is the 2P%, 3P%, eFG% of shots after offensive rebounds?

~~~~
------------------------------
       made    attempted    FG%
---  ------  -----------  -----
FG     1829         3705  49.37
2FG    1525         2756  55.33
3FG     304          949  32.03
eFG                       53.47
~~~~

## <a name="4"></a> 4. What additional data would you acquire/use to predict likelihood of scoring 2nd chance points?

1. Location of Offensive Rebounds
2. Location of other players at the time of the missed shot and rebound (many defensive players may be out of position to defend another possession)
3. Height/position of the rebounder

## <a name="5"></a> 5. What is the FG% of shots after offensive rebounds in each court zone (restricted area, (non-RA) in-the-paint, midrange, corner 3, above break 3)?¶

~~~~
                region    made    attempted     fg%
----------------------  ------  -----------  ------
       restricted area    3368         4163  0.809
 (non-RA) in-the-paint    4656        10036  0.4639
              midrange    1795         4894  0.3668
              corner 3     627         1501  0.4177
         above break 3    3419         9808  0.3486
~~~~

### Sample Visualization (made and missed shots from "(non-RA) in-the-paint" and "above break 3"). The misplaced "x" is caused by artifacts in the data.

<p align="center">
    <img src="https://github.com/andrewyuysh/oreb_euroleague/blob/master/img/oreb_3a_2p.png" width="750">
</p>

## 6. <a name="6"></a> Build a visualization to show FG% of shots after offensive rebounds.

### An Attempt at Visualization (To-Do: Hex-shape heatmap)

<p align="center">
    <img src="https://github.com/andrewyuysh/oreb_euroleague/blob/master/img/oreb_heatmap.png" width="750">
</p>

## 7. <a name="7"></a> Additional Notes

For any questions or inquiries about this project, contact me at andrewyu.ysh@gmail.com.
