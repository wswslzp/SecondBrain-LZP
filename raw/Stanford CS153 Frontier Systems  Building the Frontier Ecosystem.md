---
title: "Stanford CS153 Frontier Systems | Building the Frontier Ecosystem"
source: "https://www.youtube.com/watch?v=d0Pfu6B7gIM&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=1"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=d0Pfu6B7gIM)

## Transcript

**0:10** · Welcome.

**0:11** · Today, we have Satya Nadella.

**0:13** · Thank you so much for coming.

**0:15** · Absolutely.

**0:15** · It's my pleasure.

**0:16** · And, realizing it's a finals week.

**0:19** · So it's a different time of the day whatnot, but I appreciate the students that you all made it here.

**0:27** · I was thinking this morning how it's kind of fitting that you're the last person that we're having to this class.

**0:34** · And I say that because if I think back, your bet of putting a billion dollars into OpenAI in 2019 feels like that really set the stage for this Cambrian explosion, if you will, around AI.

**0:49** · So I'm curious to just kick it off like, what was the thought process to make that bet?

**0:56** · Yeah.

**0:56** · I mean, I think it is fascinating to look back now, six, seven, eight years in some sense.

**1:04** · I think the thing that I feel at least got me convinced that this was the right thing to go try at that time is quite frankly, what I describe as a prepared mind, which Microsoft's obsession has always been in natural language.

**1:28** · And of course, we were mostly focused on trying to get to natural language with some machine learning, some NLP, but fundamentally, if you had asked us even in 2017, 2018, it would be some combination of some symbolic logic plus machine learning.

**1:52** · So we were perhaps at that stage not the truest believers that deep learning can even get you NLP breakthroughs.

**2:02** · But that was something we wanted to have happen.

**2:06** · So I would take shots.

**2:07** · In fact, most people talk about just the OpenAI bet.

**2:10** · But we bought a bunch of companies, have invested in a whole lot of others, because the fundamental thing we were conditioned to do was anyone who had an ambitious angle on natural language irrespective of what sort of lineage they came from, we would always take it, whether it was organically inside the company or outside.

**2:32** · And that is when Sam-- and in fact, we were one happy family at that time.

**2:37** · So the idea was there.

**2:39** · That's what I'm saying.

**2:40** · You really did kick off so many things.

**2:43** · Everyone was in the same place.

**2:45** · And so to some degree, the scaling laws paper came out and their ambition on pushing the transformer with more compute and data was an appealing thing for us to take a shot at.

**2:59** · And of course, what's happened.

**3:01** · It's pretty stunning that-- the fact that the capability graph has just stayed at that scaling law Pareto is just pretty amazing.

**3:11** · I mean, as someone who worked at Microsoft, I guess 20 years ago, you've changed the culture like so much.

**3:19** · And I think it's striking to me that when you took that bet, I mean, was there an uprising within Microsoft saying, hey, we can do this ourselves?

**3:27** · Yeah, I mean, I think Microsoft over the years, I always say that at the end of the day, the core bet has to be the organic bet and what one does inside.

**3:37** · And then there are partnerships, there's M&amp;A. And I think any company like-- in some sense when you grow up in Microsoft, you learn that you can create a lot of enterprise value by building, by partnering.

**3:51** · If I look back, the PC revolution wouldn't have been possible, but for what people describe as the Gates-Grove model, which is Intel, Microsoft coming together to create essentially what was a PC ecosystem.

**4:08** · I worked on SQL Server, and so what we did with SAP to build our database business and for them to build the ERP application.

**4:15** · So we are conditioned quite frankly, for these type of ecosystem partnerships as well as organically build.

**4:25** · And so I would say there was not an uprising in some sense.

**4:28** · They would have always been like, hey, whenever you allocate your scarce resource of whether it's capital or more-- in this case, it's more than capital, the biggest decision was about compute concentration on a particular effort.

**4:43** · I mean, that was more the big bet.

**4:45** · And that's why we made it because this was the group that wanted to go drive it.

**4:51** · And we benefited obviously immensely from it.

**4:54** · And now one of the reasons why he's in town is that there was a big developer conference called Build.

**4:59** · And yesterday you announced this frontier intelligence ecosystem, which kind of right in line what you're saying.

**5:05** · And you had a bunch of other pretty huge announcements.

**5:08** · And I'd love to talk about some of those.

**5:09** · So you launched seven new models.

**5:12** · And I thought what was really interesting about at least Mustafa's description of how you did those models is that all the data is very clean.

**5:19** · There's a lot of focus on, let's say, not breaching any copyright things.

**5:23** · I'm just interested to hear from you why seven?

**5:27** · What was the thought behind that?

**5:28** · Obviously you want your own models, which makes a sense.

**5:31** · Yeah, I think if you step back-- in fact, I think you call this class the frontiers class.

**5:38** · And so I think one of the challenges of this conceptualizing, how does anyone, any individual entrepreneur or developer company, participate at the frontier?

**5:51** · There are frontier models, but how does one have real agency to add value, derive value, and protect value?

**6:00** · Because that's the question.

**6:02** · If you have a model that basically learns from data, what's the future of the firm even?

**6:08** · Which is, the firm today is about tacit knowledge inside the company that comes about because of its operations and human capital.

**6:17** · And in a world where there is going to be tokens and humans collaborating together, what's the future of the firm?

**6:25** · So there are some substantially big questions.

**6:28** · And so our vision for this is simple, which is we believe a frontier ecosystem is one where every company can actually operate at the frontier with their own IP compounding over time, not just the human capital, but even that token capital.

**6:48** · So that is the motivation we have.

**6:52** · So for example, when the models we built-- I'll come back to the lineage.

**6:57** · There's a nice technical report that I would encourage folks to go read, because I think it's probably one of the most transparent, good, detailed document on the entire pipeline that's been written lately from a model of this size, and I think you'll learn a lot from it.

**7:16** · But the purpose of both, let's take out thinking in coding models, was to be able to do this in such a way that we can license it along with the weights and really allow every company to build their own hill-climbing machine.

**7:30** · So we ourselves climbed our hill using, as you said, very clean lineage of data, making sure we were not adding a bunch of synth data in the mix.

**7:43** · So all that was very much true so that we could truly have a model where reasoning emerged.

**7:51** · And so we now have a fantastic, good, efficient model, but inside of a hill-climbing machine that any company sets up, it can go learn using the traces of that company and those tasks.

**8:07** · So our goal is every company starts thinking strategically about what's the RLE environment that they set up?

**8:17** · What is the private evals that they have?

**8:20** · How do they then welcome any model into that gym, so to speak, and then allow them to retain the IP and not leak value?

**8:31** · So to me, that's what I think every company will need to start doing.

**8:35** · Because if you're just a consumer of a foundation model, then I'm not sure how you can retain enterprise value, let alone create.

**8:46** · So the only way I see this ecosystem quite frankly being non-zero sum or positive sum where lots of participants can all be at the frontier, is they're able to take frontier models, take open-weight models, take a model like ours which is a licensed IP, and then hill climb on their own environment, and then build out their own IP.

**9:13** · So that's the core premise.

**9:15** · And we unpacked that in a lot of detail and all the tooling around it.

**9:19** · For example, one of the coolest things is if you're a Microsoft 365 customer, we can bootstrap even.

**9:25** · Because after all, what is Microsoft 365?

**9:27** · Today you use it to run your business.

**9:31** · People communicate with other people related to a business process.

**9:35** · So you can imagine we can bootstrap the RLE.

**9:40** · In fact, we can even generate the evals for, let's say, an HR onboarding process based on the observation of what you're doing.

**9:48** · That's unique to the company.

**9:50** · And first of all, it's their data.

**9:53** · Think of we built a multi-tenant SaaS application.

**9:56** · We now can turn that into a multi-tenant hill-climbing service where the data and the environment and the models and the traces and the outcomes are owned by the company.

**10:08** · Do you think that most companies, though, have the right talent to be able to build those hill-climbing machines?

**10:12** · Yeah, it's a great one.

**10:13** · So that's why I think this is the easy button on it.

**10:15** · So we are now not saying you need to build.

**10:18** · So you have the hill-climbing machine that has been instantiated for you.

**10:24** · All you need is a bit of strategic discipline in making sure that these models, the harness, the context, the evals are all artifacts and constructs that you understand and you manage them as assets.

**10:40** · Just like how you have historically done where you cared about privacy, you cared about confidentiality, you cared about security, I think in a world where AI comes into your company, these things will become as important architectural and strategic considerations.

**10:59** · And one of the other products you announced was Scout around enterprise cloud.

**11:04** · I'm kind of interested to hear the vision thinking behind that.

**11:07** · One of the things that we're very excited about is when I look at Copilot and its evolution, it started with chat.

**11:16** · And chat became very powerful, especially with reasoning models, because you could not only just essentially use it more like search, but you could use it as a thinking assistant essentially.

**11:30** · And so that became powerful.

**11:31** · Then Cowork was the next form factor.

**11:34** · And Cowork is pretty neat as a way to delegate tasks.

**11:39** · It's a multi-step reasoning tool-calling agentic loop, and so therefore you're able to do a short TAS assignment.

**11:50** · It's very much like what we were doing with GitHub Copilot, let's say, even two years ago when the agent loop started coming.

**11:56** · So we're now doing it for knowledge work.

**11:59** · But now with Scout, you essentially have the third form factor, which is autopilot.

**12:04** · So now you have the long-running agent where it continuously is operating.

**12:11** · It's monitoring.

**12:13** · It's got a heartbeat.

**12:14** · It's dreaming.

**12:16** · All the things that you expect from a Claw you can now have.

**12:21** · And you can create it.

**12:22** · You can have one with your identity.

**12:24** · So essentially, if I have an Entra ID, I can give Scout my Entra ID as a delegated ID, and it's essentially my digital twin that's working on my behalf continuously.

**12:38** · But not just that, we can also allow you to mint more autopilots.

**12:45** · And those things can have their own identity and their own sandboxes.

**12:48** · And so it's a pretty complete system.

**12:51** · So I think of it as an enterprise OpenClaw and a UI that fits in nicely with the rest of the Copilot system.

**12:59** · And it makes sense because you have those identities, you can address the security question.

**13:04** · I mean, obviously, I don't know how many of you have set up OpenClaw, but I struggled-- YOLO and get all my credentials because I'm like, I don't trust it.

**13:15** · Yeah, we even announced.

**13:16** · In fact, Peter was on stage with us at Build as well, because one of the other things is we were even working with the OpenClaw Foundation to make sure that it can be run securely.

**13:28** · We will have, in fact, on Windows an out-of-the-box experience where you can install OpenClaw and have it secured or contained in what is this new, essentially a container called MXC, which is essentially a way to sandbox the environment.

**13:48** · And so I think containment is key.

**13:51** · Because after all, you now have these long-running agents that are able to generate code and execute code.

**13:57** · And so therefore it will become very important to govern the execution.

**14:01** · And so we have a container that then you can set policy and isolation boundaries.

**14:06** · It can be process level isolation, session level isolation.

**14:10** · You can even have a VM boundary if you wanted.

**14:12** · For me for example, if anything I wanted to ever run even, I'll just run it on Windows 365, which is my cloud instance.

**14:19** · So a complete cloud instance that's fully isolated for long-running agents.

**14:25** · So I think we are all going to learn how to work with many agents.

**14:30** · And we're also going to learn how to isolate the environments for these agents, just like how back in the day, we thought about processes.

**14:39** · We're going to think about the process boundary, session boundaries, and container boundaries for agents.

**14:45** · One of the other things that you also announced was around bringing, we'll say, AI to consumers.

**14:55** · And I'm kind of curious what does that mean.

**14:59** · I mean, there's a lot of big announcements with NVIDIA.

**15:03** · Yeah, I know there are a couple of things on that.

**15:06** · One is we're very excited about this concept of unmetered intelligence.

**15:12** · So if you think about it, every PC historically the install base had a lot of GPUs.

**15:20** · If you count the number of PCs with GPUs, it's pretty substantial-- the dGPU install base.

**15:26** · So one of the things that we are trying to make sure is that in a world where these models are there, there is applications that are being written, the tokens are in short supply, we want to tap into essentially the edge compute silicon.

**15:42** · And in that context obviously NVIDIA announced a new SoC which we are very excited about their RTX.

**15:49** · So we have a Surface Laptop which is going to come out in the fall, which is built on it.

**15:54** · In fact, all our OEMs will have fantastic designs for it.

**15:58** · We also announced a dev box.

**16:00** · I mean, think about it.

**16:01** · It's going to have a petaflop of AI compute.

**16:03** · It's going to have 20 CPU cores, 128 gigabytes of unified memory for both the CPU and the AI compute.

**16:12** · And it's going to run something like a trillion parameter model locally.

**16:19** · And by the way, and we also worked with Jensen to get Windows working on a GB300.

**16:25** · So we even have a DGX workstation.

**16:27** · So I think of it as a data center desktop.

**16:32** · And so I think that there's going to be real demand for all of this because people will want-- especially when you install something like Scout or Claw or what have you, and I want it to just keep working 24 by 7 and I don't want to get billed for it, the best way to do that is to run it on your laptop or on your desktop.

**16:53** · So we are very excited about just even the rebirth of the existing PC form factor with this new unbelievable functionality brought forth because of both the silicon innovation and the model capabilities that now we can have locally.

**17:09** · So that was a lot of what we talked about.

**17:12** · But the other thing that we also said is just as there's new functionality in the old form factors, I think there's a real opportunity to create new form factors for the agent era.

**17:26** · So that's where Project Solara comes in.

**17:28** · And our goal there is to say, we showed two reference designs, one is a badge and the other one was a desk companion, if you will.

**17:41** · But the badge is pretty interesting.

**17:42** · So you can imagine an agent that has a fingerprint reader and a badge that has a fingerprint reader as well as a camera, and has enough onboard compute-- it's a MediaTek processor-- to be able to wake up something like Copilot.

**18:00** · And I can literally get notified.

**18:04** · Like I can even give it, say, a coding task or whatever, I can dictate to it, it will take the input and then go execute it in the cloud, notify me back.

**18:16** · You can imagine in healthcare if I was a nurse, I was moving station to station, I could use that to badge in the data versus the phone.

**18:26** · Like right now we're conditioned either we're entering in the PC or we are using the phone.

**18:31** · In an agent era where you really have ambient intelligence and ubiquitous computing, you can imagine these form factors now that are just endpoints for long-running agents that wake up, notify, and help you get both output input that's right there in the real world.

**18:51** · And so we're very excited about bringing even a platform for it.

**18:55** · So we will build some.

**18:56** · But the goal here is also to have even by the way new platform rules.

**18:59** · So Windows has always been-- it's fascinating that we are the only open platform out there.

**19:07** · You can go through our App Store or not.

**19:09** · You can install anything on Windows.

**19:12** · It's always had that ethos of being not something that only Microsoft-- you don't need to call Microsoft to build applications for Windows.

**19:20** · How about that?

**19:20** · So that's the openness we want even in this new agent platform so that we don't have the carryover of these platform rules that were written for the previous era.

**19:32** · I'm going to switch gears a little bit.

**19:34** · So here we're at Stanford University, probably the center of the world in terms of AI-pilled people.

**19:41** · And when you get outside of the Bay Area, Seattle, people are looking at AI and saying, like, what's good for me?

**19:51** · And I think there was a prior speaker that used the metaphor, which I found quite powerful, which was as electricity came about, we didn't sell electricity, we sold light.

**20:01** · And what do you think is that equivalent for AI?

**20:03** · Because right now there's not a lot of good messaging around AI of how it's going to benefit people.

**20:08** · Yeah, I think that's right in the sense that we have perhaps gone too into-- the bubble that I guess we all live in is more about hyping the tech and the tech progress for its sake.

**20:25** · We live in it and it's great to be impressed by it and push the frontiers of it and what have you.

**20:30** · But at the end of the day, the world will evaluate us in what was the value we created for the world, one community at a time.

**20:39** · I mean, it should always be the case.

**20:42** · And so unless I can see the true benefits of this technology be broad spread.

**20:51** · We talked about healthcare.

**20:52** · When we suddenly start seeing AI in healthcare change the cost equation, the care one can get on, not in an abstract sense, but when it happens to someone in our community, in our family when-- or even take economic opportunity.

**21:09** · Talking about this as something where it takes away jobs, it's clear that any technology that's disruptive will have real displacement.

**21:21** · But at the same time, there is going to be new economic activity where humans will have agency, which will have wages, which in fact, if you think about it, if what is current intelligence gets commoditized, humans are the one species that are most adaptive, and the sense of creating new value on top of what's the new commodity.

**21:41** · And that has to not be abstract, but it has to be real.

**21:46** · And it will happen.

**21:48** · But until that transition happens, to your point, as we go from electricity to light, and the light is not seen only by the AGI-pilled people in the zip code, but it's seen by the world as something that they can thrive in.

**22:03** · And even my point about that frontier ecosystem, when every company is not sitting there thinking that, oh my God, if I let any one of these frontier models into my organization, it's just going to run over all the IP I've created.

**22:21** · Why would they welcome that?

**22:24** · By definition they should not.

**22:25** · And so I think that's why as entrepreneurs, as students, and as incumbents, we have to shape this to an ecosystem which is positive-sum by definition.

**22:38** · If we are not and it's about a few firms that have all the returns and everybody else it's all in bad shape, you will absolutely lose social permission or we will lose social permission.

**22:53** · OK.

**22:53** · I'm going to switch over to questions.

**22:56** · So I'm generally curious about your custom silicon program and how you've learned from other hyperscalers like Google and Amazon, who have made some progress there.

**23:09** · It seems like at the hardware side, their chips that they offer are actually pretty bifurcated.

**23:16** · They have training chips and inference chips versus in AMD you've kept it unified too.

**23:23** · On the networking side, we had unembodied class talk about the optical mouse system that they built.

**23:30** · That was really interesting.

**23:31** · And at the software side, it seems like they built their own versions of CUDA with Neuron and XLA, respectively, whereas you guys are building on something based off of Triton for mining.

**23:45** · So I'm curious given these differing design decisions that you don't agree, what have you learned and where are you taking your own customers?

**23:54** · Yeah, I think the key thing is to recognize what are the new workloads.

**24:01** · Whenever you think about any new system, you want to be motivated by what's the new software or what's the new workload.

**24:10** · And the good news here is that there are these three dominant new workloads.

**24:15** · There's the training workload, there's the inference workload, and now we can say there is the long-running agent that uses inference and regular compute.

**24:26** · So if you said that's what you have, then you can start from a first principles looking at it.

**24:33** · And these are interesting type of workloads.

**24:35** · They're not like the previous scale-out workloads.

**24:38** · These are synchronous data parallel workloads where to a means, I guess point, which is you got to even think about the scale-up part.

**24:50** · Some of the tricks that worked for us for scale-out in the past won't work.

**24:55** · So therefore you now need to even innovate on the scale-up and the scale-out to really keep things coherent and the MFUs on a training run are maximized and so on.

**25:07** · So therefore, the way we come out of this and say, OK, even just yesterday we announced there's Maia 200 that's essentially being codesigned with our own models, plus the OpenAI models, because we have that IP.

**25:23** · And right now, in fact, Maia 200 is running GPT 5.5 in multiple data centers powering Copilot, and giving us total TCO advantage.

**25:33** · So that's a great way to round trip for an inference workload what's the advantage of that is.

**25:39** · We not only did that but we also built Cobalt which is our ARM processor for compute.

**25:50** · And we're benchmarking it to improve both for latency performance when it comes to, for example, the agentic loop because the place where you need great cores are for these agent loops.

**26:02** · So we're using all the GitHub Copilot traces to optimize our ARM processor even.

**26:08** · And bringing all this together with even the networking stack.

**26:12** · And so our approach would be to not-- and at the same time, we love to have the GPUs because they're general purpose to your point, which is, in fact, we're using GPUs.

**26:21** · In fact, we're using the old GPUs in our fleet to accelerate our data warehouse.

**26:27** · So Fabric is seeing 7x plus performance gains because of GPU acceleration.

**26:34** · So we think of our fleet as a heterogeneous fleet, where we will use software to get the maximum benefit out of it and do smart workload placement.

**26:45** · At the same time, optimize for the high-volume workloads like inference and training and agent loop with our own ground-up system.

**26:53** · And there's lots of design points.

**26:55** · Most people get fixated on the AI accelerator.

**26:57** · But the AI accelerator is one, the CPU is one, the network accelerator, the storage accelerator, the AI WAN is another one.

**27:06** · You want to be able to really do multi-data center hops even.

**27:11** · So, lots of stuff.

**27:12** · It's a great time, by the way, to be in computer architecture.

**27:17** · I think when I started in the industries when the Patterson book first came out and that was the RISK versus CISC debate, I feel like we're back at a time like this where you can really rethink from the physical design of a data center to-- by the way, the electrons.

**27:38** · I mean, one of the places where I'm very excited about is the efficiency with which we can bring the electrons all the way to the CPU so that the tokens are that much more efficient without all the losses in between.

**27:50** · So I think there's just a tremendous design \[INAUDIBLE\].

**27:54** · And another announcement you had yesterday was around quantum, which is kind of adjacent to what you talked about.

**27:59** · So I'm kind of curious what was the announcement and what was the recent advances there?

**28:03** · Yeah, so look, this quantum, we have been on at this for now the last 20 plus years, and it's really exciting to see the progress.

**28:14** · I'll just say one of the things is, even independent of the quantum program, even with what we were able to achieve in the last couple of years, with even the natural atom-based quantum computers with our stack-- we worked with partners on it.

**28:30** · We're able to generate now these very good traces, which those traces-- basically, if you think about what's the purpose of a quantum computer, a quantum computer can simulate nature.

**28:42** · I mean, since nature is quantum.

**28:45** · And so instead of relying on DFTs or what have you, you can now have a lot better fidelity of say, chemistry or molecular dynamics or what have you.

**29:00** · And those traces then can be taken back and you can train a model.

**29:04** · In fact, we are doing that with our material science models, where you can take the traces from even a whatever, an early stage quantum computer, to improve the data on which you train a model for something like material science or chemistry.

**29:22** · Now, our quantum program itself is, as I said, there's a software side to it, which we will put on ion trap machines, which we're putting with partners.

**29:31** · We're putting it on a photonics-based machine.

**29:34** · We're also putting it on natural atoms.

**29:36** · We have a partnership with in Denmark called QuNorth, where we will even have a quantum computer powered by Atom Computing with our stack within the year and so on.

**29:47** · So that's one side of it.

**29:49** · The second side is ultimately in order to build a quantum computer at scale, at utility-scale, you need fault tolerance.

**30:00** · Our bet on that has been that we-- there was a theoretical physicist who theorized essentially a state of matter called a Majorana in the 1930s.

**30:20** · And so one of the things that we felt that that was the state of matter that we needed to essentially fabricate and make real.

**30:29** · So we launched our first QPU, which was Majorana 1 a year ago, which essentially proved out the fundamental physics breakthrough, that you can actually have this and then instantiate it.

**30:44** · And now we've got Majorana 2, which allows this to be built at industrial scale.

**30:52** · And so there's a lot of detail in terms of how long these qubits can be stable for.

**30:58** · And by the way, one of the other things is we have perfected the digital control of this quantum computer because that's going to be super important.

**31:06** · So overall, we feel that the quantum program at Microsoft's progressing on two dimensions.

**31:11** · One is in the near-term with even what are the quantum computers that I think are most easy to fabricate and build today with these things like natural atoms.

**31:21** · And then in the long-run, we want to build out what is needed in order for true quantum computers to act like utility-scale quantum computers.

**31:32** · On that ladder, if you had a guess at timeline?

**31:35** · I'm the third CEO at Microsoft to keep going on the quantum journey.

**31:42** · I would say that what I'm now a lot more bullish is it may not-- it's kind of like the previous discussion.

**31:50** · I think of quantum as the new accelerator.

**31:54** · And remember, by the way, quantum is not going to replace classical.

**31:57** · Quantum is not going to be great at storage and memory and so on.

**32:00** · It's going to be great at computation.

**32:02** · And so you have to marry classical plus quantum in order to do things.

**32:06** · And so therefore, I think of this as maybe a lot more staged even.

**32:11** · So if you have 100 logical qubits with good error correction, we can start using it to generate synth data for science models.

**32:19** · Like that'll be a pretty important milestone that may be even more achievable in the short-run.

**32:25** · So we'll see.

**32:28** · We I think made the claim even yesterday that by the end of the decade, we believe we will be able to build a quantum computer that starts solving some real challenges.

**32:37** · Real problems?

**32:37** · Yeah.

**32:38** · Amazing.

**32:38** · Next question.

**32:46** · Thanks so much for coming.

**32:48** · I spent nine years at Microsoft.

**32:50** · I joined a year after you became a CEO as a market employee.

**32:57** · So I went through cloud transformation and then I go into AI fascination.

**33:03** · And I think my program was such an amazing experience for me.

**33:08** · And it shaped the younger person.

**33:11** · How do you think it contributed and is it still contributing to the culture and success of mine?

**33:18** · Yeah, I mean, first of all, we're very, very thrilled about, obviously students coming in and joining and having essentially the Mac program.

**33:25** · There are a couple of programs like that at Microsoft we created where people can even rotate through various functions.

**33:31** · At the end of the day, any company for it to be at the frontier, so to speak, has to be able to get people coming with fresh ideas, fresh energy, and reshaping it.

**33:43** · I always say to anyone joining Microsoft, of course you want to come in and learn about how Microsoft works, but we also want Microsoft to learn from you.

**33:52** · And more importantly, for you to have the agency to reshape what is Microsoft's culture.

**33:57** · It's not a static thing.

**34:00** · It's an organic thing that gets shaped by the behaviors, the decisions of people at the company.

**34:07** · And so we always would welcome students coming in, building their career at Microsoft.

**34:15** · One of the things as a 50-year-old company, I mean, Mike's an alum at Microsoft and still engaged with us.

**34:22** · We have people who've come, had a tour of duty, gone out, come back.

**34:27** · And so at this point, the way to think about it is the uniqueness of the Microsoft is our core DNA has remained.

**34:40** · We are a developer tools platform, knowledge worker tools company.

**34:46** · That's kind of what we've done for 50 years.

**34:49** · But the interesting thing about us is that we have been able to reinterpret that with every new platform.

**34:58** · In fact, I joined the company back in the '90s when my existential competition was Novell.

**35:05** · And now, it's some foundation lab I'd not even heard of five years ago.

**35:10** · But that is the thing that I think keeps us vibrant, which is our existential challenge, or what we need to compete with is new and fresh versus it's the same old.

**35:23** · And I think that that's an attractive part.

**35:25** · When you come to Microsoft, you will be able to go at that mission of being able to empower people and organizations all over the planet, which means a lot to us.

**35:38** · But to do so, recognizing that we as a company can bring a lot to that mission.

**35:47** · I have a follow-up question.

**35:48** · So one of the many attributes I've admired about you is you have a growth mindset, and you really look at your leadership team and drive it.

**35:55** · How have you instilled that across the company?

**35:58** · Because you clearly have.

**35:59** · You just pointed that out, that you've been able to deal with these platform transformations.

**36:03** · Yeah, I mean, at some level, I think it's not something you instill per se, Mike, you invoke what is innate in all of us, I think.

**36:14** · I mean, you have to do it more out of practice.

**36:20** · Mostly what I have to exhibit more than anything else is my ability to confront my fixed mindset.

**36:29** · Because at the end of the day, all of us, it's easy to talk about growth mindset, but it's very difficult to exercise it individually.

**36:36** · As somebody said to me, which I always liked as a sort of a nice quip, is everybody likes change, except they want the other person to change, not themselves.

**36:48** · And that, I think, is the challenge of growth mindset.

**36:53** · So it's not about talking about growth mindset.

**36:55** · It's about having the courage to confront one's own fixed mindset.

**36:59** · So it can become corporate dogma to your point.

**37:02** · So one of the keys, the reason why it's worked at Microsoft is we never made it like, oh-- --some mandate.

**37:10** · It started with you.

**37:12** · And also it's not like trademarked to Microsoft.

**37:15** · I mean, if you exercise growth mindset or you confront a fixed mindset, you'll be a better human being first.

**37:23** · You'll be a better colleague, a better friend, a better neighbor, a better parent, a better student, everything.

**37:29** · So you're not even doing this for Microsoft's sake.

**37:32** · You're doing this for yourself.

**37:34** · And I think giving that oxygen, leaving that at that, as opposed to some new corporate thing, has been very, very helpful.

**37:42** · So I'm an advocate of it, not just at Microsoft, anywhere.

**37:48** · And more importantly, it's that practice of-- there are two things that I feel that were pretty influential for me, which I learned through my wife's readings, quite frankly.

**38:01** · One was this thing called nonviolent communications, which is also another form of developing a sense of empathy, understanding where the other person is coming from, not having your amygdala always triggered and what have you.

**38:16** · So that's one which I think is it's a great read if you've not read it.

**38:20** · And then, of course, Carol Dweck's work on growth mindset.

**38:24** · These are two things that are I think, relevant for children and students and child psychology.

**38:30** · But I think they apply to corporate cultures because I think one of the fascinating things is what Herbert Simon described as the bounded rationality.

**38:40** · I think humans are great, but we have this unfortunate-- we don't see what's in our interest all the time.

**38:55** · We get hijacked often without being able to do the simple calculus to what does it mean to be at the frontier of our own behavior.

**39:10** · And I think that these are nice practices that gets us and pushes us.

**39:14** · So think of it as your training run that you need.

**39:18** · That's great guidance.

**39:20** · Thank you so much for the answer.

**39:21** · And I had my dissertation 10 minutes ago, but I really wanted to meet you.

**39:26** · Thank you so much.

**39:27** · All right.

**39:27** · Good luck.

**39:28** · We realize it's finals week.

**39:31** · Next question.

**39:34** · Yeah.

**39:34** · Thanks so much for coming.

**39:35** · I was wondering, how did you become such a good public speaker and what-- \[LAUGHTER\] I don't know, man.

**39:45** · I mean, I'm glad you think I'm a good public speaker.

**39:51** · Let's leave it at that.

**39:53** · I mean, look, I think, like anything else, it's not that I think about public speaking as a key thing that I'm trying to develop or what have you.

**40:03** · But the lucky part that I find myself is in particular, even I think one of the things is when I became CEO, you had to talk about things, perhaps that you didn't get the opportunity to talk about previously.

**40:21** · Maybe that's a better way to characterize it.

**40:23** · But the good news is, it's not as if I was not thinking about those things previously.

**40:28** · And I reflected on it.

**40:30** · Is that why is it that I was thinking about those things previously?

**40:34** · And I think that comes out of just natural interest, for example, thinking about technology, but its impact, what does it mean?

**40:45** · I have many pet passions.

**40:48** · Like what does any technological progress like AI mean to the Global South?

**40:55** · What does it mean to even what has been a dream-- and I grew up as a son of a development economist, so he instilled in me that, hey, this convergence growth is going to happen and it's going to be great and so on.

**41:07** · And so I'm obsessed about it.

**41:09** · And so as long as I think you have these passions that allow you to think broadly, and then for you to be able to talk freely about it, is the other one.

**41:21** · And so I'm not particularly an expert on public speaking, but I think the more any of us can have broad interests that we can articulate.

**41:33** · And in today's day and age, the media allows us to be able to have our own outlets.

**41:40** · And so I think that this is a great time to both build that interest and then to be able to have different medium, whether it's speaking, whether it's writing, whether it's podcasts, what have you.

**41:50** · There are a variety of ways I think we can express, reach, debate, which I think is fantastic.

**41:59** · Thank you for coming.

**42:00** · I was wondering if your undergraduate self was sitting in the audience right now, what advice would you give him?

**42:06** · And knowing what you know now, I guess, and what would you tell him to put his energy into and to maybe avoid?

**42:14** · Yeah, it's a great question.

**42:16** · I mean, it's such a privilege in some sense.

**42:19** · I wish I could.

**42:23** · Because everything is in front of you.

**42:24** · You're risk on 100% of the time.

**42:29** · Maybe that's what it is, which is-- let me just say two interesting things.

**42:37** · Yesterday on Hacker News, I came across, I forget, one of the CS classes here.

**42:41** · It had the guidelines on how to use coding agents, which I thought was well done.

**42:46** · They had the do's and don'ts.

**42:48** · And so the fascinating thing I find right now is the ability to learn new things has become so much easier.

**43:03** · Because you have this very accessible, personalized tutor that's deep that you can go and work with.

**43:14** · And so I would say more so than any assignment anxiety or I don't grade anxiety or what have you, you can have-- one of the terms one of my colleagues uses-- real cognitive coverage.

**43:32** · Like test coverage, you can now have cognitive coverage that really follow you through your curiosity.

**43:42** · If I were back as an undergrad, I would be trying to-- it's kind of what I do with GitHub sessions today.

**43:49** · GitHub app, which is what are all the coding agents and what are all they doing?

**43:54** · So that's what I would do.

**43:56** · I would be sitting with, what are the 10, 100 agents and me at Stanford learning?

**44:07** · But I need to have cognitive coverage.

**44:09** · It's not I've offloaded to the 100.

**44:11** · The key is, what am I instructing them?

**44:17** · And then when they get something done, can I understand what they did in order to have learned?

**44:24** · It's kind of like it's 100 classes.

**44:28** · It's so fascinating.

**44:28** · And that I think, is what I think will happen.

**44:30** · One of these days somebody's going to break a new pedagogy that goes with-- the tools, for example, are evolving.

**44:39** · Like think about what happened in developer tools.

**44:41** · We went from saying, hey, we have 100 CLIs to now we need a thing that to manage our CLI complexity, which is the new AD, which is like for example, the GitHub app is fantastic in that context because it's like the new inbox for managing my sessions.

**44:58** · What's the moral equivalent of that, that allows a student to navigate through their learning experience and be max curious, but really getting deeper, faster on things that you're trying to cover?

**45:17** · And I think that that's what I would do and not have anxiety.

**45:21** · Because you can always push a button to get an assignment done.

**45:24** · So that's no longer the case.

**45:26** · And the grades may or may not matter.

**45:28** · And so therefore there's a lot of relitigation on the things we valued.

**45:34** · That's a really good answer.

**45:36** · Next question.

**45:38** · Hey, thank you so much for coming.

**45:41** · So, like, whenever we're interacting with a computer, pretty much we always interact with a GUI interface.

**45:50** · But agents, they just so happen to be good at coding, happen to be not that good at interacting with GUI interfaces.

**46:00** · So for example, if I want to design a poster and I want to be able to do it, it is easier for me to get it to generate my HTML/CSS code rather than to use a GUI design product.

**46:14** · In that case, what do you think importation of \[INAUDIBLE\] for BUI interfaces versus a seal.

**46:27** · Yeah, I mean, I think you're bringing up a couple of different things.

**46:30** · One is essentially codegen is powerful, and therefore HTML and other web UI, as an artifact creation process, I think is going to really proliferate.

**46:45** · So basically, we've gone from-- we in fact, always Bill used to have this thing where, what's the difference between building an app, writing a document, or creating a website?

**46:59** · At this point, there's none.

**47:01** · You can just basically do all three by using code.

**47:04** · So that's one side of it.

**47:07** · But I think that the direct manipulation is the challenge.

**47:11** · I think in the intermediate time frame, what's going to happen is you're going to have an intermediate format.

**47:16** · So you're going to do the HTML and then you can convert into Excel, PowerPoint, PowerPoint into intermediate format and then have agents.

**47:23** · So I think that that's what you see in Copilot and elsewhere when you think about artifact creation.

**47:29** · But the ultimate thing is, can you truly teach even the agent on the model, the Canvas, and the direct manipulation of the Canvas, which has to be done fundamentally by teaching it the semantics of that Canvas?

**47:47** · And so it has to be exposed to whether it's through APIs or whether it is through a protocol or what have you.

**47:54** · And so therefore, I think you will see innovation like that.

**47:57** · But it is true that direct manipulation-- by the way, you talked about, one of the other things that struck me is one of the nice little features we added to GitHub yesterday was a thing called Canvas, and the reason was not because the agents need UI, but we need UI, because it's now become too dense to just keep tracking my CLI session or the chat session because, first of all, it's linear and it's painful you're trying to scroll through it.

**48:27** · And so one of the things that we said is now we can-- for example, I can have a Kanban board as a visualization, which both the agent and I are working on.

**48:37** · So I think that this idea of generated UI becoming the new way for human agent interaction might be one of the coolest things that will happen across all product lines.

**48:51** · Next question.

**48:53** · Hi, Santhya.

**48:54** · Thank you so much for coming.

**48:56** · If you were at our age like college freshman and you had the world at your fingertips, what's the problem that you would encourage us in \[INAUDIBLE\]?

**49:04** · Oh man, I was that, but I don't know.

**49:09** · I mean, it's always interesting to look back and say, what would I pick?

**49:17** · I don't know.

**49:18** · I mean, in an interesting world like ours right now, I think you have to go and say, what is the thing that you have inherent interests in and the world will value?

**49:34** · I think always whenever people are making choices, I think they have two things they're trying to intersect.

**49:39** · They're trying to intersect something that they believe they have a real passion for.

**49:45** · But they're also doing, quite frankly, the calculus on, what does the world value?

**49:50** · They always have some destination in mind.

**49:53** · I want that career, I want that job, I want to start that company or what have you.

**49:58** · And so I would focus on that.

**50:00** · Answering those two questions is what I think will lead.

**50:05** · And in my case, I would probably go step back and look at that.

**50:08** · It may, may be even outside.

**50:11** · One of the things if I go back to the computer industry-- I was an electrical engineer and I then drifted into software.

**50:21** · But if I went back now, I may go back into hardware, just because there is just such an unbelievable time in-- There are a lot of things that I would love to go deep on understanding what the optical side of networking would look like, some of the system design.

**50:43** · So I think that's how I think things will pan out.

**50:47** · People will pick the thing that they're good at, then they see the trajectory of what they're good at and say, wow, I'm going to bet on myself to get good at this and start something and/or policy.

**51:03** · And people talk about safety engineering, but I was thinking, wow, there are so many aspects of what does it mean to have safety around AI that require people to think through deeply.

**51:17** · And so anyway, so there are lots of choices out there.

**51:20** · Along those lines, have you guys hired like philosophers to help you with the AI of guidance?

**51:26** · I think Mustafa is a philosopher dropout or something.

**51:28** · So he's-- Sung.

**51:31** · So we have a quasi wannabe philosopher.

**51:36** · But he thinks clearly from that.

**51:41** · I mean, he's been, obviously, since being a founder of DeepMind to now, he's always thought about it, and we have always had folks in MSR who are brought real, deep, multidisciplinary approach to it, whether it's the economist, the moral philosophers, the sociologists.

**52:02** · And I think we'll always have that.

**52:05** · Next question.

**52:08** · Hi, Satya.

**52:08** · I was curious, what do you think about space data centers.

**52:12** · Because I've had a lot of startup CEOs that come here and talk and just try to convince me that we should be looking at that.

**52:18** · And the research I'm doing is showing that Elon is probably the only one that's being able to do it profitably just from the large costs per kilo.

**52:26** · I was just curious where you're.

**52:27** · I'm not an expert on any of that in both the supply side of it and the economic side of it, but it's plausible, at least, what I've read and what I've talked to people who are experts in it.

**52:43** · Seems like it makes sense.

**52:47** · The question really is you now need to not only solve both, how do you get there, but how do you build the stack that operates there and then solve all the practical issues of RMA and others.

**53:02** · Because therefore, I think there's a whole supply chain.

**53:07** · When you think about the data center, most people-- it's a complex project.

**53:13** · We're built on the shoulders of unbelievable engineering depth.

**53:18** · Starting from civil engineering, on and to electrical engineering, to mechanical engineering, to then ultimately have it meet the needs of computing.

**53:31** · And so that level of sophistication for this new payload in space has to get built, and it could get built.

**53:39** · And as far as I'm concerned, from a Microsoft standpoint, I would love to.

**53:42** · I mean, I think we have a few instances where we have already had some Azure SKUs.

**53:49** · We had a program where we even put Azure SKUs in space and what have you, but they were more like edge.

**53:57** · And so to the degree to which if somebody says to me that there's gigawatts available or megawatts available, I'm happy to plug myself in.

**54:10** · Next question.

**54:12** · Yeah.

**54:12** · So it seems that Meta is now pulling back from building frontier open models.

**54:19** · And I understand that Google \[INAUDIBLE\] doing some work with open models or flash and \[INAUDIBLE\], but they tend to be pretty small for writing like one \[INAUDIBLE\].

**54:31** · Given how you personally embrace open source, the biggest example being Linux.

**54:37** · I'm curious, do you see Microsoft and AI, OpenAI building frontier open models like at the parameter \[INAUDIBLE\].

**54:47** · Yeah, I think the thing that we're focused on, we definitely will always have open rate models.

**54:52** · And to your point, they will be more for what we will ship.

**54:56** · In fact, we launched two even yesterday, both an instruct model and a plan model for local agent loop and what have you.

**55:04** · So they are derivatives of what we have done with Phi Silica before called Ion Instruct and Ion Plan.

**55:11** · And they'll run on Windows and they'll be open rate.

**55:15** · The thing that we have focused on with the MAI lineage of models is, again, think of them as licensed, but we are going to license them pretty broadly.

**55:25** · So for example, you can go to base 10.

**55:27** · You can go to fireworks and you can then fine tune even using their inference stack.

**55:32** · And so on.

**55:33** · But the reason why we're doing that is because we want quite frankly, every company, whether it's a SaaS company, an AI native or an enterprise company to have their own model that they can then post-train, they can RL, and what have you.

**55:49** · So therefore, that'll be our goal is to build an ecosystem around the MAI lineage of models.

**55:57** · And the reason why we want to make sure they're still licensed is because at this point, there's going to be real need for inspection, safety, so there's the accounts at which we are.

**56:12** · And even if you look at the Chinese models, they're also quickly becoming closed source and so on.

**56:17** · So I think there will be.

**56:19** · And I know Jensen's working on some open rate models, so we're definitely supporters of it.

**56:24** · But we want to make sure that we are all leading.

**56:29** · The ultimate goal here is to have everyone have real agency in being able to take some model and to be able to then add to it and then protect it from having it go back.

**56:44** · So I think that they are \[INAUDIBLE\].

**56:47** · It won't be open.

**56:48** · It will be licensed.

**56:49** · What does that?

**56:50** · So we'll license the weights.

**56:52** · OK.

**56:52** · And then how does, if someone's using it on fireworks or together or something like that, how does that help y'all at Microsoft?

**57:00** · It will be licensed.

**57:01** · And so therefore, we will have an economic model in all of this.

**57:06** · Well, I think we're out of time.

**57:07** · But thank you so much for coming.

**57:09** · Thank you so much.

**57:10** · Fantastic and--