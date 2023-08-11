---
title: OpenScanHub
layout: post
category: posts
---

OpenScanHub is a service for static and dynamic code analysis. It was internally used inside Red Hat for more than 12 years and was recently open sourced. This blog post is a brief summary about it.

OpenScanHub is primarily used to scan RPM packages and source tarballs. It is extensible through [csmock][csmock-github] plugins and is not limited to any programming language. It uses open source tools like `Cppcheck`, `ShellCheck`, `gcc`, `clang` etc. to find defects in the code, but it is also extensible to proprietary tools like Coverity and Snyk. In simple words, it is just a “frontend” to run various analyzers on a codebase. It is a service and does not have a static analyzer of its own. It can also perform dynamic analysis through tools like `valgrind` and `strace`.

It can collect all the reports from various analyzers at a single place. This makes it easy for the developers to track bugs in their code, as the reports are not fragmented across different places.

The most unique feature of OpenScanHub is the ability to perform differential scans. It can compare reports from a newer version of a codebase with the older version and can report defects that were introduced in the newer version. This is an important feature while scanning legacy codebases as the maintainers do not have time to fix all the defects that may have accumulated over time. It can help them to avoid introducing new defects in the code. It is also an important feature for package maintainers (who are not upstream developers), as they can focus on defects that were introduced by a new release or a downstream patch.

RHEL 5 was the first RHEL distribution that was scanned through it. And it has been used since RHEL 7 to perform mass scans before new releases of RHEL. The most recent release that was scanned through OpenScanHub is RHEL 9. In RHEL 9, it analyzed 480 million lines of code in 3700 packages, where it identified approximately 680000 potential bugs. This helped us to eliminate hundreds of potential security issues during the productization phase of RHEL 9. It has become a critical part of RHEL releases and its usage is slowly growing with other projects.

I was responsible for open sourcing this codebase and I hope the entire open source community would benefit from it. I would like to thank [Kamil Dudka][kdudka-github], [Lukáš Zaoral][lzaoral-github] and all the OpenScanHub contributors inside Red Hat that have supported this effort. This is the beginning of building a community around OpenScanHub and you can join the effort on [GitHub][openscanhub-github].


[csmock-github]: https://github.com/csutils/csmock
[kdudka-github]: https://github.com/kdudka
[lzaoral-github]: https://github.com/lzaoral
[openscanhub-github]: https://github.com/openscanhub/openscanhub
