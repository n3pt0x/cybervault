# 🕷️ Search & Dorking

> [!NOTE]
> Dorking is a search method that consists of using advanced filters to get more accurate results.

## 📚 Resources

- [Dorks collections](https://www.blackhatethicalhacking.com/tools/dorks-collections-list/) | [(github)](https://github.com/blackhatethicalhacking/Dorks-collections-list#shodandorks)

### 🛠️ Tools

- [Exploit DB Google Hacking Database](https://www.exploit-db.com/google-hacking-database) - Ready-to-use Google dorks.
- [dorksearch.com](https://dorksearch.com/) - Google Dorks filters generator.
- [dorkgpt.com](https://www.dorkgpt.com/) - Create smart Google Dorks filters.
- [dorkbot (Github)](https://github.com/utiso/dorkbot) - Search exploits.

### 📝 Wordlist

- [DorkingWordlists](https://github.com/zebbern/DorkingWordlists)
- [Shodan Dorks](https://github.com/nullfuzz-pentest/shodan-dorks)
- [GoogleHackMasterList.txt](https://gist.githubusercontent.com/AizazZaidee/bb35d65dbbdd7744b26ad977f4ac693b/raw/6d37cdfd08042cd062d442ae21e880ac42cffaa5/GoogleHackMasterList.txt)
- [BugBounty Dorklist](https://github.com/mr23r0/Bug-Bounty-Dorks)

## Google Dorking

### 🔍 Core Filters

| Operator                           | Use case                                        |
| ---------------------------------- | ----------------------------------------------- |
| `site:domain.com`                  | Limit results to a specific site/domain         |
| `-site:domain.com`                 | Exclude a domain from results                   |
| `@` (e.g. `@reddit cybersecurity`) | Restrict search to a particular social platform |
| `inurl:keyword`                    | Search keyword in the URL                       |
| `intitle:keyword`                  | Search keyword in the page title                |
| `allintitle:keyword1 keyword2`     | Page title containing both keywords             |
| `allinurl:keyword1 keyword2`       | URL containing both keywords                    |
| `intext:keyword`                   | Search keyword in the page content              |
| `filetype:pdf`                     | Find specific file types (`pdf`, `xls`...)      |
| `ext:docx`                         | Same as filetype, alternative syntax            |
| `cache:domain.com`                 | View Google’s cached version                    |
| `related:domain.com`               | Find sites related to a domain                  |
| `link:domain.com`                  | Pages linking to a specific domain              |
| `before:YYYY` `before:YYYY-MM-DD`  | Pages created before a time                     |
| `after:YYYY` `after:YYYY-MM-DD`    | Pages created after a time                      |
| `2020..2022`                       | Return all page between 2020 2022               |
| `*`                                | Wildcard operator                               |
| `""`                               | Exact match search                              |
| `OR` / `-`                         | Boolean operators (OR / exclude)                |
| `"word1" AROUND(5) "word2"`        | Words appearing within 5 words of each other    |

### ⚡ Common Dorks

```bash
intitle:"index of" "parent directory" -html -htm -php
inurl:login | inurl:signin

filetype:env "DB_PASSWORD"
filetype:sql "database"
filetype:xls "password" site:gov

"@example.com" site:example.com

ext:(doc | docx | pdf)
```

## Twitter Dorking

- [Filters list](https://www.tweetbinder.com/blog/twitter-advanced-search/)

| Filter                                              | Explanation                                                    |
| --------------------------------------------------- | -------------------------------------------------------------- |
| `<word1> <word2>`                                   | Tweets containing word1 AND word2                              |
| `"word1"`                                           | Containing exact expression                                    |
| `<word1> OR <word2>`                                | Tweets containing word1 OR word 2                              |
| `john -doe`                                         | Containing "john" but without "doe"                            |
| `@username`                                         | All tweets where `@username` is mentionned                     |
| `from:<account>` / `to:<account>`                   | All tweets from an account or responding to an account         |
| `in_reply_to_tweet_id:`                             | Tweets replying to a specific tweet.                           |
| `retweets_of_tweet_id:`                             | Retweets of a specific tweet.                                  |
| `filter:follows` / `exclude:medias`                 | Filter results and display only results from followed accounts |
| `<mot> since:2015-02-20` / `<mot> until:2015-02-20` | Tweets filtered by dates                                       |
| `min_retweets:x` / `min_faves:x` / `min_replies:x`  | Minimal RT / likes / replies                                   |
| `lang:en`                                           | Language                                                       |
| `<word> :)` / `<word> :(`                           | Tweets positive and negative                                   |
| `<word> ?`                                          | Tweets with a question                                         |
| `near:Paris within:25km`                            | Location (city) with a distance range                          |
| `has:media`                                         | Tweets with photo, GIF, or video.                              |
| `has:geo`                                           | Tweets with geolocation data.                                  |

```bash

# Filters
# - safe : potentially hard or deleted
# - media : pictures or videos
# - retweets : only retweets
# - native_video : downloaded video (Amplify, Periscope, Vine)
# - periscope
# - vine
# - images : identified as photos (also coming from Instagram)
# - twimg : pic.twitter.com links
# - links : links to an URL
osint filter:<filter>
```

## Github Dorking

| Filter type    | Example                                                                            |
| -------------- | ---------------------------------------------------------------------------------- |
| **Secrets**    | `password` , `passwd` , `private`                                                  |
| **Languages**  | `language:python password` , `language:php secret`                                 |
| **Filenames**  | `filename:.env` , `filename:config.php` , `filename:.sql`                          |
| **Extensions** | `extension:pem private` , `extension:ppk private` , `extension:json client_secret` |
| **Users/Orgs** | `user:<username>` , `org:<company>` , `in:login <name>`                            |
| **Emails**     | `in:email <keyword>` , `fullname:John Doe`                                         |
| **External**   | `"<target>.atlassian"` , `"jira.<target>"` , `"<target>.okta"`                     |

```bash
# Secrets in env/config files
filename:.env DB_PASSWORD
filename:.db | .sql | sqlite3
extension:sql mysql dump

# Credentials in JSON
extension:json googleusercontent client_secret

# Organization leaks
org:<company> "password"
org:<company> "https://"
```
