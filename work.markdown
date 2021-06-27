---
title: work
layout: page
mermaid: true
---

You can already find a summary of my professional experience on [LinkedIn](https://www.linkedin.com/in/austin-shen/) and my CV on GitHub (probably not up to date), so it wouldn't make much sense for me to just repeat all of that here.

Instead, I want to show you a "skill tree" which reflects where I'm at with different computing concepts, tools or skills. I've used traffic light colours to indicate my level of competency with green to indicate I have ample experience, yellow to indicate I have some experience, and red to indicate I have little experience. Default blue is something I have just added or am unsure as to where to place it, but hopefully it will be coloured next time you're here.

### Computing

At the moment the nodes are ideas that are relevant to my current role. It seems pretty arbitrary what I've chosen to include here and what I've omitted. Always open to feedback so feel free to get in touch if you believe there is something I change.

<div class="mermaid">

graph LR;
    classDef red fill:red;
    classDef yellow fill:yellow;
    classDef green fill:lime;

    subgraph CS THEORY
        cs1(Computer architecture)
        cs2(Networking)
        cs3(Data structures)
        cs4(Algorithms)
        cs5(Database theory)
        cs6(Distributed systems)
    end

    subgraph PROGRAMMING
        p1(C/C++)
        p2(Python)
        p3(Haskell)
        p4(R)
        p5(Infrastructure as code)
        p6(Javascript)
        p7(Golang)
    end

    subgraph SOFTWARE
        se1(DevOps)
        se2(Public cloud)
        se3(Containerisation)
        se4(Kubernetes)
        se5(Git)
    end

    subgraph WEB
        w1(Frontend)
        w2(APIs)
        w3(Security)
        w4(Databases)
    end

    subgraph HPC
        hpc1(OpenMP)
        hpc2(CUDA)
        hpc3(Slurm)
    end

    cs1 --> p1
    p2 -- Django, Flask --> w2
    p6 -- React --> w1
    se4 --> w2
    p1 --> hpc1
    p1 --> hpc2
    se3 -- Docker, Singularity --> hpc3

    class cs1 yellow;
    class cs2 yellow;
    class cs3 red;
    class cs4 red;
    class cs5 red;
    class p1 yellow;
    class p2 green;
    class p3 red;
    class p4 yellow;
    class p5 yellow;
    class p6 yellow;
    class se1 yellow;
    class se2 yellow;
    class se3 green;
    class se4 yellow;
    class se5 green;
    class w1 yellow;
    class w2 green;
    class w3 red;
    class w4 yellow;
</div>

### References

* [Teach yourself CS](https://teachyourselfcs.com/)

\+ personal experience