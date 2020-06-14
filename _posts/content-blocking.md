---
title: "Content Blocking - How I keep my privacy around the internet"
tags:
  - content-blocking
    tracking-protection
    privacy
write-date: 2020-05-27
pending-actions: add screenshots
---

Tracking a user around the web is becoming more common these
days. It's as simple as inserting a third-party cookie into
the user's browser and recording every website that they
visit in the same cookie so that when they finally reach the
party that has been tracking them, they've collected enough
information about the user to have a fair enough picture
about them to build a profile and then do whatever they want
with that profile.

Currently, at least in the mainstream, the use of that data
is limited to _personalized ads_, as they call it. It has a
better name - **targeted** ads because that's what they
actually are - targeted.

I care about my privacy a lot enough that I don't want third-
parties like Google [Analytics] _tracking_ me around on the
web like this. I use not one, but multiple web extensions
that block this kind of tracking. To add to that, I mostly
browse in _Private Browsing_ mode. Most times, I'll have
more tabs open in my Private Window than in my main window.
As an added benefit, I get to keep a clean browsing history
as well.

### Firefox Lightbeam
I was made aware of "third-party tracking" when Firefox ran
a privacy campaign back in 2013 when they released a ( now
defunct ) add-on called Firefox Lightbeam. It was an add-on
that would link cookies and trackers and plot them all on a
canvas. What you got was a graph showing you how all the
sites that you've visited and how trackers on those websites
are linked with each other eventually connecting up to one
single large corporation like Google who would collect all
of that generated data. Who knew what they actually did with
all of that data?

### Disconnect
Then around the same time came [disconnect.me](https://disconnect.me) that took it
one step further. They allowed you to block these so-called
trackers. Initially, they even had a "private" search add-on,
that would trigger a search on [duckduckgo](https://duckduckgo.com). They do a decent
job of displaying information of trackers and blocking them.
[
until recently. Recently, because of the overload of privacy
extensions that I have in my browser, the disconnect extension
fails to open at all. I'm not sure whether it is actually
working or not. It does work if I test it in isolation in a
separate profile.

EDIT : it does not work only in Private Browsing sessions.
]
Though the extension interface hasn't changed since they
first came out so the interface does look a bit outdated.
Maybe all the magic has been happening behind the scenes:tm:

### Ghostery
I've been using [Ghostery](https://www.ghostery.com) for the longest time now. And 
that's partly because of its intuitive, customizable block
list. Of recent, the web extension sports a very neat
interface as well. The small purple alert at the bottom right
corner that appears with every page load showing quick
information of tracking technology that was blocked or
allowed by ghostery has evolved as well.

### Privacy Badger
[Privacy Badger](https://privacybadger.org) by the [Electronic Frontier Foundation](https://eff.org).
It wasn't as polished or beautiful like Ghostery, but it
worked. I had heard of it before, but I had also heard that
it was known to break a lot of websites. Then later on, I
read that the extension had gotten learning skills and 
"_automatically learns to block invisible trackers_". I
decided to try and see how much had it learnt. Well, it
wasn't as bad as I had heard previously. At least, it wasn't
breaking any websites in a visible way. So, then it stayed.

### uBlock Origin
I believe I had heard of uBlock Origin, AdBlock Plus and
Privacy Badger, all around the same time. And this was
before I had gotten Ghostery. I don't remember why I didn't
install uBlock Origin then, but when I decided to keep
Privacy Badger alongside of Disconnect and Ghostery, I
thought, "_why not have uBlock Origin as well?_"

### supplementary web extensions
I use a couple web extensions that supplement my privacy
experience during browsing the web.

#### Terms of Service; Didn't Read ( ToS;DR )
[ToS;DR](https://tosdr.org) is a service that, like the name suggests, analyzes 
the Terms of Service on various websites and assigns a
"**Privacy Grade** to the website. This grade is shown in the
icon of the extension in the browser. It also sends you a
notification when you visit websites with major issues in
their terms of service.

#### DuckDuckGo Privacy Essentials
I heard about [DuckDuckGo Privacy Essentials](https://duckduckgo.com/app) pretty late.
Nevertheless, I installed the add-on and started using it.
The interfaces looks very similar to Disconnect, but it is
Disconnect on steroids. It has more information, and has an
integration with ToS;DR as well.

After using it for a bit, I realized that the extension was
opiniated. For example, the Chrome Web Store got a C grade
by ToS;DR, but Privacy Essentials 'downgraded' the website
to a grade D, even though the website had 0 trackers. And
the reason given? "Site is a Major Tracker Network". Sure
enough, that's a fair judgement to make, Google IS a major
tracker network, I don't deny that, but they had no trackers
on that particular website, then why would the extension
flag the website?

That led me to believe that the extension was opinionated
and not giving information completely using the data collected
during that particular page load. Maybe, that information is
being served from a static database that is pre-populated.
One could argue that this is misleading to end users who
blindly believe what is shown to them.

Hence, I decided that I wouldn't completely rely on the
information shown to me and make judgements. So both, ToS;DR
and DuckDuckGo Privacy Essentials are merely on my browser
for informational purposes and I don't act on them really.
For example, if I were to act on a ToS;DR report, I wouldn't
be able to use StackOverflow anymore. ToS;DR throws a
notification in my face everytime I open a StackOverflow
link because, apparently "The terms of service raise very
serious concerns" and gives it an "E" grade with no further
explanation.

Even without acting on ToS;DR or Privacy Essentials, I think
I have a fairly better position in terms of privacy with all
the other extensions that I mentioned above. Of course, this
is always a cat-and-mouse game. One can never be 100%
protected, but it is one step harder for someone to track my
behaviour on the internet.

### a note on Ad Blockers
I don't use ad blockers like AdBlock Plus or AdGuard because
blocking ads was never my intention. I don't mind some ads
that are not too intrusive ( in the face ). The ads on
streaming services like YouTube, Spotify and the like
which hinder your experience on the service with ads is
what I mean when I say intrusive ads. And as long as they
are not following me around wherever I go on the internet,
I wouldn't mind them. What I wanted was to stop the tracking.
Ad-blocking just came as a side-effect.
