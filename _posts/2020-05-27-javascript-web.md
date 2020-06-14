---
title: "JavaScript and the Web without Javascript"
tags:
  - javascript
    web
    no-script
    libre-js
---

JavaScript powers the internet. It is what runs in the
browser and what has slowly been taking over the server-
side as well recently. But the internet existed long before
JavaScript. You actually don't need JavaScript at all to
browse the internet. If it wasn't for JavaScript, one could
practically browse the web from a text-based browser from a
terminal.

I came across [this article](https://www.wired.com/2015/11/i-turned-off-javascript-for-a-whole-week-and-it-was-glorious/) on Wired from 2015 that
described how the author turned JavaScript off on their
browser for a whole week and had a 'glorious' experience
browsing the JavaScript-free world. Reading that article
induced a thought in me - "_Is the current state of the web
still usable without JavaScript?_" It piqued my curiosity
and I wanted to find out. So I decided to do that same
exercise for a week and see how it fared. I don't think most
websites on the internet today would survive without
JavaScript; but I'm still going to try. I don't want to take
the drastic step of turning JavaScript off from within the
browser itself. Instead I'm going to rely on a web extension
called [NoScript](https://addons.mozilla.org/en-US/firefox/addon/noscript/) to disable JavaScript in the browser for
me. Let's see how the web fares against it.

In the past, I've known the ['Free JavaScript'](https://www.fsf.org/campaigns/freejs) campaign that
the Free Software foundation has been running since 2013 to
free propreitary JavaScript from running in our browsers.
I've also tried using the [LibreJS](https://www.gnu.org/software/librejs/index.html) extension that blocked
non-free JavaScript from being executed in the browser. That
experience was not a good one. I don't think this one is
going to be any better. If anything, it'll only be worse.

In another part of the internet - today ( or should I say 3
days ago ) - there was [this report](https://nullsweep.com/why-is-this-website-port-scanning-me/) by NullSweep ( aka
Charlie Belmer ) making the rounds on social media
( [Twitter](https:/twitter.com/NordVPN/status/1264284967602970631), [Mastodon](https://mastodon.ar.al/@aral/104222057850347395) ) accusing eBay of doing port scans
of users' internal networks via JavaScript. [An analysis](https://blog.nem.ec/2020/05/24/ebay-port-scanning/) of
the tracking by Dan Nemec indicated that this was a tool
[
indeed
a privacy violation. He writes,
Now, that is what is a bigger concern. That's not only a
violation of the privacy of my internal network, but they
]
built by ThreatMetrix Inc ( now part of [LexisNexis](https://risk.lexisnexis.com/products/threatmetrix) ), an
identity tracking / anti-fraud company. He goes on to quote
different privacy-related sentences from the new hompage of
ThreatMetrix. I took a look at the page too and apparently
they claim
> to identify and authenticate omni-devices and spot
suspicious behavior in near real-time by leveraging a network
that analyzes more than 150 million daily transactions from
more than 30,000 websites worldwide.

This can be considered borderline privacy violation, but then
again, they're doing it only for fraud detection right? Does
that make them righteous? Definitely not.

Now, the bigger question to be asked is, how did all of this
actually unfurl? What enabled these websites to do such
things? It turns out that they only just exploited something
that [JavaScript allowed](http://blog.andlabs.org/2010/12/port-scanning-with-html5-and-js-recon.html) them to do. It's a feature™️.
Thanks for making the web more toxic, JavaScript. That's one
more reason why one should have JavaScript disabled while
browsing the internet.

Nemec notes in his article,
> In reality, NullSweep was actually discussing a different
type of port scanning, one initiated directly by a website
the target loads in their browser. It’s an ingenius, if not
insidious, technique that allows would-be port scanners to
paradrop straight into an internal network and scan it using
Javascript from within the browser context.

Maybe, if this exercise with NoScript turns out to be a
disaster, I'll probably give LibreJS another go and see how
that fares. I hope at least that experience has gotten better
now from many years ago when I tried it. I hope I can
continue keeping it around. However, if the NoScript
exercise doesn't kill my experience, then I'm going to go
all in by disabling JavaScript completely from within the
browser itself.
