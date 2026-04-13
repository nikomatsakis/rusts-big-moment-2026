class: center
name: title
count: false

# Rust's big moment

.p60[![Tomei](./images/pesci-tomei-together.jpg)]

## If...we don't screw up.

.me[.grey[*by* **Nicholas Matsakis**]]
.left[.citation[View sl ides at `https://nikomatsakis.github.io/rusts-big-moment-2026/`]]

---

# Who am I?

.center[.p80[![Giuliani](./images/giuliani.gif)]]

???

To start, a big fan of My Cousin Vinny.

If you haven't seen it, you should. It's hilarious.

Vinny is a lawyer, come down to help his cousin, who has been falsely accused of murder and is facing the death penalty.
It's Vinny's first court case and he struggles a lot. He's ultimately saved by his girlfriend, who stole the show, winning an oscar for her performance.

Anyway, I could talk all day about My Cousin Vinny, but I don't think that's what you all are looking to hear.

---

# Who am I? (Take 2)

--

Longest serving Rust maintainer -- since 2011

--

Co-lead of the Rust language design team

--

The borrow checker is my fault (sorry not sorry)

--

Senior Principal Engineer at Amazon

---

# Rust is flying high right now

.center[.p60[!["Lucy" flying a jetpack from RustConf 2018](./images/Rust-Lucy-Art-A.svg)]]


???

From that vantage point at Amazon, I can tell you, Rust is soaring high right now.

I mean, just take a look at the platinum members of the Rust Foundation.

---

# Rust powers the cloud, big services

.center[.p80[![Platinum and Gold members of the Rust Foundation](./images/platinum-gold.png)]]

--


.arrow.abspos.top230.left290.rotate320[![Arrow](images/Arrow.png)]

.arrow.abspos.top340.left290.rotate320[![Arrow](images/Arrow.png)]

.arrow.abspos.top340.left430.rotate320[![Arrow](images/Arrow.png)]

???

To start, here are the platinum members of the Rust foundation.

You see a lot of household names. 

Right from this you can see that Rust is taking a bigger and bigger role in powering the cloud.

At AWS, Rust is being used everywhere from S3 to EC2.

Microsoft is using Rust in Azure and in their kernel-- there was a great talk by Marc Russinovich at RustConf last year about it.

From what I hear, Meta is moving more and more of their core services to Rust.

---

# Rust is used in Linux

.center[.p80[![Platinum and Gold members of the Rust Foundation](./images/platinum-gold.png)]]

--

.arrow.abspos.top500.left340.rotate320[![Arrow](images/Arrow.png)]

--

.abspos.top250.left80.rotate40.p80.bordered[![Ubuntu](images/ubuntu.png)]


--

.abspos.top200.left80.rotate340.p80.bordered[![RFL](images/RFL-stable.png)]


---

# Rust is used in Android Mobile

.center[.p80[![Platinum and Gold members of the Rust Foundation](./images/platinum-gold.png)]]

--

.arrow.abspos.top230.left420.rotate320[![Arrow](images/Arrow.png)]

--

.abspos.top180.left120.p80.bordered[![Ubuntu](images/android-move-fast.png)]


???
---

# It wasn't always this way

.center[![Announcing Rust 1.0](./images/announcing-rust-1.0.png)]

???

Rust made 1.0 in 2015. Our future was a lot less clear back then.

We had exactly one big-time production user then, Dropbox.

We had a lot of ambition, but there was so much to do. We had no IDE support. We had a fairly steep learning curve. A minimal standard library.

Go and Swift had been announced just a few years before, and each of them had backing by a big corporation, so it felt like "damn are we going to be able to pull this off?"

---

# It wasn't always this way

.center[.p60[![Them](./images/joe-and-marisa-in-deli.gif)]]

.center[<audio controls src="./images/you-know-what-i-think.mp3"></audio>]

???

All of this reminds me of a scene from My Cousin Vinny. Remember I told you that Vinny is a lawyer trying to save his cousin from false charges of murder.

There's a point where he realizes what he's up against. It's his first trial and it's the big leagues: if he screws up, his cousin is going to get the death penalty.

At this moment, his girlfriend Mona gives him a pep talk. Here, listen.

---

# StackOverflow survey from 2016

.center[.p60[![Stack overflow 2016](./images/stack-overflow-2016.png)]]

(The year before, [we were number 3](https://survey.stackoverflow.co/2015#tech-super))

???

For us, that survey was the StackOverflow survey in 2016. That year, and every year since then, Rust has toped the "most loved" category, meaning the percentage of developers using the language who want to keep using it.

You gotta understand what that means: there could be 3 people using something, but if all 3 want to keep using it, you get to 100%. So it doesn't mean you're a success.

But it does mean you've got something that people like.

---

# They come for performance...

* No GC = tight tail latency, low memory usage
* No mandatory runtime = embedded, kernel
* No undefined behavior = fewer vulnerabilities, fearless concurrency

???

And what is that something? You might think it's the usual things, fast performance or whatever. From my experience, though, that's not it.

Don't get me wrong, those things are important.

Not having a GC is what lets us get tight tail latency and low memory usage. That's why clouds are adopting Rust.

Not having a runtime is what lets us integrate into the Kernel, which is why Linux and Android are interested.

Not having UB is what lets us get really fast, really secure CLI utilities, which is why Canonical and Ubuntu are interested.

So yeah, these things are necessary. But they aren't what people love.

---

# ...they stay for reliability and versatility

> People think that Rust is all about performance. But what people love most about Rust is enums.<br>
> <br>
> &mdash; Carl Lerche

???

Actually, Carl Lerche, author of Tokio, nailed it a long time ago. He told me that what people really love about Rust is the enums. And I can attest to that. Enums-- specifically enums-- are great. But they're also just part of a larger design geared for reliability and versatility.

---

# ...they stay for reliability and versatility

> When I got to know about it, I was like: *Yeah, this is the language I've been looking for. This is the language that will just make me stop thinking about using C and Python.* **I just have to use Rust because then I can go as low as possible as high as possible.**<br>
> <br>
> &mdash; Software engineer and community organizer in Africa

???

I hear from a lot of folks who started using Rust on the *hardest part* of their system. At first they think "well, the learning curve is a pain, but it's worth it for this low-level system". But once the're past the learning curve, they find Rust is actually pretty nice. They start to use it in more and more places -- and before you know it, it's a Rust shop.

---

# Aurora DSQL makes the point

.center[.p60[[![Aurora DSQL](./images/aurora-dsql.png)](https://www.allthingsdistributed.com/2025/05/just-make-it-scale-an-aurora-dsql-story.html)]]

.footnote[
    [Link to blog post](https://www.allthingsdistributed.com/2025/05/just-make-it-scale-an-aurora-dsql-story.html)
]

???

We see this in a lot of places. One really nice version of it came out of AWS.

Aurora DSQL is one of our newly launched services. It's written 100% in Rust, but what's interesting is that it wasn't always this way.
If you read the post, you'll see that they started building just the data plane, with the control plane in Kotlin and the Postgres extensions in C.
But eventually they rewrote it to be top-to-bottom in Rust -- and that includes the internal ops web page.

I took two lessons from this. First, that the fundamentals of Rust are solid. We are delivering a great platform for building foundational software.

But also that *foundational* software is not enough. We need to aim to be usable for the full spectrum of applications.

---

# "The Rust promise"

## It takes time to learn Rust...

> I actually did not understand the borrow checker until I spent a lot of time writing Rust.

???

The pitch for Rust has traditionally been a bit of a tricky one. It's what I like to call an "eat your vegetables" pitch -- basically, invest the effort, and it'll pay off.

---

## ...but it will help you level up

> Rust is one of those languages that has just got your back. You will have a lot more sleep and you actually have to be less clever.<br>
> <br>
> &mdash; Rust consultant and open source framework developer

## ...and it will keep you and your team in sync

> Rust just lowers that bar. It's a lot easier to write correct Rust code. As a leader on the team, **I feel a lot safer when we have less experienced engineers contributing to these critical applications.**<br>
> <br>
> &mdash; Distinguished engineer working on cloud infrastructure services

???

When you're on a team, the calculus is a bit different, but it's the same basic pitch. Onboarding is a bit harder, but once people land code, it works.

This is always a tough sell, people like to get results fast, but in Rust's case, the payoff is real -- and that's why we have been seeing slow, steady growth.

The thing is, all of that is about to change.

---

# Agents are changing the game

???

Unless you've been under a rock, and even if you have been, you've probably heard a bit about AI. You've probably heard a LOT, and a lot of it is nonsense.

On the one hand, you have people telling us that coding is dead as a profession. And on the other, people say AI is useless, all hype.

Both are quite wrong. The truth is that agentic development is young. It makes a lot of mistakes and people are adding LLMs into all kinds of silly places.

But at the same time, it's a game changer. It can do tasks I never thought I would see a computer perform. And it has already changed the way a lot of people write code.

---

# LLMs turn our expectations upside down

|                                 | Human | Computer |
|---------------------------------|-------|----------|
| Tedious detail, calculations    | ❌     | ✅        |
| Ambiguous problems              | ✅     | ❌        |
| Big picture, strategic thinking | ✅     | ❌        |

???

Part of the weirdness about LLMs is that they turn our expectations upside down.

We're used to this world, where computers are great at calculations, but the only way they can handle ambiguity is to search all possibilities.

---

# LLMs turn our expectations upside down

|                                 | Human | Computer | LLM |
|---------------------------------|-------|----------|-----|
| Tedious detail, calculations    | ❌     | ✅        | ❌   |
| Ambiguous problems              | ✅     | ❌        | ✅   |
| Big picture, strategic thinking | ✅     | ❌        | ❌   |

???

LLMs are different. They actually stink at calculations. Don't ask your LLM to add numbers. But they are natives with probability, and they can attack ambiguous problems with a lot of success.

So take a look at this chart. There's many parts of programming that LLMs are not able to handle. They can't structure your code well, at least not yet, and they don't know what to do. But for many tasks they are able to automate the writing or debugging of code.

---

## ...but it will help ~~you~~ your agent level up

> Rust is one of those languages that has just got your back. You will have a lot more sleep and you actually have to be less clever.<br>
> <br>
> &mdash; Rust consultant and open source framework developer

## ...and it will keep you and your ~~team~~ agent in sync

> Rust just lowers that bar. It's a lot easier to write correct Rust code. As a leader on the team, **I feel a lot safer when we have less experienced engineers contributing to these critical applications.**<br>
> <br>
> &mdash; Distinguished engineer working on cloud infrastructure services

--

.abspos.top180.left120.p100.rotate345.bordered[![Ubuntu](images/greg-brockman-tweet.jpg)]

???

Remember this quote? I was arguing that, yeah, Rust took time to learn, but once you learned it, you could move faster. The reason was that the compiler gave you *guardrails* -- it caught mistakes early and helped you to learn.

All of those arguments apply equally well, better really, to agents. And this is part of why you are seeing a lot of people adopt Rust.

And why you have the CEO of OpenAI tweeting about it.

---

# I am not here to advocate for AI

.center[.p80[![It is a fact](./images/its-a-fact.gif)]]

???

OK, you can all breath a sigh of relief. I'm not here to advocate for AI. I'm just telling you the facts I see in terms of what's happening in the industry.

---

# Rust's big moment

.p60[![Tomei](./images/pesci-tomei-together.jpg)]

<br>

???

And this brings us back full circle.

You remember when Marisa Tomei was telling Vinny how he was gonna be really great, once he got out there?

Well I'm telling you, we are doing really great. Foundational software across the cloud, the desktop, and mobile are moving onto Rust more and more. And the biggest challenge for Rust, its learning curve, is becoming less relevant. So things are looking good, right?

--

## If...we don't screw up. <audio controls src="./images/if-you-don't-fuck-up-bg0.mp3"></audio>

???

Yes, they are -- but, well, let me play what comes next in the movie. And there it is.

---

# Challenges ahead

* Async language + ecosystem maturity
* Using the right crates and only the right crates
* Well-supported

???

Looking forward, I think we have some challenges. We're going to see lot more Rust. But it's going to put pressure on points that we already know about.





---

# Challenges ahead

???

The thing is, there's so a thing as too much of a good thing.

---

# I am here to talk about what it means for Rust

Here is what I see...

* 

---

---

# Abstractions and reliability matter more than ever

???


You might think this makes programming languages irrelevant.

---

# Fundamentals matter more than over



