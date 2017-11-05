# Technical Overview

Note: All this is liable to change once I get a block of free time to optimize the backend further. Things planned:

- Changing the origin file text markup language from [Markdown](http://daringfireball.net/projects/markdown/) to [Org](http://orgmode.org/org.html#Markup)
- Changing the static site generator from [Jekyll](https://jekyllrb.com/) to [Hugo](https://gohugo.io/)
- Incorporating [Pandoc](http://pandoc.org/) into the build process (to automatically generate PDF, ePub, etc. versions of pages)
- Using [Netlify](https://www.netlify.com/) instead of [Github Pages](https://pages.github.com/) for hosting
- Using [Netlify](https://www.netlify.com/) instead of [Cloudflare](https://www.cloudflare.com/) for CDN services, minification, SSL, and max-age headers
- Using [Zopfli Encoding](https://en.wikipedia.org/wiki/Zopfli) for seldom changed assets and pictures (rather than a less size-efficient DEFLATE encoder).

### Jekyll
Pages (located in 3 subdirectories: ["pages"](https://github.com/StevenTammen/chrya/tree/master/pages), ["studies"](https://github.com/StevenTammen/chrya/tree/master/studies), and ["notes"](https://github.com/StevenTammen/chrya/tree/master/notes)) are written in GitHub flavored markdown, which [Jekyll](https://jekyllrb.com/) then converts to HTML and inserts into the template in the ["\_layouts" subdirectory](https://github.com/StevenTammen/chrya/tree/master/_layouts).

### Hosting
This site is hosted on GitHub Pages in this repository. Because this is a so-called "project pages site" (rather than a user pages site), it is hosted at steventammen.github.io/chrya/ (rather than steventammen.github.io/).

### Custom Domain
I have opted to use chrya.com as a custom domain instead of sticking with steventammen.github.io/chrya/. Because I'm using Cloudflare as my DNS, I have acces to [CNAME flattening](https://blog.cloudflare.com/introducing-cname-flattening-rfc-compliant-cnames-at-a-domains-root/), which basically means I can use this apex domain bare without worrying about changes in GitHub Pages' server IP addresses. I've opted to go the non-www route because it means less typing over time, because it is more legible and speakable, and because I have no need of cookie separation on subdomains.

### Content Delivery Network (CDN)
Rather than sticking with Github Pages' CDN ([Fastly](https://www.fastly.com/)), this site uses [Cloudflare's CDN](https://www.cloudflare.com/features-cdn/). One of the main reasons for this is that Cloudflare offers a way to purge the CDN cache when you update pages, while GitHub's implementation of Fastly does not, as far as I can tell. Since I'm careful to individually purge files from the cache when I update them (there's [an API](https://api.cloudflare.com/#zone-purge-individual-files-by-url-and-cache-tags)), Cloudflare lets me ensure that the CDN will never send outdated files.

### Caching Everything
Using a Cloudflare page rule, I have Cloudflare's ["cache everything" option](https://support.cloudflare.com/hc/en-us/articles/200172366-How-do-I-cache-everything-on-a-URL-) activated across all pages of the site with the Edge Cache TTL set to a month (the highest it can go). Basically, things will only need to get revalidated when I update individual files and purge them from the cache. Having practically everything cached on CDN edge nodes practically all the time means that the site should always load quickly.

### Max-Age Headers
I am also using Cloudflare to set max-age headers. Last time I checked, GitHub Pages' max-age headers were 600 seconds (non-configurable). Cloudflare lets you set them a lot higher -- I am currently using max-age headers of a day, which I think is a good compromise. Having them set too short (like 600 seconds) makes them not very useful because cached files will expire before getting used, but having them set too long can cause problems when you update pages, especially if different assets are at different aging points. For example, if you change the HTML of a page in a significant way, you are probably also going to change the CSS, so if the HTML is at a later aging point than the CSS, bad things will happen when only the HTML gets updated.

### Gzipping And Minification
GitHub Pages gzips HTML, CSS, and Javascript automatically, as does Cloudflare's CDN (which also compresses [additional file types](https://support.cloudflare.com/hc/en-us/articles/200168396-What-will-CloudFlare-gzip-)). I gzip pictures on my own, since neither service automatically compresses these. I have Cloudflare set to automatically minify HTML, CSS, and Javascript when they get sent to the CDN, and it does this even if the files it receives from GitHub Pages are gzipped.

### SSL
Connections from website visitors to Cloudflare are encrypted, as are connections from Cloudflare to GitHub's servers. Unfortunately, GitHub Pages doesn't offer proper TLS/SSL for custom domains, so until they get that operational, those of us with custom domains won't be able to achieve Strict Full SSL. Since security on this site is more for philosophical reasons than practical ones (i.e., I'm encrypting communications because everything should be encrypted in principle, not because I'm dealing with credit card numbers), I don't consider this much of a compromise, but it is important to note that this site does not have SSL in the same sense that your bank's site has SSL: back-end over TLS is not validated.

### Forcing HTTPS
HTTPS is forced with two page rules in Cloudflare: the first one changes http://chrya.com/ requests to https://chrya.com/ requests, and the second one ensures that redirects from https://www.chrya.com/ to https://chrya.com/ are done entirely over HTTPS. I don't need another page rule for http://www.chrya.com/ to https://chrya.com/ redirects because http://www.chrya.com/ requests will always get redirected to http://chrya.com/ requests, which will then get changed to https://chrya.com/ requests because of the first page rule.

### HTTP Strict Transport Security (HSTS)
HSTS is enabled to prevent downgrade attacks, SSL stripping, and cookie hijacking. I'm not worried about HSTS taking my site down because I never plan to stop using HTTPS.

### Email
[Mailgun](https://mailgun.com) is used to handle all email through the site (rather than, say, Google Apps for Business).

# Contribution Guidelines

### How To Contribute With Respect To Content

At the top of every page I have included two buttons that link to its [markdown](https://daringfireball.net/projects/markdown/) source: one links to the page's location in this repository and the other links to the page's location on [Prose.io](http://prose.io/), an online markdown editor for GitHub.

You can help improve the site's content by submitting pull requests with editorial changes on Github, or by editing the pages on Prose.io and then pressing "Save" --> "Submit Change Request", which will automatically create the pull request for you. Prose.io is great if you don't have a lot of experience with Git and GitHub -- even though you need a GitHub account to propose changes through Prose.io, you need no other knowledge, so once you [set up a GitHub account](https://github.com/join), you can contribute freely without having to know all the complicated programmer stuff. If you aren't comfortable contributing through GitHub or Prose.io, you can also just email improvements to <a href="mailto:edits@chrya.com">edits@steventammen.com</a>.

At the present time, I am not aware of any easy way for me to make content editable in a rich text environment, so if you want to contribute through GitHub or Prose.io, you are going to have to learn the basics of [markdown syntax](https://daringfireball.net/projects/markdown/syntax). You won't have to know anywhere near the whole specification to help -- if you skim the sections related to paragraphs, links, lists, and emphasis you should have a good working knowledge in just a few minutes.

### How To Contribute With Respect To Design

You can help improve the site itself by submitting pull requests with design improvements. If you are comfortable with web development languages but not GitHub pull requests, you can send implementations to <a href="mailto:design@steventammen.com">design@steventammen.com</a> and I'll incorporate them into the repository myself. If you aren't comfortable with web development languages or GitHub pull requests, your ideas are still valuable, and you can send them to that same address.

For pull requests requiring significant amounts of work, it would be a good idea to check with me early on to make sure I approve of the changes or enhancements being considered. I don't want to put you in a situation where you put a lot of work into something that I wouldn't ultimately use.

# Copyright and Terms of Use

The contents of this site are licensed under the <a rel="license" href="https://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.
  
<br/>
<a rel="license", href="https://creativecommons.org/licenses/by-nc-sa/4.0/"><img src="https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png", alt="Creative Commons License"></a>
