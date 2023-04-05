# Social Media Security Datasets

The repository contains several datasets related to the cybersecurity of social networks for research in bot detection, misinformation analysis, bot market analysis, bot metrics calculation, etc.

### MKMETRIC2022

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/metrics_logo.png?raw=true" alt="metrics_logo" width="300" />
</p>

MKMETRIC2022 is a dataset with VKontakte bot identifiers and their metrics:

| # | metric       | metric description             |
| ------------- | ---------- | -------------------------------- |
|1| price| the price of a bot per like (you can remap it for another activity) in the range [0, Inf]
|2| NBQ|  normalized bot quality with values [LOW=0, MID=1, HIGH=2]
|3| BTT | bot trader type that can be [SHOP=0, ECHANGE=1]
|4| speed | how fast a bot can perform an attack in the range [MINUTE=0, HOUR=1, DAY=2]
|5| SR | survival rate that reflects the probability that social network will block the bot in the range [0, 1]
|6| Trust | 6 variations of Trust measure that reflect how well users recognize the bot.

The dataset consists of 22325 bot accounts (among which 18444 are unique), and 107598 users separated into 3 groups: *random* - random accounts (low social homophily), *shift* - accounts from communities that pose some activity in VK (medium social homophily), *student* - verified users who are students of one university (high social homophily).

Folder MKMETRIC2022 consists of the following files.

**indentifiers.csv** is a list of VKontakte bots and real users with the following fields:

| # | columns       | columns description             |
| ------------- | ---------- | -------------------------------- |
|1|dataset | identifier of bot offer (bots from the same bot offer have the same metrics - see file **offers.csv**)
|2|id | VKontakte identifier
|3|label | can be [bot, random, shift, student]. [random, shift, student] are "user label" that reflects a different level of homophily.
|4|Trust, Trust_IDN, TrustZ, TrustZ_IDN, TrustNZ, TrustNZ_IDN, SR, price, BTT, speed, NBQ | metrics (is None for users).

**offers.csv** is a list of bot offers from bot traders with the following fields:

| # | columns       | columns description             |
| ------------- | ---------- | -------------------------------- |
|1| dataset | the name of the offer (corresponds to the dataset in **indentifiers.csv**)
|2| Trust, Trust_IDN, TrustZ, TrustZ_IDN, TrustNZ, TrustNZ_IDN, SR, price, BTT, speed, NBQ | metrics

**TuringTest.csv** is the additional file with the results of the Turing Test, based on which we calculated the Trust metrics. You can use that file if you want to implement your metrics. Fields:

| # | columns       | columns description             |
| ------------- | ---------- | -------------------------------- |
|1| time | timestamp of an answer
|2| annotator | id of annotator
|3| analysed_acc_vk_id | id of analysed VKontakte account
|4| human_answer | an answer of a human for an analysed VKontakte account can be [BOT, USER, IDN]. (IDN is "I don't know")
|5| true_label | a real label of analysed VKontakte account, can be [BOT, USER] in an array (as some accounts may be in multiple datasets)
|6| dataset | identifier of the dataset in the array (as some accounts may be in multiple datasets) (see **indentifiers.csv**)

More details about metrics are presented in the [paper](https://link.springer.com/article/10.1007/s13278-023-01038-3) ([preprint](https://www.researchgate.net/publication/368714138_Social_bot_metrics)) (cite as):

```bibtex
>@article{MKMETRIC2022,
        title={Social bot metrics},
        author={Kolomeets, Maxim and Chechulin, Andrey},
        journal={Social Network Analysis and Mining},
        volume={13},
        number={36},
        year={2023},
        publisher={Springer Nature}
}
```

### MKVKTT2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/TT_logo_new.png?raw=true" alt="vk_logo" width="300" />
</p>

Datasets resulted from an experiment where users tried recognising bots (**VK**ontakte **T**uring **T**est).

Includes 2 files: *answers.csv* with results of the experiment and *areHumansCanDetectBots.ipynb* with processing the results.

**answers.csv** include the following fields:

| # | column       | column description             |
| ------------- | ---------- | -------------------------------- |
|1| time | timestamp of the annotator answer
|2| role | the role of annotator that reflects bot detection scenario (see. list below)
|3| annotator_id | Telegram id of annotator
|4| analysed_account_id | VKontakte id of analysed account
|5| answer | the label of the annotator. It can be USER, BOT, or IDN (i don't know)
|6| ground_truth_label | real label
|7| bot_quality | the quality of analysed bot account (NaN for real users), see dataset MKVK2021 (for MARSHRUTKA bot-trader - the quality was replaced with LIVE)

To each annotator, we give a role. 
Roles can be:
1. BOTS+RANDOM - 50% of accounts are MKVK2021 bots and 50% are real users. Real users are randomly selected among all VKontakte accounts. Reflects scenario when annotator tries to detect bot among random accounts.  
2. BOTS+GROUPS_SHIFTED - 50% of accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among MKVK2021 real-users accounts. Reflects scenario when annotator tries to detect bot among accounts with homophily from a large community.
3. BOTS+STUDENTS - 50% of accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among verified student accounts of one University. Reflects a scenario when the annotator tries to detect a bot among accounts with strong homophily from a small community.
4. BOTS_ONLY - 100% of accounts are MKVK2021 bots.

**areHumansCanDetectBots.ipynb** include code for result processing:
1. Test hypotheses that humans can detect bots with different qualities in different scenarios.
2. Calculating confidence intervals that describe the human ability to detect bots of different qualities in different scenarios.
3. Calculating hypothetical classifier efficiency measures that describe how classification efficiency decreased when using human-annotated datasets for supervised ML bot detection. 

More detailed experiment description presented in the paper (cite as) (paper is under review, I can provide a preprint upon request):
```bibtex
>@inproceedings{MKVKTT2021,
        title={Experimental evaluation: can humans recognize social media bots?},
        author={Kolomeets, Maxim and Vitkova, Lidia and Tushkanova, Olga and Chechulin, Andrey},
        booktitle={preprint},
        pages={},
        year={2022},
        organization={}
}
```




### MKMARKET2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/market.png?raw=true" alt="vk_logo" width="300" />
</p>

Datasets for bot market analysis. Includes 2 files: buy (to buy account) and rent (rent activity).

Some properties:

- Russian Internet segment.
- 1657 offers for renting and 45 for buying.
- 5 social networks: VKontakte, Instagram, Telegram, YouTube, TikTok.
- Datasets are labelled programmatically (may contain minor errors).
- Original description in Russian (use a translator if needed).
- 2021 year.

**rent.csv** file – offers to rent a bot (you do not receive a login and password, but the seller will perform the desired action - give 1000 likes, write comments, etc.). Each row represents offer properties:

| # | column       | column description             |
| ------------- | ---------- | -------------------------------- |
| 1       | descr   | original description. Description of the offer for renting bots from the seller. Other fields were partially extracted from this field. Since the sellers are Russian, the description is in Russian.                 |
| 2      | available      | lot size. Some bots were sold only in sets (100, 1000, etc.)        |
| 3       | price | price for 1 bot. To determine the cost per lot, multiply *available* by *price*.                     |
| 4       | sn       | social network. Can be: vk (VKontakte), instagram, telegram, youtube, tiktok.       |
| 5           | shop      | name of bot seller.                     |
| 6      | action   | requred action. It can be "view", "poll" (vote in the poll), "like", "repost", "participate" (subscribe to a group, channel, etc.), "friend", "comment", "alert" (complain about content to be blocked).                   |
| 7         | quality | how well the bot looks like a real person. It can be "low", "mid", "high" and "live" (100% human driven).       |
| 8       | action_n | complexity of action. It can be 1 (view), 2 (like, poll), 3 (participate, friend, repost), 4 (alert, comment).             |
| 9       | quality_n | numerical quality. Can be 1 (low), 2 (mid), 3 (high), 4 (live).                     |



**buy.csv** file – offers to buy a bot (you will receive a login and password). Each row represents offer properties:

| # | column       | column description             |
| ------------- | ---------- | -------------------------------- |
|1| descr | original description. Other fields were partially extracted from this field. Since the sellers are Russian, the description is in Russian.
|2| available | lot size.
|3| price | price for 1 bot.
|4| sn | so far only VKontakte.

#### Cite ([paper](https://ieeexplore.ieee.org/document/9435421)) ([preprint](https://www.researchgate.net/publication/351855704_Analysis_of_the_Malicious_Bots_Market))
```bibtex
@inproceedings{kolomeets2021analysis,
        title={Analysis of the Malicious Bots Market},
        author={Kolomeets, Maxim and Chechulin, Andrey},
        booktitle={2021 29th Conference of Open Innovations Association (FRUCT)},
        pages={199--205},
        year={2021},
        organization={IEEE}
}
```

### MKVK2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/VK_logo.png?raw=true" alt="vk_logo" width="200" />
</p>

MKVK2021 folder contains datasets with bots and real-users from VKontakte social network. 

It includes 2 CSV files: bots.csv and users.csv

**bots.csv**

Bots were collected directly from bot-traders by purchasing method (is a ground-truth bot label).
Bots also include bot-trader labels and quality labels.

The quality was evaluated with the expert method based on the description of bot-trader offer:
1. Low quality (LOW) means that bots from this company are probably auto-generated accounts that are controlled by software. <br/>
2. Medium quality (MID) means that bots are user-like bots controlled by software.  <br/>
3. High quality (HIGH) means that bots are probably controlled by humans or users from an exchange platform (bot-trader pays real-users to perform malicious actions for money).

The bot-trader label:
1. OLENI and PARIK - classical bot shops.
2. MARSHRUTKA - bot exchange platform where one pays real-users for malicious actions (fake reviews, etc.).

| name of bot-trader that provide bots | Quality |
| --------------------------------- | ------- |
| PARIK                             | LOW     |
| PARIK                             | MID     |
| PARIK                             | HIGH    |
| OLENI                             | LOW     |
| OLENI                             | MID     |
| OLENI                             | HIGH    |
| MARSHRUTKA                        | LOW     |
| MARSHRUTKA                        | HIGH    |

**user.csv** file – contains random real-users that pose some activity from 10 communities. Communities description:

| Name of community | Type       | Description of group             |
| ------------- | ---------- | -------------------------------- |
| BIGFEST       | festival   | cartoon festival                 |
| HCAKBARS      | sport      | hockey club fun community        |
| LENTACH       | mass media | Russian news                     |
| MCELROY       | blog       | re-playing of funny videos       |
| MHL           | sport      | youth hockey                     |
| SEVCABEL      | commerce   | creative space                   |
| TNULL         | developers | software development memes       |
| TPROGER       | developers | software development             |
| VARENNE       | mass media | Belarus news                     |
| VELO          | activists  | development of bicycle transport |

#### Cite this dataset as ([paper](https://ieeexplore.ieee.org/document/9407191)) ([preprint](https://www.researchgate.net/publication/351655569_Camouflaged_bot_detection_using_the_friend_list)):

```bibtex
@inproceedings{kolomeets2021camouflaged,
        title={Camouflaged bot detection using the friend list},
        author={Kolomeets, Maxim and Tushkanova, Olga and Levshun, Dmitry and Chechulin, Andrey},
        booktitle={2021 29th Euromicro International Conference on Parallel, Distributed and Network-Based Processing (PDP)},
        pages={253--259},
        year={2021},
        organization={IEEE}
}
```

or ([paper](https://isyou.info/jowua/papers/jowua-v12n2-6.pdf)) ([preprint](https://www.researchgate.net/publication/361413504_Bot_detection_by_friends_graph_in_social_networks))

```bibtex
@article{kolomeets2021bot,
        title={Bot detection by friends graph in social networks},
        author={Kolomeets, Maxim and Chechulin, Andrey and Kotenko, Igor},
        journal={JoWUA},
        volume={12},
        pages={141--159},
        year={2021}
}
```
