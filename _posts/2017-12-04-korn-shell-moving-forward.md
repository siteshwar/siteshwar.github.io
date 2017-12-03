---
title: KornShell - Moving forward
layout: post
category: posts
---

Since my [last blog post][korn-shell-not-dead] we have made some decent progress to improve code around ksh93. I will try to summarize recent developments here :

* Legacy build system has been deprecated and we are going to move to [Meson][meson-home]. The only part of legacy build system that still remains is use of 'iffe' (if feature exists) command. It is used for feature detection (same like configure script in Autotools) and will require some extra amount of work for replacement.

* Travis integration has been improved. Now we are running test cases on Travis to detect regressions. The new build system allows us to run test cases in parallel. With the legacy build system, building and testing used to take more than 20 minutes, it has been cut down to around 5 minutes now.

* We have moved to 'master' branch for development. Most of the git projects use 'master' for development. But since [AST repository][ast-repository] contained full source code of all AST projects, it took us some time to reach a conclusion on it. At the end, we decided to move full AST source code under separate branches and use 'master' only for ksh93 development.


I want to say thanks to  my fellow committer [Kurtis Rader][kurtis-github] for his invaluable contributions. He has been instrumental in improving code and has agitated a few discussions in the community. There is a growing interest in the community to keep ksh93 relevant. We are up to a good start and the list of [pull requests][github-ast-pull-requests] and [issues][github-ast-issues] is slowly increasing.  It is a sign of recovery. KornShell is heading for good times!

[korn-shell-not-dead]: http://situ.im/posts/korn-shell-not-dead
[meson-home]: http://mesonbuild.com/
[ast-repository]: https://github.com/att/ast
[kurtis-github]: https://github.com/krader1961
[github-ast-pull-requests]: https://github.com/att/ast/pulls
[github-ast-issues]: https://github.com/att/ast/issues
