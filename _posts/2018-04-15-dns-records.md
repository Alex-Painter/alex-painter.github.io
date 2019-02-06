---
layout: post
title:  "What are DNS Records and why do I need one?"
date:   2018-04-15 10:43:21 +0100
categories: software web networking
---
When I was configuring the hosting for this site (I use the excellent [Jekyll][jekyll] and [GitHub Pages][gh-pages]), I had to configure some DNS records to point my custom domain to my GitHub pages address. After reading some tutorials on how to do this, the redirects worked, however I still didn’t really understand what I had done. So this is a short article to explain what DNS records are and why we use them.

# Right then, what is a DNS Record?

To answer that question let’s first remind ourselves what a DNS is: a Domain Name System basically maps a human readable name, or a host name, to an IP address. This is so as the forgetful humans we are, we don’t need to remember a specific IP address everytime we want to go to `example.com`, or if the IP address the site is served from changes, we all don’t need to notified. So when you request `example.com`, the request will go from your ISP to a DNS, then forwarded onto the web server that’s associated with the DNS record in the nameserver (DNS server).

So, a DNS record is a single entry that gives the DNS instructions on how to handle requests. They will perform some initial validation before choosing a `zone` to pass it onto, acting essentially as a filter.

Well hold on, what is a DNS Zone? As understanding DNS Zones isn’t crucial to understanding DNS Records, I will cover those in another article in the future. If you want to read that before carrying on, please go ahead.

As you might already have seen, DNS records come in a few different flavours, such as `CNAME`, `A Record`, `AAAA` and `TXT Record` just to name a few.

# But which records do you need and what do they do?

#### A
The address, or `A` record, maps a domain or subdomain to an IP address. For example you might map an IP like `123.123.123.59` to `example.com`. 

#### CNAME
The `CNAME` or canonical name record, directly maps one domain to another, for example I have a CNAME to map `alexpainter.co.uk` to my GitHub domain of  `alex-painter.github.io`. This is also helpful if you’ve changed a subdomain of your site, and want the old subdomain to correctly redirect to the new one. For example, you could use a CNAME to redirect `hello.alexpainter.co.uk` to `mysite.alexpainter.co.uk`.

#### AAAA
This record is similar to the `A` record, however the difference is `AAAA` is for IPv6 addresses whereas the `A` is for IPv4.

#### TXT
The `TXT` record is there for adding arbitrary information about the DNS record. They are mainly used to store data for the Sender Policy Framework (SPF) which at a high level specifies domain ownership. These will normally be created automatically by the domain registrar when a domain is registered.

Here is a screenshot of my current DNS record setup for this site, just in case you’re curious:

![my record setup](/assets/dns-records.png)

This is just a quick introduction into DNS records, but hopefully this is enough information to understand what you need to use when configuring custom domains for your sites.

[jekyll]: https://jekyllrb.com/
[gh-pages]: https://pages.github.com/