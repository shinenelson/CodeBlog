---
title: "swap? status"
tags:
  - linux-swap
    awk-script
    awk
    script
    physical-memory-vs-swap-memory
    private-incognito-windows
pending-actions:
  - link other post_url
    - [sandbox] : data-islands
    - [compiling] : software compiling craze
---

I don't think there's anyone who uses a modern GNU/Linux
distribution and  gets their physical memory full enough
to swap out. No, I'm not talking aobut under-spec'd machines
My machine has 12 GB ( technically 11.6GB ) of RAM - one 4GB
stick and another 8GB; yes, the second stick was an upgrade,
hence the uneven proportion. And part of the reason for the
upgrade was this - my machine was swapping out too often.
And even now, after the upgrade, I can still manage to fill
even the 12GB up and swap my memory out.

Oftentimes, I don't even realize when my swap of 6.6GB runs
out too. I realize towards the end when my machine starts to
slow down and not very soon - just hang up. Many people who
know I use GNU/Linux ridicule me when I tell them that my
machine has hung up. It's the same question every time, "Can
GNU/Linux really hang?" Well, I can make my machine swap out
and hang, yes.

## How?
Private / Incognito Windows. Yes, I said windows in plural.
I use Private Windows heavily. In fact, most times, I'll
have more tabs in one of my Private Windows than all of my
normal windows combined ( actually, I usually have only one
normal window but multiple Private Windows ).

## And why is that relevant?
Private / Incognito Windows don't store any session
information on disk; rather they store them in volatile
memory - RAM and swap memory for the obvious reason of being
volatile. So the more tabs / windows you have, the more
memory you need to store all of these data. And when you run
out of physical memory ( RAM ), you swap out to disk.

Aside : Let's overlook the fact that Google Chrome gobbles
up how much ever RAM you give it. And also, I don't use
Google Chrome other than if persuaded by work situations or
if I have to [sandbox] Google services.

## Why not just close those tabs / windows?
Well no, those windows are my main windows, so I can't just
close them with a click. That'd be like asking me to close
my main window. Of course, I can close some of the windows
sometimes ( and I do too ), but most times, that's not the
case.

## So, now what?
I have different methods to clean up my physical memory and
make space for the system to run smoothly ( other than just
closing application windows ). However, the drawback of swap
memory is that while there is some logic in the Linux kernel
to eventually _[swap in]_ those pages from the disk back to
RAM, in my experience, it has never written whatever it has,
back to physical memory; even if the physical memory has
enough memory. Maybe there's some other threshold for the
_swap in_ to get triggered. I've only tried it with almost
the same amount of RAM available. Maybe if it had, say,
double the amount the amount of RAM available, then it might
_swap in_. Well, I can't free up double the RAM so that the
swap can do its thing, can I? In that case, I wouldn't need
the swap anymore, would I? I'm just going to _judge_ that
swap is just selfish here.

Actually, it is the task of the physical memory ( RAM ) to
summon swapped pages back when they're required by their
corresponding applications. Thinking about it, maybe, there
isn't a single _swap in_ mechanism. Maybe, like _[eventual
consistency]_, it just means that in time, when the RAM
keeps needing more swapped pages, it'll just summon them
individually and eventually free up all of the swap.

Well, often times, some of the memory might already be
deallocated by the operating system ( for example, when
applications are closed ), but the swap memory doesn't know
about this and doesn't even have to care about it because it
is supposed to be fetched back by the physical memory _when_
it is required. So it is by design that the swap doesn't
write back to the physical memory unless it is specifically
summoned. So then, what happens to those swap pages that were
deallocated by the operating system? They just stay there
forever like zombies. And who likes zombies, especially
zombie processes and memory? Nobody.

Well, if the swap won't write back to the RAM on it's own,
then what do we do? We force it to write back.

## How do you do that?
'restart' the swap [^1][^2][^3]
```sh
[sudo] swapoff <dev>|-a|--all
[sudo] swapon <dev>|-a|--all
```

## Okay, so?
I can't recall when I started doing this or how long I've
been doing it. For quite a while now, I've aliased those 2
commands into one :
```sh
alias swap='sudo swapoff --all && sudo swapon --all'
```

And then I `time swap` to run after pretty-printing the
amount of `free` memory available.
* print the output of `free` and then `swap` ( so that if
if there isn't enough memory, I can kill it just in time
before there's a memory deadlock and my machine hangs again.
```sh
alias ftswap="free --human | awk 'NR==3 { print \$3 }' && time swap"
```
and then I nest-aliased `ftswap` more ( aliasception \o/ ) :
  * _swap in_ and exit
    ```sh
    alias ftswape='ftswap && exit'
    ```
    this was my go-to alias when I needed to clean up a
    large amount of swap ( > 3GB ) and could block my other
    things because it was running. So, I used to just open
    up another terminal, run the alias and just forget about
    it. It would run its course and `exit`.

    before I ran this though, I'd run the first part of the
    alias and confirm that it was safe to just leave it
    running in the background - meaning, I would visually
    check and confirm that I'd have at least 512MB of RAM
    even after the whole swap in completed. That way I could
    continue working and not be bothered about the swap in
    activity happening in the background.

    most times it was `ftswape`, but I've used `ftswap`
    directly too when the amount of available memory was
    limited and needed close monitoring. At those times, I'd
    have some kind of memory monitor open - `watch free
    --human`, [`htop`], [`glances`] or [`bashtop`]. ( yes,
    I'm crazy enough to have all of those tools on my system.
    but hey, it was fun [compiling] them ).
  * _swap in_ before suspending system to disk
    ```sh
    alias ftswapsus='ftswap && systemctl suspend'
    ```
  * _swap in_ before hibernating system to disk
    `systemctl hibernate` just wouldn't hibernate to disk
    if swap was already in use.
    ```sh
    alias ftswapsch='ftswap && systemctl hibernate'
    ```

## What's so great about an alias?
Well, it's not about the alias anymore. In its evolutionary
progression, the first part of `ftswap` has now evolved into,
not shell functions, but an `awk` script. It takes the output
of `free --mebi`, does some basic calculation ( I could call
it _smart_; but it really is just subtracting 2 values - free
RAM and used swap ) and exits safely ( exit code `0` ) if
it is safe to _swap out_; otherwise exits with exit code `255`.

<script src="https://gist.github.com/shinenelson/a8a5550eaaefd66658a6d1f10ffbe4dc.js?file=swap-status.awk"></script>

To add some color, I added a fancy exit code if the
difference is lesser then 256MiB. The script exits with the
difference as the exit code. It was totally un-necessary,
but I left it anyway.

## How to use it?
Well, here's the irony, that'd be another `alias swap?="free --mebi | awk -v DEBUG=$DEBUG -f /path/to/swap-status.awk"`

Just to be clear, `swap` has not gone anywhere. It's the
inline `awk` parsing that was in the middle of `ftswap` that
has been replaced with the script ( obviously, because it is
an `awk` script, it can only replace the `awk` ).

Also, previously, the `awk` parsing was not decisive. It was
just pretty-printing what I needed to see in order to make a
visual-based decision whether to `SIGINT swap` when it had
almost filled up the available physical memory. Now, in its
_evolutionary progression_, I've handed over the decision-
making capability to the `awk` script so that it now exits
with a decisive exit code. Now, I can just run `swap?` to
know if my machine can _swap in_. And then `&&` it to `swap`.
```sh
swap? && swap
```

Since I got the idea from doing a lot of `ftswap`s, I replaced
the existing `ftswap` with the new alias :
```sh
alias ftswap='swap? && swap'
```
So all the child aliases of `ftswap` still function as they
used to previously. The advantage being that I don't have to
do any more visual-based decision-making for manually
swapping in. `ftswap` has gotten smart enough to know if it
is safe to _swap in_ or not and then triggers a manual swap
in if it is safe to.

[swap in]: https://askubuntu.com/a/1359
[eventual consistency]: https://en.wikipedia.org/wiki/Eventual_consistency
[`htop`]: https://hisham.hm/htop/
[`glances`]: https://nicolargo.github.io/glances/
[`bashtop`]: https://github.com/aristocratos/bashtop

#### footnotes
[^1]: [How to clear swap memory in Linux - Enable Sysadmin](https://www.redhat.com/sysadmin/clear-swap-linux "How to clear swap memory in Linux - Enable Sysadmin")
[^2]: [How to Clear Swap Memory in Linux - Linux Handbook](https://linuxhandbook.com/clear-swap/ "How to Clear Swap Memory in Linux - Linux Handbook")
[^3]: [How to Clear RAM Memory Cache, Buffer and Swap Space on Linux](https://www.tecmint.com/clear-ram-memory-cache-buffer-and-swap-space-on-linux/ "How to Clear RAM Memory Cache, Buffer and Swap Space on Linux")
