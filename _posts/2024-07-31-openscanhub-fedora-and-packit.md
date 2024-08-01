---
title: OpenScanHub, Fedora and Packit
layout: post
category: posts
---

TLDR: We have deployed OpenScanHub on the [Fedora infrastructure](https://openscanhub.fedoraproject.org/) and recently integrated with [Packit](https://packit.dev/). An example scan can be seen on [GitHub](https://github.com/strace/strace/pull/300/checks?check_run_id=28180162251) and more information can be found in the [OpenScanHub](https://fedoraproject.org/wiki/OpenScanHub) and [Packit](https://packit.dev/docs/configuration) documentation.

This is a follow up on my [previous blog post](openscanhub) about OpenScanHub.

# Fedora
Since open sourcing OpenScanHub, we have made major progress towards making it easier for the community to use it. After several rounds of getting approval from the Fedora community and the leadership, it has been deployed on the [Fedora infra](https://openscanhub.fedoraproject.org/). Also, we made it work on a larger scale to run scans more securely through [resalloc](https://github.com/praiskup/resalloc). Instructions to use this service are given on the [Fedora wiki](https://fedoraproject.org/wiki/OpenScanHub).

Since then we have run a couple of mass scans on critical path packages in Fedora rawhide, you can read discussions about these mass scans on the OpenScanHub [mailing list](https://lists.fedoraproject.org/archives/list/openscanhub@lists.fedoraproject.org/). A brief summary of this progress can be found in my talk at [DevConf](https://www.youtube.com/watch?v=rcuIvAttWgY).

# Packit
Packit is an open source project aiming to ease the integration of projects with Fedora Linux, CentOS Stream and other distributions. Since I started working on OpenScanHub a couple of years ago, Packit has always been on the top of my list for integration. It is used by some very prominent open source projects like systemd, strace, util-linux, etc. and is targeted towards upstream developers to decrease the maintenance burden of packaging. It is a great integration point for OpenScanHub as the bugs should be fixed as soon as possible upstream.

The Packit team did service side integration of OpenScanHub recently. It is enabled only for rawhide, as rawhide is the closest candidate to upstreams. A differential scan is performed on each pull request against the target branch, so the developers can focus only on the findings introduced in the pull requests.

Alternatively, you can use the Packit CLI tool to submit a scan. If you are already using Packit CLI, you can use the `packit scan-in-osh` subcommand to perform a scan. This feature is documented through [Packit CLI](https://packit.dev/docs/cli/scan-in-osh) documentation.

# Credits
This was a coordinated effort among multiple teams inside Red Hat. I would like to thank all the people who have helped me:

* [Kamil Dudka](https://github.com/kdudka) - Product Security
* [Lukáš Zaoral](https://github.com/lzaoral) - RHEL
* [Tomas Tomecek](https://github.com/TomasTomecek) - Packit
* [Pavel Raiskup](https://github.com/praiskup) - Resalloc
* [Kevin Fenzi](https://github.com/nirik) - Fedora
* [Michal Konecny](https://github.com/zlopez) - Fedora
* [František Lachman](https://github.com/lachmanfrantisek) - Packit
* [Laura Barcziová](https://github.com/lbarcziova) - Packit

Also, many different contributors have helped me from Red Hat and the Fedora community on different occasions. It would be impossible to name all of them. So, if you have helped me with OpenScanHub, I sincerely thank you for your help.

We have been using this service successfully for more than a decade inside Red Hat and now its community’s turn!
