# Security Datasets

Repository contains several datasets related to cybersecurity of social networks, and can be used for research in bot detection, misinformation analysis, bot metrics calculation, etc.

### MKVK2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/VK_logo.png?raw=true" alt="vk_logo" width="200" />
</p>

MKVK2021 folder contains datasets with bots are real-users from VKontakte social network. 

It includes 2 csv files: bots.csv and users.csv

**bots.csv**

Bots were collected directly from bot-traders by purchasing method (is a ground-truth bot labels).
Bots also include bot-trader label and quality label.

The quality was evaluated with expert method based on the description on bot-trader offer:
1. Low quality (LOW) means that bots from this company are probably auto-generated accounts that are controlled by software. <br/>
2. Medium quality (MID) means that bots are probably user-like bots that are controlled by software.  <br/>
3. High quality (HIGH) means that bots are probably controlled by human or users from an exchange platform (bot-trader pay real users to perform malicious actions for money).

The bot-trader label:
1. OLENI and PARIK - classical bot shops.
2. MARSHRUTKA - bot exchange platform, where one pay real-users for malicious actions (fake reviews, etc.).

| Name of bot-trader that provide bots | Quality |
| --------------------------------- | ------- |
| PARIK                             | LOW     |
| PARIK                             | MID     |
| PARIK                             | HIGH    |
| OLENI                             | LOW     |
| OLENI                             | MID     |
| OLENI                             | HIGH    |
| MARSHRUTKA                        | LOW     |
| MARSHRUTKA                        | HIGH    |

**user.csv** 

users.csv contains random real-users that pose some activity from 10 communities.

Communities description:

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

#### Cite this dataset as:

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

or

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


### MKMARKET2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/market.png?raw=true" alt="vk_logo" width="300" />
</p>

Datasets for bot market analysis. Includes 2 files: buy (to buy account) and rent (rent activity).

Some properties:

- Russian Internet segment.
- 1657 offers for renting and 45 for buying.
- 5 social networks: VKontakte, Instagram, Telegram, YouTube, TikTok.
- Datasets are labeled programmatically (may contain minor errors).
- Original description in Russian (use a translator if needed).
- 2021 year.

**Rent file** – offers to rent a bot (you do not receive a login and password, but the seller will perform the desired action - give 1000 likes, write comments, etc.). Each row represent offer properties:

1. descr – original description. Description of the offer for renting bots from the seller. Other fields were partially extracted from this field. Since the sellers are Russian, the description is in Russian.
2. available - lot size. Some bots were sold only in sets (100, 1000, etc.)
3. price - price for 1 bot. To find out the cost per lot, multiply *available* by *price*.
4. sn - social network. Can be: vk (VKontakte), instagram, telegram, youtube, tiktok.
5. shop - name of bot seller.
6. action - requred action. Can be view, poll (vote in the poll), like, repost, participate (subscribe to a group, channel, etc.), friend, comment, alert (complain about content to be blocked).
7. quality - how well the bot looks like a real person. Can be low, mid, high and live (100% human driven).
8. action_n - complexity of action. Can be 1 (view), 2 (like, poll), 3 (participate, friend, repost), 4 (alert, comment).
9. quality_n - numerical quality. Can be 1 (low), 2 (mid), 3 (high), 4 (live).

**Buy file** – offers to buy a bot (you will receive a login and password). Each row represent offer properties:

1. descr – original description. Other fields were partially extracted from this field. Since the sellers are Russian, the description is in Russian.
2. available - lot size.
3. price - price for 1 bot.
4. sn - so far only VKontakte.

#### Cite
```bibtex
>@inproceedings{kolomeets2021market,
        title={Analysis of the Malicious Bots Market},
        author={Kolomeets, Maxim and Chechulin, Andrey},
        booktitle={TBD},
        pages={TBD},
        year={2021},
        organization={TBD}
}
```

### MKVKTT2021

<p align="center">
  <img src="https://github.com/guardeec/datasets/blob/main/readme_img/TT_logo.png?raw=true" alt="vk_logo" width="300" />
</p>

Datasets with result of experiment where users tried to recognise bots (**VK**ontakte **T**uring **T**est).

Includes 2 files: *answers.csv* with results of experiment and *areHumansCanDetectBots.ipynb* with processing of the results.

**answers.csv** include the following fields:
1. time - timestamp of the annotator answer
2. role - role of annotator that reflect bot detection scenario (see. list below)
3. annotator_id - Telegram id of annotator
4. analysed_account_id - VKontakte id of analysed account
5. answer - label of annotator. Can be USER, BOT or IDN (i don't know)
6. ground_truth_label - real label
7. bot_quality - quality of analysed bot account (NaN for real users), see. dataset MKVK2021 (for MARSHRUTKA bot-trader - quality was replaced with LIVE)

To each annotator we give a role. 
Roles can be:
1. BOTS+RANDOM - 50% accounts are MKVK2021 bots and 50% are real users. Real users are randomly selected among all VKontakte accounts. Reflects scenario when annotator tries to detect bot among random accounts.  
2. BOTS+GROUPS_SHIFTED - 50% accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among MKVK2021 real-users accounts. Reflects scenario when annotator tries to detect bot among accounts with homophily from large community.
3. BOTS+STUDENTS - 50% accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among verified students accounts of one University. Reflects scenario when annotator tries to detect bot among accounts with strong homophily from small community.
4. BOTS_ONLY - 100% accounts are MKVK2021 bots.

**areHumansCanDetectBots.ipynb** include code for result processing:
1. Test of hypothesis that humans can detect bots with different qualities in different scenarios.
2. Calculation of confidence intervals that describe human ability to detect bots of different qualities in different scenarios.
3. Calculation hypothetical classifier efficiency measures that describe how classification efficiency decreased when using human annotated datasets for supervised ML bot detection. 

More detailed experiment description presented in paper:
```bibtex
>@inproceedings{kolomeets2022netglow,
        title={Experimental evaluation: can humans recognize social media bots?},
        author={Kolomeets, Maxim and Vitkova, Lidia and Tushkanova, Olga and Chechulin, Andrey},
        booktitle={Proc. of the Networks in the Global World 2022 (NetGloW 2020)},
        pages={},
        year={2022},
        organization={}
}
```


