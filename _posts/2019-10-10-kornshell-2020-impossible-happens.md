---
title: KornShell 2020 - Impossible Happens!
layout: post
category: posts
---

TLDR: Christmas came early. ksh-2020.0.0 was released today. Read the release announcement [here][ksh-2020-release-announcement].

More than 2 years ago, I [announced my intentions](korn-shell-not-dead) to revive AT&T KornShell. When I started working on it, this codebase was a big hairball that nobody wanted to touch. It’s written in such a tricky way that can make the best C programmers sweat. Build system was complicated and debugging build failures was a nightmare. Test coverage was bad and even a simple bug fix could end up breaking basic functionality. There were lots of old bugs that have not been fixed for decades. It seemed almost impossible that we would be able to make a new release.

Today we are releasing stable version of ksh-2020.0.0. This marks the first stable release of ksh after a gap of more than 6 years. I will summarize key changes here:

- More than 500,000 lines of code were dropped to simplify the codebase.

- Build system was changed from Nmake to Meson. This improved build speed by a factor of 35 and made it easier to debug build failures.

- Downstream patches from different vendors were upstreamed.

- Hundreds of new tests were added to get better test coverage. This includes writing interactive tests for vi and emacs bindings through `expect` based framework.

- Coverity defect rate (bugs per thousand lines of code) was brought down from more than 2 to less than 0.5. This is below average defect rate of projects that are scanned through Coverity.

- Refactored thousands of lines of code to make the style consistent and easier to maintain.

These changes have helped to bring this codebase closer to 21st century and sparked a new interest in keeping ksh alive.

On a personal note, it was amazing to work with awesomest [ridiculous_fish][ridiculous_fish-github] to [revive fish shell back in 2012][fish-shell-2012]. fish shell has come a long way since then and has managed to expand its community from very few people to hundreds of new contributors and thousands of new users. It’s a privilege to work with another gifted programmer, [Kurtis Rader][krader1961-github], to give a new life to ksh. Kurtis used to be a fish shell contributor, but I never got a chance to work together with him until he started contributing to ksh. It would not have been possible to make a release without his consistent hard work and enthusiasm. Also, thanks to [Kamil Dudka][kdudka-github] for helping me in making key decisions and reviewing pull requests.

It was a big setback to ksh when David Korn and his team stopped working on it a few years ago. 10th October 2013 was [the last day][dgk-gsf-last-day] of David and his team at Bell Labs. As a tribute to previous maintainers, we are making this release on 10th October 2019. We may not be able to bring long term vision previous maintainers had, but we can try to keep ksh relevant to the present time. I am hoping this release will open new frontiers for the future of KornShell.

It’s not the end, it's a new beginning!

Comments on [Hacker News][hacker-news] and [reddit][reddit].

[ksh-2020-release-announcement]: https://groups.google.com/d/msg/korn-shell/-tQkll8BxXU/X4ON61CHBwAJ
[ridiculous_fish-github]: https://github.com/ridiculousfish
[krader1961-github]: https://github.com/krader1961
[kdudka-github]: https://github.com/kdudka
[fish-shell-2012]: https://www.mail-archive.com/fish-users@lists.sourceforge.net/msg03044.html
[dgk-gsf-last-day]: https://www.mail-archive.com/ast-developers@lists.research.att.com/msg01462.html
[hacker-news]: https://news.ycombinator.com/item?id=21214334
[reddit]: https://www.reddit.com/r/unix/comments/dfy6lp/kornshell_2020_impossible_happens/
