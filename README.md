# Security Datasets

Repository contains the datasets taht can be used for experimental evaluation of supervised machine learning algorithms as well as for data visualization research in the field of information security.

### Bots from Vkontakte social network

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg" alt="VK_logo" style="zoom:80%;" />
</p>

Vkontakte_bots folder contains datasets that can be used for training and testing algorithms for social networks bot detection using friend list features. It includes 2 folders: bots and users.

Bot folder contains 8 datasets. Each dataset in the bot folder contains bots from separate bot-selling company. All bots are of different quality. <br/>
Low quality (LOW) means that bots from this company are probably auto-generated accounts that are controlled by software. <br/>
Medium quality (MID) means that bots are probably user-like bots that are controlled by software.  <br/>
High quality (HIGH) means that bots are probably controlled by human or users from an exchange platform.

The quality was evaluated by the description on the website of the company that traded bots.


| Name of company that provide bots | Quality |
| --------------------------------- | ------- |
| PARIK                             | LOW     |
| PARIK                             | MID     |
| PARIK                             | HIGH    |
| OLENI                             | LOW     |
| OLENI                             | MID     |
| OLENI                             | HIGH    |
| MARSHRUTKA                        | LOW     |
| MARSHRUTKA                        | HIGH    |

User folder contains 10 datasets. Each datasets contains real social network random users collected from separate social network group.

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

The dataset filename is hashed user_id. Each row represent friends of this user and their properties:
- hashed user id (id_of_friend_hashed).
- the number of friends (friends_count). 'Friend' in the context of Vkontakte social network is a user that confirm the friend request from other user.
- the number of groups (groups_count). In VKontakte social network each user can join  groups. Groups can be dedicated to some event or social interest.
- the number of subscriptions (followers_count). In VKontakte social network a user can subscribe to another user. The difference between a subscription and a friendship is that you don’t need another user’s confirmation to subscribe.
- the number of followers (subscriptions_count). Followers are users who subscribed to one's account.
- the number of photo albums (albums_count) attached to user profile. 
- the number of photos (photos_count) attached to user profile. 
- the number of posts in user profile. Each VKontakte user has his/her microblog. The number of posts is the number of records in this microblog.
- how old is id. As we hashed id, we include account 'age' as separate field. Lower values are more old accounts.

Missing values are mark as '-1'. It  indicates that profile or field has been closed by privacy settings.

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
  <img src="http://drive.google.com/uc?export=view&id=1cAdoPt3WibBMxgnti_NonUm-JXikde6F" alt="VK_logo" style="zoom:5%;" />
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
