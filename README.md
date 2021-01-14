# Security Datasets

Datasets collected for machine learning and data visualization research in the field of information security.

### VKontakte bots

<div style="text-align:center"><img src="https://upload.wikimedia.org/wikipedia/commons/2/21/VK.com-logo.svg" alt="VK_logo" style="zoom:80%;" /></div>

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

```tex
//TBD
```
