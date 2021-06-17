---
theme: default
class: 'text-center'
highlighter: shiki
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)

---

# openSUSE docs: Tame the beast, make it a friend

<img border="rounded" src="ad.jpg" style="height:25%; width:25%; margin-left: 11em" />Adrien Glauser (nycticorax@opensuse.org)
__Attila Pinter (adathor@prontonmail.com)__

---

# Who we are

Attila:

* lives in Indonesia
* DevOps and SysAdmin
* entrepreneur -- works for the company he has founded

Adrien: 

* lives in Switzerland
* ~90% of a PhD in something to do with concepts and linguistics
* Python and Haskell fanboy

---

# Why we got into documentation

## Learning

* documenting something tests your understanding of it
* committing to documentation in itself is a nice incentive for learning

---

## Take some weight off user support

* when you support new users, it's exhausting to repeat things over and over.
* following a single conversation can be taxing (imagine following multiple in parallel).
* even forums are not that discoverable, and information is fragmented

__Context differences between the person supporting and the supported person are difficult to detect and capture in a live conversation. Good documentation makes context *especially assumptions* explicit. Will come back to that later__

---

## Don't Repeat Yourself and equalize use opportunities

* when someone finds oneself scratching their head in front of an already solved problem, there is potential waste. 
    * the time and energy spent scratching their head is spent twice.
* the waste scales immensely when you have a large community like openSUSE
    * it also does not help with inequalities: if you are not lucky enough to talk to the most knowledgeable people (think of separate linguistic communities), you are worse off everybody else who are lucky enough to know someone around who can help.

---

# The state of the Tumbleweed documentation

Tumbleweed is the openSUSE rolling-release distro, and it's great. But such greatness takes a tiny bit of understanding to be taken advantage of. 

What's in there for people interested in TW?

The official Leap reference manuals?

* great, but they don't talk about Tumbleweed at all. Sure, they talk about tools common to Leap and TW. This falls short, as the workflow between rolling and fixed-point release is so different.

The openSUSE wikis, especially the SDB?

* not bad, but there is no explicit and visible maintainership, so you cannot trust anything, because you don't know who's vouching for what you read.

---

# Why wikis are usually not great for important things that need updating

Absence of visible maintainership means that truth is contaminated with uncertainty.

How to tell up-to-date and factually correct from outdated or incorrect? 

__You cannot tell apart up-to-date + factually correct and recommended parts from the part which aren't. So the user has no rational option but to try and pray. (Or just use Fedora or Ubuntu)__

Wikis work just like GitHub repositories: when you can honor the implicit contract with the user that contents are curated and maintained.

__NB: Wikipedia pay people, Arch uses wiki categories as GitHub repositories__

We are just making this explicit, by using a GitHub repositories.

---

# General questions about openSUSE distributions

People interested in an openSUSE distribution have factual issues:

* "Should I pick X or Y in the installer" if I want to do Z?"
* (I am booting to a black screen). How to use an Nvidia + some other GPU?
* How to get software X?
* How to update / upgrade?

Many special cases of these for TW:

* How to create snapshots and to roll back from them?
* How to add third-party repositories
* How to keep my kernel-dependent software X across Tumbleweed snapshots?

---

# Questions about Tumbleweed 

However many questions go beyond factual, technical questions:

* How often should I update?
* How should I solve conflicts between dependencies?
* Should I use zypper or Yast? zypper or dnf? tool X or Y?

These "best-practice" questions stem from:

* the conceptual differences between fixed-point and rolling- release
* the specifics of selection of tools at the core of the openSUSE experience (zypper / snapper / yast / obs)
* questioning the defaults ("vendor stickiness", snapper config defaults, zypper config defaults -- no autorefresh)
* the developments of software underlying or gradually integrated to a bleeding edge distribution
* "comfort" improvements (zstd compression by default, pipewire, dnf)
* trends and fashion

---

# Thus documenting Tumbleweed cannot do away with recommendations:

* the more people know, the more they're pushing their system and questioning the defaults, until their questions cannot be met only on technical facts
* openSUSE and Tumbleweed in particular are appealing to people eager to learn and tinker with their system, so good docs are required to honor this implicit promise: __the risks inherent to the rolling-release model are worth taking__.

---

# The journey in a nutshell

* started late November 2020
* the goal is to have the 9 first sections of the table of contents covered by the end of late summer 2021: 
    * https://github.com/openSUSE/openSUSE-docs-revamped-temp/blob/dev/ToC.md
* we have about 6 done already, but we are slightly beyond schedule
* why? are we just lazy and incompetent?

---

# The docs writer's debt

## Redundancies

* cherry-picked example: setting up offload to an Nvidia GPU
    * Leap official documentation: https://doc.opensuse.org/documentation/leap/reference/single-html/book-reference/index.html#sec-gui-desktop-suse-prime
    * openSUSE wikis (SDB): https://en.opensuse.org/SDB:NVIDIA_SUSE_Prime
    * but also, forums: https://forums.opensuse.org/
    * not to forget a friendly gecko at: https://opensuse-guide.org/3d.php
* too many sources, giving similar but slightly different tips, published at different times
* we don't want to control what third-parties say about our beloved distribution, so we have to either work with them or compete with them
* we cannot compete with them unless we present a single source of truth (and recommendations!) to the user -- which means removing redundancies
* which means deleting the works of others unless they can be quickly identified and agree to merge their contents with ours

---

## Meeting our own reviewing ambitions

* our reviewing process: on a new submission review
1. struct. & contents #1
2. language., style and punctuation #1 ->
3. struct. & contents #2
4. language., style and punctuation #2

* (1) happens entirely in-house; however
* for (2) and (3) we try to get more experienced and knowledgeable contributors (developers or maintainers)
* but even though those will usually be flawless as far as technical facts, they might not always feel easy about making recommendations or have time to explore recent use cases so as to make an informed recommendation
* we are working on the docs at a time where there is no tradition of such a reviewing process to hook onto!

---

## Floating boats of complex, integrated tech stacks on fragmented waters

* Yast2, zypper, snapper -- those are at the core of the openSUSE user experience, and quite neatly integrated with the operating systems
* but there is a mismatch between the level of integration of these tools and the level of integration / coordination of the people maintaining them
* not a criticism: it's bound to happen in a world where you need to specialize
* what would help would be specific time windows or places where potential reviewers can be identified and invited to reviewing
    * Progress, Pagure?

---

# Silver linings in sight!

* openSUSE Heroes are the grease between the cogs of the infrastructure
* openSUSE docs folks are the pumps pushing know-how and best-practices towards current and future users
* doing it is a blessing, and so is benefiting from it:
    * learning by teaching complements learning by doing
    * relieving user support means more people for contributing to other areas
        * check out how the docs bot allows us to avoid repetitions (**demo time**)
    * writing and integrating documentation is easy to reference and take advantage of in a curriculum
    * ultimately the docs is a precious navigational instrument: it helps a community know where it's heading and helps it remember where it comes from because it embodies a particular history and tradition
    * used in conjunction with good feedback mechanisms (like the _End of the Year_ surveys ;P) it makes for one of the most beautiful place you can contribute in openSUSE.
