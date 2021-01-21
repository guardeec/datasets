# Security Datasets

Repository contains the datasets taht can be used for experimental evaluation of supervised machine learning algorithms as well as for data visualization research in the field of information security.

### Bots from Vkontakte social network

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg" alt="VK_logo" style="zoom:80%;" />
</p>

Vkontakte_bots folder contains datasets that can be used for training and testing algorithms for social networks bot detection using friend list features. It includes 2 folders: bots and users.

Bot folder contains 8 datasets. Each dataset in the bot folder contains bots from separate bot-selling company. All bots are of different quality. 
Low quality (LOW) means that bots from this company are probably auto-generated accounts that are controlled by software. 
Medium quality (MID) means that bots are probably user-like bots that are controlled by software.  
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
