---
title: "Firefox Content Blocking"
tags:
  - firefox
    content-blocking
    tracking-protection
    privacy
write-date: 2020-05-28
---

[I use Firefox]({% post_url ????-??-??-why-i-use-firefox %}). Because I care about my privacy and don't
want third-parties ( yes Google [Analytics], I'm implying you )
_tracking_ me around on the web, I use not one, but multiple
[content blockers]({% post_url ????-??-??-content-blocking %}) that protect me from being tracked.

Recently, Firefox has been working in that direction trying
to build that experience into the browser by default. It
started as a [Firefox Test Pilot Experiment](https://medium.com/firefox-test-pilot/test-pilot-tracking-protection-graduation-report-7452b5ccc477) back in 2016-17.
Even before the Test Pilot experiment, an initial version
of the product was released for [Private Browsing](https://blog.mozilla.org/blog/2015/11/03/firefox-now-offers-a-more-private-browsing-experience/) sessions
back in 2015 with Firefox 42. Then in November 2017, with
Firefox 57 ( Firefox "Quantum" ), mozilla gave it another
upgrade by letting users use the feature ["always"](https://blog.mozilla.org/firefox/tracking-protection-always-on/). They
called it **Enhanced Tracking Protection**. However, the
more significant update to the feature came with the release
of Firefox 69 last week when the feature was [turned on by
default](https://blog.mozilla.org/blog/2019/09/03/todays-firefox-blocks-third-party-tracking-cookies-and-cryptomining-by-default/) for all users.

Until now, this was a fairly visible, prominent but opt-in
feature in Firefox' Preferences. However, with this update,
it has become a default setting for all users. That means
that a lot of users who are not aware of the impact of such
tracking are protected by default.

To clarify, I use [Firefox Developer Edition](https://firefox.com/developer) as my default
browser ( though not set as the default browser ). That means
that I've seen these features long before they are released.
However, I do have the stable release of the browser installed
and is set as my default browser too.

I have historically been using [multiple content blockers]({% post_url ????-??-??-content-blocking %})
to protect myself from trackers on the internet. So I've had
multiple layers of protection when it came to tracking.
However, This news led me to consider to try out Firefox' new
feature. Considering that the feature itself has been around
for a long time ( almost 4 years ), it has had long enough
time to mature and smoothen out any rough edges, have a very
extensive list of trackers and probably do a decent enough
job out-of-the-box.

I recall when Firefox released the [Screenshots](https://blog.mozilla.org/firefox/share-exactly-see-screen-firefox-screenshots/) feature (
using the same strategy - first run as a Test Pilot, then
graduate it into the product ), I was excited to rush to
`about:addons` to remove / disable the existing add-ons that
I was using. Why? Because I had the required feature built-
into my browser. And that too a better one than that I was 
using at the time. I got it out-of-the-box, so there was no
need for an external "add-on" to do the same task. So here I
was having the same thoughts again, but this time about
tracking protection.

Even before Screenshots, there used to be another extension
called [FireBug](https://getfirebug.com) which used to be a Developer Tool for Firefox that
could be used to debug JavaScript in the browser. In 2016,
Firefox merged most of Firebug's features into the default
DevTools[^1] in Firefox making the need for FireBug obsolete.

Well, I didn't want to just flip a toggle ( or a few toggles )
and do it right away, half-prepared and then suddenly give a
lot of data to those corporations who were currently finding
it difficult to track me. Privacy and Tracking Protection is
not anywhere close to the feature / value that Screenshots
was replacing. I needed to be sure that I had at least
comparable levels of privacy once I turned all of the existing
add-ons that I was using, off.

I've decided to run a trial for a week and see how Firefox'
Tracking Protection holds up to my browsing. My plan is to
create a new profile and not install any extensions in it.
I will start using it as the extra window that I use for my
Private Browsing in my normal workflow. Another feature that
I really like about Tracking Protection is that it gives you
an overview of the trackers it has blocked during the past
week. This report can be viewed in the `about:protections` page.

I'm guessing that the report will give me an overview of the
protection that I'd get if I ran it on my default profile.
Actually, it might give me more insights because I intend to
use the new profile as an alternative to my current Private
Browsing session. While Tracking Protection does work in
Private Browsing sessions, it does not include those metrics
in the report. And I browse any link in my Private Browsing
session. I'm more careful about which links I open in my
actual profile session. So, by letting this new profile
protect my rogue browsing, I'd actually be getting more than
enough data to make the decision whether it is good enough
for my default profile.

I'm also guessing that all kinds of ad blocking protections
that I used to get out-of-the-box with my exisiting add-ons
are going to go away. That's an acceptable trade-off
considering that I'm actually more interested in the
Tracking Protection than the ad blocking. And I'm getting
that out-of-the-box with the browser itself. No add-ons
required. However, it might take some getting used to from
a totally ad-free browsing experience to a lot of ads. And
well, if it gets too much to bear with ( because I've had an
ad-free experience for so many years now ), I'll just go back
to all of my existing add-ons.

I'm hoping that this exercise will give me good insight on
whether Firefox' Tracking Protection is good enough for a
privacy paranoid like me. At the end of the week, if the
experience looks fine to me, I might switch my main profile
to Tracking Protection and disable all my existing privacy-
protecting add-ons. I might not remove them altogether just
yet.

[^1]: [Firebug lives on in Firefox DevTools](https://hacks.mozilla.org/2016/12/firebug-lives-on-in-firefox-devtools/)
