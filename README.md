# Security Datasets

Repository contains several datasets related to cybersecurity of social networks, and can be used for research in bot detection, misinformation analysis, bot metrics calculation, etc.

### MKVK2021

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

Datasets for bot market analysis. Includes 2 files: buy (to buy account) and rent (rent activity).

Some properties:

- Russian Internet segment.
- 1657 offers for renting and 45 for buying.
- 5 social networks: VKontakte, Instagram, Telegram, YouTube, TikTok.
- Datasets are marked up programmatically (may contain minor bugs).
- Original description in Russian (use a translator if needed).

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
