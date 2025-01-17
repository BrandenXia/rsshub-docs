# 🌟 Popular

## AP News <Site url="apnews.com"/>

### News <Site url="apnews.com" size="sm" />

<Route namespace="apnews" :data='{"path":"/rss/:category?","categories":["traditional-media","popular"],"example":"/apnews/rss/business","parameters":{"category":{"description":"Category from the first segment of the corresponding site, or `index` for the front page.","default":"index"}},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["apnews.com/:rss"],"target":"/rss/:rss"}],"name":"News","maintainers":["zoenglinghou","mjysci","TonyRL"],"location":"rss.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

### Topics <Site url="apnews.com" size="sm" />

<Route namespace="apnews" :data='{"path":"/topics/:topic?","categories":["traditional-media","popular"],"example":"/apnews/topics/apf-topnews","parameters":{"topic":{"description":"Topic name, can be found in URL. For example: the topic name of AP Top News [https://apnews.com/apf-topnews](https://apnews.com/apf-topnews) is `apf-topnews`","default":"trending-news"}},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["apnews.com/hub/:topic"],"target":"/topics/:topic"}],"name":"Topics","maintainers":["zoenglinghou","mjysci","TonyRL"],"location":"topics.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## Docker Hub <Site url="hub.docker.com"/>

### Image New Build <Site url="hub.docker.com" size="sm" />

<Route namespace="dockerhub" :data='{"path":"/build/:owner/:image/:tag?","categories":["program-update","popular"],"example":"/dockerhub/build/wangqiru/ttrss","parameters":{"owner":"Image owner, the owner of the official image fills in the library, for example: /dockerhub/build/library/mysql","image":"Image name","tag":{"description":"Image tag","default":"latest"}},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"Image New Build","maintainers":["HenryQW"],"location":"build.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## Fediverse <Site url="fediverse.observer"/>

### Timeline <Site url="fediverse.observer" size="sm" />

<Route namespace="fediverse" :data='{"path":"/timeline/:account","categories":["social-media","popular"],"example":"/fediverse/timeline/Mastodon@mastodon.social","parameters":{"account":"username@domain"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"Timeline","maintainers":["DIYgod"],"location":"timeline.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## GitHub <Site url="github.com"/>

:::tip
GitHub provides some official RSS feeds:

-   Repo releases: `https://github.com/:owner/:repo/releases.atom`
-   Repo commits: `https://github.com/:owner/:repo/commits.atom`
-   User activities: `https://github.com/:user.atom`
-   Private feed: `https://github.com/:user.private.atom?token=:secret` (You can find **Subscribe to your news feed** in [dashboard](https://github.com) page after login)
-   Wiki history: `https://github.com/:owner/:repo/wiki.atom`
:::

### Repo Issues <Site url="github.com" size="sm" />

<Route namespace="github" :data='{"path":"/issue/:user/:repo/:state?/:labels?","categories":["programming","popular"],"example":"/github/issue/vuejs/core/all/wontfix","parameters":{"user":"GitHub username","repo":"GitHub repo name","state":{"description":"the state of the issues.","default":"open","options":[{"label":"Open","value":"open"},{"label":"Closed","value":"closed"},{"label":"All","value":"all"}]},"labels":"a list of comma separated label names"},"radar":[{"source":["github.com/:user/:repo/issues","github.com/:user/:repo/issues/:id","github.com/:user/:repo"],"target":"/issue/:user/:repo"}],"name":"Repo Issues","maintainers":["HenryQW","AndreyMZ"],"location":"issue.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## Instagram <Site url="www.instagram.com"/>

:::tip
It's highly recommended to deploy with Redis cache enabled.
:::

### User Profile / Hashtag - Private API <Site url="www.instagram.com" size="sm" />

<Route namespace="instagram" :data='{"path":"/:category/:key","categories":["social-media","popular"],"example":"/instagram/user/stefaniejoosten","parameters":{"category":"Feed category, see table above","key":"Username / Hashtag name"},"features":{"requireConfig":[{"name":"IG_PROXY","optional":true,"description":""},{"name":"IG_USERNAME","description":"Instagram username"},{"name":"IG_PASSWORD","description":"Instagram password, due to [Instagram Private API](https://github.com/dilame/instagram-private-api) restrictions, you have to setup your credentials on the server. 2FA is not supported."}],"requirePuppeteer":false,"antiCrawler":true,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"User Profile / Hashtag - Private API","maintainers":["oppilate","DIYgod"],"location":"private-api/index.ts"}' :test='undefined' />

## JavBus <Site url="www.javbus.com"/>

:::warning
Requests from non-Asia areas will be redirected to login page.
:::

:::tip Language
You can change the language of each route to the languages listed below.

| English | 日本语 | 한국의 | 中文             |
| ------- | ------ | ------ | ---------------- |
| en      | ja     | ko     | (leave it empty) |
:::

:::tip
JavBus has multiple backup domains, these routes use default domain `https://javbus.com`. If the domain is unreachable, you can add `?domain=<domain>` to the end of the route to specify the domain to visit. Let say you want to use the backup domain `https://javsee.icu`, you can add `?domain=javsee.icu` to the end of the route, then the route will be [`/javbus/en?domain=javsee.icu`](https://rsshub.app/javbus?domain=javsee.icu)

**Note**: **Western** has different domain than the main site, the backup domains are also different. The default domain is `https://javbus.org` and you can add `?western_domain=<domain>` to the end of the route to specify the domain to visit. Let say you want to use the backup domain `https://javsee.one`, you can add `?western_domain=javsee.one` to the end of the route, then the route will be [`/javbus/western/en?western_domain=javsee.one`](https://rsshub.app/javbus/western?western_domain=javsee.one)
:::

### Works <Site url="www.javbus.com" size="sm" />

<Route namespace="javbus" :data='{"path":"/:path{.+}?","radar":[{"source":["www.javbus.com/:path*"],"target":"/:path"}],"name":"Works","maintainers":["MegrezZhu","CoderTonyChan","nczitzk","Felix2yu"],"categories":["multimedia","popular"],"url":"www.javbus.com","example":"/javbus/star/rwt","parameters":{"path":{"description":"Any path of list page on javbus"}},"location":"index.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## Lofter <Site url="www.lofter.com"/>

### User <Site url="www.lofter.com" size="sm" />

<Route namespace="lofter" :data='{"path":"/user/:name?","categories":["social-media","popular"],"example":"/lofter/user/i","parameters":{"name":"Lofter user name, can be found in the URL"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"User","maintainers":["hondajojo","nczitzk","LucunJi"],"location":"user.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## pixiv <Site url="www.pixiv.net"/>

### Keyword <Site url="www.pixiv.net" size="sm" />

<Route namespace="pixiv" :data='{"path":"/search/:keyword/:order?/:mode?","categories":["social-media","popular"],"example":"/pixiv/search/Nezuko/popular","parameters":{"keyword":"keyword","order":{"description":"rank mode, empty or other for time order, popular for popular order","default":"date","options":[{"label":"time order","value":"date"},{"label":"popular order","value":"popular"}]},"mode":{"description":"filte R18 content","default":"no","options":[{"label":"only not R18","value":"safe"},{"label":"only R18","value":"r18"},{"label":"no filter","value":"no"}]}},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"Keyword","maintainers":["DIYgod"],"location":"search.ts"}' :test='{"code":1,"message":"expected 503 to be 200 // Object.is equality"}' />

### Rankings <Site url="www.pixiv.net" size="sm" />

<Route namespace="pixiv" :data='{"path":"/ranking/:mode/:date?","categories":["social-media","popular"],"example":"/pixiv/ranking/week","parameters":{"mode":{"description":"rank type","options":[{"value":"day","label":"daily rank"},{"value":"week","label":"weekly rank"},{"value":"month","label":"monthly rank"},{"value":"day_male","label":"male rank"},{"value":"day_felame","label":"female rank"},{"value":"day_ai","label":"AI-generated work Rankings"},{"value":"week_original","label":"original rank"},{"value":"week_rookie","label":"rookie user rank"},{"value":"day_r18","label":"R-18 daily rank"},{"value":"day_r18_ai","label":"R-18 AI-generated work"},{"value":"day_male_r18","label":"R-18 male rank"},{"value":"day_female_r18","label":"R-18 female rank"},{"value":"week_r18","label":"R-18 weekly rank"},{"value":"week_r18g","label":"R-18G rank"}]},"date":"format: `2018-4-25`"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"Rankings","maintainers":["EYHN"],"location":"ranking.ts"}' :test='{"code":1,"message":"expected 503 to be 200 // Object.is equality"}' />

### User Activity <Site url="www.pixiv.net" size="sm" />

<Route namespace="pixiv" :data='{"path":"/user/:id","categories":["social-media","popular"],"example":"/pixiv/user/15288095","parameters":{"id":"user id, available in user&#39;s homepage URL"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["www.pixiv.net/users/:id"]}],"name":"User Activity","maintainers":["DIYgod"],"location":"user.ts"}' :test='{"code":1,"message":"expected 503 to be 200 // Object.is equality"}' />

## Reuters <Site url="reuters.com"/>

:::tip
You can use `sophi=true` query parameter to invoke the **experimental** method, which can, if possible, fetch more articles(between 20 and 100) with `limit` given. But some articles from the old method might not be available.
:::

### Category/Topic/Author <Site url="reuters.com" size="sm" />

<Route namespace="reuters" :data='{"path":"/:category/:topic?","categories":["traditional-media","popular"],"example":"/reuters/world/us","parameters":{"category":"find it in the URL, or tables below","topic":"find it in the URL, or tables below"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["reuters.com/:category/:topic?","reuters.com/"]}],"name":"Category/Topic/Author","maintainers":["LyleLee","HenryQW","proletarius101","black-desk","nczitzk"],"description":"-   `:category`:\n\n      | World | Business | Legal | Markets | Breakingviews | Technology | Graphics |\n      | ----- | -------- | ----- | ------- | ------------- | ---------- | -------- |\n      | world | business | legal | markets | breakingviews | technology | graphics |\n\n  -   `world/:topic`:\n\n      | All | Africa | Americas | Asia Pacific | China | Europe | India | Middle East | United Kingdom | United States | The Great Reboot | Reuters Next |\n      | --- | ------ | -------- | ------------ | ----- | ------ | ----- | ----------- | -------------- | ------------- | ---------------- | ------------ |\n      |     | africa | americas | asia-pacific | china | europe | india | middle-east | uk             | us            | the-great-reboot | reuters-next |\n\n  -   `business/:topic`:\n\n      | All | Aerospace & Defense | Autos & Transportation | Energy | Environment | Finance | Healthcare & Pharmaceuticals | Media & Telecom | Retail & Consumer | Sustainable Business | Charged | Future of Health | Future of Money | Take Five | Reuters Impact |\n      | --- | ------------------- | ---------------------- | ------ | ----------- | ------- | ---------------------------- | --------------- | ----------------- | -------------------- | ------- | ---------------- | --------------- | --------- | -------------- |\n      |     | aerospace-defense   | autos-transportation   | energy | environment | finance | healthcare-pharmaceuticals   | media-telecom   | retail-consumer   | sustainable-business | charged | future-of-health | future-of-money | take-five | reuters-impact |\n\n  -   `legal/:topic`:\n\n      | All | Government | Legal Industry | Litigation | Transactional |\n      | --- | ---------- | -------------- | ---------- | ------------- |\n      |     | government | legalindustry  | litigation | transactional |\n\n  -   `authors/:topic`:\n\n      | Default | Jonathan Landay | any other authors |\n      | ------- | --------------- | ----------------- |\n      | reuters | jonathan-landay | their name in URL |\n\n  More could be found in the URL of the category/topic page.","location":"common.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

-   `:category`:

      | World | Business | Legal | Markets | Breakingviews | Technology | Graphics |
      | ----- | -------- | ----- | ------- | ------------- | ---------- | -------- |
      | world | business | legal | markets | breakingviews | technology | graphics |

  -   `world/:topic`:

      | All | Africa | Americas | Asia Pacific | China | Europe | India | Middle East | United Kingdom | United States | The Great Reboot | Reuters Next |
      | --- | ------ | -------- | ------------ | ----- | ------ | ----- | ----------- | -------------- | ------------- | ---------------- | ------------ |
      |     | africa | americas | asia-pacific | china | europe | india | middle-east | uk             | us            | the-great-reboot | reuters-next |

  -   `business/:topic`:

      | All | Aerospace & Defense | Autos & Transportation | Energy | Environment | Finance | Healthcare & Pharmaceuticals | Media & Telecom | Retail & Consumer | Sustainable Business | Charged | Future of Health | Future of Money | Take Five | Reuters Impact |
      | --- | ------------------- | ---------------------- | ------ | ----------- | ------- | ---------------------------- | --------------- | ----------------- | -------------------- | ------- | ---------------- | --------------- | --------- | -------------- |
      |     | aerospace-defense   | autos-transportation   | energy | environment | finance | healthcare-pharmaceuticals   | media-telecom   | retail-consumer   | sustainable-business | charged | future-of-health | future-of-money | take-five | reuters-impact |

  -   `legal/:topic`:

      | All | Government | Legal Industry | Litigation | Transactional |
      | --- | ---------- | -------------- | ---------- | ------------- |
      |     | government | legalindustry  | litigation | transactional |

  -   `authors/:topic`:

      | Default | Jonathan Landay | any other authors |
      | ------- | --------------- | ----------------- |
      | reuters | jonathan-landay | their name in URL |

  More could be found in the URL of the category/topic page.

## RSSHub <Site url="docs.rsshub.app"/>

### New routes <Site url="docs.rsshub.app/*" size="sm" />

<Route namespace="rsshub" :data='{"path":"/routes/:lang?","categories":["program-update","popular"],"example":"/rsshub/routes/en","parameters":{"lang":{"description":"Language","options":[{"label":"Chinese","value":"zh"},{"label":"English","value":"en"}],"default":"en"}},"radar":[{"source":["docs.rsshub.app/*"],"target":"/routes"}],"name":"New routes","maintainers":["DIYgod"],"url":"docs.rsshub.app/*","location":"routes.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## Telegram <Site url="t.me"/>

### Channel <Site url="t.me" size="sm" />

<Route namespace="telegram" :data='{"path":"/channel/:username/:routeParams?","categories":["social-media","popular"],"example":"/telegram/channel/awesomeDIYgod/searchQuery=twitter","parameters":{"username":"channel username","routeParams":"extra parameters, see the table below\n| Key                    | Description                                                           | Accepts                                            | Defaults to  |\n| ---------------------- | --------------------------------------------------------------------- | -------------------------------------------------- | ------------ |\n| showLinkPreview        | Show the link preview from Telegram                                   | 0/1/true/false                                     | true         |\n| showViaBot             | For messages sent via bot, show the bot                               | 0/1/true/false                                     | true         |\n| showReplyTo            | For reply messages, show the target of the reply                      | 0/1/true/false                                     | true         |\n| showFwdFrom            | For forwarded messages, show the forwarding source                    | 0/1/true/false                                     | true         |\n| showFwdFromAuthor      | For forwarded messages, show the author of the forwarding source      | 0/1/true/false                                     | true         |\n| showInlineButtons      | Show inline buttons                                                   | 0/1/true/false                                     | false        |\n| showMediaTagInTitle    | Show media tags in the title                                          | 0/1/true/false                                     | true         |\n| showMediaTagAsEmoji    | Show media tags as emoji                                              | 0/1/true/false                                     | true         |\n| showHashtagAsHyperlink | Show hashtags as hyperlinks (`https://t.me/s/channel?q=%23hashtag`) | 0/1/true/false                                     | true         |\n| includeFwd             | Include forwarded messages                                            | 0/1/true/false                                     | true         |\n| includeReply           | Include reply messages                                                | 0/1/true/false                                     | true         |\n| includeServiceMsg      | Include service messages (e.g. message pinned, channel photo updated) | 0/1/true/false                                     | true         |\n| includeUnsupportedMsg  | Include messages unsupported by t.me                                  | 0/1/true/false                                     | false        |\n| searchQuery            | search query                                                          | keywords; replace `#hashtag` with `%23hashtag` | (no keyword) |\n\nSpecify different option values than default values can meet different needs, URL\n\n```\nhttps://rsshub.app/telegram/channel/NewlearnerChannel/showLinkPreview=0&showViaBot=0&showReplyTo=0&showFwdFrom=0&showFwdFromAuthor=0&showInlineButtons=0&showMediaTagInTitle=1&showMediaTagAsEmoji=1&includeFwd=0&includeReply=1&includeServiceMsg=0&includeUnsupportedMsg=0\n```\n\ngenerates an RSS without any link previews and annoying metadata, with emoji media tags in the title, without forwarded messages (but with reply messages), and without messages you don&#39;t care about (service messages and unsupported messages), for people who prefer pure subscriptions.\n\nFor backward compatibility reasons, invalid `routeParams` will be treated as `searchQuery` .\n"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["t.me/s/:username"],"target":"/channel/:username"}],"name":"Channel","maintainers":["DIYgod","Rongronggg9"],"description":"\n  :::tip\n  Due to Telegram restrictions, some channels involving pornography, copyright, and politics cannot be subscribed. You can confirm by visiting `https://t.me/s/:username`.\n  :::","location":"channel.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />


  :::tip
  Due to Telegram restrictions, some channels involving pornography, copyright, and politics cannot be subscribed. You can confirm by visiting `https://t.me/s/:username`.
  :::

## X (Twitter) <Site url="x.com"/>

Specify options (in the format of query string) in parameter `routeParams` to control some extra features for Tweets

| Key                            | Description                                                                                                                          | Accepts                | Defaults to                               |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------- | ----------------------------------------- |
| `readable`                     | Enable readable layout                                                                                                               | `0`/`1`/`true`/`false` | `false`                                   |
| `authorNameBold`               | Display author name in bold                                                                                                          | `0`/`1`/`true`/`false` | `false`                                   |
| `showAuthorInTitle`            | Show author name in title                                                                                                            | `0`/`1`/`true`/`false` | `false` (`true` in `/twitter/followings`) |
| `showAuthorInDesc`             | Show author name in description (RSS body)                                                                                           | `0`/`1`/`true`/`false` | `false` (`true` in `/twitter/followings`) |
| `showQuotedAuthorAvatarInDesc` | Show avatar of quoted Tweet's author in description (RSS body) (Not recommended if your RSS reader extracts images from description) | `0`/`1`/`true`/`false` | `false`                                   |
| `showAuthorAvatarInDesc`       | Show avatar of author in description (RSS body) (Not recommended if your RSS reader extracts images from description)                | `0`/`1`/`true`/`false` | `false`                                   |
| `showEmojiForRetweetAndReply`  | Use "🔁" instead of "RT", "↩️" & "💬" instead of "Re"                                                                                | `0`/`1`/`true`/`false` | `false`                                   |
| `showSymbolForRetweetAndReply` | Use " RT " instead of "", " Re " instead of ""                                                                                       | `0`/`1`/`true`/`false` | `true`                                    |
| `showRetweetTextInTitle`       | Show quote comments in title (if `false`, only the retweeted tweet will be shown in the title)                                       | `0`/`1`/`true`/`false` | `true`                                    |
| `addLinkForPics`               | Add clickable links for Tweet pictures                                                                                               | `0`/`1`/`true`/`false` | `false`                                   |
| `showTimestampInDescription`   | Show timestamp in description                                                                                                        | `0`/`1`/`true`/`false` | `false`                                   |
| `showQuotedInTitle`            | Show quoted tweet in title                                                                                                           | `0`/`1`/`true`/`false` | `false`                                   |
| `widthOfPics`                  | Width of Tweet pictures                                                                                                              | Unspecified/Integer    | Unspecified                               |
| `heightOfPics`                 | Height of Tweet pictures                                                                                                             | Unspecified/Integer    | Unspecified                               |
| `sizeOfAuthorAvatar`           | Size of author's avatar                                                                                                              | Integer                | `48`                                      |
| `sizeOfQuotedAuthorAvatar`     | Size of quoted tweet's author's avatar                                                                                               | Integer                | `24`                                      |
| `excludeReplies`               | Exclude replies, only available in `/twitter/user`                                                                                   | `0`/`1`/`true`/`false` | `false`                                   |
| `includeRts`                   | Include retweets, only available in `/twitter/user`                                                                                  | `0`/`1`/`true`/`false` | `true`                                    |
| `forceWebApi`                  | Force using Web API even if Developer API is configured, only available in `/twitter/user` and `/twitter/keyword`                    | `0`/`1`/`true`/`false` | `false`                                   |
| `count`                        | `count` parameter passed to Twitter API, only available in `/twitter/user`                                                           | Unspecified/Integer    | Unspecified                               |

Specify different option values than default values to improve readability. The URL

```
https://rsshub.app/twitter/user/durov/readable=1&authorNameBold=1&showAuthorInTitle=1&showAuthorInDesc=1&showQuotedAuthorAvatarInDesc=1&showAuthorAvatarInDesc=1&showEmojiForRetweetAndReply=1&showRetweetTextInTitle=0&addLinkForPics=1&showTimestampInDescription=1&showQuotedInTitle=1&heightOfPics=150
```

generates

<img loading="lazy" src="/img/readable-twitter.png" alt="Readable Twitter RSS of Durov" />

Currently supports two authentication methods:

- Using `TWITTER_COOKIE` (recommended): Configure the cookies of logged-in Twitter Web, at least including the fields auth_token and ct0. RSSHub will use this information to directly access Twitter's web API to obtain data.

- Using `TWITTER_USERNAME` `TWITTER_PASSWORD` and `TWITTER_AUTHENTICATION_SECRET`: Configure the Twitter username and password. RSSHub will use this information to log in to Twitter and obtain data using the mobile API. Please note that if you have not logged in with the current IP address before, it is easy to trigger Twitter's risk control mechanism.


### Keyword <Site url="x.com" size="sm" />

<Route namespace="twitter" :data='{"path":"/keyword/:keyword/:routeParams?","categories":["social-media","popular"],"example":"/twitter/keyword/RSSHub","parameters":{"keyword":"keyword","routeParams":"extra parameters, see the table above"},"features":{"requireConfig":[{"name":"TWITTER_USERNAME","description":"Please see above for details."},{"name":"TWITTER_PASSWORD","description":"Please see above for details."},{"name":"TWITTER_COOKIE","description":"Please see above for details."}],"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"Keyword","maintainers":["DIYgod","yindaheng98","Rongronggg9"],"radar":[{"source":["x.com/search"]}],"location":"keyword.ts"}' :test='undefined' />

### User media <Site url="x.com" size="sm" />

<Route namespace="twitter" :data='{"path":"/media/:id/:routeParams?","categories":["social-media","popular"],"example":"/twitter/media/DIYgod","parameters":{"id":"username; in particular, if starts with `+`, it will be recognized as a [unique ID](https://github.com/DIYgod/RSSHub/issues/12221), e.g. `+44196397`","routeParams":"extra parameters, see the table above."},"features":{"requireConfig":[{"name":"TWITTER_USERNAME","description":"Please see above for details."},{"name":"TWITTER_PASSWORD","description":"Please see above for details."},{"name":"TWITTER_COOKIE","description":"Please see above for details."}],"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"User media","maintainers":["DIYgod","yindaheng98","Rongronggg9"],"radar":[{"source":["x.com/:id/media"],"target":"/media/:id"}],"location":"media.ts"}' :test='undefined' />

### User timeline <Site url="x.com" size="sm" />

<Route namespace="twitter" :data='{"path":"/user/:id/:routeParams?","categories":["social-media","popular"],"example":"/twitter/user/DIYgod","parameters":{"id":"username; in particular, if starts with `+`, it will be recognized as a [unique ID](https://github.com/DIYgod/RSSHub/issues/12221), e.g. `+44196397`","routeParams":"extra parameters, see the table above; particularly when `routeParams=exclude_replies`, replies are excluded; `routeParams=exclude_rts` excludes retweets,`routeParams=exclude_rts_replies` exclude replies and retweets; for default include all."},"features":{"requireConfig":[{"name":"TWITTER_USERNAME","description":"Please see above for details."},{"name":"TWITTER_PASSWORD","description":"Please see above for details."},{"name":"TWITTER_AUTHENTICATION_SECRET","description":"TOTP 2FA secret, please see above for details.","optional":true},{"name":"TWITTER_COOKIE","description":"Please see above for details."}],"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"User timeline","maintainers":["DIYgod","yindaheng98","Rongronggg9"],"radar":[{"source":["x.com/:id"],"target":"/user/:id"}],"location":"user.ts"}' :test='undefined' />

## YouTube <Site url="youtube.com"/>

### Channel with username <Site url="youtube.com" size="sm" />

<Route namespace="youtube" :data='{"path":"/user/:username/:embed?","categories":["social-media","popular"],"example":"/youtube/user/@JFlaMusic","parameters":{"username":"YouTuber username with @","embed":"Default to embed the video, set to any value to disable embedding"},"features":{"requireConfig":[{"name":"YOUTUBE_KEY","description":" YouTube API Key, support multiple keys, split them with `,`, [API Key application](https://console.developers.google.com/)"}],"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["www.youtube.com/user/:username"],"target":"/user/:username"}],"name":"Channel with username","maintainers":["DIYgod"],"location":"user.ts"}' :test='undefined' />

## 哔哩哔哩 bilibili <Site url="www.bilibili.com"/>

### UP 主动态 <Site url="www.bilibili.com" size="sm" />

<Route namespace="bilibili" :data='{"path":"/user/dynamic/:uid/:routeParams?","categories":["social-media","popular"],"example":"/bilibili/user/dynamic/2267573","parameters":{"uid":"用户 id, 可在 UP 主主页中找到","routeParams":"\n| 键           | 含义                              | 接受的值       | 默认值 |\n| ------------ | --------------------------------- | -------------- | ------ |\n| showEmoji    | 显示或隐藏表情图片                | 0/1/true/false | false  |\n| disableEmbed | 关闭内嵌视频                      | 0/1/true/false | false  |\n| useAvid      | 视频链接使用 AV 号 (默认为 BV 号) | 0/1/true/false | false  |\n| directLink   | 使用内容直链                      | 0/1/true/false | false  |\n\n用例：`/bilibili/user/dynamic/2267573/showEmoji=1&disableEmbed=1&useAvid=1`"},"features":{"requireConfig":[{"name":"BILIBILI_COOKIE_*","optional":true,"description":"如果没有此配置，那么必须开启 puppeteer 支持；BILIBILI_COOKIE_{uid}: 用于用户关注动态系列路由，对应 uid 的 b 站用户登录后的 Cookie 值，`{uid}` 替换为 uid，如 `BILIBILI_COOKIE_2267573`，获取方式：\n1.  打开 [https://api.vc.bilibili.com/dynamic_svr/v1/dynamic_svr/dynamic_new?uid=0&type=8](https://api.vc.bilibili.com/dynamic_svr/v1/dynamic_svr/dynamic_new?uid=0&type=8)\n2.  打开控制台，切换到 Network 面板，刷新\n3.  点击 dynamic_new 请求，找到 Cookie\n4.  视频和专栏，UP 主粉丝及关注只要求 `SESSDATA` 字段，动态需复制整段 Cookie"}],"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["space.bilibili.com/:uid"],"target":"/user/dynamic/:uid"}],"name":"UP 主动态","maintainers":["DIYgod","zytomorrow","CaoMeiYouRen","JimenezLi"],"location":"dynamic.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

### UP 主投稿 <Site url="www.bilibili.com" size="sm" />

<Route namespace="bilibili" :data='{"path":"/user/video/:uid/:disableEmbed?","categories":["social-media","popular"],"example":"/bilibili/user/video/2267573","parameters":{"uid":"用户 id, 可在 UP 主主页中找到","disableEmbed":"默认为开启内嵌视频, 任意值为关闭"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["space.bilibili.com/:uid"],"target":"/user/video/:uid"}],"name":"UP 主投稿","maintainers":["DIYgod"],"location":"video.ts"}' :test='{"code":1,"message":"expected 503 to be 200 // Object.is equality"}' />

### 排行榜 <Site url="www.bilibili.com" size="sm" />

<Route namespace="bilibili" :data='{"path":"/ranking/:rid?/:day?/:arc_type?/:disableEmbed?","name":"排行榜","maintainers":["DIYgod"],"categories":["social-media","popular"],"example":"/bilibili/ranking/0/3/1","parameters":{"rid":{"description":"排行榜分区 id","default":"0","options":[{"label":"全站","value":"0"},{"label":"动画","value":"1"},{"label":"国创相关","value":"168"},{"label":"音乐","value":"3"},{"label":"舞蹈","value":"129"},{"label":"游戏","value":"4"},{"label":"科技","value":"36"},{"label":"数码","value":"188"},{"label":"生活","value":"160"},{"label":"鬼畜","value":"119"},{"label":"时尚","value":"155"},{"label":"娱乐","value":"5"},{"label":"影视","value":"181"}]},"day":{"description":"时间跨度","default":"3","options":[{"value":"1","label":"1日"},{"value":"3","label":"3日"},{"value":"7","label":"7日"},{"value":"30","label":"30日"}]},"arc_type":{"description":"投稿时间","default":"1","options":[{"value":"0","label":"全部投稿"},{"value":"1","label":"近期投稿"}]},"disableEmbed":{"description":"默认为开启内嵌视频, 任意值为关闭"}},"location":"ranking.ts"}' :test='{"code":0}' />

## 豆瓣 <Site url="www.douban.com"/>

### 豆瓣小组 <Site url="www.douban.com" size="sm" />

<Route namespace="douban" :data='{"path":"/group/:groupid/:type?","categories":["social-media","popular"],"example":"/douban/group/648102","parameters":{"groupid":"豆瓣小组的 id","type":{"description":"类型","default":"latest","options":[{"label":"最新","value":"latest"},{"label":"最热","value":"essence"},{"label":"精华","value":"elite"}]}},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["www.douban.com/group/:groupid"],"target":"/group/:groupid"}],"name":"豆瓣小组","maintainers":["DIYgod"],"location":"other/group.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## 微博绿洲 <Site url="weibo.com"/>

:::warning
微博会针对请求的来源地区返回不同的结果。一个已知的例子为：部分视频因未知原因仅限中国大陆境内访问 (CDN 域名为 `locallimit.us.sinaimg.cn` 而非 `f.video.weibocdn.com`)。若一条微博含有这种视频且 RSSHub 实例部署在境外，抓取到的微博可能不含视频。将 RSSHub 部署在境内有助于抓取这种视频，但阅读器也必须处于境内网络环境以加载视频。
:::

对于微博内容，在 `routeParams` 参数中以 query string 格式指定选项，可以控制输出的样式

| 键                         | 含义                                                               | 接受的值       | 默认值                              |
| -------------------------- | ------------------------------------------------------------------ | -------------- | ----------------------------------- |
| readable                   | 是否开启细节排版可读性优化                                         | 0/1/true/false | false                               |
| authorNameBold             | 是否加粗作者名字                                                   | 0/1/true/false | false                               |
| showAuthorInTitle          | 是否在标题处显示作者                                               | 0/1/true/false | false（`/weibo/keyword/`中为 true） |
| showAuthorInDesc           | 是否在正文处显示作者                                               | 0/1/true/false | false（`/weibo/keyword/`中为 true） |
| showAuthorAvatarInDesc     | 是否在正文处显示作者头像（若阅读器会提取正文图片，不建议开启）     | 0/1/true/false | false                               |
| showEmojiForRetweet        | 显示 “🔁” 取代 “转发” 两个字                                       | 0/1/true/false | false                               |
| showRetweetTextInTitle     | 在标题出显示转发评论（置为 false 则在标题只显示被转发微博）        | 0/1/true/false | true                                |
| addLinkForPics             | 为图片添加可点击的链接                                             | 0/1/true/false | false                               |
| showTimestampInDescription | 在正文处显示被转发微博的时间戳                                     | 0/1/true/false | false                               |
| widthOfPics                | 微博配图宽（生效取决于阅读器）                                     | 不指定 / 数字  | 不指定                              |
| heightOfPics               | 微博配图高（生效取决于阅读器）                                     | 不指定 / 数字  | 不指定                              |
| sizeOfAuthorAvatar         | 作者头像大小                                                       | 数字           | 48                                  |
| displayVideo               | 是否直接显示微博视频和 Live Photo，只在博主或个人时间线 RSS 中有效 | 0/1/true/false | true                                |
| displayArticle             | 是否直接显示微博文章，只在博主或个人时间线 RSS 中有效              | 0/1/true/false | false                               |
| displayComments            | 是否直接显示热门评论，只在博主或个人时间线 RSS 中有效              | 0/1/true/false | false                               |
| showEmojiInDescription     | 是否展示正文中的微博表情，关闭则替换为 `[表情名]`                  | 0/1/true/false | true                                |
| showLinkIconInDescription  | 是否展示正文中的链接图标                                           | 0/1/true/false | true                                |
| preferMobileLink           | 是否使用移动版链接（默认使用 PC 版）                               | 0/1/true/false | false                               |

指定更多与默认值不同的参数选项可以改善 RSS 的可读性，如

[https://rsshub.app/weibo/user/1642909335/readable=1&authorNameBold=1&showAuthorInTitle=1&showAuthorInDesc=1&showAuthorAvatarInDesc=1&showEmojiForRetweet=1&showRetweetTextInTitle=0&addLinkForPics=1&showTimestampInDescription=1&showTimestampInDescription=1&heightOfPics=150](https://rsshub.app/weibo/user/1642909335/readable=1&authorNameBold=1&showAuthorInTitle=1&showAuthorInDesc=1&showAuthorAvatarInDesc=1&showEmojiForRetweet=1&showRetweetTextInTitle=0&addLinkForPics=1&showTimestampInDescription=1&showTimestampInDescription=1&heightOfPics=150)

的效果为

<img loading="lazy" src="/img/readable-weibo.png" alt="微博小秘书的可读微博 RSS" />

### 博主 <Site url="weibo.com" size="sm" />

<Route namespace="weibo" :data='{"path":"/user/:uid/:routeParams?","categories":["social-media","popular"],"example":"/weibo/user/1195230310","parameters":{"uid":"用户 id, 博主主页打开控制台执行 `$CONFIG.oid` 获取","routeParams":"额外参数；请参阅上面的说明和表格；特别地，当 `routeParams=1` 时开启微博视频显示"},"features":{"requireConfig":[{"name":"WEIBO_COOKIES","optional":true,"description":""}],"requirePuppeteer":false,"antiCrawler":true,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["m.weibo.cn/u/:uid","m.weibo.cn/profile/:uid","www.weibo.com/u/:uid"],"target":"/user/:uid"}],"name":"博主","maintainers":["DIYgod","iplusx","Rongronggg9"],"description":":::warning\n  部分博主仅登录可见，未提供 Cookie 的情况下不支持订阅，可以通过打开 `https://m.weibo.cn/u/:uid` 验证\n  :::","location":"user.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

:::warning
  部分博主仅登录可见，未提供 Cookie 的情况下不支持订阅，可以通过打开 `https://m.weibo.cn/u/:uid` 验证
  :::

### 关键词 <Site url="weibo.com" size="sm" />

<Route namespace="weibo" :data='{"path":"/keyword/:keyword/:routeParams?","categories":["social-media","popular"],"example":"/weibo/keyword/DIYgod","parameters":{"keyword":"你想订阅的微博关键词","routeParams":"额外参数；请参阅上面的说明和表格"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"name":"关键词","maintainers":["DIYgod","Rongronggg9"],"location":"keyword.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## 小宇宙 <Site url="xiaoyuzhoufm.com"/>

### 播客 <Site url="xiaoyuzhoufm.com/" size="sm" />

<Route namespace="xiaoyuzhou" :data='{"path":"/podcast/:id","categories":["multimedia","popular"],"example":"/xiaoyuzhou/podcast/6021f949a789fca4eff4492c","parameters":{"id":"播客id，可以在小宇宙播客的 URL 中找到"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":false,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["xiaoyuzhoufm.com/podcast/:id"]}],"name":"播客","maintainers":["hondajojo","jtsang4"],"url":"xiaoyuzhoufm.com/","location":"podcast.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

## 知乎 <Site url="www.zhihu.com"/>

### 用户动态 <Site url="www.zhihu.com" size="sm" />

<Route namespace="zhihu" :data='{"path":"/people/activities/:id","categories":["social-media","popular"],"example":"/zhihu/people/activities/diygod","parameters":{"id":"作者 id，可在用户主页 URL 中找到"},"features":{"requireConfig":false,"requirePuppeteer":false,"antiCrawler":true,"supportBT":false,"supportPodcast":false,"supportScihub":false},"radar":[{"source":["www.zhihu.com/people/:id"]}],"name":"用户动态","maintainers":["DIYgod"],"location":"activities.ts"}' :test='{"code":1,"message":"Test timed out in 10000ms.\nIf this is a long-running test, pass a timeout value as the last argument or configure it globally with \"testTimeout\"."}' />

