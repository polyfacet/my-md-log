# Principles and mottoes
<div class='editDate'>Created: 2021-11-18</div>
<div class='editDate'>Modified: 2021-11-23</div>

## Introduction
Lately I have realized that I have gone from "solution-oriented" to "problem-oriented", therefore I thought I would write down some principles and mottoes which I either strive for or is somehow programmed in me. Maybe I will add the reasons to it in the future.

---
## Problem solving

    If I had an hour to solve a problem,
    I'd spend 55 minutes thinking about the problem and five minutes thinking about solutions.

    -- Albert Einstein
 

It is easy to jump to the solution part when a problem is encountered within my field (PLM Software customizations). Often there can exist a multitude av solutions to a given problem. However, once created a solution you will basically have to live with it, since removal/redoing will always have lower priority than new features. And removing is also more complex, due to legacy and the too frequent case: That the WHYs of the implementation are missing/left undocumented. Which makes it a more daring task to do than adding a new feature.

An interesting article on the topic:
<https://www.forbes.com/sites/nelldebevoise/2021/01/26/the-third-critical-step-in-problem-solving-that-einstein-missed/?sh=136840d23807>

---

## Zen of Python

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one– and preferably only one –obvious way to do it.[a]
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than right now.[b]
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea – let's do more of those!

Source: [Wikipedia](https://en.wikipedia.org/wiki/Zen_of_Python)

A note about the Python language is that i reduces the use of the noisy {}; which are so frequent in so many programming languages. Similar to VB.NET - the sibling of C# - which for some reason it is popular to frown upon. 
Even though VB.NET have some syntax that I don't like, it is most of the time much more explicit and clean than C#
As seen in example below, the VB-syntax could actually also be a typical pseudo-code.

VB.NET
``` vb
    If ItIsWeekend Or Holiday Then
        Chill
    Else
        Work
    End If
```

C#
``` csharp
    if (ItIsWeekend() || Holiday()) {
        Chill();
    }
    else {
        Work();
    }
```

This could be refactored/simplified to:
``` vb
    If ItIsAWorkingDay Then
        Work
    Else
        Chill
    End If
```
Or written like I see too often 

``` csharp
    if (IsWeekend()) {
        Chill();
    }
    else {
        if (Christmas() || Easter() || Vacation()) {
            Chill();
        }
        else {
            Work();
        }
    }
```
---

## In simple terms
As a Feynman fan I must include some of his quotes.

    If you can't explain something to a first year student,
    then you haven't really understood.

    -- Richard P. Feynman

This one I like because often in my work discussion are often handled on detail level. But the documentation should be written on a high level, so it is easy to understand and easy to reevaluate in the future. It connects back to Einsteins quote about problem solving to. Often if you try to explain something in simple terms you may often find that the solution has it flaws. Often the solution is more complicated than it needs to be.
