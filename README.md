<!--
author:   Andre Dietrich; Sebastian Zug

email:    LiaScript@web.de

version:  0.0.1

language: en

narrator: US English Female

comment:  Try to write a short comment about
          your course, multiline is also okay.

-->

# RemoteLabs as OER

The next evolutionary step
---------------------------

## Introduction

!?[Industrial eLab Magdeburg](https://www.youtube.com/watch?v=bICfKRyKTwE)

## Edrys

> Edrys is an open and modular remote teaching platform (and the first live LMS)
>
> Source: https://github.com/edrys-org

    {{1}}
![edrys](https://raw.githubusercontent.com/edrys-org/edrys/main/docs/index/screen-settings.png)

### Concepts

    {{0-1}}
![edrys](https://raw.githubusercontent.com/edrys-org/edrys/main/docs/stations/structure.png)

     {{1}}
![stations](https://raw.githubusercontent.com/edrys-org/edrys/main/docs/stations/arduino-lab.png)

## Edrys-Lite

{{1}} WebSite: https://edrys-labs.github.io

![edrys](https://raw.githubusercontent.com/edrys-labs/edrys-Lite/main/img/overview.png)

### Technologies

Peer-To-Peer in da Browser

    {{1-2}}
``` ascii    __Fig:__ Classic Client & Server Applications
    👨🏾‍💻 --.     .-- 👩‍💻
          \   /

👩‍💻 ------  🖥️  ------ 👨🏾‍💻

          /   \
    👨🏾‍💻 --'     '-- 👩‍💻
```

    {{2}}
``` ascii    __Fig:__ Peer^2^Peer- or Mesh-Networks
- - - --👨🏾‍💻-----👩‍💻
              /  \
             /    \
    👩‍💻------+-----👨🏾‍💻- - -
      \    /      /
       \  /      /
        👨🏾‍💻     👩‍💻- - - -
```

#### 1. WebRTC

> The __Web Real-Time Communication__ is a free and open-source project providing web browsers and mobile applications with real-time communication (RTC) via application programming interfaces (APIs).
> It allows audio and video communication to work inside web pages by allowing direct peer-to-peer communication, eliminating the need to install plugins or download native apps...
>
> _Source: [Wikpedia](https://en.wikipedia.org/wiki/WebRTC)_

    {{0-1}}
``` ascii
                     (WebRTC)
Alice 👩‍💻 <------------------------------> 👨🏾‍💻 Bob
```

    {{1}}
``` ascii
               (Signaling Server)

       .-------------> 🖥️ --------------.
       |    "{1}{}"   /  A      "{2}{}" |
       |             /    \             |
       |            /      \            V
                   /        \
Alice 👩‍💻 <--------'          '--------- 👨🏾‍💻 Bob
            "{4}{}"             "{3}{}"
      A                                  A
      |                                  |
      '----------------------------------'
      A    "{5}{Direct Communication}"   A
      |                                  |
      '-- - - - - - - - - - - - - - - - -'
             "{6}{InDirect via TURN}"
```

    {{7}}
> More confusing information on WebRTC:
>
> !?[WebRTC](https://www.youtube.com/watch?v=7cbD-hFkzY0&autoplay=1&start=412)


#### 2. CRDTs

> A _**C**onflict-free **R**eplicated **D**ata **T**ype_ (CRDT) is a new type of data structure[^1] that can be replicated across multiple instances in a network with the following guarantees:

    {{1}}
1. A replica can be updated independently, concurrently and without coordinating with other replicas.
2. Inconsistencies can be resolved automatically.
3. Although replicas may have different state, they are guaranteed to eventually converge.

    {{2}}
__Task:__ Implement an distributed counter

    {{3}}
``` ascii
Alice 👩‍💻

[0]---------*-->[5]--[+1 = 6]--------*-->[8]-- - - - - - - - - - - - 
           /            \           /          \
          A              V         A            \
         /                        /              \
[0]---[+5 = 5]-----------------[+2 = 7]-- - - - --*- - - - - - - - - -

Bob 👨🏾‍💻
```

    {{4}}
__Solution:__ Use Sets and Unions instead... 

    {{5}}
``` ascii
Alice 👩‍💻

{(a,0)}----------*-->{(a,0),(b,5)}->{(a,1),(b,5)}---*-->{(a,1),(b,7)}
                /                         \        /   
               A                           V      A   
              /                                  /
{(b,0)}---{(b,5)}----------------------------{(b,7)}-----------------

Bob 👨🏾‍💻
```

    {{6}}
<section>

__ Implementations__

- [Automerge](https://automerge.org)
- [__Yjs__](https://docs.yjs.dev)

</section>


[^1]: The CRDT concept was defined in 2011 by Marc Shapiro, Nuno Preguiça, Carlos Baquero and Marek Zawirski.

      See also: https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type

### Demo

- __WebSite:__ https://edrys-labs.github.io

- __Modules:__ https://github.com/topics/edrys-module?q=edrys-lite

- __Labs:__ https://github.com/topics/edrys-lab


## What have Poland and Arnold Schwarzenegger in common?

                {{1}}
<!-- style="border: 1px solid black" -->
> # Poland Is Pioneering the World’s First National Open Textbook Program
>
> Access to educational materials varies considerably across the world. Many in low- and middle-income countries do not have textbooks, and the ones that exist are often out of date. Two recent initiatives in Poland, however, are getting free, open textbooks into classrooms—textbooks that are available online and can be easily adapted, translated, and improved upon by teachers and students...
>
> _ Source: https://www.opensocietyfoundations.org/voices/poland-pioneering-worlds-first-national-open-textbook-program _
>
> The literature can be found here: https://zpe.gov.pl

                {{2}}
<!-- style="border: 1px solid black" -->
> # Arnold Schwarzenegger’s Flexbook Initiative
>
> These flexbooks are open textbooks that are shared under the Creative-Commons license CC-BY-NC-SA (Attribution-NonCommercial-ShareAlike).
>
> _ Source: https://www.ck12.org/fbbrowse/ _

