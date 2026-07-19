---
title: "Stanford CS153 Frontier Systems | The Discipline of Delivering Value per Gigawatt"
source: "https://www.youtube.com/watch?v=VeTqsCpcDgg&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=4"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=VeTqsCpcDgg)

## Transcript

**0:09** · Thank you so much for joining us, Amin.

**0:11** · Please give me round of applause for Amin Vahdat.

**0:13** · \[APPLAUSE\] You guys have no idea how hard it was to get Amin to show up, seriously.

**0:23** · This is the one lecture that I've been super excited about.

**0:28** · And Sebastian, who many of you know who is my co-founder on AMP, wanted to be here, and he's so bummed that he couldn't because he's busy working on the cluster for your guys' final projects.

**0:39** · Sebastian worked on the Borg Export DQM scheduler-- that designed that, too.

**0:43** · So we're very much a Google family over at AMP.

**0:49** · And so Amin is a bit of a rock star in our lore.

**0:54** · So to give you guys some context, Amin is the head of-- basically in charge of the internal infrastructure at Google.

**1:03** · The TPUs that make Gemini possible really would not be anywhere close to scale they are at if it wasn't for Amin.

**1:13** · So pay attention to every word he says.

**1:17** · Think about him as the opposite of Jensen.

**1:20** · Jensen is a rapid fire, high-throughput LLM.

**1:24** · Think about Amin kind of as the distillation of three frontier models who have been trained on the practice and discipline of infrastructure for the last-- how long have you been doing this, Amin?

**1:38** · Coming up on 30 years, I'm sad to say.

**1:41** · 30 years.

**1:42** · So every word Amin speaks has-- every token that he produces as an LLM has-- universe is contained in them.

**1:51** · And we will probably not understand what he actually means for years.

**1:54** · So I'm glad it's going to be recorded and put up on YouTube, because I think years from now people will look back at his lecture and realize how profound his influence was on the industry.

**2:04** · To concretize that, how much compute does the internal pool at Google have today, Amin?

**2:12** · Start off with the easy question that I can't answer.

**2:15** · I've seen some Twitter posts that say we have among the largest computing infrastructures in the whole planet.

**2:20** · And I think I'm willing to stand up behind that one.

**2:23** · Would you say it's in the tens of gigawatts?

**2:25** · Tens of gigawatts?

**2:29** · I will say that we are aiming for tens of gigawatts.

**2:33** · Over the next four years, it'll be well in the north of tens of gigawatts.

**2:36** · Over some time period, yeah.

**2:38** · So we crunched the numbers this morning.

**2:40** · We think about 1 gigawatt to build out is how much?

**2:43** · So 1 gigawatt is about $40 billion of infrastructure.

**2:47** · Do the math.

**2:48** · And as much as I hate to say it, Amin's infrastructure org is literally one of the most efficient on the planet.

**2:58** · Because there was a time when I was starting out AMP and we were looking at how much single cluster utilization was across the industry.

**3:05** · And some of our portfolio companies, some of the speakers here were running them at 70%, 80% utilization.

**3:12** · And some of the other big tech companies were similar, in fact, worse.

**3:15** · I'm sure you saw the Colossus cluster is not running at peak utilization, and I think it's at 11% MFU, which is-- honestly, MFU is kind of hard to get up.

**3:23** · But at Google, my understanding is if the node allocation is less than 96%, it's considered a major outage.

**3:30** · Is that right?

**3:30** · Yeah, so I think what this really points to is, when you hear numbers like $40 billion per gigawatt-- and I've heard numbers like $50 billion a gigawatt from other sources.

**3:42** · The numbers are going up.

**3:44** · Things are getting more expensive.

**3:45** · I think the most important consideration isn't how many gigawatts you have, it's how much capability and value you're delivering to your users.

**3:55** · And this is something to really be aware of.

**3:57** · In other words, if I've got a gigawatt here and a gigawatt there, they're not the same.

**4:02** · How much reliability you have actually really, really matters.

**4:05** · I could go spend $40 or $50 billion on a gigawatt.

**4:08** · And if I don't do the work to make sure that every one of those nodes is super reliable-- So a gigawatt, let's say that's 150,000 to 200,000 CPUs, GPUs, it could be whatever you want.

**4:24** · One of those goes down, maybe your whole computation stops.

**4:29** · If you're not, a, making sure it doesn't fail, b, when it does fail, figuring out which one it is and getting it repaired really fast, you just wasted a lot of money because your utilization, and what we call your goodput, is nowhere near what it needs to be.

**4:44** · If you have the TPUs deployed but no one can schedule a job on them, it doesn't matter how much money you spent on them.

**4:51** · So I think that a lot of these measures are actually broken.

**4:55** · The measure isn't how much money you spend per gigawatt, it's actually how much value you deliver per dollar.

**5:03** · And if I can spend half the money, deploy half the capacity, and give you the same capability, awesome.

**5:09** · Better, if I can deliver twice the value from that gigawatt, I now need to build fewer gigawatts.

**5:16** · Or I can only get so many gigawatts.

**5:19** · Energy's massive problem.

**5:21** · And we had Jensen here last week.

**5:24** · And one of the questions I asked him is, how do you-- he said something similar, which is-- Is this why everybody's laptop is signed by Jensen?

**5:30** · Yeah, basically.

**5:32** · You should get it-- well, no, no, no, Stanford's going to yell at us for trying to get signatures.

**5:36** · We got yelled at, as you guys know, physically.

**5:38** · I have a GPU, by the way, signed by Jensen.

**5:40** · So it's a long line of \[? code. ?\] It's a tradition, rite of passage.

**5:44** · So how do you measure intelligence output per unit of input?

**5:50** · It's ultimately what as a systems person, we're trying to optimize.

**5:53** · And if the output is this very heterogeneous output, which is coding tokens, image tokens, and so on, but the input is this generalizable input called compute or flop, so to speak, how do we reconcile the fact that the evals are just different?

**6:07** · We're-- so tough, close to impossible question to answer.

**6:11** · We are working on benchmarks that measures intelligence per dollar actually.

**6:14** · And we've published some things externally.

**6:16** · I can send folks references out of Google broadly-- That'd be great.

**6:20** · --that captures this question of intelligence, and then it's intelligence per dollar.

**6:24** · But what I really want to emphasize, though, is that it is how much you're actually getting out of it.

**6:29** · So another way to look at it is, per gigawatt, how much revenue are you generating?

**6:34** · Maybe revenue is not the right measure.

**6:35** · How many daily active users do you have for your service?

**6:39** · So it's not how many gigawatts do you have?

**6:40** · It's-- Daily active users per se.

**6:43** · OK, got it.

**6:43** · If I'm doing Gemini app and I have a gigawatt behind it, no one cares that I have a gigawatt behind it, or 2 or 4 or 1/2.

**6:51** · It's how many daily active users do I who are happy, and then how is that growing?

**6:57** · And now the question is, how do I deliver?

**7:01** · So this is where the efficiency part comes in.

**7:03** · I want to make sure that every TPU is up.

**7:06** · But by the way, if I have a bunch of TPUs and I don't have the compute and the storage and the networking to go along with it, then it doesn't matter how many TPUs I have, especially in the age of agents.

**7:17** · Actually, it's a orchestration of the whole.

**7:20** · Because if I'm having all my expensive TPUs sitting around idle, waiting for an agent to finish running its simulation through a CPU that has to go get some data from the storage that might be in a whole other region, that's a problem.

**7:34** · So it's the orchestration as a whole.

**7:37** · I think there's too much fixation on how many gigawatts of capacity we have.

**7:40** · By the way, I spend a lot of time making sure that we have a lot of megawatts, a lot of gigawatts of capacity.

**7:46** · So I get it.

**7:47** · But there isn't enough on how much value are you getting out of it.

**7:49** · Are you extracting the most utility out of every machine that you build and deploy?

**7:55** · So if you've closed the loop to say-- I think what I'm hearing you say is the eval is the business metric that matters.

**8:03** · In the case of Google, it's daily active users or whatever for the Gemini app.

**8:07** · But the challenge as an infrastructure person, which you have an extraordinary history and background doing, is you're always trying to design general primitives that are not over specified for a particular output.

**8:21** · Yeah.

**8:22** · And if intelligence is a humanities scale measure, then how do you reconcile the difference between designing an infrastructure primitive that's general for all of humanity, but that might not align with the specific measure of intelligence that matters to Google?

**8:35** · Does that question make sense?

**8:36** · It makes sense.

**8:37** · I think it's a great philosophical question.

**8:41** · The good news is, in practice, what we do care about are the business outcomes, because we have to believe, and it turns out to be accurate, that people are going to vote with their feet and use the services that are giving them value.

**8:53** · In other words, if we have Gemini DAOs and they're going at a certain rate, for whatever reason, if it's competing against ChatGPT or Claude or Grok or whatever else, if people are using it, they're voting with their feet.

**9:08** · They must be getting the intelligence and the utility that they need.

**9:10** · If they're using coding in one scheme versus another, if we're delivering the value.

**9:15** · Now, a lot of this does come down to how many flops do you have, how much HBM bandwidth do you have, how much ICI or NVLink or whatever else, bandwidth you have.

**9:24** · All these low-level measures matter.

**9:26** · But in the end, what it rolls up to is happy users, paying enterprise customers, developers who are getting their work done.

**9:34** · That's what we're trying to maximize.

**9:36** · So if we have capacity that is sitting on idle, that's a bug.

**9:42** · OK, got it.

**9:43** · The value that's delivered is a great metric.

**9:45** · So what we have to now make sure is when we have these gigawatts of capacity, the infrastructure layer is fascinating because there are thousands, millions of things that can go wrong.

**9:55** · You know this very well.

**9:56** · And each of them unfortunately matter.

**9:59** · So it's about systematically going after it.

**10:02** · So in other words, there is no major breakthrough when we say, hey, in going from 99% availability to 99.9% availability, super hard.

**10:12** · One would think 99% reliability, that's pretty good.

**10:15** · If you think about it, though, that means that 3.65 days of the year you're down.

**10:20** · That's not good.

**10:22** · In fact, it might be unacceptable.

**10:24** · Now, though, I want to come back to power for a second, because power oftentimes is your biggest constraint.

**10:30** · You talked about 11% MFU.

**10:34** · If you look across all the fleets-- I won't tell you what the numbers are.

**10:37** · But if you look at the amount of power provisioned at the edge of a data center region and how much power is actually used by the compute, it's probably a lot lower than you want it to be.

**10:49** · Reason number one, overprovisioning for reliability.

**10:54** · So in other words, to really get to what the power service wants, which is five nines of availability, which means 30 seconds of downtime a year, you basically have to have 2n, 1 plus 1 redundant feeds.

**11:07** · One goes away, the other basically switches over immediately.

**11:10** · That means that half your power capacity is not being used at any given point in time.

**11:15** · That's what it takes to deliver five nines of reliability.

**11:19** · Now though, what if you go to your customers and say, hey, would you rather have 99.9% reliability and double the capacity, or 99.999% reliability and half the capacity?

**11:34** · Historically, the answer would have been, give me the five nines.

**11:38** · I can't take the outage.

**11:40** · Today, though, if you go to the frontier labs and say, would you rather have twice the capacity but then 3.65 days of the year or 0.365 days of the year you don't get any of it, they'll say, oh, yeah, sign me up, give me more capacity.

**11:54** · I'll take the downtime.

**11:55** · Is that a new phenomenon, or is that a-- It's a recent phenomenon.

**11:58** · It's a recent phenomenon.

**11:59** · Because again, if you're delivering-- historically, if you're delivering an enterprise-grade service, it's five nines, can't be down.

**12:06** · But training a frontier model, it's about throughput.

**12:09** · You'll take the downtime for a day or two days or three days a year, \[? if ?\] the other 362 days of the year.

**12:15** · I'm not speaking for everyone, I'm just-- But by and large, your customers are telling you-- your internal customers are saying-- Internal and some external.

**12:23** · --we will take access over reliability.

**12:25** · Yes.

**12:26** · And this is a fascinating new development.

**12:27** · But now even getting to that 99.9%, 1,000 things can go wrong.

**12:32** · Because the thing I want to emphasize is, if we're serving a frontier model, that's hundreds, perhaps thousands of CPUs or GPUs, doesn't matter.

**12:43** · If we're training, it's tens of thousands, perhaps more, of the same accelerators.

**12:49** · But the computation is synchronous.

**12:52** · What this means is that basically all of the TPUs, all the GPUs are talking to each other synchronously.

**12:57** · They're distributing data.

**12:58** · All reduce.

**12:59** · All gather, whatever else it is.

**13:02** · One of the nodes goes down, everything goes down.

**13:06** · So literally, it's-- again, how do we build internet scale web services to this day?

**13:13** · To date, if you're building web search, it's designed basically to have any rack go away at any point in time, and no one notices.

**13:21** · We barely notice.

**13:22** · We do notice.

**13:22** · We'll go get it fixed.

**13:24** · But there is no downtime, no outage.

**13:26** · Why?

**13:26** · Because we have a backup for all the data on that rack and at least one other place in that same cluster.

**13:32** · And we have spare compute capacity, and it's fungible.

**13:36** · So if you think about TPU or GPU training inference, every node is special.

**13:41** · Every node has a specific expert whatever layer in the overall model that it's serving.

**13:47** · If it goes away, propagation stops.

**13:51** · Serving stops.

**13:53** · So how you manage these things to actually deliver the value at scale completely changes.

**13:58** · So everything that we developed over the past 20, 25 years that said, loose coupling, don't worry about individual failures, all that's gone out the window, too.

**14:06** · Do you believe FLOPs should flow like megawatts?

**14:09** · Well, they're closely related.

**14:11** · But as you said, what I really believe is system balance is what matters most.

**14:16** · So if you are overfixated on FLOPs and you don't have enough HBM bandwidth, or if you don't have enough SRAM, or if you don't have enough network bandwidth, then it doesn't matter how much FLOPs you have.

**14:27** · We can build infinite FLOPs and connected via thin pipes to one another, or put very little HBM bandwidth or very little HBM capacity.

**14:38** · That's easy.

**14:39** · Scaling FLOPs is easy.

**14:41** · Building a coordinated supercomputer that scales out to 10,000, 100,000-ish TPUs that has the right balance point, super hard.

**14:50** · And this balance point is the key insight.

**14:53** · So I'll share with you all.

**14:57** · I used to be a professor.

**14:59** · I love this room, by the way.

**15:01** · seeing this room-- I took undergraduate classes in a room like this up at another school up the road at Berkeley.

**15:08** · We're equal opportunity systems people, right, guys?

**15:12** · Yes.

**15:13** · It turns out Berkeley does pretty good work in systems as well.

**15:15** · Yes.

**15:16** · That is great.

**15:17** · But one of the things that I loved learning most about, and that has really stayed with me, I'll share it with you all, in case, you don't know it, is Amdahl's Law.

**15:25** · Who here knows about Amdahl's Law?

**15:27** · Oh, no.

**15:28** · Amdahl's Law?

**15:29** · Amdahl's Law.

**15:31** · Sorry.

**15:31** · I failed as a professor.

**15:32** · Please, go ahead.

**15:33** · So the Amdahl's Law of system balance-- basically, this was late '60s, so before I was born.

**15:41** · He came up with this law that said, for every million instructions per second that you built into your parallel system, your distributed computation, you would need a megabyte per second of I/O.

**15:54** · So in other words, if you're going to provision a million instructions per second, think of it as FLOPs today, you better have that I/O to back it up, because compute without data is useless, and you have to be able to feed it.

**16:07** · And now, shockingly, over just-- it was 1967 he came up with this, so almost 60 years-- this has helped.

**16:15** · Now, he was building small scale in the late '60s.

**16:20** · Now we're talking about 10,000, 100,000, sometimes spread across even a wide area network.

**16:27** · You have to provision a network, because almost all your data is across a network today.

**16:32** · So your I/O is networked I/O. You have to provision for every some number of FLOPs, some amount of HBM bandwidth, some amount of network bandwidth, or you're going to starve-- you're going to basically waste your money.

**16:47** · If you don't build to this ratio, you'll have huge amount of flops that aren't doing anything.

**16:53** · To some extent, this is what's happening today with the very low MFU utilization that we have.

**16:58** · Why?

**16:59** · Because with the move to mixture of experts, sparse computation.

**17:03** · Actually the hardware today, all of it, actually, isn't built at the right system balance point to manage the fact that actually you now need a lot more memory bandwidth relative to the computation ratios.

**17:17** · So when you think about evaluating your systems, utilization, super key, the reliability part.

**17:23** · I really want to get this across.

**17:25** · But then system balance is also super key.

**17:28** · If you don't have the right system balance, you're wasting your money.

**17:32** · So when you say $40/$50 billion per gigawatt, yes.

**17:36** · But if you had to spend $55 billion and make sure that that gigawatt was balanced or reliable, you'd do it.

**17:46** · So I think the key here is-- because otherwise, you're not going to get the value out of it.

**17:51** · If you say, hey, with my gigawatt, I've got all these gigaFLOPs, teraFLOPs, petaFLOPs, exaFLOPs, \[? yettaFLOPs, ?\] whatever it is, awesome.

**18:00** · But what do you actually get out?

**18:02** · And what you get out depends on system balance, and it depends on reliability.

**18:08** · But now going back to the agents, system balance isn't just for your TPUs and GPUs.

**18:13** · It's the balance to the CPUs that are sitting next door, the storage that's sitting next door or in the next rack, the network that connects it all together, not the high-speed NVLink or \[? ICI ?\] network, but the data center network that connects it all together.

**18:28** · It breaks my brain a little bit to try to figure out, how do you decouple the individual bottlenecks in the memory storage bandwidth supply chains and align that in a predictable fashion to accomplish system balance?

**18:42** · How does one even approach that problem?

**18:44** · So for those of you who took undergraduate or graduate architecture, you've got your seven-stage pipeline with the instruction fetch and decode and access, and how do you actually-- and that's how we got superscalar performance, seven stages, super complicated within the core.

**19:03** · Now we've got 127 stages.

**19:06** · Within a CPU, it's possible to get that microarchitecture more or less balanced.

**19:13** · But even there, getting the right balance point is super tough.

**19:16** · That's why you get pipeline bubbles.

**19:17** · That's why you say, OK, how many cycles per instruction do I really have and how do I drive that down, actually?

**19:22** · So now extend this out across 100,000 nodes.

**19:25** · It is an impossibility.

**19:26** · 100% MFU is not possible.

**19:30** · So that should be like-- you could with a toy just like shout it out and say go.

**19:36** · But in general, for a real computation, you're not going to get perfect balance because there's-- let's say there's just little micro variation in cache hit rate of one TPU/GPU versus another that will cause a pipeline bubble.

**19:50** · So because now you're waiting for the data to come from another node, the MFU just won't \[INAUDIBLE\].

**19:55** · So you have this compounding.

**19:56** · Yep, and it'll multiply.

**19:58** · And let's talk for a second-- because what you described is the computational bottleneck.

**20:02** · I'm talking about, now you add a network.

**20:04** · No, no, procurement.

**20:05** · Oh.

**20:06** · How do you-- literally, the world can't produce enough memory.

**20:12** · Yes.

**20:13** · I'll ask if this is true or not.

**20:15** · There's reports that one of the frontier labs cornered the market on memory recently through buying a bunch of call options, and then the rest of the industry revolted.

**20:25** · Is that true?

**20:25** · I don't know If it's true or not.

**20:27** · I read the same-- or I can't keep up with the X, So I have the same tweet, whatever-- This is from a group chat this morning.

**20:35** · Group chat this morning.

**20:36** · This actually came out three or four months ago.

**20:38** · Oh, then the group chats are behind.

**20:40** · In this particular case, the group chat is behind.

**20:43** · These things-- yes, the supply chain is a massive, massive issue.

**20:47** · I'm \[? not ?\] responsible for the supply chain and procurement.

**20:50** · The problem is that things just continue to go up and up and up every month.

**20:55** · And the lead time is years.

**20:57** · So in other words, basically if you want to say I want a gigawatt of capacity, if I want a net new gigawatt of capacity, my lead time is somewhere around two or three years.

**21:07** · It doesn't matter if I've got my $40 or $50 billion.

**21:10** · Just for buying everything and building it, it's a very physical process.

**21:16** · So gigawatt end to end, I've got to go get that capacity of power somewhere.

**21:21** · We have a final project here, which is the one-person frontier lab.

**21:24** · And they have increasingly less time.

**21:26** · But look, the project is a microcosm of life.

**21:29** · And what you just heard is Amin saying there's a bottleneck he can't throw more money at to clear.

**21:34** · For sure.

**21:35** · So if you could prompt them to solve it from a technological perspective, what could they do to help unblock that bottleneck?

**21:41** · And we're going after it on multiple fronts, because pulling that in-- in other words, if I had the ability so many times-- so many times, actually, if I had the ability to go spend more money and get more capacity tomorrow, it'd be an easy decision.

**21:54** · But if you're saying, hey, you now have to commit to how much capacity you want in two years time, commit, like no going back-- today, you have to say exactly how much capacity you need in two years time-- basically, there's going to be one of two outcomes.

**22:07** · There's a third that's infinitesimally small probability.

**22:10** · Outcome number one is, you predict too little, and then you're going to be really upset that you're leaving opportunity on the floor.

**22:18** · Outcome two is you overpredicted and now you wasted a bunch of money.

**22:22** · There's some other possibility, which says you predicted perfectly, which never happens.

**22:25** · So if you could pull that in, and now you said, OK, how much capacity do you need tomorrow, you're probably going to nail it.

**22:32** · Or if you overpredict by 0.05% or something, how do you pull that lead time in?

**22:39** · And actually, this is a technical problem.

**22:42** · This is truly a technical problem, where from procurement to manufacturing-- right now, if I wanted to have a gigawatt, I'd have to go build a new building, a big building, probably multiple buildings, actually.

**22:55** · What does that mean?

**22:56** · I have to go now get some land.

**22:58** · Maybe I've got some land buffered up.

**23:00** · But if I don't, I'm in trouble, because I now have to go do permitting.

**23:04** · That's-- Six months.

**23:05** · --indeterminate.

**23:06** · Who knows, et cetera?

**23:08** · But by saying, OK, well, you know what?

**23:09** · The land is kind of cheap, so let me have a bunch of land on the side.

**23:13** · Now, is the land prepared for a building to go down?

**23:15** · Actually, you probably have to grade it.

**23:18** · Let's go ahead and spend the money to grade it ahead of time, too.

**23:21** · Now.

**23:21** · I'm ready.

**23:22** · But now I put down the pad.

**23:24** · Do I go procure the power?

**23:25** · That starts getting expensive.

**23:27** · Or do I go to the utility?

**23:28** · The utility, now-- everybody is going to the utility saying, I want a gigawatt.

**23:31** · I want 5 gigawatts.

**23:32** · I want 10 gigawatts.

**23:34** · They'll say, sure, I'll get you that, but you have to agree to pay me for all of that for the next 20 years.

**23:39** · You want a gigawatt?

**23:40** · Sign this contract that says you will pay me for a gigawatt 24/7 for 20 years.

**23:45** · Why?

**23:46** · Because there's no capacity to back it on the grid anymore.

**23:48** · It used to be if I went to utility and said I want a gigawatt, they'd say, sure, I've got a gigawatt-- well, I wouldn't go for gigawatt.

**23:55** · I'd say, give me 10 megawatts.

**23:56** · And they'd say, sure, 10 megawatts, no problem.

**23:59** · I've got that.

**24:01** · You don't need to sign a contract.

**24:03** · It's so much slack capacity, I'll get you 10 megawatts.

**24:07** · No longer true.

**24:08** · But my understanding is the reason grid-connected capacity is so acutely undersupply is because hyperscalers are saying, well, we only want sites that are expandable.

**24:18** · So everything under 100 megawatts is just stranded.

**24:22** · Yes.

**24:23** · But that's a bunch of stranded unutilized capacity in America.

**24:26** · If you were the chief energy officer of America and you were trying to drive up utilization of those stranded assets, what would you do?

**24:33** · So I think the 100 megawatts, if you look at it, it'll add up to something, but it's not going to add up to the majority of the demand.

**24:41** · I think that just from a scale and operations perspective, if we really want to go after this, actually, we should \[? understand ?\] some of those 100 megawatt sites, for sure.

**24:49** · I think that as serving takes off, that will happen naturally.

**24:52** · I see.

**24:53** · So in other words, we are up until recently in a place where most demand was for training.

**24:59** · And training does need large contiguous chunks of infrastructure.

**25:02** · As we move to more and more of the demand going to serving, that's going to shift naturally.

**25:07** · Because serving is more fungible.

**25:09** · It's more fungible.

**25:09** · It's smaller.

**25:10** · I don't need a gigawatt to do training.

**25:12** · I don't need 500 megawatts to do training.

**25:14** · I can serve some number of tokens per minute coming from a small-ish deployment.

**25:19** · So I think we're going to understand that somewhat naturally, but I don't think that's going to fulfill the needs, because there is going to be benefit to scale, and we are going to have to figure out how we get larger amounts of power concentrated, delivered to some number of locations.

**25:35** · Yep, makes sense.

**25:36** · I could go on for hours, Amin, but we should switch to questions.

**25:40** · The question is, if you were Stanford student again, what technical problem would you obsess over?

**25:44** · I will say that I get this, I think, is a really good question, but the answer I'll give is to go-- all of them really, really matter, honestly.

**25:56** · In other words, there is no one bottleneck.

**25:58** · And predicting the future is really hard.

**26:01** · So let me give you an example.

**26:02** · When I was a graduate student, what everyone said is absolutely, positively, don't work in artificial intelligence.

**26:10** · That's the worst thing to work in.

**26:13** · And that was true again after 10 years, and then true after another 10 years.

**26:17** · And now look what's happened.

**26:18** · Trying to predict the future?

**26:19** · Really, really hard.

**26:21** · I would say pick the problem domain that you are most intrinsically excited about because that passion for it, that's what's going to carry you forward.

**26:33** · And then in this model, I would say everything from algorithms, to hardware engineering, to chip design, to operating systems, to model architecture, it all matters, which is really good.

**26:48** · So probably, a pretty good chance that what you pick is going to be really, really important.

**26:55** · And if you pick something solely because your prediction is that it's going to be the most important one, but you don't like it, I think that outcome will be the bad outcome, because also, a pretty good chance that you'll have mispredicted.

**27:09** · I have a quick question based on that.

**27:11** · Many of you submitted your project ideas.

**27:15** · And there were 500.

**27:16** · So it's taken me a while, but I'm steadily reading all of them because I don't want to have Claude hallucinate.

**27:22** · How many people here feel like you picked a project idea because you were truly, intrinsically motivated by it?

**27:30** · Good number.

**27:31** · That's actually very helpful.

**27:33** · It wasn't clear to me based on the readings, because there's a surprising similarity between many of the problems you guys are interested in.

**27:41** · And I wish we were seeing more diversity in those problems.

**27:44** · But that's for another time.

**27:46** · Next question.

**27:46** · The question is, what's your favorite story from your time at Google?

**27:49** · There are a lot of favorite stories.

**27:51** · And thanks for reminding me of the great time I had at Duke as a professor.

**27:56** · The stories that are-- we've had, of course, many joyous moments, many funny moments.

**28:01** · But I think that for me, the moments that are best are the ones where you learn the most.

**28:10** · So the one that actually comes to mind, just top of mind, is when the original TPU v2 design was happening, and we were going to go build this supercomputer at the time, 256 nodes.

**28:22** · It's gotten much bigger, over 9,000 nodes now.

**28:25** · And we were debating what network to use.

**28:29** · This was around 2015-- what network technology to use.

**28:33** · And my primary area of research understanding at the time was networking and the conventional wisdom from 45 years or whatever at the time of networking was, whatever you were going to do in networking, you were going to use ethernet.

**28:49** · And some really smart folks said, no, this domain, we want a distributed shared memory system, read/write semantics, point to point, not switched.

**29:01** · And ethernet is the wrong solution.

**29:05** · I was like, what the heck?

**29:07** · Look, I have 40 years of history behind me and always been right.

**29:12** · Me and the thousand other people have always been right.

**29:15** · But then when we dug into it back and forth-- and it was one of these super spirited debates, not an angry debates, to be clear.

**29:23** · But it was a-- smart people, whatever you want to say, really going at it and really convinced that they were right.

**29:33** · So it turned out I was wrong.

**29:35** · It turned out that actually you don't want to use ethernet for TPU supercomputer.

**29:40** · And that has stood the test of time for the past decade.

**29:43** · I got it wrong.

**29:45** · I learned something new.

**29:47** · So the best thing about Google, actually, I would say, is how often I get to learn something.

**29:54** · In that story, who was the person who was the first principal thinker that came to that conclusion first and then evangelized that standard?

**30:01** · Hard to say, but probably Norm Jouppi, Stanford PhD.

**30:05** · So, yeah.

**30:06** · Yeah, Norm is-- Maybe he learned something new.

**30:09** · Next question.

**30:09** · The question, what was it like during the ChatGPT code red?

**30:12** · I think it was a great time, and I think it remains.

**30:15** · I think that Google has changed as a company.

**30:21** · when I really first started seeing Sundar in action up close-- I now report to him.

**30:25** · I didn't at the time.

**30:26** · But one of the things that he did in that moment was he did a fairly big reorg.

**30:31** · The biggest part of it was bringing Brain and DeepMind together.

**30:34** · Probably, many of you have heard of that.

**30:36** · It was a fantastic move.

**30:37** · He also brought different infrastructure teams together under my leadership.

**30:43** · That was the lower headline, but I think also turned out to be a good move, not because of me, but because it allowed us to move with more speed and more unification.

**30:55** · I would say that seeing how the people came together was really fantastic.

**31:01** · The culture at Google is different than it was three and half years ago.

**31:05** · I would say it's been a reinvention.

**31:07** · I think that we're actually through that now.

**31:10** · If you'd asked me a year ago, would I say that we were through it, probably not.

**31:13** · I think we're now at this point through it.

**31:16** · Sundar deserves a lot of credit.

**31:18** · Demis Hassabis and Jeff Dean deserve a lot of credit for it as well.

**31:22** · But really, I speak of November 2022 often, actually, internally, and frankly, fondly.

**31:31** · I can repeat the question if you-- Please, do.

**31:33** · So I think the premise is networking is a bottleneck at all layers.

**31:38** · We at Google have been leveraging optical circuit switches to remove that bottleneck.

**31:43** · So are you worried, am I worried that we're going to limit ourselves, given the fact that we can't reconfigure these optical circuit switches at per packet granularity?

**31:53** · Is that assumption?

**31:54** · Sorry, I interrupt you.

**31:55** · Go ahead.

**31:55** · Yeah, go ahead.

**31:56** · Good question.

**31:57** · So we don't restrict ourselves to optical circuit switching.

**32:00** · Optical circuit switching plays a role in our networking.

**32:04** · But the lecture which you're referring to, the presentation I made in terms of all layers, for example, you would not use optical circuit switching for on-chip network.

**32:13** · No way, not applicable.

**32:15** · And you would not use optical circuit switching for portions-- to large portions of the WAN.

**32:22** · But even within the data center where we do use it extensively, it's not the sole technology.

**32:27** · It's an augment.

**32:28** · In other words, we have a lot of electrical packet switches, a lot of electrical packet switches.

**32:32** · And if you look at the TPU within a rack, it is a point-to-point network, but every connection today between TPUs within a rack is copper.

**32:43** · There's direct copper, because that is the right technology.

**32:46** · Between racks, we have optical circuit switches, but the optical circuit switches essentially creates today a three-dimensional torus.

**32:56** · Why do we do this?

**32:57** · The reason is reliability.

**32:59** · So if you think about it, if I lose a TPU, I now have, again, lost my entire lattice.

**33:08** · If information is flowing through this torus, pairwise connectivity, I lose that one TPU, everything's gone away.

**33:14** · What I can now do with my optical circuit switch is I can remove that rack wholly.

**33:19** · I can plug in another rack and those-- within a rack today, we have 64 TPUs.

**33:24** · Those 64 TPUs can take in the exact position of the 64 TPUs that I took out.

**33:30** · But what does the optical circuit switch do?

**33:32** · And this would require some pictures and some slides probably.

**33:36** · Basically what it then says is imagine that I have the ability to take fiber, unplug it, replug it to another rack without any humans.

**33:45** · That's what optical circuit switch does, is essentially-- so what is an optical circuit.

**33:49** · It's a chip about this big, square.

**33:52** · It has 136 mirrors on it-- could be more.

**33:56** · It could be less.

**33:57** · Each mirror can be rotated in three dimensions.

**34:00** · Essentially what we do is we take every rack and all the fiber that's coming out of that rack.

**34:04** · We connect it to the optical circuit switch.

**34:07** · The fiber-- now it's light shining out to the fiber comes into the optical circuit switch shining down on those mirrors.

**34:14** · So light comes in, hits a mirror, gets reflected in a particular direction, depending on how I rotate the mirror under MEMS control, these tiny mirrors and tiny motors.

**34:24** · It will get reflected precisely to go out and output port.

**34:28** · But I can program what output port it goes out.

**34:31** · So in other words, essentially, what it gives me is a programmable topology.

**34:35** · So that if I decide that a rack needs to be virtually removed, virtually removed-- this is all under software control-- and then another rack gets plugged in the exact same position that other rack got removed, I now can maintain my topology.

**34:48** · The torus becomes whole again.

**34:49** · And I can do this in, let's say, seconds.

**34:52** · So essentially, what the real differentiator has been for TPUs is the ability to have much higher levels of availability.

**35:01** · I can now recover from failures instantaneously, as long as I have a few spare racks, quote unquote, "lying around."

**35:11** · And the spare racks, by the way, could be doing smaller computations.

**35:14** · They don't have to be doing the gigantic computation.

**35:16** · That's place one.

**35:17** · Place two that it becomes useful is, let's say-- I told you about the compute problem and the storage problem.

**35:22** · We're doing agents.

**35:24** · I now one more level above that have a different optical circuit switching layer where I can say, point the mirrors to that cluster over there where the storage that I need is located.

**35:33** · I now can short-circuit many layers of a general-purpose electrical packet switch that I would have to have normally provisioned and built to go to that distant cluster and basically create a direct connect.

**35:44** · So really think of it-- so I still have lots of electrical packet switches, but I now have many fewer than I would have needed where I can program which cluster I can talk to.

**35:54** · You're right, it's not per packet.

**35:56** · But if I know that I'm going to run this five-hour job and this five-hour job needs the storage over there, point the mirrors over there.

**36:04** · The next five-hour job needs a storage over there.

**36:07** · As part of Borg, scheduling the job, it would say point the mirrors over there for the next five hours.

**36:13** · I see.

**36:14** · That saves me from provisioning layer upon layer upon layer of network and miles and miles of fiber, essentially allowing me to not have infinite bandwidth wherever I want it.

**36:24** · It's not fully fungible, because you're right, if at a second granularity, I said, oh, wait a second, I want to go over there.

**36:29** · It's not that I can't.

**36:30** · I still have electrical packet switches over there, just not with the full bandwidth.

**36:33** · The full bandwidth is pointed over there for the next five hours, or however long I decide I need to move back over here.

**36:40** · It's kind of a deep question.

**36:41** · So optical circuits such as they have their role.

**36:44** · They're not a magic bullet that solves all problems.

**36:47** · We use a lot of electrical packet switches.

**36:49** · Why is the torus the topology you settled on versus others?

**36:53** · Originally for ML training, the number one collective was all-reduce rather than all-to-all.

**37:02** · And for an all reduce, actually the torus is the perfect topology, because you essentially are disseminating parameters to everyone with potentially a little bit of computation, a little tiny bit of computation on each distribution.

**37:16** · So the best and fastest way to do dissemination of data for this particular style is with an all-reduce.

**37:23** · Now, if you are doing an all-to-all, turns out the switch topologies have their benefits as well.

**37:28** · For that regime, what is the optimal topology?

**37:31** · Optimal-- if you truly need to do all-reduce-- sorry, all-to-all with arbitrary communication, the switch topology with standard factory \[INAUDIBLE\] topology would be the best.

**37:42** · But it winds up that model designers can work around the topology in very clever ways.

**37:48** · And they do.

**37:48** · Yeah.

**37:50** · Next question.

**37:50** · The question-- I'm not going to take your assumptions.

**37:53** · Your assumption was all chips are becoming obsolete.

**37:55** · That is not true.

**37:56** · However, your question was, how does Google think about hardware depreciation, correct?

**38:01** · Let's take that.

**38:02** · Yeah, so all chips are not becoming obsolete.

**38:05** · There's so much demand that our older-generation ships continue to see very heavy use at Google.

**38:10** · And this is true.

**38:11** · Whether it's older-generation TPUs or GPUs.

**38:13** · It's true across the industry.

**38:14** · H100s are massive demand, despite the fact that Rubin has been announced, et cetera-- fantastic chips as well, H100s, and H200s, and B200s, and GB200s, et cetera, as well.

**38:26** · So we depreciate our compute hardware over six years at Google.

**38:30** · I think that is more or less standard across the industry.

**38:33** · I think a few people might do five, but six years, I believe, is standard.

**38:38** · We are seeing use at least for that period of time and typically longer for our hardware.

**38:43** · So it works out well.

**38:46** · How do we plan?

**38:46** · This was the problem that we were talking about earlier.

**38:49** · It's very, very hard to plan for the future because we're having to make these predictions fairly far in advance.

**38:56** · One saving grace is, when we're provisioning watts and data center space, that's fungible.

**39:02** · In other words, it could be Generation X, it can be Generation X plus 1.

**39:05** · It can be Generation X plus 2.

**39:07** · It can be Generation X minus 1.

**39:08** · So we first need to have an envelope for watts.

**39:13** · But the lead time for these chip stores is also significant.

**39:15** · You've got to get your orders in early, and you have to plan for those as well.

**39:19** · I can tell you that planning is a massive and complicated effort and fast-changing.

**39:26** · Because let's say that I have a plan, and then a new use case comes up.

**39:31** · There's a new invention internally at Google, a new product launch.

**39:34** · And it needs a particular kind of capacity.

**39:37** · Now I have to figure out how to fit that in.

**39:39** · I have to replan.

**39:40** · So essentially-- by the way, another very interesting domain is, how do you plan under uncertainty, and how do you dynamically replan quickly based on all the new information that you have, demands that you have, customers that come in?

**39:53** · A new cloud customer comes in and wants to buy a bunch of GPUs, but it's not the GPUs that I ordered.

**40:00** · It's a different kind of GPU.

**40:01** · How do I order these new ones, get them?

**40:03** · And by the way, they want to build close to their cluster in Minnesota.

**40:08** · I'm making all this up.

**40:09** · So all these constraints come in and now we have to replan dynamically and essentially daily based on the new information that we get.

**40:18** · Awesome.

**40:18** · Next question.

**40:19** · How do you see robotics capabilities being unblocked?

**40:23** · Yeah, I think a really exciting domain.

**40:27** · And I think that this is-- to me, if I think about the internet revolution, it really was the coupling with the mobility revolution that made it truly the impact that it was, basically taking the internet into the real world, making it mobile.

**40:41** · I think I'm biased, so you all can check this, but I think that the best example that we have of really advanced robotics out there in the world working in very complex scenarios is Waymo.

**40:53** · So I think that's a good example of this scaling approaches.

**40:58** · In robotics, I think in many cases, you're going to find that latency really matters, but safety is the primary consideration.

**41:05** · And I think you're going to have very similar scaling requirements.

**41:08** · But safety, reliability will just shoot through the roof in terms of your considerations.

**41:14** · And that's going to, then, argue for locality and essentially whatever you want to call it, single-threaded programming.

**41:21** · I don't mean single-threaded as in, OK, there's only one core on the CPU or whatever or on the TPU.

**41:26** · But essentially, you can't have variability.

**41:30** · If there's a safety question, you can't say, oh, wait, I had a context switch of 10 milliseconds, and I wasn't running when the safety, whatever, algorithm needed to be running.

**41:38** · So I do think that the similar scaling laws are going to apply, but the scale that you can count on for robotics is going to be much, much less.

**41:47** · If you're counting on 20,000 TPUs in a data center 1,000 miles away for your robotics application to work, depending on the robotics application may or may not work.

**42:00** · The question is, do you have any thoughts on the SpaceX-Anthropic partnership that was announced today where they're going to-- Anthropic is going to be able to use some compute from the former xAI Colossus cluster?

**42:13** · Similar announcement on Cursor.

**42:16** · So Cursor is going to be leveraging a bunch of capacity on SpaceX, xAI.

**42:21** · And I think what you're seeing here is massive demand for inference compute today.

**42:26** · So really, if you think about it, you'd have to say that coding agents really exploded.

**42:32** · They've been around for quite some time.

**42:34** · So I do know that, but they really exploded four or five months ago.

**42:39** · And nobody predicted it at this level.

**42:42** · So nobody essentially had enough lead time to say I need more GPUs, more TPUs to handle this explosive demand for serving.

**42:50** · People are now looking around and saying, what capacity can I get where?

**42:54** · And I don't the inside story of whatever Elon and Dario discussed, or whoever, but clearly, a good opportunity for Anthropic to leverage a bunch of available capacity that SpaceX had less use for.

**43:08** · What got me into this field and what convinced me to switch from being a professor to my job at Google?

**43:17** · I was lucky in that for whatever reason, I was-- I remember I was six years old.

**43:22** · I was in Iran at the time, actually.

**43:25** · My family moved to the US when I was six, so it was right before we moved.

**43:28** · I saw a magazine cover and had a computer on the magazine cover.

**43:33** · And somehow I decided I was going to become a computer programmer.

**43:39** · Never seen or touched a computer, but I decided that.

**43:42** · I think my defining characteristic is I'm very stubborn.

**43:44** · I never change my mind.

**43:46** · And fortunately, I loved it.

**43:48** · So when I was in high school.

**43:51** · I was that kid.

**43:52** · And this was a while ago.

**43:54** · I was in the lab programming all the time.

**43:58** · So boring story, I still love it to this day.

**44:04** · And I loved it so much that I really decided I had to get a PhD.

**44:08** · I needed to understand the material.

**44:10** · It wasn't about anything other than really love for the material.

**44:15** · Becoming a professor was natural.

**44:17** · I came to Google because I had been a professor for 12/13 years and actually never had a real job.

**44:24** · I had jobs in research labs, but that didn't count.

**44:26** · So I said, if I'm teaching all these people, I better know something about what it's like to be an industry.

**44:31** · So I came to Google on a one-year sabbatical.

**44:34** · I loved being a professor, and actually I was quite haughty about people working in industry, meaning I couldn't understand why anyone would want to work in industry, no offense to anyone here, because I was so biased.

**44:48** · I admit I was biased.

**44:50** · I got to Google-- very, very fortunate.

**44:53** · So Google, at the time I joined, in 2010, there were seven people between me and the CEO.

**44:59** · All seven of them, including Eric Schmidt, the CEO at the time, had a PhD in computer science.

**45:05** · So here's this guy who knew nothing about industry, literally nothing.

**45:10** · Any other place I would have gone, I think there would have been like \[? organ ?\] rejection, or I would have been like, oh, I was so right.

**45:15** · Industry is terrible.

**45:17** · Google was a match to me.

**45:19** · And it took me a while, probably three years, to figure out that I was having so much fun that I wouldn't go back to being a professor.

**45:27** · But I miss it, actually.

**45:29** · And I love it, a fantastic job.

**45:31** · One of the best jobs ever.

**45:33** · But the opportunity to really put ideas into practice-- and Google is the kind of place where, yes, it is about business impact and it's about the outcomes, but it's also about doing the right thing for people, our users, and doing the right thing about before for technology.

**45:50** · In other words, like solving hard technical problems really valued at the company.

**45:54** · Good question.

**45:55** · And I think there are a lot of good firms out there, honestly.

**45:57** · So I think it really-- I'm very optimistic about the space.

**46:01** · And I think there are a number of strong firms-- really was a valuation of their technology, valuation of their people, how far along we were with them relative to others.

**46:12** · Really, I wouldn't read too much into it about this one is the very best, or this one is the second best, et cetera. \[? Kairos ?\] is fantastic.

**46:20** · We're big believers, obviously.

**46:22** · But I think there's going to be a number of winners in this area.

**46:25** · Good question.

**46:26** · What do you see as next for TPUs to beat GPUs, or is that even a goal?

**46:31** · Not even a goal.

**46:32** · I do get this question fairly frequently.

**46:34** · I think it's a good and reasonable question.

**46:36** · But I think that the good news is that the market is expanding so dramatically that there is no beating or there's no competing per se.

**46:44** · In other words, there's no winning and losing.

**46:47** · I think it's about driving impact.

**46:49** · So we buy and sell a huge number of GPUs.

**46:53** · We use a huge number of GPUs.

**46:54** · GPUs are fantastic products.

**46:56** · And I think they're going to-- I have, by the way, all the respect in the world for Jensen-- would call him for advice on a number of things, for sure.

**47:07** · He's amazing.

**47:08** · His company is amazing.

**47:09** · But I would say that we're going after different domains and different customer use cases, et cetera.

**47:16** · What I'll say broadly is for TPUs, we just a couple of weeks ago announced our latest eighth-generation TPUs-- 8i, "i" stands for "inference," and 8t, "t" stands for "training."

**47:28** · So for the first time we're launching two chips in one year.

**47:32** · Why am I mentioning these two?

**47:34** · It's because we, for the first time, are specializing the TPU line.

**47:38** · In other words, previously, we had one chip for both serving and training, and that was the right decision based on everything we could see, because we could have probably-- we always could have built two chips.

**47:48** · But if one chip is 5% better for one and the other chip is 5% better for the other, it's actually better to have the one fungible chip.

**47:56** · Right now, the needs are diverging so much that we're actually seeing big uplift, major uplift in specializing for inference and training.

**48:03** · What I see coming moving forward is further increase in specialization.

**48:09** · Why?

**48:10** · Because general-purpose CPUs, they, for many years, a decade plus have slowed in their rate of performance efficiency improvement year over year.

**48:19** · So what that means is that now you actually have to pick the workloads that are large, and you can't necessarily say, hey, just wait a year and your CPUs will get twice as fast, because that won't be good enough to keep up with the demand.

**48:32** · We have to pick our big workloads-- inference and training are two great examples-- where we can now say, hey, we can actually do something, let's say, twice as good because we specialize.

**48:41** · The lesson in hardware design is the more you specialize, the better performance you can get for the subset of workloads that you can run.

**48:50** · CPUs aren't going away, like they're general-purpose.

**48:53** · They can do anything.

**48:55** · A TPU can't do anything.

**48:56** · But for the domains where it runs, it's literally 100x more efficient than, let's say, CPU.

**49:02** · So we're in the process of finding those use cases one by one and saying, OK, now-- and maybe it won't even be a TPU.

**49:11** · Maybe there's going to be some other big workload that doesn't require tensors, matrix algebra, maybe, or there'll be some other one that needs a different system balance point.

**49:22** · By the way, that's the key observation between 8i and 8t.

**49:25** · The memory-to-compute to networking ratios are different.

**49:28** · So you actually would design the chip differently because that's what that application needs.

**49:32** · We're going to keep looking and specializing for the different domains.

**49:37** · The question is around unblocking your own production bottlenecks from vendors and suppliers like TSMC.

**49:44** · Yeah, we're deeply engaged across the supply chain.

**49:48** · So I say the simple answer is it's a domain that we're comfortable with.

**49:55** · My team right now is in Taiwan and South Korea and Thailand, et cetera, as well, as we speak.

**50:03** · So it is a complex issue, but I am actually not worried about being able to secure supply, our fair share of supply at Google.

**50:13** · I think the challenge is, again, it comes down to the efficient use of that capacity.

**50:18** · That's going to be as key as anything.

**50:20** · Now, the total demand in the world is going to be significant.

**50:24** · But I think from a supply-chain perspective-- maybe I'll just give a generic answer.

**50:29** · If you are a vendor for a component-- let's say it's a capacitor-- do you want to have one customer?

**50:39** · I'll leave it as a hypothetical.

**50:42** · And Let's say that customer was going to say, I'm going to buy you out for three years.

**50:47** · All your capacitors, whatever you got, I'll buy it all out.

**50:51** · I would say that's not good for the vendor, actually.

**50:53** · Even if they might make more money in one or two or three years.

**50:58** · So the flip side of it is as component vendors, they want to have some diversity, again, whatever it is, SEC filings.

**51:08** · How many customers make up 90% of your revenue?

**51:13** · If that answer is one or two, investors aren't super happy, because now you're beholden to exactly one or two customers.

**51:21** · I think this is a misunderstood point.

**51:23** · And I'm going to try to connect to different questions here just to help synthesize, because we're lucky enough to have a professor who's better than me.

**51:30** · But if you've noticed many times when you guys ask questions, you place some context, and there's an assumption in there about the industry, and then you ask the question?

**51:39** · And many times I've noticed over the course of the quarter you guys use these words like "winner" or "loser."

**51:45** · There's this embedded zero-sum mindset that I've picked up in this class.

**51:50** · And I don't know why that is.

**51:52** · But it's a constraint of your own making.

**51:57** · There's no such thing as winners and losers in the real world.

**52:00** · They're just people who get shit done and who don't.

**52:03** · People who have impact and who don't.

**52:05** · So I would encourage you guys to really think first principles about some of these assumptions.

**52:12** · Just here, we've had somebody who-- his answer just demonstrated that.

**52:15** · He said-- I think the question had some assumption like, oh, NVIDIA is locking up all the production at TSMC.

**52:21** · What are you going to do about it?

**52:22** · Are you going to lose?

**52:23** · He's like, well, actually, it turns out vendors don't want concentration risk.

**52:28** · If you break down, from a first principles, how their business works, then you can see they actually want Google to have some percentage of their production demand.

**52:35** · And in infrastructure in mission-critical supply chains, you need to have redundancy built in, because earthquakes happen.

**52:41** · Geopolitics happens.

**52:42** · And if you want to be a reliable, stable partner to your customers, you plan for that.

**52:47** · So generally, I would-- just let's tone it down a little bit on the whole competition stuff, because it only holds you back.

**52:57** · Have an-- I don't know if you agree with this, but-- \[INAUDIBLE\] I'm fine with the questions, by the way.

**53:01** · But I think the advice back is great, in that, really, I view what we're doing at Google as participating in an ecosystem to lift the entire industry, but also lift all the users.

**53:13** · It's not going to happen on the back of any one company.

**53:15** · There's no one company that's going to come out of this as the winner, for sure.

**53:19** · There's going to be many winners.

**53:20** · And by the way, the other thing that is true is the huge number of the winners haven't even been invented yet.

**53:28** · Some number of you in this room are going to start some of the winners, no doubt over the next several years.

**53:34** · There's going to be use cases and opportunities that none of us, certainly not me, can predict that you all are going to invent.

**53:41** · There's going to be a lot of winners.

**53:44** · One caution I want to say, though, is we are also going through-- and this is not about companies-- a time of societal transformation.

**53:51** · So if I may just-- I know this isn't on the topic of this conversation, but it's top of mind for me.

**53:56** · I would also encourage this group, who is thinking about technology to also think about our responsibility as technologists to make sure that we are building in guardrails and safety as we deploy our inventions in terms of how we help drive the societal transformation.

**54:12** · I think five years from now, 10 years from now, how we work, how we live, how we learn is going to look a lot different.

**54:18** · And we do want it to also be better as a whole, maybe hopefully significantly better.

**54:24** · And in the ecosystem as this transition is happening, it's stressful for a lot of people.

**54:29** · There's fog of war.

**54:30** · People don't know.

**54:30** · Information is not being disseminated out.

**54:33** · What are some areas of is a misalignment across the ecosystem that you would encourage, not just them, but other speakers in this class who are watching each other's lectures to think about?

**54:43** · Oh, it's a great question.

**54:45** · By the way, congratulations to you and Michael in terms of this class.

**54:48** · And all these students and these thoughtful questions, I'm just blown away, honestly, by the-- It's all \[? Mike ?\] behind the scenes.

**54:54** · --quality of the discourse here and the fantastic questions here.

**54:59** · Blind spots?

**55:00** · I think that-- frankly, I thought that your feedback to the room here is fantastic.

**55:05** · Probably across the ecosystem there is a notion of a single winner a bit too much, and probably also a bit focus on individuals winning and losing, that pairwise fight.

**55:22** · I won't name any names.

**55:23** · You all know what the names are.

**55:24** · But person X is out against person Y. And I don't how much value that's adding to anybody.

**55:31** · From your perspective, what do you think true bottlenecks are?

**55:33** · Yeah, it goes back to the question of, what you would study if you were coming out of Stanford?

**55:37** · There is no one bottleneck.

**55:39** · What is the primary bottleneck?

**55:41** · Honestly, it shifts daily, weekly.

**55:44** · Yes, I hear about memory getting locked up in the supply chain or some other issue that might be coming up.

**55:51** · On a particular day, the bottleneck might be the reliability of a particular cluster for training our next foundation models, that might be the bottleneck.

**56:00** · I would say the one that I have least understanding of the solution is energy.

**56:08** · In other words, I can roughly make up answers that I have some confidence in for most topics, but for us to scale energy to the level that we need to across the planet, there are ways to do it.

**56:22** · A lot of them are brute force and expensive-- and expensive, not just in dollars.

**56:28** · So the biggest innovation bottleneck, I would say in terms of really getting what we need, an energy abundance, which also means affordability is-- yeah, it's probably energy.

**56:42** · And in the energy space, which solutions do you think are being underexplored or which vectors could be more systematically explored?

**56:54** · I think that here in the US, we could look a lot more at wind, solar, batteries.

**57:04** · We are at Google, for sure.

**57:07** · But this is a manufacturing and scaling process that has some physics involved with it, and physics meaning just some time.

**57:16** · So this is an area where we probably underinvested, again, as a community.

**57:22** · Two days ago, there was a company that just announced some money they'd raised to build data centers as a network of distributed floating \[? pods. ?\] Is that a promising vector?

**57:36** · How would you analyze that solution?

**57:38** · Yeah, and, of course, we and others are looking at data centers in space.

**57:41** · I think that there are a number of really in-space energy 5x more efficient.

**57:47** · And if you get into a sun synchronous orbit 24/7, no or very little battery needed.

**57:53** · I would say there are a number of promising directions like this.

**57:57** · They're all fairly far out, and all carry some risk.

**58:00** · So for me, it would be a portfolio.

**58:03** · The proven technique elsewhere in the world is solar, wind, battery.

**58:09** · And pretty affordable, pretty fast to manufacture, pretty fast to stamp out significant capacity deployments in short amounts of time.

**58:18** · Well, when you say far out, you're talking roughly a decade or so of-- 5 to 10 years, we can argue, 5 to 10 years.

**58:24** · It's pretty short.

**58:24** · It's pretty short, but we have a lot to do over the next, a, with some risk, and we have a lot to do over the next 5 or 10 years.

**58:31** · The question is, at what point does the hardware stop being a bottleneck?

**58:36** · No point in the future that I can see does the hardware stop being a bottleneck.

**58:40** · So in other words, I would say that right now, massive model innovations, but also massive bottlenecks.

**58:48** · So we are in a place right now where-- Rich Sutton won the Turing Award a couple of years ago.

**58:54** · He wrote this article-- I encourage you all.

**58:56** · It's short.

**58:56** · It's an essay-- called "The Bitter Lesson."

**58:58** · And it says 70 years of AI experience as throw more compute at the problem, and you're going to get better results.

**59:05** · And we're living that.

**59:08** · I don't see-- again, I'll go with the 5- or 10-year view.

**59:11** · I don't see computes not being a bottleneck for the next 5 or 10 years.

**59:15** · I'd wait.

**59:16** · Personally, I'd go longer.

**59:19** · I'd go much longer, probably.

**59:20** · But here's the way I'd look at it, if we came up with a massive algorithmic breakthrough-- and if you think of transformers, before transformers, there was a previously dominant algorithm for learning LSTMs Long Short-Term Memory, transformers roughly 5x more efficient-- same results, five times less compute, amazing.

**59:41** · If we had another transformers like-thing, transformers prime, 5x more efficient, I'm pretty sure that we'd still be constrained on compute.

**59:52** · All that capacity would get used usefully, maybe not overnight, but quickly.

**59:59** · The question is, how you thinking about infrastructure equity of access of and the impact on the environment?

**1:00:07** · Yeah, I love this question.

**1:00:09** · I appreciate this question.

**1:00:10** · Our goal at Google, my goal at Google is that our data centers should be a uplift for the local community and an uplift for the grid.

**1:00:19** · So whether it's noise, water, and power, across the board, the goal is that these should all be viewed as positives.

**1:00:28** · Of course, jobs and access to the technology, but we, in my opinion, must be coming with uplift to the community.

**1:00:36** · There are concerns, by the way.

**1:00:37** · I don't want to understate them, et cetera, across the country, across the world, but we really are working proactively.

**1:00:44** · Let me give an example here.

**1:00:46** · PUE, Power Usage Efficiency-- historically at Google, up until the last few years, we had two designs that we considered for how we build our data centers.

**1:00:57** · One that was more power-efficient by 10%.

**1:00:59** · 10% is a lot.

**1:01:00** · That says if you have a gigawatt, you're 10% more efficient.

**1:01:03** · That's 100 megawatts that you now get to use that you otherwise wouldn't be able to use.

**1:01:09** · Two designs, one that used more water and one that used essentially no water.

**1:01:15** · The one that uses no water, 10% less power-efficient.

**1:01:19** · As a whole, maybe that makes sense.

**1:01:21** · Maybe that makes sense from our bottom line to say, well, go use more water, but you get 10% power efficiency.

**1:01:27** · But in a particular community, that could make zero sense.

**1:01:31** · That would be a huge net-negative for the community.

**1:01:34** · So what we've done-- what I've done is we've said what, actually, unless there is abundant water in a particular community where the community would say, actually, we'd rather-- you use less power, we're going to go in with the less power-efficient design, but the one that uses almost no water.

**1:01:50** · That needs to apply across the board.

**1:01:53** · In other words, this needs to be a asset.

**1:01:56** · Another example here is, we've recently developed technologies to have a gigawatt of demand response across the country.

**1:02:05** · What this means is-- I told you about how the grid overprovisions.

**1:02:09** · They overprovision for the homes, the communities for that one week of the year where whether it's the coldest or the hottest, where they have to have the most power available for people's homes.

**1:02:21** · What we want to be able to do is we want to say, OK, we'll take power the one week of the year, the two days of the year that you need it.

**1:02:28** · You tell us.

**1:02:29** · And we'll give you back 100 megawatts.

**1:02:31** · We'll power things down on our data centers.

**1:02:33** · This goes back to the 99% reliability bit.

**1:02:36** · So we'll work with the utility where actually now, they can provision less while guaranteeing that the houses, the homes, and the community that need them have the power that they need without having to have 2x the provisioning for the bad two days or the bad week of the year.

**1:02:51** · We're happy to take that downtime.

**1:02:53** · We're happy to be, again, an asset to the grid, an asset to the community.

**1:02:56** · We have to do more by the way.

**1:02:58** · I'm not at all suggesting that this is done, but we very much are taking this-- I'm very much taking this super seriously.

**1:03:04** · And what should-- we wrap on this note.

**1:03:06** · What should other-- let's say that's what you're doing there.

**1:03:10** · What should other cloud infrastructure-- what should other infrastructure folks who are scaling capacity in the ecosystem be doing more of that you think we're not doing enough?

**1:03:18** · I'll cast in the positive.

**1:03:20** · What I'm proud of is that when we say-- and this goes back to even the first question, so it's coming back our first discussion point that you raised.

**1:03:27** · We're not trying to figure out how to build capacity at any cost.

**1:03:30** · It's not, hey, we need a gigawatt.

**1:03:31** · We've got to go spend 40 billion or 40-- whatever the number is.

**1:03:34** · It's optimal scaling is the goal.

**1:03:36** · It's optimal scaling.

**1:03:37** · And that is efficient delivery of that capacity for our users, our customers.

**1:03:41** · But it's also, how do we make sure that actually we're a good asset, a community asset, and welcome-- that gigawatt is not just an abstract gigawatt in somebody's spreadsheet.

**1:03:49** · It's a massive deployment in the state of Utah, and it needs to be an asset for them.

**1:03:54** · And that check mark needs to be there.

**1:03:56** · So I would encourage all hyperscalers, all builders of capacity to be thinking of it end to end, not just go get me a gigawatt, but use it efficiently, deliver it effectively, have it be an asset for the community.

**1:04:10** · Thank you.

**1:04:10** · We might need some of your professorial insights on how we do that.

**1:04:14** · Anyway, thank you so much, Amin.