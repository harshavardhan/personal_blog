---
title: "Random thoughts centered around my daily activity"
type: "page"
---

My current workflow for writing a new article: Write up whatever comes to my mind in an editor like [Sublime Text](https://www.sublimetext.com/), keep iterating through the material and modify it. Check for any grammar mistakes on [Grammarly](https://www.grammarly.com/), convert it into Markdown, and commit the article.

---

[Off facebook activity](https://www.facebook.com/off_facebook_activity/activity_list) tracking: I am quite surprised to see this list. I have no clue how FB has information on all the apps I use and the sites I visit. Need to block third-party cookies (disabled by default in Firefox) and client-side javascript code corresponding to things like FB avatar or "like page" embeds (can use extensions like [Facebook Container](https://addons.mozilla.org/en-US/firefox/addon/facebook-container/)). There are also some APIs to which third parties can directly communicate info like email, IP and browser fingerprint. Some people might say there's no harm in sharing your data for better personalization. And privacy is a myth, governments and ISPs track you anyways. (You can opt-out from FB saving your off-facebook activity now via settings and clear your collected data too) (Restricting tracking on web is easier than mobile apps imo)

---

I like [this](https://github.com/Yashasvi-Sriram/scv) idea from a friend of mine for maintaining CVs. Just have a short note on each repo for adding content to CVs and pull content from individual repositories.

---

This site is built on Hugo, a static site generator. SSG's might be great for generating static content on the web. I use [Netlify](https://www.netlify.com/) for hosting (have also heard of Zeit, now [Vercel](https://vercel.com/)). Both these companies are doing great in terms of business too.

---

I thought there were *some* similarities between Hugo and Django. (Maybe because both were made with a similar view in mind: generating material for content sites) Django's templating looks similar to Go templating (used by Hugo). And Django uses web templates as a base for rendering content like most SSGs. I like the Django debug logs on browsers much in comparison to Hugo's debugging. (Some better version of [this](https://github.com/kaushalmodi/hugo-bare-min-theme) should be shipped by default?)

---
A small piece of info whenever you see a (capital) Y/n for yes/no, yes is the default, but if you see a y/n, you have to type over what you want to do precisely. I wanted to document this little thing I missed a lot of times: whenever I see a y/n on Linux terminal, I press the enter key by default and try deciphering the error msg why it failed.

---

Tip: Use SSH keys instead of logging in via password. Use ssh config for managing multiple ssh keys at work. In short, manage config via files: .gitconfig, .kube/config. 

---

An interesting read on [Pypi malicious packages](https://www.zdnet.com/article/two-malicious-python-libraries-removed-from-pypi/). Also, many similar cases with public registries: npm, Dockerhub.

---

I wanted a platform to know people’s opinions and thoughts. Facebook and Instagram are used mostly for sharing pics, life moments, and memes. So recently, I joined Twitter (better late than never). Initially, I didn’t want my feed to be cluttered and avoided celebrities, filtering feed by using private lists.

---

No edit option for a tweet was surprising for me. And also seeing many people mentioning that their tweets auto delete tweets after x days. (Saw some online clients which do this by utilizing the Twitter API)

---

I find deleting an account on a site quite amusing (more so after the [GDPR](https://en.wikipedia.org/wiki/General_Data_Protection_Regulation) frenzy). Some people might argue whatever is once public has to remain public (Imagine who had archived what). And also, think of the catastrophic things to delete like comments with nested replies. It is even more true with digital information. It's usually hard to have information deletion policies where information is shared with or exposed by APIs to certain third-parties. And who knows if they have cached (or archived?) your data.

---

After reading an [article](https://hacks.mozilla.org/2018/05/a-cartoon-intro-to-dns-over-https/) on [DNS over HTTPS](https://en.wikipedia.org/wiki/DNS_over_HTTPS), I was horrified imagining the web on HTTP days when anyone can make a [MITM attack](https://en.wikipedia.org/wiki/Man-in-the-middle_attack), decipher data as opposed to HTTPS. But how does DNS over HTTPS prevent intermediate routers from tracking based on a reverse DNS lookup? (Is DoH useless wrt protecting privacy?)

---

When I was thinking of adding search feature to my site, I came across [Lunr](https://lunrjs.com/) (name inspired from [Solr](https://lucene.apache.org/solr/)). Looking for ones with more advanced capabilities, I came across [Algolia](https://www.algolia.com/), Search as a service. Instead of writing your own search for the site, you can use it, which does better synonym matching, search across personalized indexes, search analytics and typo correction, etc. In the world where Google has so dominated search, that's mostly a monopoly; it's nice to see services like Algolia and Elasticsearch build things around search.

[Elasticsearch](https://www.elastic.co/elasticsearch/) is based on [Lucene](https://lucene.apache.org/core/) (like Solr) and can be used for searching programmatically (like for a location search on maps, tinder dates near you) using already indexed data.

I am sometimes quite surprised about how many companies' banking on the enterprise model of open source projects can sustain. (It means the basic version of the software is open-sourced. You need to pay some extra bucks for enterprise features, support, training, certifications, hosted cloud management, etc.)  Some examples are [Jetbrains](https://www.jetbrains.com/) (awesome [IntelliJ](https://www.jetbrains.com/idea/features/) and even [Kotlin](https://kotlinlang.org/), the day they became a primary sponsor for [ICPC](https://icpc.global/) I should have understood that they're super-rich), HashiCorp, ElasticSearch, Grafana, MongoDB, Redis to name some of them. 

But winning a hosted cloud offering war is difficult when giants like AWS host your open-source software and provide it as a SaaS. You can read about what happened at [here](https://grafana.com/blog/2019/03/20/everything-you-need-to-know-about-the-oss-licensing-war-part-1./) and [here](https://www.scylladb.com/2018/10/22/the-dark-side-of-mongodbs-new-license/) to understand about AWS Elasticsearch offering and license shifts of MongoDB, Redis. Also, take cloud providers like Alibaba, Tencent, for instance. Good luck fighting them in Chinese courts with updated licenses. 

Also, note a different paradigm of search from text to visual like in the case of [Pinterest](https://www.pinterest.com/).

---

Keeping a service secure is hard. We keep on seeing many data leaks happening round the clock. So it's crucial to minimize password reuse. You can also check if your account has been compromised in a data breach on [haveibeenpwned](https://haveibeenpwned.com/). Trust Google enough and use suggested passwords everywhere? (Too lazy to change all passwords manually, looking for an *imaginary* tool which can do the password change to suggested password by automating a forgot password, verify from mail and change password workflow)

---

> Focus should be on content. Good blog, good content!