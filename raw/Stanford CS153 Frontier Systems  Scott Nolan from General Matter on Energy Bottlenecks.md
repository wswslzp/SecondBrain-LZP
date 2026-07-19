---
title: "Stanford CS153 Frontier Systems | Scott Nolan from General Matter on Energy Bottlenecks"
source: "https://www.youtube.com/watch?v=wisccQYTRQc&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=7"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=wisccQYTRQc)

## Transcript

**0:08** · We are super lucky to have with us today, to talk about energy bottlenecks, Scott Nolan.

**0:14** · Welcome, Scott.

**0:14** · Thanks.

**0:15** · Yeah, thanks for having me.

**0:18** · I'm excited to be here.

**0:19** · So if you remember, we started the class by talking about how we're going through a great transition, right?

**0:26** · So we have the old system stack that is transitioning to the new system stack.

**0:31** · And to go back to our organizing mental model and metaphor for the class of the AI factory, you guys remember this, right?

**0:41** · This is how intelligence is being manufactured, the frontier-- pre-training, mid-training, post-training, deploy to agents, rinse and repeat.

**0:50** · And for the last few weeks, as you guys have heard from folks like Mati at ElevenLabs, Andy at Black Forest Labs, and Amit at Luma, those are all different types of intelligence that are being figured out in the field right now.

**1:10** · Today, we're going to zoom out a little bit because sometimes it can get easy to forget that what's happening at AI labs-- sure, it's exciting, right?

**1:24** · We're getting new capabilities that have never been possible before, and that is what's driving so much growth in the industry right now and excitement and revenue and all of that.

**1:34** · But that's just one part of what's going on because to deliver new capabilities to the world, it takes a number of things to come together, right?

**1:43** · And we talked about how there are some major bottlenecks on that progress of capabilities.

**1:51** · And one of them, as we've talked about before, is compute.

**1:56** · But the point of this class is to try to give you sort of a macro systems view of what's going on in the world, not just in model labs but up and down the stack, OK?

**2:09** · And I find the stack, the whole idea of a stack even, is quite rigid sometimes because it kind of presents this view of how things work, when, ultimately, it's just one type of mental model and scaffolding.

**2:24** · And as you know, we've been talking about a different kind of mental model and scaffolding, which is a frontier AI pipeline.

**2:31** · And what I'd like to do is zoom out a little bit now, OK?

**2:35** · This is my handiwork.

**2:39** · I'm not a professional artist, but this is my attempt to try and be as close to Hayao Miyazaki as I can, being I grew up watching a bunch of Studio Ghibli movies.

**2:53** · And this is sort of a stylized mock-up of what I think is a systems-level view of how these capabilities factories are working.

**3:04** · And so if you look, right at the center of the factory, we've got the pipeline-- data, compute, algorithms, pre-training, foundation models, mid-training, and so on.

**3:13** · But to make that work, it takes a whole other bunch of systems to come together.

**3:20** · Now, if you look at the right side of the factory, you got a little box there that I call-- think about that as analogous to the data center that's providing compute.

**3:31** · And we talked about in lecture 1 how compute is super critical, it's important.

**3:34** · But remember, that's just one bottleneck.

**3:37** · Sometimes what gets lost in the conversation is that powering the data centers is a whole other important thing called energy and electricity.

**3:48** · And to keep your compute running on time, well, somebody's got to power the data center.

**3:54** · And we are going through-- well, I would say we've been now in four years of relentless pressure on that part of the supply chain because after ChatGPT came out in late 2022, that turned out to be this-- so for a long time before ChatGPT came out and scaling laws had been discovered, big question on everybody's mind was, what is AI going to be useful for?

**4:22** · I mean, it's cool technology, but really, how is it going to change the world?

**4:26** · And ChatGPT, I would say, was the first consumer killer app.

**4:30** · It became this way to consume the technology of language models that were legible to everyday people, but the supply chain wasn't ready for that.

**4:40** · It takes two years to tape out chips and stand up data centers.

**4:45** · And so in early 2023, a few months after ChatGPT came out, there was a huge compute crunch and, for a short window of time, also a huge energy crunch.

**4:54** · At that moment in time, a bunch of us in the industry who were paying attention to what was going on started realizing, wait, if this continues, we're not going to be able to keep the progress going because at some point in the future-- cool, we had a consumer killer app now with ChatGPT, but at some point, somebody's going to figure out an enterprise killer app, some tool or way to use this technology that's useful to enterprises and businesses.

**5:22** · And that's what happened, right?

**5:23** · What happened in December 2025, a few months ago?

**5:28** · Claude 4.6 came out.

**5:31** · Anyone remember that?

**5:33** · How many of you were coding over the winter break?

**5:38** · Yeah.

**5:39** · Did it feel different?

**5:41** · Right?

**5:41** · And then all the adults-- well, you guys were students, so you had some free time, but all the adults who were on parent duty came back from winter break and started using Claude at work.

**5:53** · And stuff started to change because now suddenly you've got enterprises and businesses going, hey, this is really useful.

**6:00** · We want more of this stuff.

**6:03** · And that was a Groundhog Day moment.

**6:05** · Now, for me, it wasn't that surprising because, as you know, four years ago when ChatGPT came out, that's when I realized compute was going to be a bottleneck.

**6:13** · I started working on a version of trying to unblock that bottleneck at a16z.

**6:18** · But elsewhere in the industry, there's a guy called Scott who was realizing that energy was going to go through a similar problem, because if you just keep going down the supply chain, you realize that that's going to be a huge bottleneck.

**6:31** · And so the reason I have the electricity part of this map so much bigger than the data center map is actually from an urgency perspective.

**6:40** · Even if you have a data center ready to go, if you can't get power to it, it doesn't matter.

**6:48** · It's over.

**6:49** · You can't train models.

**6:51** · And so for this class, we wanted to make sure you got a view into that part of the world as well.

**6:57** · And so for the next few minutes, we're going to get an expert deep-dive into this part of the factory.

**7:06** · Ideally, all of this is just happening in one place.

**7:09** · And at some point in the future, maybe we can have modular data centers on campus next to the lab with a modular reactor or something.

**7:17** · We're not there yet.

**7:18** · And so instead, we have data centers in one part of the world and energy power generation in other parts of the world.

**7:25** · So this is a glorified, idealized, utopia schematic here.

**7:29** · But for this lecture, we're going to be zooming in to energy.

**7:34** · So with that, why don't we start with you, Scott?

**7:37** · Thank you for coming.

**7:39** · Tell us about yourself.

**7:40** · How did you get here?

**7:41** · Cool.

**7:41** · Yeah, thanks for having me.

**7:43** · So, Scott Nolan, CEO of General Matter.

**7:46** · We are a uranium enrichment company for nuclear energy.

**7:50** · I started off as an engineer.

**7:51** · I was a mechanical undergrad, aerospace master's.

**7:55** · That was Cornell, and I ended up coming to Stanford for a second master's degree, in business, of all things.

**8:02** · But I said in a lot of engineering classes, they were pretty much all of my electives, including some CS classes.

**8:07** · So did that, wrapped that up in 2011, joined Founders Fund, the VC firm.

**8:13** · I was there for over a decade, just fully focused on anything hard tech, anything engineering, technology driven, and that included energy.

**8:23** · And so one part of energy I had always been interested in was nuclear.

**8:28** · It always felt like this branch of energy production that just had gotten completely forgotten and sidelined as it being a massive mistake for the past 50 years.

**8:39** · And for that decade, I would meet with so many different nuclear companies.

**8:43** · And by 2020, there were starting to be some pretty interesting ones, but they all said the same thing-- that they had no fuel and that they had to get their fuel from Russia, which was really shocking to me.

**8:54** · I dug into it for the better part of 2023 and realized it was all because of this one missing step, which is what we're working on.

**9:01** · So we'll get into it, but for today's class, I think the interesting thing is just this energy topic in general.

**9:08** · How much of a bottleneck is this?

**9:09** · How do we solve it?

**9:10** · And we'll go through that.

**9:11** · Yeah, that sounds great.

**9:12** · So we're going to-- you'd have to take my word for it.

**9:14** · We're going to start with three pretty smart people who talk about energy a bunch as bottlenecks to their businesses.

**9:21** · So first one is Sam from OpenAI, and this is him testifying to the Senate.

**9:30** · You have to tell the truth when you testify to the Senate, so you know this is true.

**9:36** · So everything is going to converge to the cost of energy, to the cost of electricity.

**9:41** · Chips are going to get cheaper, models are going to get cheaper, but energy is fundamentally what you consume when you're running these models.

**9:49** · And one version of this is \[INAUDIBLE\] who was a Stanford professor for a time also, has argued that all costs, all monetary things should be denominated in joules.

**10:03** · And so this gets back to the same sort of thing.

**10:07** · And then you think about Jensen.

**10:11** · And probably his incentive should be to say that chips are the bottleneck or that something about what he's doing is a bottleneck, but even he would argue or admit on the Joe Rogan podcast that energy is actually the bottleneck.

**10:26** · So that's pretty powerful.

**10:27** · And then you go to Elon.

**10:30** · And there's many bottlenecks that he could talk about, but the one that he wants to highlight is energy.

**10:37** · And I think you're seeing this now in some of the plans with SpaceX.

**10:42** · And so I guess I left that out of my background.

**10:44** · I was an engineer.

**10:45** · I worked at SpaceX right out of school and then did a bunch of other stuff before Founders Fund.

**10:51** · That was before you came back for grad school, right?

**10:53** · Before, yeah.

**10:54** · I did everything backwards, basically, but-- Better late than never.

**10:57** · --it's OK.

**11:00** · And then it's like, OK, well, these are people at the very forefront of data centers of the models, thinking about what's coming next.

**11:08** · But then you go mainstream, and you realize, well, even the Financial Times is realizing this.

**11:13** · They're realizing that, actually, what's upstream of data centers and all the compute is power, and you really need power.

**11:18** · And then where are we going to get it from?

**11:21** · And we'll have some time after these slides to talk about some theories about this.

**11:27** · But you then might ask, well, OK, how big a problem is this really?

**11:30** · Is this really something that we can easily tackle?

**11:33** · You mentioned, OK, let's talk about energy, electricity.

**11:36** · It just sounds, to most people, like so unexciting and boring.

**11:40** · Oh, it's big metal wires and infrastructure.

**11:43** · And why do we care about this?

**11:44** · Certainly, someone has this solved.

**11:45** · How could that possibly be a problem?

**11:47** · We've been doing it for a hundred years.

**11:52** · But then you look at the demand, and you realize, wait, this is way super linear.

**11:58** · And how are we actually going to keep up with this?

**12:00** · And then you say, well, OK, maybe it gets to a terawatt.

**12:04** · In a decade, it gets to a terawatt.

**12:06** · That's pretty fast, but maybe we can keep up with that.

**12:10** · Maybe it's not so hard.

**12:11** · And then you look at what we've actually done over the past-- in this chart you've got over years x-axis.

**12:20** · And you look at the last 20 years, and you realize, wait, we haven't done much of anything.

**12:24** · And in fact, one terawatt's kind of a problem based on what we've been doing.

**12:32** · We need to be much more on a China-like slope.

**12:34** · Or you look at the yellow portion of this, and you realize, wait, we need to be on a very different slope even than China.

**12:42** · And so we have to go from almost a complete standstill on grid expansion to nearly vertical.

**12:47** · And so that's going to require some very different activities than what we've been doing as a country for a long time, for longer than pretty much anyone in this room has been around.

**12:57** · So I think with that, you quickly realize, OK, it does seem like maybe electricity is the bottleneck to AI.

**13:06** · Maybe Jensen and Sam and Elon are all on the same page because this is so overwhelmingly obvious that you have to solve this.

**13:13** · And then you would say, well, OK, how are we going to solve this?

**13:17** · This is clearly a big problem.

**13:20** · We haven't done much.

**13:21** · How do we go really quickly on ramping production?

**13:26** · And if you rewind to five years ago, stranded energy was enough.

**13:31** · So there was-- Could you define stranded energy?

**13:33** · Yeah.

**13:33** · So there was plenty of stranded energy, and stranded energy would be things like a hydroelectric dam in some rural region that there's no population nearby really consuming it.

**13:44** · Or maybe it's geothermal, isolated geothermal with existing technologies that no community to consume it or stranded wind in West Texas.

**13:53** · The list goes on and on, anything like that, something where there's supply without real demand.

**13:58** · And so what you saw late 2010s, early 2020s, that was completely dominated by companies that said, OK, I see that stranded power.

**14:05** · I'm going to go build something there.

**14:07** · The very first builds that happened were typically Bitcoin mining centers.

**14:14** · Yep.

**14:15** · You didn't have the really huge AI data center demand, but you did know that, OK, what can I do with stranded power?

**14:21** · I can mine Bitcoin.

**14:23** · I don't need that much connectivity.

**14:24** · I don't need fiber.

**14:25** · I can get by with iridium or something if it's middle of nowhere.

**14:28** · I can get enough connectivity to actually perform that.

**14:33** · And so you saw companies like-- on the left is a company called Crusoe, which now is doing the Stargate project in West Texas.

**14:44** · And that project is linked up with wind and natural gas and all sorts of things, some of it which was stranded.

**14:51** · And so that was a great strategy for a long time.

**14:54** · At this point, most of those great resources that were stranded without nearby demand have been claimed.

**14:58** · People have gobbled those up.

**15:01** · And the capacity that we need is increasing quite a bit, and so even those small chunks of electricity that were available would not even be enough today to satisfy things.

**15:12** · And so things are really moving to ask the questions of, how can we create massive net new power production?

**15:20** · And so this was something I was starting to think about, both the stranded topic and the bigger topic, at Founders Fund late 2010s, early 2020s, and coincidentally invested in-- if the top left is Crusoe, then invested in all of these companies.

**15:36** · And so top left is a data center just like Crusoe.

**15:40** · I don't actually think it's a Crusoe one.

**15:42** · You've got SpaceX, which is now talking about in-orbit power production.

**15:46** · And then you've got a company called Panthalassa doing distributed energy in the ocean.

**15:50** · And so lots of different angles on this.

**15:52** · People have different theories.

**15:54** · We can talk about in-orbit.

**15:55** · We can talk about other options.

**15:56** · But today, we'll talk about on-land because that really dominates things, and that's the reality that we're living in.

**16:03** · And so you say, OK, well, we need to produce a lot of power on land.

**16:06** · What are the constraints?

**16:07** · What are we designing for?

**16:09** · What are the things that the data centers actually care about?

**16:12** · And one of the big things they care about is uptime.

**16:15** · So data center, can you run it on solar?

**16:18** · Can you run it on wind?

**16:19** · You could, but you're going to need a lot of batteries.

**16:21** · And by the time you had enough batteries to get this uptime, at least those batteries exist today grid scale, your cost is going to be pretty high.

**16:29** · And so people have gone away from that.

**16:33** · What you're seeing today, the last couple of years, is a lot of natural gas-powered data centers running on turbines.

**16:39** · Turbines are getting pretty scarce.

**16:41** · The lead time for turbines is a few years now, which has increased drastically.

**16:47** · And the producers of turbines generally are not ramping production quickly enough to even remotely keep up with this.

**16:54** · And so then you say, OK, well, we need something that's not natural gas, can be baseload.

**17:00** · Where do we look?

**17:01** · And you might say, well, OK, what are the other factors?

**17:04** · Maybe we don't want to put out a lot of carbon.

**17:06** · Maybe we want it to be pretty safe.

**17:08** · And so then you look at the historical statistics, factoring in every plant that's ever been built.

**17:14** · And you realize that-- here's the baseload chart.

**17:18** · Then you realize, looking at safety and cleanliness of power source, that, actually, nuclear is pretty good.

**17:24** · It's actually lowest carbon emission of any of them, and it's essentially tied for safest with wind.

**17:31** · And so those two things together, if you care about safety or emissions, it's going to push you pretty hard towards nuclear.

**17:39** · And that's why all the hyperscalers are looking to that.

**17:43** · I think they all realize nuclear is not going to be something where you build a plant overnight.

**17:47** · It's not a one-year project.

**17:48** · It's something that we're going to see ramping in the next 5 to 10 years, truly ramping and moving the needle.

**17:53** · Until then, it's kind of a race who can find stranded power, who can find enough turbines, who can maybe stand up solar with enough battery storage if they're less cost sensitive.

**18:04** · But long term, everyone's looking to nuclear.

**18:07** · And so then you say, OK, well, if nuclear is the long-term scaling limiter to electricity, 5- to 10-year time frame, and electricity is the bottleneck to AI, then you probably realize, well, that's kind of unexpected, but maybe nuclear is actually the bottleneck to AI scaling, if you're talking about here on land at least.

**18:30** · And so then you might ask the third question, well, OK, is there a bottleneck to nuclear, which brings us to what we're working on.

**18:36** · Every nuclear reactor runs on fuel.

**18:38** · I think a lot of people hear nuclear, and you would think it's a magical technology, it's like a perpetual motion machine.

**18:45** · But no, you actually need to refuel it every year or two, depending on the reactor.

**18:49** · For more advanced reactors, there's some that are designed for 5- to 10-year refueling cycles, but it does require constant fuel, and it constantly burns up fuel, just like any other type of engine.

**18:59** · And that fuel comes from five different steps.

**19:02** · You start by mining.

**19:04** · You turn it into a gas.

**19:05** · You enrich it.

**19:07** · You turn it back into solid, and then you make your fuel pellet.

**19:09** · And you might then think, just like electricity, well, this is a solved problem.

**19:14** · What could be the issue?

**19:16** · But you actually look at these five steps, and it turns out that the US has less than 0.1% market share today of enrichment, which is the middle step.

**19:27** · And so the US is actually unable to produce its own nuclear fuel at any scale whatsoever, and we rely completely on European firms and, even to this day, Russia.

**19:38** · Even though there's sanctions, we still import because we really need to.

**19:43** · And so there's this missing piece right in the middle.

**19:47** · And so we can't really scale nuclear fuel as a country, which means we can't really scale nuclear, which will mean that we can't scale data centers in AI.

**19:59** · And if scaling is one thing, cost is another.

**20:02** · At some point, the cost will matter a lot.

**20:03** · People will start being more price sensitive.

**20:05** · It won't just be an arms race for who can stand up a data center the fastest.

**20:09** · There'll be margin compression.

**20:10** · Costs will matter.

**20:11** · But in fact, cost is the biggest-- of the cost of advanced nuclear fuels, the biggest cost in many cases and the biggest portion of that is actually enrichment, which is why we're working on it.

**20:24** · And so you do the build one more time, and you realize, enrichment is the bottleneck all the way through to AI on a five-year time frame.

**20:34** · And so that's why we're almost in a race against time at General Matter, going as quickly as we possibly can to bring enrichment back online in the US at scale, with a highly scalable method that we think can completely win on cost.

**20:50** · And we're getting a lot of support from that.

**20:52** · So when we started the company, there was no ban on Russian uranium.

**20:56** · There was no AI data center boom.

**20:59** · It was under Biden administration.

**21:00** · We started by working on advanced fuel for advanced reactors, and that was a big push.

**21:04** · And then now this administration is very focused on energy production, and there's follow-through on that push across administrations.

**21:13** · In the bottom right, you can see our August groundbreaking of our facility in Kentucky.

**21:18** · In that image, there's people from the full range of political spectrum all getting together around this.

**21:24** · And so going from the very beginning, you can see the tech leaders are realizing energy is the bottleneck.

**21:29** · All the way to DC, everyone realizes that energy is upstream of everything, not just AI but also manufacturing and pretty much any industry that you want does rely on it.

**21:40** · And the current state of it in the US is far worse and far less ready to scale than a lot of people realize, so that's what we're working on.

**21:49** · Thank you, Scott.

**21:51** · Why don't we take a beat there because you said a few things I want to double click on?

**21:56** · Scott mentioned Bitcoin mining.

**21:58** · And he sort of mentioned that in passing, but the reason I want to zoom in on that is because sometimes the cultural commentary around a piece of technology can often make the underlying progress, that's quite real and clearly of fundamental, confusing.

**22:21** · Nominally, from a meme's perspective, the way this manifests itself on the timeline and so on is people saying SBF funded Anthropic.

**22:29** · SBF was running FTX at the time, the fact that people in the crypto community were investing in AI stuff-- we can disagree on whether crypto ended up delivering on its promises or not, but what we have to acknowledge is that Bitcoin mining was a bit of a dress rehearsal for AI.

**22:54** · And sometimes I get all these questions where-- there'll be a team working on a pretty important fundamental bottleneck at the infrastructure layer, but just because they've raised money or something or have done some political donation or something with somebody from the crypto community, the underlying progress just gets thrown out.

**23:13** · It's like a throw out the baby with the bathwater moment because people go, oh, if crypto people are involved, or Bitcoin mining is involved, because that didn't work out-- and yet, who knows?

**23:21** · At some point, we may have decentralized censorship resistance and so on, and then we will have truly decentralized computing.

**23:32** · These things take a long time.

**23:33** · But from a first principle's perspective, I find it quite sad and disappointing when people aren't able to decouple those two things.

**23:44** · You mentioned Crusoe as an example of a company that you've worked with before.

**23:51** · I think Crusoe was originally a Bitcoin mining company.

**23:53** · Yep.

**23:54** · Right?

**23:54** · And then many of the innovations that they ended up realizing during the Bitcoin era have ended up translating into building infrastructure for the AI era.

**24:08** · And I think those learnings have ended up becoming valuable.

**24:12** · Venture capitalists sometimes like to call these evolutions pivots.

**24:15** · And I think there's an unnecessary stigma around that, when, in fact, pivots are just one step of the continuous feedback loop we've talked about before, in my view, right?

**24:25** · And it's an update, and the best leaders update their priors.

**24:29** · Similarly, as you've been approaching the energy discussion, nuclear is another one of these areas that has been unfortunately plagued by a bunch of confusion, politics, social divisiveness.

**24:48** · What advice would you have for people here who believe that-- they'd like to work on energy, they'd like to work on nuclear, but, for whatever reason, feels like because of the past political climates or social objections to that technology, the fundamental progress is not legible.

**25:10** · Am I making sense?

**25:11** · Is my question making sense?

**25:12** · Yeah.

**25:12** · I mean, you can even go back to that chart, the emissions and the safety track record of nuclear.

**25:17** · Well, we'll talk about nuclear, but going back to what you were saying before, these pivots.

**25:22** · I think pivots is one thing, but I would say, if a company is building something that you can think of more like a primitive, like a fundamental building block, which you might say, well, utilization of stranded electricity feels like a primitive-- and, yes, what we might do with it today is mine Bitcoin.

**25:41** · Right.

**25:43** · We think that this is going to be really useful, and that's what Crusoe's approach was.

**25:47** · They went from Bitcoin mining to saying, well, actually, yeah, we're mining Bitcoin, but we're also massively reducing emissions that are occurring just because this gas was not just stranded.

**25:58** · Because it was stranded, people were just burning off methane straight into the atmosphere with both carbon emissions and particulate emissions.

**26:05** · Right.

**26:05** · And they took it, and they ran it through a turbine and made power and mined Bitcoin and reduced emissions.

**26:10** · And so they felt like, hey, no matter what, even if you discount the value of mining Bitcoin to zero, we're still creating value.

**26:17** · Right.

**26:18** · And we're making money, and we can invest in this infrastructure.

**26:20** · And they took that, and they built enterprise cloud deployments, slightly larger scale.

**26:26** · They would go after bigger projects, not just stranded oil wells in North Dakota but stranded wind in West Texas.

**26:31** · And then they took that, and they leveraged that into something else.

**26:34** · So it's really building this up over time, I think, on top of a basic primitive is probably the way to think about it, even more than a pivot, even though maybe the final, end-state product that people interacted with looked different.

**26:46** · Yep.

**26:47** · And so I think of that as something we're basically doing.

**26:52** · It's something lots of companies have done in the past.

**26:54** · It's something SpaceX did.

**26:56** · It was really, how can we reduce the problem of commercializing space into a fundamental piece?

**27:02** · And that fundamental piece was launch capacity, and you could denominate that in dollars per kilo to an orbit.

**27:09** · And that was a really powerful thing.

**27:11** · If we can just make this cheaper, we can do a lot of really cool stuff with that.

**27:15** · And make something cheaper, you get more of it, and people will build on this and will push forward the commercial space economy.

**27:21** · So that was that thesis.

**27:23** · For us, our fundamental building block that we're working on is enrichment, which is really just refining.

**27:28** · It's refining of, fuel, it's refining of uranium based on its isotope.

**27:32** · And you want to get the fissile isotope in enough concentration that you can run a reactor.

**27:38** · And so that's a very, very fundamental thing to do in a whole sector of energy that's been unfairly put on the sidelines.

**27:48** · And we can talk about why that's happened, but if you can enrich, you can make fuel.

**27:52** · If you can make fuel, you can make 5% fuel, you can make HALEU, you can make these different grades that different reactors run on, and you can supply to anyone.

**28:01** · And so you can supply to the existing reactors that are powering 20% of the grid in the US today with zero carbon emission.

**28:08** · And those utilities are very eager to work with new entrants and to support the expansion that's going to happen.

**28:15** · Or you can work with advanced reactors, which probably are what most people hear about, all the small modular reactors or microreactors.

**28:21** · And you can make them more enriched fuel that they need to get their smaller form factor.

**28:26** · And so I think back to your question of what should people in the room think about when working on a problem, I wouldn't worry so much about what the public narrative of it is or what very surface-level treatment of it tells you.

**28:42** · I would go a lot of clicks deeper, just go all the way to the bottom and figure out, OK, well, what are we actually solving for here?

**28:48** · If we want baseload, if we want it to be clean, if we want it to be very scalable and safe, let's look at the numbers.

**28:54** · And you look at the numbers, and you realize that despite a lot of-- not even a lot-- a few very famous nuclear accidents, and famous partly because it's a hard thing to understand, the safety track record of nuclear is so much better than anything else.

**29:12** · And even accidents like Three Mile Island had, I think, based on all analysis, no direct measurable deaths from that accident.

**29:24** · Same thing with even in Japan with Fukushima.

**29:27** · Maybe there was one fatality but thousands from the tsunami that caused it.

**29:32** · And so nuclear has just been this technology that if you look back to the '50s and '60s, obviously, we were supposed to do two things.

**29:40** · We were supposed to go to space, and we were supposed to have energy that was abundant and clean and very power dense.

**29:46** · And we've done one of them, but now we're finally doing the second.

**29:49** · And so I think it's partly the industry's fault.

**29:52** · I think the government gets a lot of blame, the public gets a lot of blame, but I think a lot of it was actually the industry not making the case for nuclear nearly strongly enough.

**30:01** · Yeah.

**30:02** · And it definitely wasted a lot of time, but no time like the present.

**30:07** · I mean, we're old guys now, but I'm going to date ourselves.

**30:14** · In the 2010s, there was this meme of the "keep calm, don't panic" meme.

**30:19** · Do you remember that one?

**30:22** · It's this red poster.

**30:23** · Yeah.

**30:24** · It's the London Underground one.

**30:25** · It's the London Underground one.

**30:27** · There's also the dog sitting in the burning building, everything's fine.

**30:29** · Everything's fine.

**30:30** · Yeah.

**30:30** · Yeah.

**30:31** · So I think those are two ends of the spectrum, right?

**30:33** · Stuff is burning down.

**30:35** · You're saying it's fine.

**30:36** · And that's cope, and that's one spectrum.

**30:38** · Yep.

**30:38** · But then the other spectrum is, something happens, which always-- something goes wrong in the physical world.

**30:45** · And then everybody panics and overcorrects, and that sets us back for the next decade.

**30:49** · Where in the spectrum should the students-- is there a repeatable way for people to calibrate on where the right place is to be so that you're not just overindexing on the memes and instead actually landing at the right place?

**31:03** · Yeah, I think it's a mistake to get too caught up in the moment.

**31:06** · You have to be somewhat aware of what's going on.

**31:08** · And if you have an idea that's clearly 20 years too early, I think that's not going to be a good thing to work on.

**31:14** · You're probably better off working on something that's more immediately necessary and then come back to that idea later.

**31:21** · But I would just focus on the fundamentals.

**31:23** · And so the framework I always go back to-- I've always found it compelling-- is, what's the really important problem that's not getting solved, that's not going to get solved by someone else, that somehow your skill set lines you up to be really useful for?

**31:41** · And so really just work on those things.

**31:42** · Yep.

**31:43** · That could be at an existing company.

**31:45** · It could be at a new company.

**31:46** · You could start your own company.

**31:48** · It could even be in a nonprofit, in the government.

**31:50** · It could be in lots of different places, but I'd say, work on whatever you're going to be the most useful for that's actually an important problem and find the right place to do that.

**32:01** · I'm guessing questions are piling up, so I'm going to ask a couple more while people get their questions in.

**32:09** · As a proof point for how powerful it is to truly internalize-- when this lecture is live, I would encourage you to go back and listen to every word Scott said, internalize it, and then try and practice it as a proof point of how powerful that framework is.

**32:27** · You started General Matter in January 2024, was it, right?

**32:34** · Yeah, that's when we became a company.

**32:36** · Before that, we were working on this in fall of '23.

**32:38** · And I had been starting on this even in December of '22.

**32:42** · Right.

**32:42** · So you spent about a year truly understanding the problem, doing the five whys in 2023?

**32:49** · Mm-hmm.

**32:50** · Scott then started the company General Matter.

**32:52** · Remember, Scott's never started a hardware business before.

**32:55** · He worked at SpaceX, of course, and got a ton of really great lessons and worked at Founders Fund.

**33:01** · But really, is this the first company you started?

**33:04** · Yeah.

**33:05** · Yeah, first company Scott started, OK?

**33:08** · January 2024, 24 months later, 24 months, Scott announced-- this was January of this year-- that General Matter has been awarded a $900 million contract from the DOE to do uranium enrichment.

**33:28** · Can we get round of applause for that for a second?

**33:30** · \[APPLAUSE\] The rate of progress that Scott single-handedly and the General Ma-- how big is the team?

**33:42** · We're close to a hundred now.

**33:43** · Hundred people have accelerated in such a short amount of time that's so fast that the US government is saying, we're going to hand this hundred-person company startup almost $1 billion contract to help us move the country forward.

**34:03** · And so sometimes the timelines on which you can make a difference, especially if you do the right systems analysis, and you focus on alignment between your mission, your business model, the technology, are quite extraordinary and can surprise people.

**34:17** · But maybe you could take us behind the scenes a little bit on what it took to go from that moment when you founded the company to that contract.

**34:23** · Yeah.

**34:24** · And I would highlight that-- you just mentioned alignment.

**34:28** · The thing that's really aligning is, this is a multibillion dollar project.

**34:32** · And the DOE has said, hey, we want to help.

**34:35** · We want to help accelerate this and help you go even bigger than you would otherwise Right.

**34:39** · And so the contract itself is to help us build that capacity as quickly as we possibly can.

**34:43** · And so the aligning thing is, we'll bring even more private capital to the project in that amount.

**34:48** · Right.

**34:48** · And so I think if you ask, OK, well, how does this come about?

**34:53** · We chose to work on a problem that we believed would not be solved and was completely important and required urgent action.

**35:01** · And fortunately, the DOE congress had already been thinking about this.

**35:05** · They had already funded these programs.

**35:07** · We didn't have to convince them that these programs should exist.

**35:09** · They knew that they should exist, and they were open to new entrants coming in and helping solve it.

**35:13** · And so what it looked like was identifying the problem in 2023, really asking ourselves if this was a thing to work on.

**35:22** · We concluded that, yes, it was.

**35:24** · Pulled the team together in late '23 with all the right people from the industry.

**35:28** · We asked ourselves, OK, what does the right team look like for something like this?

**35:32** · And we handpicked those people from a bunch of different companies that included national labs, other companies in the nuclear energy space, and then people from Tesla and SpaceX because we were going to run a pretty similar playbook to break into a really capital-intensive, incumbent-dominated, stagnant industry.

**35:48** · And so we wanted those exact type of people with that DNA and that experience, and so we pulled the team together.

**35:54** · And then we evaluated, do we want to put our hat in the ring for this program?

**36:01** · And it was completely on the direct path of what we were going to do anyway.

**36:05** · And we said, yes, let's put our best effort forward to do this.

**36:08** · And so first few months of the company was legitimately 100-hour weeks, just living and sleeping at the headquarters and doing all the work that we were going to do over a few years to get the plan extremely buttoned up.

**36:24** · And then became the search for the right site.

**36:27** · So the other thing with nuclear was we knew, yes, we can have the best technology, we can have the best overall plan, but you also need a really supportive community and a supportive location for what you're doing.

**36:37** · And so we're headquartered in LA, but our facility won't be in LA.

**36:41** · Our facility will be in Western Kentucky.

**36:43** · And so that's where we're doing construction and actual enrichment and manufacturing.

**36:49** · And so we found a site there that's in the same city as the last place the DOE, the US, did commercial enrichment in 2013 before it was shut down.

**36:59** · It's called Paducah, Kentucky.

**37:00** · There's a DOE site there.

**37:01** · We originally went there looking for some old buildings that we could use, but then we found that there was a hundred acres at the south end of the site that had not ever been developed and was perfect for what we needed.

**37:12** · And so that was the beginning of the partnership with the DOE.

**37:17** · And, yeah, like you said, they've been extremely supportive of someone new coming in to help try and solve this problem.

**37:24** · I'm going to ask you a follow-up, sort of last question on this.

**37:27** · There's a lot of anxiety, and fear, uncertainty, and doubt about the current administration not supporting science and engineering in the country, but what you just outlined is a direct counterexample to that.

**37:44** · How supportive was the federal government in this?

**37:46** · DOGE, my understanding is there were members of DOGE that helped smooth things along for you.

**37:52** · Is that true?

**37:53** · Or do you feel like the United States is asleep at the wheel and actually not helping entrepreneurs make progress on a bunch of critical infrastructure like the one you're working on?

**38:02** · Yeah, I'd say definitely not asleep at the wheel.

**38:04** · I think going back to something I said earlier, the support for this has been ever since the Biden administration in 2022, 2023.

**38:13** · And so I don't think it's a political thing.

**38:14** · I think we can get into some of the details there, but it's been something where there's been congressional support for, first, doing HALEU, which is the advanced reactor fuel, and then doing LEU, which is what the grid currently consumes.

**38:30** · And so it's a known problem, it's a known opportunity.

**38:33** · We really need to bring this back as a country.

**38:35** · And so, yeah, there's just been a bunch of support from across the political spectrum.

**38:41** · That's the political side.

**38:42** · Then within the government, you have people who have been putting their whole careers into this.

**38:47** · And I think within DOE and the Nuclear Energy Department, those are people that are in it not because nuclear has been growing-- because it hasn't since the '90s-- but because they really believe in it.

**38:56** · And I think, yeah, there's just been incredible support from across DOE for what we're doing also.

**39:03** · So I'd say it's the type of thing that, to your question of should people be worried about what's happening day to day and memes and public opinion, there's certainly going to be ups and downs for nuclear over the next few decades.

**39:17** · I think it's going to be drastically ups.

**39:21** · But there's been the same support, very consistent support, from everyone in the government.

**39:27** · On the topic of jobs, so there's a bunch of jobs you've now created in California, but you also create a bunch of jobs in Kentucky.

**39:34** · Yeah.

**39:35** · Over the next four years, how many jobs do you think General Matter is going to create?

**39:40** · I mean, it's hard to say.

**39:41** · It's certainly hundreds and hundreds of jobs.

**39:44** · Even in LA, it's probably close to 500 over the next few years.

**39:47** · In Kentucky, it's that much or more.

**39:51** · If you go back to the really early days of SpaceX, apparently, they thought the company would ever only be 200 people.

**39:58** · Clearly, that's not true.

**39:59** · It's close to 20,000 now.

**40:01** · So these things have a way of, when you're working on a really important problem that can just keep scaling, I think that's-- maybe my one lesson from over a decade at Founders Fund was things can scale much more than you think, and they often need to scale much more than you think, which goes back to the SpaceX example, off by two orders of magnitude on what headcount would someday be.

**40:23** · And for us, I think just near future, we look at hundreds of people in LA, hundreds in Kentucky.

**40:30** · That'll probably put you at a thousand for doing what we need to do.

**40:34** · So a thousand new jobs created by a startup whose path is definitely accelerated by AI.

**40:41** · To do the five whys-- and Scott kind of walked us through how, arguably, uranium enrichment is the bottleneck on AI.

**40:51** · As you guys have heard multiple times, there's a narrative that AI eliminates jobs and reduces jobs, when in fact, Scott is living proof that entirely new jobs are being created in real time, in the thousands, to unblock the bottlenecks for AI scaling.

**41:08** · And I think this is an important alignment mechanism everyone should be aware more and more, which is, this is not some dream that AI can create new jobs.

**41:17** · It is literally creating new jobs, both in the knowledge sector in California, people who are working on engineering systems for you, but also in the construction industry halfway across the country.

**41:29** · And so I expect to see more and more companies like General Matter, assuming the public understands that AI is actually net new, is igniting a renaissance in the physical world, that we will end up in a place where jobs that didn't exist before are going to be created.

**41:45** · But I don't know if you'd agree or if I'm being overly optimistic.

**41:48** · I'm pretty optimistic.

**41:49** · I mean, in our case, we have dozens of open roles, and we're looking to hire hundreds of people.

**41:55** · We can't find enough good people, not quickly enough.

**41:58** · And so in our experience-- it's obviously different for every company and every person, but our experience is that we want to find more good people and give them jobs.

**42:08** · And so we're in a deficit, and so how do we find enough great people?

**42:13** · So for people that want to work hard and are good at what they do, there's, at least at our company, tons of opportunity across pretty much every type of engineering, every type of construction type role, finance.

**42:25** · You name it, we'll hire people.

**42:29** · I mean, we could do a quick poll before we run to questions.

**42:31** · How many people now feel like they'd be interested in a job working on uranium enrichment?

**42:38** · Great.

**42:38** · Pretty good.

**42:39** · All right.

**42:39** · Looks like 95%, I think, I saw.

**42:42** · Great.

**42:43** · We'll get people connected.

**42:45** · OK.

**42:46** · First question.

**42:47** · Yeah, the question is essentially, DOE contract originally was all the way out through 2034.

**42:52** · That's a long time.

**42:53** · We're here today, almost a decade ahead of that.

**42:56** · What do we do?

**42:57** · People are doing turbines.

**42:59** · How do we scale up to actually make this relevant?

**43:01** · And then what about space?

**43:03** · And so our timeline is much faster than the 2034 timeline.

**43:08** · So our whole goal, because the industry needs it, is to be online before the end of the decade and then to be scaling very rapidly from there.

**43:16** · So we hope we can be on a useful timeline for any reactor that's trying to launch and scale up.

**43:21** · So as they're doing the deployments, first, criticality in many cases this year, demos next year, really scaling '28, '29.

**43:30** · We hope to be really ready for them as they're really scaling.

**43:35** · I think most of the real hockey stick that you'll see on these big-picture charts that we looked at, that'll be early 2030s into 2035.

**43:42** · So we're going to see one-off deployments, I think, in the next couple of years, tens not hundreds of SMRs.

**43:50** · And then for the really big builds, those do take 5 to 10 years to do, gigawatt-scale reactors.

**43:55** · And so there's a little bit more time there, but we're trying to be well ahead of everything.

**44:00** · So our time frame acknowledges that, I think.

**44:02** · Getting back to then the turbine question and natural gas, yeah, it does take five years plus to build a gigawatt-scale reactor in the US, and that's probably being optimistic.

**44:15** · And so in the meantime, you do need to find something else.

**44:18** · And so people have found the stranded wind.

**44:19** · They found natural gas pipelines that they can hook up to.

**44:23** · And then you need the turbines, but now the turbines are sold out a couple of years.

**44:27** · You might need grid, interconnect a lot of that power.

**44:31** · Electronics equipment is out a couple of years at industrial scale.

**44:35** · So I think the next couple of years are almost going to be the hardest of, how do we keep scaling?

**44:39** · How do we not hit the wall while we wait for nuclear to come in a few years' time frame?

**44:45** · And then you asked about space.

**44:47** · And I think the space approach is one that really only one company can do, and it's an answer to all these questions.

**44:54** · And there's some technical challenges that they're going to have to solve, but I wouldn't bet against SpaceX in solving technical challenges, but that'll be their solution.

**45:02** · I think it'll be uniquely their solution to just put some synchronous data center satellites in orbit.

**45:09** · Other people really can't do that.

**45:11** · And so I think everything else will be fought either as-- that's by air.

**45:16** · Everything else will be a ground game and maybe some in the ocean, but I think it's going to be dominated, almost with every other company, by who can scale power on land and therefore who can scale nuclear.

**45:29** · You don't think our friend Jeff Bezos is going to find a way to-- also find a comparable solution in space?

**45:37** · I think even SpaceX would say they hope for that.

**45:41** · Certainly, in the early days, it was like, we don't want this whole industry just riding on us.

**45:46** · The whole goal of SpaceX is to make humanity multiplanetary.

**45:50** · So end goal is that.

**45:52** · SpaceX felt like they had to do it.

**45:54** · If other people could chip in, that's something they would want.

**45:57** · But if you just look at the actual launch volume of SpaceX versus Blue Origin, it's just drastic, and Blue Origin started before SpaceX.

**46:06** · Well, Blue Origin has the advantage of using AI now to accelerate all its engineering operations, which SpaceX didn't.

**46:12** · You guys had to do it all from scratch.

**46:13** · Fair, that's fair.

**46:14** · Yeah.

**46:15** · OK.

**46:15** · We'll see how good the AI engineering agents are, though.

**46:18** · Yeah.

**46:19** · I guess this is what next year's class is going to be about, Mike, the space race.

**46:23** · Yeah.

**46:24** · OK, next question.

**46:25** · Yeah, so two-part question.

**46:27** · One was, what was it like early days SpaceX, and how did that shape how you thought about engineering?

**46:31** · And then two, why did I decide to leave SpaceX.

**46:33** · So part one of the question, really, when I joined, I was an intern at first in college.

**46:42** · It was 35 people, roughly.

**46:44** · We were just trying to get the very beginning parts built and working.

**46:51** · And so it was everything from, let's build test stands that we're going to test the engines on.

**46:56** · The part I worked on was propulsion systems.

**46:59** · And I was a structural thermal analyst on the propulsion team, which was low single digits sort of team.

**47:05** · And so we had to design the test stands.

**47:07** · We had to design our very first, most primitive engines, like heat-sink-based engines.

**47:13** · We weren't even doing full nozzles.

**47:14** · It was just, can we get the combustion to work right?

**47:17** · Let's build the test fixtures.

**47:19** · And so it was relatively scrappy.

**47:20** · It was, how can we make a lot of fast progress?

**47:23** · We don't need to make the fanciest test stand ever.

**47:26** · It just has to work, and so let's do what's fast and relatively cheap and optimized for the things you're trying to optimize for.

**47:33** · And so back then, it was purely schedule optimization and some cost optimization with a hard line on safety.

**47:40** · And so if you satisfied those things, it was, yeah, let's get it built, and let's get it out there, and let's test it.

**47:45** · And then we'll learn a bunch, and then we'll do the next thing.

**47:48** · And so it's really just like, OK, how many of these steps can we just chew through and get to the finish line?

**47:55** · And so fast forward all the way through 2025, 2026, 2027, we got the engines developed.

**48:03** · They were working great.

**48:04** · We got the Falcon 1, the first rocket, launched a couple times.

**48:09** · First time, it didn't make it that far.

**48:11** · It had a fire inside the engine bay area due to an aluminum nut on a fitting on a fuel line that was hooked into a different part of the engine.

**48:25** · And that crack led to a fuel leak which caught on fire and took down the rocket.

**48:29** · Second one basically worked.

**48:31** · It got all the way to orbit, not full orbit, but second stage deployed.

**48:35** · And you had a fuel sloshing issue where a lack of extra baffles allowed, basically, a spiral to form, and second stage went out.

**48:45** · And then at that point, everything-- shortsightedly to your second question, I felt like, OK, the rocket works, the engines work, and maybe it's not going to be as exciting as it was in the early years.

**48:58** · Here's this example of this really important company, SpaceX, founded by someone who's an engineer with some business experience.

**49:05** · Maybe I need to go get business experience.

**49:07** · And so that was my conclusion, but I think it was the wrong one.

**49:10** · As it turned out, the company scaled another over 10x.

**49:17** · People who have stayed there, a lot of my friends, have gotten to work in some of the coolest projects that anyone could work on in the past decade.

**49:25** · And it was absolutely the right place to be for a lot of reasons.

**49:29** · So I think at the time, though, I felt like, oh, 100-person company, that's a big company.

**49:33** · You've got to be at startups when there are three people.

**49:37** · And I felt the same thing about Palantir at one point, about Square at one point, thought about dropping out of different things to go work at these places but felt like, oh, maybe 50 or 60 people or 80 people is too big.

**49:51** · And again, completely incorrect.

**49:53** · A hundred people is actually just where you get into the really hard stuff of scaling a business, seeing how you go from ideas and just product market fit to actually operationalizing and executing.

**50:05** · The people who I know who were at SpaceX during that window of a hundred people to a thousand people, those are the real operators.

**50:12** · They know how to build and run teams.

**50:14** · They know how to do manufacturing, even the people all the way up to 10,000.

**50:18** · So, yeah, there's still two more orders of magnitude to go of learning.

**50:24** · And so definitely ended up doing a lot of cool stuff that I've been excited about, but also really a great decision to stay there for everyone who did.

**50:33** · Yeah.

**50:34** · The question was, how do you grapple with the perceptions of nuclear power in the US?

**50:38** · And then anything we can learn from Europe?

**50:41** · Man, the Europe one is really almost a tragic example of-- there's plenty of learnings there.

**50:46** · So Germany completely shut down its nuclear energy program, shut down its reactors, reactors that were working fine, with the idea being, well, we're going to shut these down, and we're going to do renewables.

**50:59** · And then if you look at empirically what's occurred, they have not replaced it with renewables.

**51:03** · It's almost entirely replaced with baseload, which means coal, natural gas, fossil fuels.

**51:10** · And the consequence has been obviously carbon emissions but even air quality.

**51:17** · You can look at air quality maps of Germany now with no nuclear versus Germany before versus France, which has a great percentage of nuclear on the grid.

**51:27** · You look at their quality, and it's completely blue and clean over France and then completely red over Germany.

**51:34** · And there's other reasons for that too, but it's just completely self-defeating to turn off affordable energy, very cheap energy once it's built that's clean, and replace it with burning biomass and fossil fuels.

**51:52** · No reason for it.

**51:53** · So I think that's a real-life, present-day example of what not to do.

**51:59** · And that alone doesn't prove that you should go build as much nuclear as possible because you could say things like, well, it is expensive to build up front.

**52:10** · Once it's amortized, keep it going, but it's expensive to build up front.

**52:13** · And I think that's actually the next thing that the industry is going to solve is, how do we make it much cheaper to build up front?

**52:20** · And so that's both on-- you see a few startups doing nuclear development businesses, things like the nuclear company Elementl, Oppenheimer Energy, the grandson of Robert Oppenheimer.

**52:33** · And you see all the SMR companies that are saying, we can build these things in factories, make them much, much cheaper, shippable, install at the site.

**52:41** · And then all you need is this fuel source that currently the US doesn't produce, on top of not producing the conventional.

**52:48** · So I think the way that we grapple with perception is, fortunately, perception on its own is getting much better because of all these examples and people caring now about expanding the grid and doing it cleanly.

**53:00** · There's only one option, it's nuclear.

**53:03** · And you look at the charts of for and against nuclear, and they've gone from mostly negative on nuclear to just completely crossing the past few years to where public perception is now positive on it.

**53:14** · And so fortunately, we're working on something that we felt like was absolutely the right problem, but the consensus has moved along with that really quickly.

**53:25** · Yeah.

**53:26** · So the question was, Kazakhstan, huge producer of uranium, I think 40% worldwide.

**53:34** · And then, OK, there's the ore production.

**53:37** · What should the future of this look like in the country?

**53:43** · And I think going back to the five steps in the supply chain, different countries probably want to focus on the things that they are uniquely able to do.

**53:54** · Kazakhstan, Canada, Australia, a few other countries have incredible uranium ore deposits that put them in the lead for production.

**54:01** · They can produce at costs that no one else can, whether it's existing mining technologies or more modern ones.

**54:10** · And then, OK, what should these next steps look like?

**54:12** · I think one idea that we have on all these steps is, ideally, they're colocated, at least the ones that are involved, like chemical processing.

**54:20** · And so why scatter these things across the country?

**54:22** · And right now it's very scattered across the country due to the history of it in the US.

**54:30** · And then how do we think about our specific step of enrichment?

**54:34** · Our goal long term is same goals that SpaceX had-- bring back this technology in the US, use it to help scale the industry, do it at a much lower cost structure.

**54:46** · And by doing that, we hope there's going to be a lot more fuel production, a lot more nuclear energy.

**54:50** · And so our goal is actually for countries that don't do enrichment.

**54:54** · US, first and foremost, let's solve the problem here.

**54:58** · But if we have allies, let's do it for them.

**55:00** · Let's do it at incredibly low cost that leaves little room for anyone else to really worry about it, which then has a huge downstream proliferation benefit of fewer countries saying, well, I need to do this, which then leads to a whole lot of complexity from a geopolitics perspective.

**55:19** · That's way above my pay grade, but if we can help solve this, it seems like a good thing on so many levels, both for power production, more clean energy, less fossil fuel carbon emissions, less risk of worldwide proliferation of nuclear weapons, on and on and on.

**55:37** · Could you actually take a few minutes?

**55:39** · I realized we skipped over the five steps in the supply chain for uranium.

**55:43** · Yeah.

**55:43** · If you could walk people through step by step, what's going on?

**55:46** · That would be the General Matter or the uranium version of the pre-training and training post.

**55:53** · Yeah.

**55:53** · Right, could you walk through that for a sec?

**55:55** · Yeah.

**55:55** · Going back to the reactors, you need to put fuel on them.

**55:57** · They consume the fuel.

**55:58** · They're ultimately burning up U-235.

**56:01** · That's the fissile material.

**56:02** · That's what's going to have the chain reaction that releases neutrons to make heat.

**56:05** · You take the heat-- heat water, generally, run a steam turbine, and you make electricity off of that.

**56:11** · And so, OK, we need fuel that has relatively dense U-235 content by weight.

**56:18** · And the way you do that is you get the mined product.

**56:22** · You then convert it from U3O8 to UF6.

**56:26** · You then enrich that UF6 gas, which is, again, a refining or separation process.

**56:33** · You then have a gas that's not going to help make fuel rods.

**56:36** · You need to turn that back into a solid through a chemical process.

**56:39** · And then you take that solid, and you form it into whatever pellet shape you want.

**56:44** · And so the step that we do is simply working with the gas and separating it.

**56:49** · So in our facility, there's no nuclear reactions.

**56:51** · We're not a nuclear reactor.

**56:52** · We specifically avoid any nuclear reactions by keeping materials spread out enough so that it can't form a critical mass.

**57:00** · And then there's no chemical reactions.

**57:02** · It's separation process.

**57:05** · And can you talk for a second, in that five-step process from mining to fabrication, why has the United States historically done so badly on enrichment?

**57:13** · On all the other parts of that supply chain, there's options in the US.

**57:18** · Yeah.

**57:19** · Well, historically, we did really well, actually.

**57:22** · In the '80s, we were about 86% of worldwide capacity on enrichment, and it occurred in a few different sites across the US.

**57:32** · You take that all the way through the Cold War, that's when we really reach our peak.

**57:36** · The US was providing all of its own utility power through enrichment at DOE sites.

**57:43** · They were government run.

**57:44** · They were former either Manhattan Project or Cold War sites.

**57:48** · And so with the fall of the Berlin Wall, though, we said, OK, there's now more free trade.

**57:55** · We can now trade with Russia.

**57:56** · Russia had all these warheads that it was in everyone's best interest to start disarming post-Cold War.

**58:02** · And so the US had a program called Megatons to Megawatts, nicknamed that, where we took the weapons, and we down blended them, and we ran them in our reactors.

**58:13** · And as a result, we said, OK, we actually have this supply now.

**58:16** · We have more free trade.

**58:17** · We can actually get this from Europe.

**58:20** · Our technology is actually relatively expensive that we were running at the time, very uneconomical compared to what we could get out of Russia or Europe.

**58:27** · And so we said, let's just do free trade on this.

**58:32** · The entities that ran the enrichment plans in the US had a hard time at that point making money on them and said, hey, it's time to sunset these.

**58:41** · And so the last of those was 2013.

**58:44** · And so since then, it's been decommissioning and preparing that site back for other industrial uses, which is what we're doing.

**58:52** · And so it was really a \[? path ?\] dependency of we had a certain technology.

**58:57** · It was not globally competitive.

**58:58** · The Berlin Wall fell.

**59:00** · We started trading with Russia, Europe even more, shut down what we had.

**59:04** · And then I think there was a-- people probably had plans of how we'll bring back enrichment when we need to, and I think the need is just coming much more quickly than people would have expected.

**59:13** · And as a recurring theme, we are now back to the future, basically, of uranium enrichment.

**59:20** · We were doing historically well, 20-year stagnation for whatever reason, and now it seems like AI has reignited the trajectory that basically took a bit of a detour, but we're back on track now, roughly speaking.

**59:33** · Yep.

**59:34** · Yeah, very similar to many other industries, similar to the space industry.

**59:37** · It didn't mean that it was as simple just reassembling the Space Shuttle or rebuilding Saturn V. You want to do things leveraging all the progress of the last few decades.

**59:48** · And so you are going to always want to start clean sheet and question everything.

**59:53** · Right.

**59:53** · And that's what we did.

**59:55** · And so many, many very exciting engineering challenges and problems to work on, but that's the fun.

**1:00:03** · And to borrow Peter Thiel, how far are we from flying cars now, even though we only got Twitter for a while?

**1:00:10** · Probably closer.

**1:00:11** · Closer?

**1:00:12** · Well, I mean, you look at all the-- not that far away, actually.

**1:00:15** · You look at Joby and all these other companies.

**1:00:17** · Right.

**1:00:17** · Flying cars for final project.

**1:00:18** · Thank you so much, Scott.

**1:00:19** · Yeah.

**1:00:19** · Thank you, guys.

**1:00:20** · \[APPLAUSE\]