# Security Datasets

Datasets collected for machine learning and data visualization research in the field of information security.

### VKontakte bots

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg" alt="VK_logo" style="zoom:80%;" />
</p>

Datasets for social networks bot detection by friend-list. Includes 2 folders: bots and users.

Bot folder includes 8 datasets - one for each company that sell bots.

| Name of company that provide bots | Quality | Description                                                  |
| --------------------------------- | ------- | ------------------------------------------------------------ |
| PARIK                             | LOW     | probably, auto-generated accounts that are controlled by software. |
| PARIK                             | MID     | probably, user-like bots that are controlled by software.    |
| PARIK                             | HIGH    | probably, bots that are controlled by human or users from an exchange platform. |
| OLENI                             | LOW     | probably, auto-generated accounts that are controlled by software. |
| OLENI                             | MID     | probably, user-like bots that are controlled by software.    |
| OLENI                             | HIGH    | probably, bots that are controlled by human or users from an exchange platform. |
| MARSHRUTKA                        | LOW     | users from the exchange platform.                            |
| MARSHRUTKA                        | HIGH    | users from the exchange platform with more filled profiles.  |

User folder includes 10 datasets - one dataset includes users collected from one group.

| Name of group | Type       | Description of group             |
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

File name is hashed user_id. Each row represent friends of this user and their properties:

- Hashed user id.
- The number of friends. Each user has its friend list. To make friends, a user must send a request, and another user must confirm it.
- The number of groups. In VKontakte each user can join groups. Groups can be dedicated to some event or social interest.
- The number of subscriptions. A person can subscribe to another person. The difference between a subscription and a friendship is that you don’t need another person’s confirmation to subscribe.
- The number of followers. Followers are people who subscribed to your account.
- The number of photos. A person can upload some photos.
- The number of albums. A person can combine photos into albums.
- The number of posts. Each VKontakte user has his/her microblog. The number of posts is the number of records in this microblog.
- How old is id. As we hashed id, we include account age as separate field. Lower values are more old accounts.

-1 value indicates that the profile or field has been closed by privacy settings

#### Cite

```bibtex
>@inproceedings{kolomeets2021camouflaged,
                title={Camouflaged bot detection using the friend list},
                author={Kolomeets, Maxim and Tushkanova, Olga and Levshun, Dmitry and Chechulin, Andrey},
                booktitle={2021 29th Euromicro International Conference on Parallel, Distributed and Network-Based Processing (PDP)},
                pages={},
                year={2021},
                organization={IEEE}
                }
```


### Bot Market

<p align="center">
  <img src="http://drive.google.com/uc?export=view&id=1cAdoPt3WibBMxgnti_NonUm-JXikde6F" alt="VK_logo" style="zoom:20%;" />
</p>


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
