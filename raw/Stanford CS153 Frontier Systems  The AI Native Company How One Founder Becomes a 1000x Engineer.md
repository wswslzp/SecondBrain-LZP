---
title: "Stanford CS153 Frontier Systems | The AI Native Company: How One Founder Becomes a 1000x Engineer"
source: "https://www.youtube.com/watch?v=Lri2LNYtERM&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=5"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=Lri2LNYtERM)

## Transcript

**0:09** · We are super lucky to have with us today, Garry Tan and Diana Hu from YC.

**0:14** · \[APPLAUSE\] Before we dive in, I'm going to do a couple of minutes of warm up.

**0:28** · This is a really special lecture for a couple of reasons.

**0:33** · One, this class, CS 153, which, as you know, Mike and I started teaching four years ago, which was security at scale, small group, 50 people, was inspired by is a composite of several different classes that have been taught at Stanford by Silicon Valley leaders.

**0:54** · And when I was an undergrad, sophomore year, Peter Thiel, taught the first version of how to start zero to one.

**1:04** · It was CS 183.

**1:05** · How to start a startup, and that became the book Zero to One.

**1:09** · The following year, YC taught a version of that class that Sam put together.

**1:16** · And Gary was at YC at the time, or had just initialized.

**1:22** · And so those are the spiritual descendants of this class.

**1:25** · And then there's CS 43, which was Terry Winograd's class.

**1:27** · We've talked about those Computers and the Open Society, which was the first freshman seminar I took.

**1:32** · And so over the years, we've tried to take the best parts of all those classes and bring it together in 153.

**1:39** · But it's just really poetic to have Gary back, because based on many of the things Gary learned here at Stanford, he went out and took the spirit of Stanford out to Silicon Valley.

**1:51** · And to have him back and be able to talk about all of his work, and now with Diana helping to update some of the YC philosophy that we're going to talk about, it's a close the loop moment.

**2:07** · So thank you guys for coming back.

**2:08** · It's really appreciated.

**2:10** · Thanks for having us.

**2:11** · Oh, no.

**2:11** · This is the fun part.

**2:12** · So I'm going to let you-- before we dive in, I'd like to give a couple of minutes of context on why this is an important lecture for you guys.

**2:23** · So as you know, 153 is a systems class.

**2:26** · You've heard up and down the stack from landpower shell and energy like Scott Nolan at General Matter to the chip layer.

**2:34** · We had Jensen last week.

**2:37** · There's a full rewrite of systems going on to unblock bottlenecks on frontier progress right in the world.

**2:43** · One of those things that we need to unblock bottlenecks on is capital.

**2:48** · And as you heard from Ben Horowitz a few weeks ago, Mark and Ben came up with a system to try and scale the deployment of capital in Silicon Valley over 10 years ago and are now thinking through how to update that system.

**3:01** · And YC is very similar, and I'd like to connect the dots between lecture 1, where we talked about the compute bottleneck.

**3:09** · And if you remember, one of the reasons I talked about how compute is a bottleneck today is because we're in the pre-standardization of compute era.

**3:19** · And if you zoom back to the Industrial Revolution, one of the things that allowed this very important thing called electricity to become a stable resource, a piece of infrastructure that lots of people could develop on and access, was the development of standards.

**3:35** · One of them was AC, DC, and then we had institutions enforce those standards.

**3:41** · One of those institutions was utility companies that developed a grid to coordinate the production, demand, and supply of electricity.

**3:50** · In the capital world, when I showed up in Silicon Valley in 2011, we were in the pre-standardization of venture capital.

**4:02** · It was a complete mess.

**4:03** · There were a bunch of VC firms, who were all trying to do their own deals and figure out how to negotiate with founders and so on.

**4:09** · And into that mess stepped Paul Graham and Jessica Livingston and introduced a new standard for how capital should be allocated, and that was called The SAFE.

**4:20** · How many people have heard of The SAFE?

**4:22** · There we go.

**4:23** · OK, so this is living proof.

**4:25** · At the time, it wasn't legible to me how profound The SAFE was.

**4:29** · It was basically a two page legal document that YC put up online and said, here's how we're going to fund startups.

**4:35** · It's called The SAFE, Simple Agreement for Future Equity.

**4:38** · And at the time I was like, I was a student here, and I saw it.

**4:42** · I was like, OK, whatever, legal document.

**4:44** · In hindsight now, it's so obvious to many of us in the ecosystem that that was a pivotal moment in the history of Silicon Valley, where the YC team saw what was going on and realized-- at that point, there was another-- We were living through the rise of the cloud and SaaS era.

**5:03** · AWS and GCP and so on had started to make compute quite accessible, and that had reduced the marginal cost of innovation in the valley.

**5:11** · But venture capital still hadn't caught up with that era.

**5:15** · It didn't cost much to produce software, and so there was a moment of abundance we knew we were going to go through back then, but to get capital out to innovators like you guys, there was a venture capital bottleneck at that time, which now seems cute given the numbers we're living through today.

**5:33** · But at that time, it really did feel like it was hard to get time with VCs and get good deals and so on.

**5:39** · And so when into that mess, stepped YC and published The SAFE, it became a standard for how early stage startups were going to be funded.

**5:48** · And then by enforcing it, YC became an institution that standardized seed stage funding.

**5:55** · And the arc of Silicon Valley would have looked very different without that one document.

**6:02** · And so as it's very obvious to me at AMP, we live through this every day on the compute side.

**6:09** · We might even at some point open source a standard agreement for future compute, something like that, but, we look to what YC has done as somewhat of a spiritual ancestor for the work we're doing.

**6:22** · And so it's very cool to have you guys back.

**6:25** · Within that context, I hope this gives you a little bit connect the dots moment for why lecture 1 and this lecture are parallels.

**6:33** · And systems design is not just something you do in engineering.

**6:36** · You can do it in any domain you're in to try and accelerate the pace of progress and unblock bottlenecks.

**6:43** · Is this making sense to people?

**6:46** · Can I get a yes?

**6:47** · Yes.

**6:48** · Come on.

**6:48** · It's spring quarter, guys.

**6:49** · Can I get a yes?

**6:50** · Yes.

**6:51** · Yes.

**6:51** · Thank you.

**6:52** · All right, with that over to you guys.

**6:54** · Thank you so much for coming.

**6:55** · Why don't we start with, introductions about yourself, how you got here, and then you can dive in.

**6:59** · Absolutely.

**7:00** · Hey, everyone.

**7:01** · I'm Garry Tan.

**7:02** · I was a Stanford class of '03.

**7:05** · I took a lot of classes in here.

**7:06** · I fell asleep in this lecture hall a great many times.

**7:09** · Thank you so much for bringing me back.

**7:12** · It's great to be back to the farm.

**7:13** · And every time I come back to the farm, I'm shocked that I get to be up here because I feel like I just blinked and I was in your seat.

**7:23** · And zooming out, that's actually desperately what I want for every single one of you is, what we were talking about here is there's a grand shift.

**7:33** · All those historical things literally, the new standards are being established right now, and there are people in this room who are actually going to be the people who establish those things.

**7:43** · And then Diana and I and the team at YC, we're hoping that we're-- The SAFE was a legal instrument, what we're going to talk about today is actually code.

**7:52** · And not just code, Markdown is code.

**7:56** · Literally the new, and we're going to link it all the way over to what a startup is, what people in this room are going to be spending your entire lives building the railroad for the rest of society over.

**8:09** · For our generation, we were building the internet and we were building mobile phones and we were building social networks, and your generation is going to create the cognitive layer for all of society.

**8:23** · And what we're talking about is just stuff that-- these are our hunches even.

**8:29** · You guys are going to go and actually build it.

**8:31** · And so thank you for bringing us back.

**8:34** · Diana, do you want to introduce yourself.

**8:37** · Thank you for having us.

**8:38** · I'm Diana.

**8:38** · I'm one of the general partners at YC, and we are living through an exciting time, as you all know with what all the capabilities with AI is unlocking.

**8:49** · And we have a lot of interesting things to share for all of you in this lecture.

**8:54** · We've seen unprecedented growth from a lot of the companies in our portfolio that have gone from zero to tens of millions in dollars in revenue in one year, which was impossible before within a year.

**9:06** · It would have taken four or five years to get to basically series B level traction.

**9:10** · And hundreds of millions of dollars in capital.

**9:14** · It's just a different moment.

**9:15** · Different world.

**9:16** · And we're going to tell you how these founders have done it, and we're going to go through really what it means to build a company now to be AI native.

**9:24** · So with that, it's a pretty packed lecture, so we're going to just get right in.

**9:29** · AI is going to change the unit of production.

**9:31** · When I was sitting in your seat, I knew that I needed to raise money, I needed to hire a lot of people.

**9:37** · This was about me learning how create a new cult.

**9:42** · Palantir was like that, YC, ultimately, it's a religion.

**9:47** · This is something that we believe that nobody else believes yet.

**9:51** · That is still true.

**9:52** · All the things we're going to talk about a team is still valuable, human beings are still valuable, but it's not going to be just humans.

**9:59** · It's going to be humans in concert with agents, with memory, and evals and a customer loop.

**10:04** · So by the end of this talk, you're going to understand what we're talking about.

**10:07** · Right now, it sounds a bunch of buzzwords.

**10:09** · We don't want this to be a bunch of buzzwords.

**10:10** · We want you to take these ideas and actually implement them and remake society, and we think you will do that.

**10:18** · Let's see.

**10:21** · I'll tell you my personal story.

**10:23** · In 2008, I got into YC.

**10:25** · We raised about $4 million.

**10:26** · I hired 10 people.

**10:28** · We created Posterous, which is a dead simple blog platform, and we sold that to Twitter three years later for $20 million.

**10:37** · And honestly, I was able to create all the software we made over two years with 10 people and all that capital, but me with the $200 a month Claude code Max plan.

**10:49** · And anyone in this room could do that. and?

**10:51** · It didn't take two years.

**10:53** · It took about five days.

**10:55** · So I experienced that speed up.

**10:57** · Recently, I created Gary's List and then that caused me to create GStack.

**11:02** · We're going to talk about what those things are.

**11:04** · But as Diana said, we're in 2026 now, and so a six-person team can hit 10 million in revenue with just the things that we're talking about today.

**11:15** · And a lot of you already this, so it might be review, but for some of you, this is some astonishing good news.

**11:23** · So let's talk about GStack.

**11:24** · This is something that I discovered.

**11:26** · Late last year, I saw Steve Yaghi, a famous blogger and engineer.

**11:31** · I believe he was an early Googler.

**11:33** · He wrote that "people using AI coding agents are 10 to 100x more productive as engineers using Cursor in chat today."

**11:41** · And then at Anthropic there are about 1000x as productive as Googlers were in 2005.

**11:47** · And I was like, what is going on?

**11:49** · And so I had to try it.

**11:50** · I opened Claude code, and, of course, I ended up writing around a million lines of code in, which is really, really crazy.

**12:00** · Let's see.

**12:01** · Let's just talk about the things that you might read on the internet.

**12:05** · These are all wrong.

**12:06** · It's not just AI slop.

**12:08** · Actually, yes, LLMs are very verbose and some of it is boilerplate, but when you create your own software factory, this is actually what you're fighting.

**12:18** · This is actually what you're preventing from happening by default.

**12:22** · Yes, there are hallucinations.

**12:24** · Yes, those are actually the things that we're trying to control.

**12:27** · Can you make demo code very quickly?

**12:29** · Yes, but how do you get it to production?

**12:32** · Well, you actually have to get to 100%, or 80% to 90% test coverage.

**12:36** · That's actually one of the main reasons why plan dash, en dash review as a skill exists.

**12:43** · That's the number one with a bullet skill that I use about 20 times a day to get to 80%, 90% test coverage so that I am not shipping slop.

**12:52** · I'm shipping something that is actually literally usable and that I rely on every day in production.

**12:58** · This is very controversial.

**12:59** · I've gotten in trouble over this.

**13:01** · I apologize to people for who took my trolling as serious.

**13:06** · Is LOC gamble and something that might be not usable?

**13:12** · Actually, yes.

**13:13** · LOC on its own can be wrong, but on the other hand, if you have tests, if the real measure of whether or not these things work is actually look down and does it work for you?

**13:23** · Does it work for your customers?

**13:25** · Are people actually paying?

**13:26** · That's actually the true metric.

**13:28** · Look, it might be a garbage metric, but I might argue that in the age of-- there's nothing in Claude Code or the model or the harness, or GStack, or any of these things that tell the model to write as many lines of code as possible.

**13:41** · If anything, the reverse is probably true.

**13:43** · We're trying to write as dense and concise code as possible to serve the purpose.

**13:49** · And I think that that's something that's quite important to talk about.

**13:53** · This is my experience.

**13:54** · I got to 87,000 stars.

**13:57** · My other project, GBrain, is 13,000 stars.

**14:00** · So I mean, basically for someone who was not coding at all in December of last year, I have more than 100,000 GitHub stars and about 15,000 people use it every single day.

**14:11** · Hundreds of thousands of skill invocations.

**14:14** · And so I don't know.

**14:15** · This is what I'm learning.

**14:18** · Last year, probably before Claude 4.5-- Opus 4.5 came out, we were talking about Copilot.

**14:26** · Today, I think we're really talking about a software factory.

**14:29** · And so if you use GStack, you'll understand this is actually what's happening.

**14:34** · What I discovered is that-- and this is more or less by accident, as I was writing half a million lines of code for recreating my startup that I created two other times previously, but doing it in about five days or during the course of several months creating GStack, I realized that it's actually really useful to pull out specific personas of what is already in the latent space.

**15:02** · And so the most famous skill that a lot of people use that it's actually interestingly, a distillation of what we already do at Y Combinator when we have 15 partners, 16 partners at YC, when you have an idea and you're doing office hours with us, we're mainly asking questions about what's the problem, who's the customer, how do you know that, and then what are we building.

**15:25** · And so that's what the office hours skill is.

**15:27** · We basically took actually three or four months of transcripts across thousands of conversations, distilled that into something very, very potent.

**15:37** · And then I had to distill that down by 90%.

**15:40** · And then that's what is shipped in open source/office hours in GStack.

**15:45** · But as I went, it turns out there are lots of different things that I like to use to actually make it easier and far better-- the product that you can create with coding agents can be better if you're literally pulling out the latent space for a particular vibe and thing that you're trying to go for.

**16:05** · So plan-ceo-review, for instance.

**16:07** · My favorite thing about that is it asks the question-- OK, well, it has context.

**16:11** · It knows what you're trying to build-- What is the 10x version of that?

**16:15** · What is the platonic ideal of that?

**16:18** · And so when I was a product manager at both Palantir and Microsoft and a founder for my startups, when I thought about product, that's what I wanted to do.

**16:28** · I wanted to figure out, what is the perfect manifestation of the thing that we could build.

**16:32** · And then when I build-- what I'm building right now needs to be on a roadmap that is a straight line from where we want to go, from where we are now.

**16:42** · And then the other thing that I discovered as we were doing this stuff is that you can boil the ocean.

**16:47** · Who here remembers that term, boil the ocean?

**16:51** · If you go and work someplace, you're going to go into a meeting where people start saying things that are a little too scary, and then immediately people in that room are going to say, whoa, whoa, whoa, let's not boil the ocean.

**17:02** · And my response to that, based on my experience with coding agents and what's happening right now, is actually, let's boil the ocean.

**17:09** · The things that you can do, like basically you sitting in front of one of these terminals, you can do the work of about 500 to 1,000 people.

**17:18** · And if that's true, then all of the expectations that we currently have in society around what a founder can do, what a company can do, what a small team can do, what you can do sitting in front of a computer, they're actually 1,000x wrong.

**17:33** · And actually what's funny is that's baked into the model weights.

**17:36** · Who here has asked Claude Code before, how long is this going to take?

**17:40** · And it'll give you, oh, it's going to take about three weeks to code all of this stuff, and then you press approve on the plan and then literally it's done in about an hour.

**17:50** · So, I mean, all of us have experienced that.

**17:53** · The models themselves have not caught up to this new reality that we can actually boil the ocean.

**17:58** · So anyway, use GStack.

**18:00** · There's a lot of stuff in there.

**18:02** · We have very little time, so I feel like I need to skip ahead.

**18:05** · GStack was basically my understanding of building open source and putting it out there, and I'm still working on it.

**18:12** · But the new thing that I've been working that everyone at YC has been just completely immersed in is OpenClaw and Hermes agent, and they're actually teaching us brand new primitives on how to think about code, how to think about markdown, and how those things work together to do real work.

**18:33** · And so this is somewhat obvious, but I have to say it because I keep-- like anytime I would build an agentic system and it broke, it would every single time break because something was wrong about what I was trying to do.

**18:51** · I was either trying to do deterministic work, things that should be in code in my markdown skill, or I was trying to do latent stuff, actually the things that my agent should be doing using the LLM in the code.

**19:08** · And a concrete example, for instance, is we spend a lot of time trying to curate the experience of people at YC events.

**19:17** · Anyone actually can just use Claude.

**19:20** · You don't even need Claude Code.

**19:21** · You could use ChatGPT.

**19:23** · Put in bios of eight people coming to your dinner party and you can have it go and Google that person, run a dossier and then figure out who should sit next to who.

**19:34** · That's very easy to do in latent space, but try to do that with an 800-person dinner party or with the 6,000 people that are coming to start up school.

**19:45** · You can't do it.

**19:46** · The model's not big enough.

**19:47** · It hallucinates.

**19:49** · It doesn't work.

**19:50** · And so what do you do?

**19:51** · Well, that's the perfect example of you need to make the latent space work with the deterministic space.

**19:59** · And so how do you actually do that?

**20:03** · The toy example here is like, well, what is a skill?

**20:06** · Who here has played with a skill or used a skill file?

**20:10** · So skill file is actually-- I mean, it sounds facile.

**20:13** · If you go on Twitter and believe the haters, they're going to say like, ha, ha, it's just a bunch of markdown files.

**20:19** · Who cares?

**20:20** · But the big difference now with LLMs is like you can actually do real work with this stuff.

**20:27** · The thing that keeps coming back over and over again is that you can do real investigations about it.

**20:33** · And so basically what is a skill?

**20:37** · It's basically just a runbook.

**20:40** · If you've ever thrown an event and you need to throw that event over and over again, what do you do?

**20:46** · You go into your notebook and you just write down, well, one, we need to do to secure a venue.

**20:50** · Two, let's figure out who should come.

**20:52** · It's just this-- any human being or agent should be able to look at it and say, OK, after I read 1, 2, 3, 4, 5, 6, however many steps it is, maybe it's branching.

**21:02** · It could be very complicated, actually.

**21:04** · Do I know how to do that thing?

**21:08** · This is a very simple concept, but the really cool thing is that you can actually make it call code.

**21:15** · And that's what I find myself doing inside of OpenClaw and Hermes all the time.

**21:20** · And this is where it links to what you guys are doing as founders.

**21:24** · And this is the pattern that we're seeing inside every YC founder or inside every YC startup now.

**21:30** · We're not picking up the phone and doing it ourselves, just like we're not opening VS code and writing code ourselves.

**21:36** · Claude Code revolutionized how we write code and we don't open like-- Me, Karpathy, and tons of other people in this room probably don't open the editor at all.

**21:46** · The same thing is happening with OpenClaw and Hermes agent.

**21:51** · So all non-technical or process oriented things in knowledge work are now-- you can do it in OpenClaw.

**21:58** · Like you can have Twilio call someone.

**22:01** · You can use Gemini Live to actually book a thing or buy a thing or here's my credit card, all of these things.

**22:09** · Who he remembers that Google demo where they stood up on one of their conferences and they're like, so proud, Gemini can now call, and get you an appointment?

**22:18** · And then they never ship that thing.

**22:20** · You don't need to wait for them to ship that anymore because you can have that yourself.

**22:23** · And that's the most empowering thing.

**22:24** · So code is code.

**22:27** · The concrete example I have is like who here uses OpenClaw?

**22:30** · And it always, for some reason thinks that you're in Greenwich in the UK.

**22:37** · And so this is a perfect example of I had to write code in TypeScript.

**22:42** · It's context-now.mjs and I have tests for it, and then I have it built into my system so that I don't rely on the latent space to do it.

**22:52** · It just tells me, here's the time.

**22:54** · And then actually, here's the things that are coming up.

**22:56** · And if I don't do that, left to its own devices, the latent space will be like, oh yeah, it's 3:00 AM.

**23:03** · Why are you still up?

**23:04** · And it's like, what are you talking about?

**23:05** · It's the afternoon right now.

**23:08** · The next important thing that we discovered, anyone who has used Claude Code a lot, has probably seen this error message at the top of Claude saying, you're Claude.md is 40,000 tokens or 40,000 lines or something like that.

**23:21** · And then you Google around and you're like, OK, well, how do I fix that?

**23:24** · Well, how you fix it is actually a resolver.

**23:27** · So a resolver is actually really important because it's amazing how much you have to spend time getting this right.

**23:37** · Claude.md is a whole bunch of instructions on how to do things that you develop.

**23:41** · You got mad that Claude Code did this or that, or wrote the changelog in a certain way, and you say, hey, I don't want it like that.

**23:48** · Don't do it like that anymore.

**23:49** · Well, turning it into a proper resolver means you take that instruction and it's like anytime you have to write to the changelog, load changelog.md.

**23:57** · And so suddenly you don't need that in your context.

**24:02** · The agent itself knows, oh, OK, here's this master directory of all the things I know how to do.

**24:08** · And I need to load the instruction only when I actually need it.

**24:13** · It sounds so simple, but it's kind of obvious.

**24:15** · But this is actually the core of having a really great agent.

**24:19** · Actually, it's having a resolver.

**24:21** · When I need to check signatures, I want it to actually go to my executive assistant skill, who is a particular person like, well, I needed to look up in my brain repo how to do that.

**24:32** · And I have a skill, a specific code path.

**24:35** · And it's not a code path.

**24:36** · It's like a markdown code path.

**24:38** · I call it a skill pack.

**24:40** · I have a skill pack specifically for that thing.

**24:42** · I did it once, and then that's where-- here's another primitive that I discovered that I find myself doing about 20 times a day when I'm using OpenClaw or Hermes agent.

**24:53** · It's called Skillify.

**24:54** · So you're going up one level in abstraction.

**24:59** · So let's use one of these examples.

**25:02** · Save this article.

**25:03** · Well, I do that once.

**25:04** · I look at the input, I look at the output, I get the agent to do exactly what I want.

**25:09** · And then once I have it in a position where I like it, I actually tell it skillify.

**25:14** · And then on the right, that's actually what the skill says.

**25:18** · And this is a summarized version of it.

**25:20** · I have an article on X about it if you want to see all the full details.

**25:24** · But long story short, you write the skill, you write the code.

**25:28** · And then here's the part that is actually broken in Hermes agent.

**25:31** · I think they're about to fix this, actually, but it's not enough to do it once.

**25:37** · You actually need to test it.

**25:39** · You have to-- if you work in a finance organization, think about all the people, like 10% or 20% of people who work in some of these organizations just do compliance.

**25:48** · And you're like, what are all these people doing?

**25:50** · Actually, in an agentic system, this is exactly the illustration of that.

**25:54** · Look at all these steps.

**25:56** · Writing the skill and writing the code is only 2 out of the 10 steps.

**25:59** · All of the rest of it is making sure that this messy system that is more like a human system than perfect, beautiful beam of light code can still work and do work that you want.

**26:11** · OK.

**26:12** · So you did something in Claude Code, or you did something in OpenClaw.

**26:17** · You made it work.

**26:18** · Then you say, skillify.

**26:19** · What does it actually do?

**26:20** · Well, you have to write unit tests for the actual code.

**26:22** · You have to write LLM evals for the skill file.

**26:26** · Then you have to write an integration test.

**26:28** · Then you have to make sure that there's a resolver trigger, an agent.md.

**26:31** · And then you have to test that.

**26:33** · You need an LLM as judge eval to make sure that when that thing comes up, it's broad enough that it actually gets triggered.

**26:41** · And then there's this other concept that you can look up in GBrain called check resolvable that is very important.

**26:46** · You want it to be DRY, Don't Repeat Yourself.

**26:48** · Otherwise, you end up with 1,000 skills that do all the same thing.

**26:52** · You need an end to end smoke test and then ultimately you need a schema.

**26:55** · You need to figure out where does this live in my memory and my repo.

**26:59** · So we're going really fast, but that's why memory is actually really important.

**27:04** · And so my next project that is out now that I'm working on is called Gbrain.

**27:09** · It's actually a three-layer memory system built on top of what Karpathy already talked about with his Knowledge Wiki.

**27:14** · So I started with the Knowledge Wiki as well.

**27:16** · And then it started falling over because it just uses grep.

**27:20** · And so I had to add vector search, RRF fusion, backlinks, I added a graph database.

**27:28** · It's a type knowledge graph.

**27:30** · I'm about to add an epistemology systems so that we know that things are-- there are hunches or beliefs by specific people or world knowledge.

**27:42** · And I want to track when things-- what's funny about-- maybe this is very specific to me.

**27:47** · I'm super fascinated with the idea that people in this room are going to go on to-- your journey as a founder, literally is that you have a hunch.

**27:57** · You think that the world needs x, nobody believes that yet.

**28:01** · But I want my knowledge system to be able to track like, oh, well, I heard so-and-so, this person in this room, this person in a red shirt right here, he tweeted this.

**28:09** · And nobody else believed that yet.

**28:11** · But he's going to go and spend like a year, two years, five years proving it correct.

**28:16** · And then if my GBrain is actually working properly, it's going to spot that.

**28:20** · It's going to be like, oh, actually here's at Stanford, there was this one person who believed x.

**28:26** · And then they manifested it.

**28:27** · And so I don't know.

**28:28** · For me, philosophically, I'm fascinated by knowledge systems truly capturing what's going on.

**28:34** · And that's what-- I think about this.

**28:37** · I'm just building software for myself.

**28:38** · This is the stuff that we have to think about.

**28:41** · And if you spot in my voice like, I'm excited about this because I'm building again and I'm building for myself.

**28:51** · And then we're open sourcing this stuff because we want all of you to actually be able to do it.

**28:56** · I feel like I need to expand on-- one of the things that GBrain does is like it's a very specific schema for my use case.

**29:04** · But one of the last things I need to do before I go to V1, hopefully in the next couple weeks, is I actually need to make fully dynamic ontology, which is a great buzzword that I've learned from Palantir back in the day.

**29:18** · Right now the schema is built for me, but there's no reason why it can't be built for you.

**29:23** · Whether you're a researcher, whether you're a journalist, whether you're a politician, each person is going to have a different schema.

**29:29** · We need to support all of those things.

**29:31** · So zooming out, I'm about to pass it over to Diana to take it all the way home.

**29:35** · I gave you the primitives that we're learning literally week by week.

**29:39** · I didn't even know about Skillify until it flew out of my hands at 3:00 AM using OpenClaw.

**29:46** · And then I put it on X, and that went viral.

**29:50** · I'm just learning as I go.

**29:51** · I'm not an expert.

**29:52** · Sometimes it's like my favorite line from Alan Watts, if you guys know Alan Watts is he goes to a room like this.

**30:00** · He used to give lectures and he would say, I am not a guru.

**30:04** · I am just an entertainer.

**30:06** · So I want to pass this over.

**30:11** · We're talking about the agentic company.

**30:13** · Diana's going to tell you a lot more about it.

**30:15** · But the concepts that I just talked about, one of the weirder things we realized is these actually map to the company.

**30:22** · So a skill is a squishy human being who's an employee who has a capability.

**30:28** · A resolver is the org chart.

**30:30** · Who Handles what?

**30:31** · How does it happen?

**30:33** · The filing rules, where it goes in the brain is the internal process.

**30:37** · Where does the information live?

**30:39** · Check resolvable is this thing that makes sure that the resolver works for the set of things that you want to get done.

**30:45** · And that's like audit and compliance.

**30:46** · When I was sitting in your seat, I had no idea why so many people in so many human organizations had to spend so much time on audit and compliance.

**30:55** · But now, at age 45, building a lot of agentic systems and looking at Skillify and how much time I spend just trying to make the things like friggin' work, I actually understand now.

**31:07** · Human systems are very messy, and that's what check resolvable is.

**31:10** · And in the end, the funniest thing is what a trigger eval is, you would think, oh, well, of course it's in the trigger.

**31:16** · It's in the result-- in agents.md it should just work.

**31:19** · But no, you even have to check that.

**31:21** · That itself is its own latent space squishy operation that you have to check.

**31:26** · And in an org those are performance reviews.

**31:30** · So with that, I want to hand this over to Diana to take us to the actual applied portion that will actually help you.

**31:39** · So I think a couple of things that Garry went over are a lot of the details on how you could implement it with a lot of the building blocks.

**31:48** · And if we really backtrack and step now a couple layers up, one of the key concepts of building an AI native company is you need to change fundamentally how companies are run.

**32:00** · I think normally today, pre AI, companies are basically run as a open loop.

**32:06** · People make decisions and a lot of those decisions take a while to come back and is basically lossy.

**32:14** · There's no concrete tight feedback loop.

**32:16** · If a lot of you have studied control systems-- how many of you have taken control systems and know the difference between open loops and closed loops?

**32:24** · The problem with open loop systems is as error accumulates, the systems become more erroneous, and then it goes off the rails, as opposed to let's say, a closed loop system.

**32:34** · Very famous closed loop systems could be like PID controllers.

**32:38** · You have a tight feedback loop into the controller so that a lot of the error stays within check.

**32:45** · And this is how a lot of robotic systems work a lot better.

**32:48** · So we basically now with AI, have the capability to take a lot of these lossy information of how companies run into becoming a closed loop system.

**32:58** · So what that means fundamentally today for old-school companies, information lives in people's head in an org.

**33:07** · They have a lot of side conversations, DMs in Slack.

**33:11** · They have a lot of meeting notes that are not written.

**33:14** · They have just vibes, how they feel about a particular decision and all very lossy.

**33:20** · This is basically how decision in companies are made.

**33:23** · And now the ability is to change all of that into a closed loop system where you tie these agents that Garry described and how to implement it into basically the fabric of how you make decisions for a company.

**33:37** · So the idea is that you would have an agent like a Hermes or OpenClaw embedded into all the decision making.

**33:43** · And what it means the agent needs to have read access to every single artifact that the company produces.

**33:49** · So for some of you that might be working on some projects in school, you could have a small version of this.

**33:54** · You could have an agent that basically connects to your GitHub codebase, connects to your Discord, and even start recording all the meetings you have with your teammates as you make progress.

**34:05** · And as you get all these contexts, the agent can then suggest what are the best next items to work on, or bug fixes.

**34:14** · And put it in your GBrain.

**34:16** · Put it in your GBrain and the memory context.

**34:18** · And this is how you start embedding this agentic system that starts building the system and self-healing.

**34:23** · So that's one of the things that we're seeing companies do where they can pull this crazy stats of one employee making in the revenue per company at least one or $2 million, which now the public comps-- take like a Salesforce.

**34:39** · Maybe the employee comps of how much revenue they bring in is under six figures.

**34:43** · So this is huge.

**34:44** · It's at least a 10x based on what we're seeing on the startups.

**34:48** · And what does this look specifically is when agents are able to read the full state.

**34:53** · In practice, we actually implemented this also at YC with our engineering team.

**34:58** · We're basically able to cut the sprint time in half and produce 10x the amount of work.

**35:03** · And some of you may have read this blog post from Jack Dorsey about the agentic organization.

**35:09** · How many of you have read that post?

**35:12** · Some of you are familiar with this concept.

**35:14** · And I think it talks a lot about now making an organization very flat and basically getting less need for middle management, because middle management used to be just all about this lossy information routing.

**35:28** · You end up basically having three roles in a company.

**35:32** · One is everyone starts building, so everyone becomes effectively an individual contributor that ships something, and even people that are non-technical, you now have the power to build with all these tools.

**35:44** · So even a salesperson could be building their whole pipeline of calls and meetings and automate all of that.

**35:51** · And then the other person is the DRI who tends to be-- some of you are familiar with this term from Apple.

**35:56** · How many of you DRI?

**35:58** · The concept of a direct responsible individual, that every outcome in a company trades down to a particular owner that owns the outcome.

**36:07** · And the way it works is that the DRI orchestrates with the IC to make sure something gets done.

**36:11** · For example, a goal for a company might be we need to increase the revenue by 3x by the end of the week.

**36:18** · They're responsible to orchestrate all the things that need to happen to get there.

**36:22** · They work with the sales team to get all the calls booked with the engineering team to ship all of these.

**36:26** · And that tends to be oftentimes the founder.

**36:28** · Now, the new role that comes into this AI native organization is we call it AI founder.

**36:36** · If you hear Garry, he really much embodies this, is you're living at the edge of the future with all the tools.

**36:45** · In order to get your company to run fast, you've got to be trying all the tools.

**36:48** · Everything is changing and moving so quickly.

**36:51** · Literally, we had this big revolution with agentic coding that just happened end of last year with Claude 4.5.

**36:59** · When it came out, that's when things started to work.

**37:01** · But if you were not building, if you were not at the edge, you would not be able to bring all those innovations into your company.

**37:08** · So that's one of the things that we're seeing the best founders at YC do.

**37:12** · Yeah, there are people who are still operating like Copilot level from last year, and it's not going to make it, bro.

**37:18** · They're not going to make it.

**37:20** · Now, the other thing that get talked a lot about is in order to build all these agentic systems to avoid, quote unquote the "AI slob" is what cannot be delegated.

**37:33** · It's really a concept of a taste.

**37:35** · How many of you have been hearing a lot on the taste is what's going to be durable?

**37:40** · I think a lot of you agree with this, right?

**37:43** · Coding, let's just call it, shipping code is going to zero, the cost of it.

**37:48** · But what is not going to zero is the taste to build something good, the taste to discern what's good or bad.

**37:54** · And as part of that, that really manifests in terms of evals into the systems for how you build all these agents.

**38:01** · And what that means is that generic benchmarks won't make it whether your product works.

**38:07** · I know sometimes people are trying to just hit some generic public benchmark MMLU.

**38:13** · It doesn't tell you whether your product or agents are really working or upsetting the user.

**38:18** · A lot of the product that a lot of you-- if some of you want to hopefully start companies, raise your hand.

**38:25** · Maybe.

**38:25** · Yeah.

**38:27** · Great.

**38:28** · So part of it, the actual judge ultimately of whether something is good is whether users really want it.

**38:34** · And with that, it's going to be different in every single domain.

**38:39** · There's no way to automate that.

**38:41** · And how can you tell?

**38:42** · I think the agent-- you will have to go into all the details deep.

**38:46** · Did it follow the instructions?

**38:48** · Was the answer correct?

**38:50** · Did it preserve the customer trust?

**38:52** · Was this something that was spewing correctly or incorrectly?

**38:56** · Did it actually hit the business goals?

**38:58** · Did it comply with the domain rules?

**38:59** · So a lot of these things that Garry talked about in terms of resolvers and skillifying it and improving the system apply here.

**39:08** · But in order to do that, you still need the human in the loop to tell when something goes wrong and to basically label a particular interaction or pipeline or workflow that is incorrect.

**39:19** · And that is something that you're going to have to own and do and painstakingly actually look through all the traces.

**39:28** · This is how, Garry, you go through a lot of the system, too.

**39:31** · You read through the traces and click when it's wrong or right and decide to skillify it, right?

**39:36** · Yeah.

**39:38** · Well, what's cool though, is once you get the basics going, my favorite thing that I haven't released yet but I will release is a cross-modal eval.

**39:47** · So I'm about to add the skillify where you can actually have the frontier models of Opus, GPT 5.5, and DeepSeek V4 all evaluate the inputs and the outputs, and then rate it and then feed it back to the original subagent saying, this is the rating, and here's what you need to do for the next try.

**40:07** · And then you actually iterate.

**40:09** · And so you can meta prompt to get something that is 10 times better than the first version of what it is.

**40:15** · What's weird is like these abstractions are basically stacking because that's what-- I learned that from GStack.

**40:19** · A lot of YC founders said, well, I like Claude Code, but that's like my ADHD CEO.

**40:25** · And then Codex is my nearly non-verbal 200 IQ CTO, and I need both of them to do cross-modal analysis.

**40:34** · And then it ships with zero bugs.

**40:36** · So these are all things that are like stacking.

**40:38** · We're just discovering these things like week to week right now.

**40:41** · And this is effectively the section on all the founders here would be the ones building the evals and exactly that.

**40:48** · As part of doing this cross-modal evaluation, you have to start with being able to capture a lot of the traces.

**40:54** · And the way you capture the traces is going to be very context dependent on the product you build.

**40:58** · And if you're building let's say, a video application, it's very different than a speech application, consumer model, B2B, SaaS, all very different.

**41:09** · And then you need to convert a lot of the failure cases.

**41:13** · And you have to detect when they fail into actually evals that you use.

**41:16** · And then the step 3 is to be able to replay this constantly into the system in order to self-heal and improve the system, and improve the prompts automatically, which is exactly what Garry's describing that he's going to ship.

**41:29** · He's doing like a general version, but for each of you, you can build all of these.

**41:33** · These are still the same principles.

**41:35** · Can we meta a prompt here for a second?

**41:37** · You're sitting here listening to a lecture about this stuff, but the lecture is totally useless if you don't go and open your own Hermes agent and OpenClaw and load up your own GBrain and actually use-- there are 40 skills that you can test out and try inside GBrain.

**41:53** · And some of it is make your own.

**41:55** · Basically do stuff and then skillify your own stuff and then release it open source too and see what other people want.

**42:02** · We're getting there together.

**42:06** · And so the exhortation is like, not only are we meta prompting the machines themselves, we need to meta prompt one another to be better and to be able to fuse with the machines in a new and more profound way every single day.

**42:21** · Now, the last lecture, we're going to go over is that for some of you here in the audience that are excited to start a company, this is probably one of the best times in history ever to start a company.

**42:33** · And this is not an overstatement.

**42:34** · You might have heard this from other lecturers that came here.

**42:37** · Is that right?

**42:38** · The times right now are unprecedented, and part of it is we're seeing this.

**42:44** · A lot of the wedge in practice is you pick a painful workflow.

**42:48** · You go inside deep into the customers, and you basically become the forward deploy engineer.

**42:54** · And what that looks like, we've seen it across many industries, and these are examples of companies that have done this crazy growth that I'm telling you, that gone zero to eight figures in revenue within a year.

**43:05** · For example, Salient is this company that's doing voice agents for loan servicing.

**43:10** · They closed some of the top banks in the US.

**43:13** · And the way they did it is they built agents how Garry described it.

**43:17** · Other companies, HappyRobot as well that closed the series B recently last year and 10x the revenue in a year.

**43:24** · Same thing.

**43:24** · They embedded themselves with freight forwarders and built the best agents to automate a lot of that cruddy work with truckers and coordinating timelines.

**43:34** · And then the other one is Reducto.

**43:35** · I don't know how many of you may have heard of this company that is doing document processing.

**43:41** · The other opportunity is there's just so much tooling that needs to be built for all these tools.

**43:46** · Just the fact of doing better document processing is making all of the other agents better, because they all need to not read documents.

**43:54** · But if you increase it, it improves RAG and memory and brain to be a lot better.

**43:59** · So Reducto is another of these teams that are growing.

**44:02** · So what this means is that a lot of these companies that are seeing all these impressive growth is they're just demoing AI or some side project.

**44:13** · They're actually deploying full solutions.

**44:16** · And part of it, if you want to start a company in this fashion, you basically go undercover because some of you-- a lot of you probably don't have necessarily a background-- the founders of Salient or HappyRobot did not come from a finance background or logistics.

**44:32** · Not in the training set.

**44:33** · Not in the training set, but the way they became experts is they actually shadow, or took a job and learn the depths of everything that had to be done with it, and then they were able to automate a lot of the repetitive labor and handle a lot of messy domains into this latent space that Garry described.

**44:52** · And all these workflows before were just done by phone or email, spreadsheets and all very random places where an agent embedded into all the system could just create a solution that would just work.

**45:06** · And I guess the other thing is we want to show you this graph that Anthropic posted in terms of the deployment in different industries.

**45:17** · And we're seeing that right now I think a lot of you-- I don't know if a lot of you in computer science-- how many of you are a little bit afraid of the CS jobs after you graduate?

**45:27** · I mean, there's a real fear because for this chart taken by Anthropic, 50% penetration into the usage of these tools.

**45:36** · But what is interesting is these giant whitespace in all these other domains in terms of back office, finance, data, academics, cybersecurity, customer service.

**45:47** · This is like a huge white space.

**45:49** · There's room for hundreds and hundreds of AI unicorns that are waiting to be started, perhaps by some of you in the room.

**45:56** · I guarantee it.

**45:57** · Because some of you may feel it's like all the ideas are done, but what we're seeing that is not the case.

**46:02** · Yeah, we're at the first pitch of the first inning on the revolution, and you guys are the shock troops.

**46:07** · And one other stat I want to give you from the last batch at YC, is that in the past, only the best top 1% of the companies grew 10% week over week.

**46:18** · That was the metric that PG set.

**46:20** · And in the past, perhaps the batch of Airbnb only-- maybe Airbnb, another company hit it.

**46:25** · But now what we're seeing, things have dramatically changed where on average this is the growth of companies that within three months they basically 3x.

**46:34** · Yeah, in the history of YC, this has never happened before.

**46:37** · So we get to live in this moment where people in this room can create something that actually has a real impact, and you can see it and you can tell because your customers are going to say, I can't believe this exists, and thank you, and they'll pay you.

**46:51** · And then every week, 10% more people will be paying you.

**46:55** · And what we want to close off here, I know a lot of the lecture theme has been about how you could build a one-person frontier lab.

**47:01** · This whole lecture was about that lab can become a one-person company, and that could be you.

**47:07** · We just gave you all the secrets here.

**47:09** · Thank you, everyone.