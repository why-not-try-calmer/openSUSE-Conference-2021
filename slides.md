__NB: Italicized text like this is not supposed to appear on the slides. It refers to what I want to say orally in more details.__

---
# Who we are

Adrien: 
* lives in Switzerland
* ~90% of PhD in something to do with concepts and linguistics
* Python and Haskell fanboy

Attila:
* lives in Indonesia
* DevOps and SysAdmin
* entrepreneur -- works for the company he has founded

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

__NB: Context differences between the person supporting and the supported person are difficult to detect and capture in a live conversation. Good documentation makes context explicit. Will come back to that later__

---

## Being lazy together

*Being lazy*. 
* when someone finds oneself scratching their head in front of an already solved problem, there is potential waste. 
* the time and energy spent scratching their head is spent twice.

*Together*. 
* the waste scales immensely when you have a large community like openSUSE
* it also does not help with inequalities: if you are not lucky enough to talk to the most knowledgeable people (think of separate linguistic communities), you are worse off everybody else who are lucky enough to know someone who can help.

---

# The sad state of the Tumbleweed documentation

Tumbleweed is the openSUSE rolling-release distro, and it's great. But such greatness takes a tiny bit of understanding to be taken advantage of. 

What's in there for people interested in TW?
* the official Leap reference manuals
*    * great, but they don't talk about Tumbleweed at all. Sure, they talk about tools common to Leap and TW. This falls short, as the workflow between rolling and fixed-point release is so different.
* the openSUSE wikis, especially the SDB
*    * there is no explicit and visible curation, you cannot trust anything, because you don't know who's vouching for what you read. 

---

# Why wikis are usually not great for important things that need updating

Absence of visible maintainership means that truth is contamined with incertainty.

How to tell up-to-date and factually correct from outdated or incorrect? 

__NB: You cannot tell apart up-to-date + factually correct and recommended parts from the part which aren't. So the user has no rational option but to try and pray. (Or just use Fedora or Ubuntu)__

Wikis work just like GitHub repos: when you can honour the promise to your users that there is maintainership behind the curtains.

__NB: Wikipedia pay people, Arch uses wiki categories as GitHub repositories__

We are just making this explicit, by using a GitHub repo. 

---

# What do you want to document, again? (1/2)

People interested in an openSUSE distribution have factual issues:

* "Should I pick X or Y in the installer" if I want to do Z?"
* (I am booting to a black screen). How to use an Nvidia + some other GPU?
* How to get software X?
* How to update / upgrade?

Many are special cases of these for TW:

* How to create snapshots and to roll back from them?
* How to hook to third-party repositories
* How to keep my kernel-dependent software X across Tumbleweed snapshots?

---

# What do you want to document, again? (2/2)

But they have perhaps even more issues about best-practices:

* How often should I update?
* How should I solve conflicts between dependencies?
* Should I use zypper or Yast? zypper or dnf? tool X or Y?

These best-practice questions stem from:
* the conceptual differences between fixed-point and rolling- release
* the specifics of selection of tools at the core of the openSUSE experience (zypper / snapper / yast / obs)
* questioning the defaults ("vendor stickiness", snapper config defaults, zypper config defaults -- no autorefresh)
* the developments of software underlying or gradually integrated to a bleeding edge distribution
* "confort" improvements (zstd compression by default, pipewire, dnf)
* trends and fashion

---

# So documenting TW cannot do away with recommendations:

* the more people know, the more they're pushing their system and questioning the defaults, until their questions cannot be met only on the basis of technical facts
* openSUSE and TW in particular are appealing to people eager to learn and tinker with their system, so a good docs is required to honour the implicit promise that the risks associated with the rolling-release workflow are worth taking.

