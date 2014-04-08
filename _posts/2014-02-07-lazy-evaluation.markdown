---
layout: post
title: A Lazy Evaluation
description: Why I Find Learning Haskell Hard
tagline: Why I Find Learning Haskell Hard
category: personal
---

Haskell is really hard to learn. I've realised as much after taking a semester-long course in it, and after many evenings spent afterwards trying to learn more.

I really like the idea of Haskell. Its design principles and paradigms just make sense to me. Purity, laziness, and a strong, expressive type system are incredibly appealing to me.

Haskell has a bit of a reputation of having a fairly academic community, but one thing it definitely has going for it is the sheer amount of high-quality learning materials available for it. Between [Learn You a Haskell For Great Good](http://learnyouahaskell.com), [r/haskell](http://reddit.com/r/haskell), [#haskell](http://www.haskell.org/haskellwiki/IRC_channel) and the [School Of Haskell](https://www.fpcomplete.com/school) a wannabe Haskellite is completely spoiled for choice for learning resources.

My problem though, is that I don't struggle with the idea of this (taken from [LYAH](http://learnyouahaskell.com)):

{% highlight haskell %}
reverse' :: [a] -> [a]
reverse' [] = []
reverse' (x:xs) = reverse' xs ++ [x]
{% endhighlight %}

or this:

{% highlight haskell %}
map' :: (a -> b) -> [a] -> [b]
map' f xs = foldr (\x acc -> f x : acc) [] xs
{% endhighlight %}

or this:

{% highlight haskell %}
main = forever $ do
    putStr "Give me some input: "
    l <- getLine
    putStrLn $ map toUpper l
{% endhighlight %}

... or various other Haskell concepts taken in isolation. The language makes an awful lot of sense once its concepts are explained to you and you put a bit of mental effort in. Don't get me wrong, there's an absolutely **huge** amount there to learn - but each individual concept itself is usually quite understandable when you understand the motivation for it.

I suppose that's the problem I have with learning Haskell - the motivation for concepts. When you start a CS course, you learn how the machine works. You most likely learn an imperative language at the same time, and it's quite easy to map the relationship between the control structures and primitives in that language to the concepts you're learning about the underlying machine.

But mapping from the programming language to the machine is the easy bit. The hard bit is mapping from the real world, the point you're writing this program, to the programming language. I suppose that's why Object-Oriented Programming became so popular - even a flawed model of the real world is useful if it's easily mappable.

And when you're learning Haskell, it is **hard** to map from the real world to what you're writing. I don't mean mapping *I want to reverse a list* or *I want to alter each element of this data structure with this function* or even *I want to take input from stdio*. I mean taking a problem like *I want to make an application that streams music from this API* and going and writing an application that does that. I've been learning Haskell for about 6-7 months now, and I still have no idea how I'd structure that application.

Throw an imperative programming language at me and a problem and I'd have a general idea of how I'm going to structure it. Sure, it may not be idiomatic and it'll probably have to change massively as I run into problems - but I can start and figure it out as I go.

This isn't a complaint about Haskell, or even the learning materials available - stuff like [Real World Haskell](http://book.realworldhaskell.org/) and [Write Yourself A Scheme in 48 Hours](http://jonathan.tang.name/files/scheme_in_48/tutorial/overview.html) are seriously great resources for being introduced to this kind of thinking. It's just a musing on something I've found while trying to learn Haskell. It's been a serious source of frustration for me as I've been learning the language. I had always thought that I'd struggle to learn these infamous *functional concepts* when I started learning Haskell, but the real frustration has come from not knowing how to tie them together into something tangible, to hack away at a **real** application - the way I normally learn these things. I'm slowly getting there, but it is absolutely every bit as difficult as everybody said it would be.

So, if you're thinking of learning Haskell, or struggling yourself - don't worry about the stuff that sounds scary like *monads* or *purity* or *laziness*. If you work on it a bit, you'll understand them. Just don't underestimate just how **much** there is to learn, or how long it'll take you until you're able to hold enough of it in your head at once to work on something real.
