# SEO audit: Narsee Monjee College website

Divij Kansara, 22 November 2026

I crawled the college website to learn how a technical SEO audit works. This is what I found.

## What I did

I used Screaming Frog SEO Spider (free version) on 22 November 2026, then checked the main findings by hand in my browser.

The crawl covered 73 HTML pages and 200 URLs in total, including images and other files. It found 43 images. It did not hit the free version's 500 URL limit, so this covers the whole site rather than a sample.

## Summary

Almost every page on the site has the same title and the same description, and no main heading. That gives search engines very little to tell one page from another.

No page has the tags that create a preview when a link is shared. Almost no image has alt text, so screen reader users get nothing where the pictures are.

Most of this comes from the site template, not from individual pages. A few changes would fix a lot of pages.

I would start with page titles.

## Finding 1: pages look the same to search engines

| Issue | Pages | Share |
| --- | --- | --- |
| Duplicate page titles | 70 of 73 | 96% |
| Missing H1 heading | 70 of 73 | 96% |
| Duplicate meta descriptions | 71 of 73 | 97% |
| Page titles too long to display fully | 70 of 73 | 96% |

I checked three pages by hand. None had an `h1` tag, and the browser tab text was identical on the admissions page and a course page.

A page title is what you see in a browser tab and as the clickable line in Google results. An `h1` is the main heading on the page. A meta description is the grey text under the title in search results. These are the main signals a page gives about what it covers.

Here almost every page sends the same signal. If someone searches for a specific course, Google has little to work with when picking which page to show. The course page, the homepage and the contact page all look similar to it.

This probably matters most during admissions, when people search for specific things like a course name or a deadline.

The fix is in the template rather than on 70 separate pages. The template should produce a different title, heading and description for each page. I would do the admissions page, the course pages and the contact page first, since those are what people search for.

## Finding 2: no canonical tags

135 URLs have no canonical tag. That is all of the ones checked.

The crawl also found 4 URLs with query parameters, 2 with uppercase letters and 1 with a space in it.

The same page can often be reached through more than one address. A capital letter in one, something after a question mark in another. A search engine can treat those as separate pages with identical content.

A canonical tag is one line that says which address is the proper one. Without it the search engine decides on its own, and if it decides differently at different times the page can move around in results.

The site has the URL inconsistencies that cause this, so it is not only a theoretical risk.

Adding a canonical tag to the template would cover every page.

## Finding 3: shared links show no preview

All 73 pages are missing Open Graph tags. The same 73 are missing X Card tags.

I searched the page source for `og:` and found nothing.

When you paste a link into WhatsApp or LinkedIn you normally get a small box with a picture, a title and a line of text. Open Graph tags are what build that box. Without them a shared link is just plain text.

For a college this is worth fixing. A lot of people first see the college through a link someone sent them. A student forwards a course page to a parent. A teacher posts admissions dates in a group. All of those currently look like nothing.

Four tags in the template would fix it: `og:title`, `og:description`, `og:image` and `og:url`.

## Finding 4: images have no alt text

41 of the site's 43 images have no `alt` attribute. The same 41 have no width or height set, and 15 are over 100 kB.

Alt text does two things.

The first is access. Screen readers read alt text aloud, so people using one get nothing where the images are. On a college website that affects who can use the site at all.

The second is that search engines cannot see what is in a picture. Alt text tells them.

It also explains something else the crawl flagged. 71 of 73 pages have internal links with no text in them. Those are images being used as links, and with no alt text there is nothing to read.

Images that mean something need short descriptions. Images that are only decoration should have an empty alt attribute (`alt=""`) so screen readers skip them instead of reading out a filename.

## Finding 5: a few pages look broken

| Issue | URLs |
| --- | --- |
| Page with no `head` tag | 1 |
| Page with no `body` tag | 1 |
| URL served over HTTP, not HTTPS | 1 |
| Pages with no links to other pages | 2 |
| Page with no title | 1 |

The counts are small, but these are different from everything above. The rest of this report is about things that are missing. These look like something went wrong.

Every page should have a `head` section holding information about the page and a `body` section holding what you see. A page missing either has invalid HTML. Browsers usually cope, but it suggests the page was not built properly.

The page served over HTTP is the most visible one. Chrome shows a "Not secure" warning on pages like that.

The two pages with no links out are dead ends. Someone landing there has nowhere to go but back.

These are small enough to look at one at a time. The HTTP address should redirect to the secure version.

## What I would fix first

Page titles.

They reach further than anything else here. They show up in search results, in browser tabs and in bookmarks, and they affect all 73 pages. The fix sits in one place, and you can check it worked by opening two pages and reading the tabs.

Alt text is more serious for the people it affects, and I nearly put it first. I put it second because fixing it means writing a description for every image by hand, which is much slower.

I am ranking by how far each fix reaches and how much work it takes. I do not have traffic data for this site, so I cannot rank by actual impact.

## What this audit could not see

- The crawl reads HTML as the server sends it. Pages that build content with JavaScript may contain more than it recorded.
- I had no access to Google Search Console, so I do not know what the site ranks for, which pages get traffic, or what Google has indexed.
- No analytics data, so I ranked findings by reasoning rather than measurement.
- No server logs, so nothing here about how search engines actually crawl the site.
- I did not measure page speed properly. Only image file sizes were flagged.
- This describes the site as it was on 22 November 2026.

---

An audit I did to learn how the process works. Not commissioned by the college.
