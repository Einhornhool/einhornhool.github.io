+++
title = "WTF are CMAKE Interface Targets"
date = 2023-12-20
draft = true
+++

For my current job I need to write test applications for quite a large codebase. This software uses a complex, *historically grown*[¹] build system, comprising of different build tools and build generators, which somehow all work together.
Part of this system is, as in most larger C/C++ code bases, CMAKE.

So far I haven't had much experience with CMAKE, because RIOT OS does not use it. I have integrated a few third-party packages in RIOT, which needed to be configured and build with CMAKE, but apart from that I have no idea how to actually use it.
To be honest, I've even tried actively to avoid it. To me it seemed comlicated and I never really understood their documentation. During my work with RIOT I got used to working with plain Makefiles and messing around with them directly.
Something's not working? Just open the Makefile, see what happens and fix it. Of course this also sucked sometimes, but at least I knew where to look.
Having Makefiles automatically generated and needing to know all the commands and options seemed like weird black magic.

I understand that CMAKE makes life a lot easier when you work on a large project with lots and lots of dependencies. I would never want to write Makefiles for that huge codebase. So this week I actually bit the bullet and started looking into CMAKE.
I started with their official [tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html), which helped to learn some basics. But boy do I hate their documentation. Whenever the tutorial referred to the docs for one of the functions, I had no clue what they actually tried to tell me and had to additionally google most of it.
Sometimes I found better explanations, sometimes I didn't.

One thing that really bugged be was the *interface target*. I really did not understand what it does from the docs. After some searching I found [this Blog](https://leimao.github.io/blog/CMake-Public-Private-Interface/), which did a better job at explaining, but I still couldn't quite picture it.
So here's my own attempt at making sense of this.

[^1]: "historically grown" as in "We quickly threw a bunch of stuff together and made it work to meet the targets and did not have time to clean up"
