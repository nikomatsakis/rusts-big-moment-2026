# Rust's Big Moment...If We Don't Screw Up — Brainstorm

## The moment

People come to Rust for one thing — performance, safety, whatever drew them in — but they stay because of the combination. Reliability, efficiency, tooling, ecosystem — individually they're nice, but together they create something different: a trusted, versatile tool that people want to bring to *every* problem. The vision doc interviews showed this over and over: "I don't want to write code in any other language but Rust." People's careers change because Rust gave them confidence to enter domains they couldn't before.

This trend is accelerating. And there's a surprise twist: the learning curve — Rust's biggest perceived liability — may actually be an advantage in the age of AI agents. The type system and borrow checker that were "hard for humans to learn" become "hard for agents to get wrong." The compiler is a built-in code reviewer that never sleeps. "If it compiles, it works" is even more valuable when the thing writing the code doesn't have domain intuition.

So yes, Rust is set up for success.

## But if we don't screw up

The danger isn't external. It's us. Rust is siloed — the project, the ecosystem, the companies using Rust, the people who want to contribute — all operating in their own worlds without good connective tissue. And there are things we've long held dear — values that got us here — where the specific *forms* those values take are now holding us back. We need to bend the curves: honor the intent behind our principles while letting go of the shapes that have become constraints.

---

## Chapter: Async — leave room for the long game, unblock the short term

- async fn is more powerful than others
- async fn is really limited
- the "just add async" vision
- async fn doesn't compose the way we expect
- challenge:




### Status quo

Async Rust has fueled massive adoption for network services. But it's widely seen as qualitatively harder than sync Rust — not just more complex, but a different kind of challenge. The problem isn't async concepts. The problem is that patterns which work in sync Rust don't transfer: traits, closures, recursion, scoped patterns, drop — each breaks in async in its own way, and the compiler doesn't guide you to the workarounds.

The challenge is that async covers so damn many things. We've been making slow but steady progress on the language, but the instinct to design the complete solution before shipping anything means features sit for years. The ecosystem is waiting — Tower remains on 0.x because it can't express the APIs it needs. The maintainers want to ship a cleaner design, but they're blocked on language features.

### Shiny future

The "Just add async" roadmap is about carving out pragmatic compromises. Ship the things that unblock the ecosystem now (RTN, AFIDT, `.box` notation, ergonomic ref-counting) while the harder problems (structured concurrency, async drop, streams) continue to develop. Server-first, but not server-only — we're not closing doors, we're opening the first one.

This is where we need to gently push back on a deeply held belief. Mara Bos wrote a classic post: "Rust is not a company." And the logic is right — Rust is bottom-up, project goals are the union of contributor goals, management exists to create space for contributors to thrive. But pure bottom-up has limits. Focusing on your own interests and desires only gets you so far. To really innovate, you have to look at what *others* need too. "Without people who have it as their personal goal to make something happen, things just don't happen" — Mara says this like it's fine. But when the things that need to happen are this important, it's not fine. We need to leave room for the long game while we unblock in the short term. Too often, perfect is the enemy of good, and we get stuck.

---

## Chapter: Sustainability & funding — desiloing Rust

### Status quo

Async's hard problems — structured concurrency, async drop, the trait solver work that underpins everything — need years of sustained, focused effort. They're not the kind of thing that gets done in volunteer bursts. And this is true across Rust, not just async.

But the deeper problem is that Rust is siloed. The project, the ecosystem, the companies using Rust, the people who want to contribute — they're all operating in their own worlds, without good connective tissue between them.

- **Companies** use Rust heavily but have no clear path to invest back — they don't know what the project needs, and the project doesn't know what they need.
- **Users** hit pain points (async complexity, crate discovery, missing batteries) but there's no structured way for that to flow back into priorities.
- **The project** sets direction bottom-up, which gives you great prioritization for free — but it also means you optimize for the people already here and stop looking outward. Rust has always learned the most from the people who "almost liked it." The borrow checker got better because of them. Error messages got better because of them. The risk of success is that we turn inward.
- **Would-be contributors** show up with energy but can struggle to find where they fit — not because anyone's hostile, but because the silos make it hard to connect intent with opportunity.

The power of bottom-up is real. But pure bottom-up has limits. Mara Bos wrote a classic post: "Rust is not a company." And the logic is right — project goals are the union of contributor goals, management exists to create space. But focusing only on your own interests and desires only gets you so far. To really innovate, you have to look at what *others* need too.

### Shiny future

Desiloing means building connective tissue.

**Project goals and the vision doc** are tackling the alignment problem — how the project communicates its priorities outward, and how it listens. Not top-down mandates, but a shared picture of where we're going that everyone — contributors, companies, users — can see and respond to.

**Technical roadmaps** like "Just add async" give concrete shape to the priorities. A roadmap says: here are the specific goals, here's how they connect, here's the order. It turns alignment into action — and gives companies and funders something concrete to point at.

**Funding** connects the money to the work. The Foundation's Rust Maintainer Fund and the RustNL Maintainers Team are already in motion. But there's a new idea I plan to propose: **directed funding for roadmaps**. People and companies can fund a specific roadmap — "Just add async," or whatever matters to them — and that money drives the work forward, with a percentage off the top going to maintainers who do the review and design guidance work. This is the desilo in action: users signal what matters by funding it, the project has already vetted the roadmap, and both contributors and maintainers are sustained.

---

## The pivot

But this is all focused on the project. And the reality is that the experience of Rust is way bigger than that. *And that's by design.* The small standard library, the rich ecosystem, the extensibility — these are features, not bugs. So how do we scale the ecosystem to match the moment?

---

## Chapter: The ecosystem — battery packs, working groups, raising the floor

### Status quo

Rust's small standard library and rich crates.io ecosystem are strengths. Extensibility — traits, macros, the whole system — is a core part of how Rust achieves versatility. We don't want to change that.

But people need to know what to pick. The vision doc interviews are full of this pain: "The crates to use are sort of undiscoverable. There's a layer of tacit knowledge." The Rust org has been reluctant to bless crates, and for good reason. But the problem is real, and ignoring it because the solution is hard isn't working.

### Shiny future

**Battery packs.** A collection of functionality, publishable by anyone. At first it doesn't seem like much — but the key idea is that it gives us a way to define groups of crates, a curated starting point, while preserving the small stdlib and the extensible focus that has served Rust so well. It's not the Rust project picking winners. It's a mechanism for the community to organize recommendations.

**The Rust Commercial Network.** Building on the success of the Safety Critical Consortium, this brings together companies and users who are building things in Rust. Not the Rust project talking to itself — the ecosystem talking to the project.

**User Working Groups** organized around *use cases*, not language features. An Async User Working Group (name TBD) composed of people building network services. Their goal: define a battery pack of crates, a reference architecture for their domain. This is different from what we've done before — it's not the Rust project picking winners, and it's not random individuals hoping someone notices their crate. It's users organizing around their needs and curating what works. New contenders have a forum to be evaluated by the people who'd actually use them.

**Raising the floor.** The current async ecosystem is a patchwork of pre-0.1 crates, maintained by heroic individuals, often without security audits, without the polish and reliability that companies need. Take the battery pack that the working group defines and raise it to production grade. Stable releases, not perpetual 0.x. Security best practices and audits. Documentation that meets the bar. Sustained maintenance, not volunteer heroics. And do it without burning everybody out.

The Commercial Network provides the money. The working group provides the direction. The battery pack provides the scope.

**The Foundation as ecosystem infrastructure.** A family of support services:

- Security staff that help educate and make it easier than ever for crate maintainers to follow best practices.
- The Rust Innovation Lab providing a legal entity for projects that need one.
- Ecosystem funding to get money to the crates and maintainers that working groups identify as essential.

Right now, if you maintain a critical Rust crate, you're on your own. The Foundation's role is to wrap support services around the ecosystem so maintainers can focus on the code. Rust can't scale by asking more of individuals. It scales by building shared infrastructure that makes each person more effective and more sustainable.

---

## Close: building the cycle

How can we build stronger bridges between the Rust project, the ecosystem, and Rust users? How can we build a beneficial cycle, where we support, inform, and influence each other?

That's what all of this is going for. Each piece feeds the next:

- **Users** tell us what they need — through working groups, the Commercial Network, the vision doc, and by showing up with energy we actually support.
- **The project** sets priorities based on that — through project goals, technical roadmaps, and a culture that values pragmatic progress.
- **Funding** flows to make it happen — directed roadmap funding, maintainer funds, Foundation support services.
- **The ecosystem** raises its floor — battery packs, reference architectures, production-grade crates.
- **Users benefit**, and the cycle repeats.

The Rust project, the ecosystem, and Rust's users — right now these operate too independently. The vision is a cycle where each strengthens the others. That's how Rust seizes this moment. That's how we don't screw up.
