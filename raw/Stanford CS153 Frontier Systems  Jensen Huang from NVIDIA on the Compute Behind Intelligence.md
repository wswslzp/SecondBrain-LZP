---
title: "Stanford CS153 Frontier Systems | Jensen Huang from NVIDIA on the Compute Behind Intelligence"
source: "https://www.youtube.com/watch?v=tsQB0n0YV3k&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=6"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=tsQB0n0YV3k)

## Transcript

**0:08** · I would like to welcome back Preacher Huang.

**0:12** · \[APPLAUSE\] We have been now locked in a global race, way faster than NASCAR racing.

**0:27** · And it's partly your fault. Jenson's been the preacher that's given us all the power we need, all the energy, and some more, to have what I think has been the craziest 12 months of my life, certainly for many of you.

**0:42** · And we're just getting started the energy with which you approach every single thing you do, including the class last year.

**0:53** · And then every time I've had the chance to hang out with you, you've given so much time to the students, to the founders.

**0:59** · Thank you.

**1:01** · Should we jump right in?

**1:02** · Yeah.

**1:03** · Let's go.

**1:03** · All right.

**1:04** · We're going to rapid fire.

**1:05** · What is codesign?

**1:07** · And why is it so important?

**1:12** · I'll answer that in a second.

**1:13** · Yes, please.

**1:14** · But this is a great time to be in computer science.

**1:18** · And obviously, the reason is because computing is being reinvented for the first time, as dramatically as it is, for the first time, really, in about 60-plus years.

**1:30** · The computer that we know, that you all use in our computing model, our mental model, the architecture of a computer, how you write the program, run the program, how you think about even taking computers to market, what it's used for, for 64 years, it has been largely the same since the IBM system 360.

**1:51** · In fact, my first architecture book for learning about computer architecture was the system 360's manual.

**1:59** · And so a lot has changed.

**2:03** · As we went from PCs to internet, and mobile, and cloud, and all those things.

**2:07** · But the fact of the matter is the computing model, the fundamental part of computer science has largely remained the same until now.

**2:14** · For the first time, the way you write the software, how you process the neural network versus the software, and what the applications can do has now dramatically changed.

**2:27** · Everything is fundamentally different.

**2:29** · At the highest level, one simple way to think about it is, computing, as we knew it before, was largely prerecorded.

**2:39** · It's content that we prerecorded, images, videos, software that we largely prerecorded.

**2:46** · But now, everything is generated.

**2:49** · And the nice thing about generating everything in real-time is that it could be contextually consistent, contextually relevant to what it is that you're dealing with.

**3:00** · And of course, it can respond to your intention, not just explicitly to the things that you instruct.

**3:08** · And so the computer is fundamentally different in that way.

**3:14** · Now, the question is, what does that mean at every single layer of the stack?

**3:19** · From how the computer, how the software is now developed, the methodology of it, how you organize your company to be able to develop software of today completely changed.

**3:31** · And so the methodology, the tools we use, the approach that we think about software coding, completely changed.

**3:38** · How we run the software, neural network versus compiled binaries, very, very different.

**3:44** · And so what does that mean to the computer system, the network, the storage?

**3:49** · What does that mean to the software stack and the cloud services that sit on top of that?

**3:54** · And of course, everything about the applications.

**3:57** · What did it open up?

**3:58** · And somebody just came and said, this piece of software we just opened up, called Alpamayo.

**4:06** · And I've been working on self-driving cars now for about 13 years.

**4:13** · And the days of robotaxis are going to be literally everywhere.

**4:17** · Everything that moves will be robotic.

**4:18** · And that's an example of an application that we wouldn't consider doing, until deep learning and artificial intelligence came along.

**4:28** · That was such a big unlock that I said, hey, aha, all of these problems that we wanted to solve in the past, that we need a computer vision for, really are now fundamentally unlocked.

**4:42** · And so it's how you think about every single stage of that.

**4:47** · What is a software engineer?

**4:49** · How do you organize the company?

**4:52** · What is a computer for the age of AI?

**4:55** · How do you architect that?

**4:56** · All the way to what you can use it for.

**4:59** · And therefore, where you would deploy it.

**5:04** · All of that has fundamentally changed.

**5:06** · And for me, the journey really started about 15 years ago.

**5:10** · And I had the benefit of seeing some early works in the area.

**5:15** · And as all Stanford students do, you break the problem down.

**5:20** · You reason about it from first principles.

**5:22** · And you come to the conclusion, literally, everything has changed.

**5:25** · And so here you are, computer scientist students, this is really the first generation of AI becoming useful.

**5:34** · And where we, a couple years ago, was in the generative part of AI.

**5:40** · And as you guys know, generative AI not only made it cool for us to do image generation, and text summarization, and translation, and whatnot, but generative AI also enabled us to think.

**5:54** · And so when I saw generative AI, what other people saw was that it was able to generate images, and I surely appreciated that as well.

**6:04** · But the fact that you can generate thoughts in the form of images, but you can generate thoughts, you can also reason with it.

**6:12** · And the ability for AI to think after GPT was very, very obvious.

**6:18** · Now, the question is, how would you train, how would you fine tune an AI to be able to reason step by step by step?

**6:25** · And how would you teach it how to do so at fairly large scale in a semi-supervised way?

**6:31** · And so those are the engineering problems you had to solve.

**6:34** · But the moment you see GPT, you say, aha, thinking is just around the corner.

**6:39** · And thinking is generating tokens that you consume internally.

**6:43** · And generating tokens that you consume externally would be called tool use.

**6:48** · And so the idea that after GPT happened two years ago, that we would be at this moment, was fairly easy to predict.

**6:57** · Now, of course, an unbelievable amount of technology was invented, and a lot of amazing people did amazing work, but you could almost see that moment here.

**7:07** · And so here we You now have agentic systems.

**7:10** · And so now, the question is, what's next?

**7:13** · And what happens in a world, where a computer is not responsive to what you ask it to do, it's not on-demand?

**7:24** · Today's computing is really on-demand computing.

**7:27** · The word "on-demand" was actually created in our generation to talk about how you think about using computers.

**7:35** · Time sharing computers that you would use on-demand became cloud computers.

**7:39** · And cloud computing, of course, is on-demand.

**7:42** · But in your new world of agentic system, the computers are now continuously running.

**7:49** · And so what happens in a world where the computers are continuously running?

**7:54** · What happens to cloud services?

**7:56** · What happened to your personal computer?

**7:57** · What happens to all of these different systems?

**8:00** · Now, there's a great opportunity again to rethink all of that.

**8:04** · And so my introduction to everything about computer science has changed, and everything about every field of science has changed because of the things that we've changed.

**8:17** · And so this a good time to go to school.

**8:19** · OK.

**8:20** · That's it.

**8:21** · What was your question?

**8:23** · You know what, I'm just going to turn it over to the kids.

**8:27** · Codesign.

**8:28** · Codesign.

**8:28** · Codesign.

**8:29** · Let's just go into-- the students have questions.

**8:31** · They've all been asking questions in Discord.

**8:33** · They're all voting on each other's questions.

**8:35** · Codesign is really interesting.

**8:37** · Codesign is super interesting.

**8:39** · And basically, codesign said, back in the old days, we abstracted computing, so that the people who design microprocessors, design microprocessors People who worked on compilers, worked on compilers.

**8:54** · And people who worked on languages, worked on languages, and so on and so forth.

**8:57** · You guys that.

**8:58** · And we actually had different fields.

**9:02** · And in fact, this happened at Stanford.

**9:04** · What's the beauty of risk?

**9:07** · What was the beauty of the work that John Hennessy did?

**9:10** · The beauty of it is that you got to think about compilers and microprocessor architectures harmoniously, codesign, because otherwise, you could end up creating a microprocessor that's super, super tight, and everything is maximally optimized.

**9:27** · But unfortunately, it's hard to compile.

**9:29** · It's difficult. It's not compilable.

**9:31** · And so they created a simpler instruction set that exposed simplicity to compilers, so that compilers could do a better job of generating code.

**9:40** · And it turns out, a simpler machine, codesigned with a compiler, creates better performance than two systems that were optimized individually.

**9:51** · That's very Stanford.

**9:54** · This is part of your heritage as all of you in John Hennessy's trail of amazing work that's left behind.

**10:02** · And so you take that, and you think about, well, what happens in the post world of general purpose computing?

**10:09** · Why is it that every problem in computer science would be solvable by a general purpose instrument?

**10:15** · At some level, you could say, well, if you had a general purpose instrument, you prefer that.

**10:20** · However, there are some extreme problems, whether it's computer graphics back in the old days, or molecular dynamics, or quantum chemistry, or fluid dynamics and large multiscale, mesoscale, multiphysics problems or deep learning.

**10:35** · These problems are so computationally intense.

**10:38** · Why would you use a general purpose computer to go do that?

**10:41** · And so there, the big insight is, if you understood the stood the algorithms, understood the computer systems, understood, if you will, the compilers, the frameworks, and understood the architecture of chips, and you were optimizing all of it at the same time.

**10:59** · And so here are the facts.

**11:02** · This is what happens when you do it what I just described.

**11:04** · NVIDIA is probably the first computer systems company that's extreme codesign.

**11:09** · Meaning, we literally codesign across all of that and including CPUs, GPUs, networking, and switches, and storage.

**11:16** · And so the question is, what you get-- well, Moore's Law, back in the old days, you guys all know about that, Moore's Law was about 2x every 18 months, so call it 10x every 5 years.

**11:29** · So 10x every 5 years is 100x every 10 years.

**11:32** · And that was in the good old days of Moore's Law.

**11:35** · And for all the computer scientists in the room, you know that Moore's Law was underpinned by a concept called Dennard scaling.

**11:42** · And Dennard scaling ran out of steam several years ago, probably about a decade ago, in fact.

**11:48** · And we kept squeezing it.

**11:49** · We kept squeezing it.

**11:50** · But over the course of last 10 years, if you just allowed microprocessors to continue to scale, and you just don't touch the software and just benefit from the speed up of semiconductors, microprocessor design, at best case, you would have gotten 100x, but probably, because Dennard scaling slowed down and Moore's Law largely ended, you probably got something along the lines of 10x over the course of 10 years.

**12:14** · Well, in the case of NVIDIA and codesign, we got 1 million x over 10 years, 1 million x.

**12:21** · And so somewhere between 100,000x and 1 million x, so when you're talking about numbers that big, it really doesn't matter.

**12:28** · And so 1 million x over 10 years, we were able to get scaling and computation scales so large, so fast that AI researchers say, why don't we just take all of the internet?

**12:42** · Why even worry about what data to go curate and what data to create?

**12:46** · Let's just take all of the world's data and just give it to the computer.

**12:50** · And that's really the big breakthrough.

**12:52** · When you're able to do something so insanely fast-- for example, if you were able to travel at the speed of light, where we choose to live doesn't matter.

**13:03** · If you were able to go from New York to California in 10 minutes, everything about society would change.

**13:12** · And so if you're able to do computing a million times faster, everything about computing changed.

**13:18** · And that's really the big breakthrough.

**13:20** · Because of codesign, because of the way NVIDIA approached it, we accelerated computing so far that it created all this infinite abundance opportunity for everybody to think about the future.

**13:31** · And so anyways, here we are.

**13:33** · Cool.

**13:33** · I have a bunch of follow up questions, but I'm not going to ask-- That one word led to that.

**13:39** · GPT 10 \[INAUDIBLE\]-- That's what it's like to work at NVIDIA.

**13:42** · You give me one word, and you get ranted at for about half an hour, because I got too much to share with you.

**13:50** · The question is, how should education evolve in response to the industry is changing?

**13:54** · Yeah.

**13:54** · And that's a really excellent question.

**13:56** · And I think the answer, clearly, is, AI should be part of your curriculum, not just in learning about AI, but using AI for the curriculum.

**14:06** · The problem with textbooks, as you know, it takes an enormous amount of effort to do.

**14:11** · And when I was taking classes at Stanford, Professor Hennessy was still writing his textbook.

**14:17** · It was all handwritten down.

**14:18** · And each week, it seemed like he was writing a chapter.

**14:23** · I don't even how he writes a chapter a week, but every week, he was writing about a chapter.

**14:27** · And then over time, all of those notes turned into a textbook, into the first edition.

**14:32** · And that must have taken several years.

**14:34** · And so I think it's not possible for universities for pre-recorded textbooks to keep up with information and knowledge that's being generated in real-time by AI.

**14:50** · And so I think the future, probably, has to be some union of the two.

**14:53** · And I don't know about you guys, but I can't learn anymore without AI.

**14:58** · And so not only do I have the I read the papers, but I also, once I read the papers, I might ask it to go read a whole bunch of the other papers that are associated with it.

**15:08** · And then now, it becomes a super researcher.

**15:10** · And then first, I ask it to summarize, I ask it some basic questions.

**15:15** · And then after that, you interact with that paper as if it's a researcher that's dedicated to you.

**15:20** · And so most people don't realize that.

**15:23** · I think a lot of people still think that you summarize a document.

**15:26** · But in the process of summarizing the document, that AI learned a lot.

**15:31** · And I think that in the future, I do hope that curriculum are tightly integrated.

**15:39** · In defense of the textbooks, though, I will say that first principles don't change.

**15:44** · In the final analysis, Mead and Conway is still a solid of fundamental methodology as before.

**15:53** · It is true that the scaling process that led to constant current density, constant power density, all of those design optimizations associated with modern semiconductor design, we've exhausted all of that.

**16:12** · None of that is iso anything anymore.

**16:14** · But it's still good to know where we came from.

**16:18** · And so I would still encourage to appreciate the first principles.

**16:22** · While I was going to Stanford, I was already working at AMD.

**16:27** · And I was designing microprocessors at the time.

**16:31** · And it was still really good to see simultaneously, how we design things in practice versus the first principal methods associated with learning about eventually, how to design these things.

**16:46** · And I really enjoyed having freedom, both sides of it.

**16:52** · And I ended up learning a lot more.

**16:54** · And so what that means is, when you're using AI, which is real world, it's contextually relevant now, it's contemporary.

**17:02** · And meanwhile, you have first principles knowledge that you're learning at the same time.

**17:06** · You're kind of getting the same thing that I experienced.

**17:08** · The question is, what are your thoughts on open source?

**17:10** · How does open source stay at the frontier?

**17:12** · Yeah, there's really the question of closed source versus closed proprietary software versus open source.

**17:18** · There's a question of my intentions with open source.

**17:21** · And so I'll start with my intentions of open source.

**17:24** · First of all, NVIDIA uses more Anthropic and OpenAI tokens than just about anybody.

**17:33** · And the reason for that is, obviously, we do a lot of coding, we do a lot of design.

**17:37** · And 100% of our engineers are now agentically supported.

**17:42** · And so I want them to be working with agents, using the latest generation tools, and remodernize how NVIDIA does work altogether.

**17:51** · So number 1, if you can use OpenAI and Anthropic, I would highly recommend you use it.

**17:57** · And the reason for that is because it's useful.

**17:59** · It works really well.

**18:01** · It's getting better all the time.

**18:02** · And as you know, large language models, it's the technology inside by Claude is a product.

**18:09** · And Claude Code is a whole harness around it.

**18:12** · And that harness is getting better all the time.

**18:14** · The model is getting better all the time.

**18:15** · It's not likely that anybody open source go to GitHub, download something, it's going to work nearly as well.

**18:21** · So I highly recommend, and we do, use off the shelf frontier AI models.

**18:28** · The question is, why is it that we're advancing and working so hard on open models?

**18:34** · The reason for that is because language models are very important because they represent the codification of our intelligence.

**18:41** · And we want to automate ourselves, especially it's a very important part.

**18:46** · But you need to know that AI is about learning the representation, the meaning, the structure of information.

**18:54** · And so the question is, where is information?

**18:56** · Well, we're living in information right now as we speak.

**18:58** · The reason why there's structure is the reason why every day, you show up, it's largely the same.

**19:03** · Otherwise, it'd be like practically white noise.

**19:05** · And so the fact that biological systems and physical systems have structure.

**19:10** · And from that structure, I must be able to learn higher level representation.

**19:15** · And if I can learn the representation, then I could manipulate it.

**19:19** · Does that make sense?

**19:20** · And so just because I can learn the representation of language, I can then generate it, I can manipulate it, I could put it to use.

**19:27** · And so I want to do the same thing for chemicals, and proteins, and genes, and physics, and physical systems, robotics, for example.

**19:36** · And so notice, the way you represent all of those things are fundamentally different, because the structure is different and the dimensionality is different.

**19:45** · How you train it is fundamentally different, because you don't have a whole bunch of internet corpus of human language on it.

**19:53** · So you've got to come up with new strategies for all of that stuff.

**19:57** · And so we decided that we would dedicate ourselves in some fundamental pillars, because the company has the talent and the scale.

**20:06** · We have the ability to put the first piece of artifact out in the world-- data, model, how to train it, and several different domains.

**20:14** · And so some of the domains, I care very much about.

**20:17** · One of them is called, of course, Nemotrons language.

**20:19** · And I'll come back to that in a second, why does it we're doing it?

**20:22** · And then second is BioNemo, that's for biology.

**20:25** · And we have Alpamayo.

**20:28** · Somebody mentioned it earlier, for autonomous vehicles, basically, artificial intelligence, navigation.

**20:36** · And then we have Groot, which is a humanoid articulation, robotics, artificial general robotics.

**20:44** · And then we have climate science, basically mesoscale multiphysics.

**20:49** · And so all of these different domains, we decided that we should go and pioneer it.

**20:56** · And the reason for that is because, otherwise, the scientists in these different domains, they simply won't have the scale and the technology necessary to go build that foundation model.

**21:06** · And so we decided that we would do that.

**21:08** · And as a result of doing that, we activated health care.

**21:12** · We activated life sciences.

**21:14** · We're working with every single self-driving car company in the world, doesn't matter which one it is.

**21:19** · There's NVIDIA in there somewhere.

**21:20** · And so we enabled that entire ecosystem to really flourish.

**21:25** · And we're working with robotics right now, and so on and so forth.

**21:29** · Without us making that first effort and building a foundation model, it's hard to activate the whole industry downstream.

**21:36** · And so it's really about expanding AI and democratizing this capability.

**21:42** · The reason why we do language models is because, two reasons-- one, there are too many societies, where the scale of their language is not big enough for somebody else to decide to make it a high priority.

**21:56** · They'll understand Swedish.

**21:59** · But making Swedish a top priority is not likely, because the country is big, but not so big.

**22:06** · Chinese, of course, well taken care of.

**22:08** · Indian, certain dialects, very well taken care of.

**22:11** · But as you know, you have 230 others.

**22:14** · And so there are too many others that unless you deeply care, it's never going to be great.

**22:20** · And human intelligence, no matter the size of your population, somebody should care.

**22:26** · And so we created a large language model that's near frontier, Nemotron is close to frontier.

**22:31** · And we make everything available, so that if somebody wants to then fine tune it into whatever language of their choice, they got no trouble doing that.

**22:39** · And then the second reason is very important, is because we want to also take these language models and fuse it with the domain-specific models because of human priors.

**22:53** · So for example, Alpamayo is a language model fused with a world model.

**23:00** · And so on the one hand, it's really designed to detect cars, and roads, and things like that.

**23:05** · But on the other hand, we also believe that if the AI model, if Alpamayo, the self-driving car model, can reason reason like a human, and it could reason with human priors, then the amount of experiences it needs to have before it could be an extremely good and safe driving car, the amount of training data is reduced, and we've proven that.

**23:28** · Alpamayo is probably one of the most effective self-driving car systems in the world.

**23:34** · And it's really only experienced a few million miles, not billions of miles.

**23:39** · And so the system actually works.

**23:42** · So anyways, I just gave you a long-winded answer.

**23:44** · I broke it all down.

**23:45** · You can't just ask a simple question.

**23:48** · Well, we talked about-- Open models is really important.

**23:50** · And then one more thing.

**23:53** · That wasn't enough.

**23:54** · One more thing.

**23:55** · If you care to have AI be safe and secure, it has to be open.

**24:00** · And the reason for that is, you can't defend against a black box, and you can't secure a black box.

**24:06** · And you can't put a black box of some incredible capability into your system with a completely opaque.

**24:13** · Now, of course, there's a lot of different ways you could solve the opaqueness.

**24:17** · For example, you could say, before it does anything, you have to reason about it to me step by step.

**24:23** · Before you do anything at all, you have to come up with a plan, you have to reason about it step by step.

**24:27** · But you could always lie.

**24:28** · And the nice thing about transparent systems is that then everybody gets to interrogate it.

**24:36** · If you have a transparent system, then researchers get to use it.

**24:39** · If you have a transparent system, an open system, then the way you defend against super-agentic systems in the future for cybersecurity is obviously not to go into a battle of who gets the better one.

**24:51** · You come up with some model, model 7.0.

**24:55** · And the only way I combat against that, I'm completely vulnerable until I come back with an 8.0.

**25:01** · And then you got to come back with a 9.0.

**25:03** · And we just go back and forth, driving each other nuts.

**25:06** · And that's obviously not the smartest way to do it.

**25:09** · The smartest way to do it is, you're going to create these incredible cybersecurity systems or the cybersecurity threats.

**25:17** · And what we're going to do is, we're going to have millions, billions, swarms of cheap AIs.

**25:23** · And we're going to systematically surround it.

**25:25** · And so it's, if you will, a giant dome.

**25:29** · So for example, Nemotron Nano is being used for cybersecurity.

**25:33** · And so all these cybersecurity firms take Nemotron Nano, because it's so fast and so cost-effective, you can train it to detect cyber attacks and then just deploy trillions of them.

**25:46** · Yeah.

**25:47** · On the topic of open scaling, we hung out in January.

**25:52** · I feel like-- you know that one scene in Thor?

**25:55** · Do you remember, he was just hanging, and he kept rotating in that direction?

**26:00** · It's zero gravity.

**26:00** · Here at AI Coachella, we got no gravity.

**26:02** · \[CHUCKLES\] Thor-- Ragnarok.

**26:05** · Do you remember that?

**26:06** · We can move a little bit back.

**26:07** · \[INAUDIBLE\] OK.

**26:08** · You guys don't watch movies?

**26:10** · Well, we got a whiteboard, too, if you want to get up and walk.

**26:13** · So in January, we met, and we talked about this topic, open scaling.

**26:16** · We talked about bottlenecks.

**26:17** · We talked about data as one bottleneck, compute as another bottleneck.

**26:23** · There's at least one experiment that we announced at GTC together, which was the coalition scaling idea.

**26:29** · The second is on how to improve utilization on compute, which is increasingly scarce.

**26:34** · It came out last week that there was a memo at xAI that said Memphis cluster pool is running at 11% MFU utilization, which I think, corresponds to something like 11 billion or something of unutilized MFU flops.

**26:48** · How can the open space-- well, maybe you could talk a little bit about why coalition scaling is an experiment worth trying.

**26:55** · And we have Brian coming, actually, in the final office hours, to talk about progress.

**26:58** · And then how do we get utilization to be better for the open ecosystem when you don't have fully integrated companies that can optimize up and down the stack?

**27:08** · Yeah.

**27:09** · Do you guys know what my MFU is?

**27:12** · And FU, do you guys know?

**27:15** · You guys don't use that anymore?

**27:17** · So MFU is just simply wrong.

**27:21** · It's the amount of the percentage of flops, basically, that you consume while doing your work.

**27:31** · Model flops utilization.

**27:32** · Yeah.

**27:33** · And so unfortunately, with every metrics, depending on what you measure, you could be measuring the wrong thing.

**27:41** · And so let me tell you why.

**27:43** · If you ask me, do I want to be at high MFU personally or low MFU?

**27:49** · I would like to be at low MFU all the time.

**27:52** · And the reason for that is because I want to be so smart, I'm overprovisioned for the work.

**27:57** · Because I'm overprovisioned, I got so many flops and sitting idle.

**28:01** · And the reason for that is because, the way the computing works in these large scale data centers is, you have flops, you have memory bandwidth, you have memory capacity you have network capacity.

**28:12** · At any given point in time, something is bottlenecked.

**28:15** · At any given point in time, something is bottlenecked.

**28:18** · And so what you want to do is you want to overprovision on everything, so that you can avoid Amdahl's law.

**28:26** · Otherwise, you're fighting Amdahl's law all the time.

**28:28** · But then if you're provisioning for peak, not your base loads, then you're going to have a bunch of those flops sitting while overprovisioned, when you don't need them, because spiky.

**28:36** · At the right time, it goes to 100% MFU, but only for a short period of time.

**28:42** · And if that short period of time, you don't get all that overprovisioned flops, then during that short period of time, it becomes a long period of time.

**28:50** · And so what are you seeing for teams that are trying to-- And flops are cheap.

**28:55** · No, flops are cheap.

**28:56** · H100s are going up in price.

**28:59** · Well, not because of its flops, but because of H100.

**29:01** · Hopper, its bandwidth, its architecture, its everything else, not just its flops.

**29:08** · So should we think about compute as not a scarce resource?

**29:12** · No, no, that's not the question.

**29:14** · It's like this-- when you ask about a car, back in the old days, when we were unsophisticated, we used to say, how many horsepower is your car?

**29:22** · But these days, who does that?

**29:24** · So what's the right measure you think we should be thinking about?

**29:26** · Performance.

**29:27** · And when you tell the teams, guys, this is the perf we've got to hit next year, what are you finding is the eval you're reaching for more and more?

**29:34** · You have to come up with a real eval, a really serious eval.

**29:39** · Because otherwise, you'd be improving your flops.

**29:41** · You figure out something that you guys can improve.

**29:45** · And you're improving that number, it doesn't make you smarter.

**29:48** · You're improving that number, it doesn't make you more successful.

**29:50** · And so there's nothing wrong with having a lot of flops, but it's not the complete.

**29:59** · Necessary, not sufficient, that's all.

**30:01** · In one sense, you could think about the output of tokens as intelligence.

**30:05** · So it should be some unit of intelligence per watt?

**30:08** · Yeah.

**30:08** · Yeah.

**30:10** · Notice, the tokens per watt is more than flops.

**30:16** · In fact, we that now, because for decoding these large language models, the singlemost important thing for generating tokens per watt is actually the aggregate bandwidth across the NVLink 72.

**30:29** · And the MFU is incredibly low, because the prefill is not that much, it's mostly decode.

**30:35** · But you can decouple, decode, and prefill.

**30:36** · It's disaggregated.

**30:37** · And so notice, I just delivered incredibly high tokens per watt with extremely low MFU.

**30:43** · MFU.

**30:43** · But not all tokens are born equal, right?

**30:46** · And so how do we account for that?

**30:48** · When you're designing the systems of the future, what is the right way to measure without a standard measure of intelligence?

**30:53** · When you have coding tokens being more valuable for watt than, I don't know, some other kind of token.

**30:58** · Does that question make sense?

**31:00** · Makes perfect sense.

**31:01** · You always have to come back to not just optimizing for SAT scores.

**31:07** · You're optimizing for something bigger.

**31:09** · And so that's basically it.

**31:11** · It's the same idea.

**31:12** · You have to decide what evaluation.

**31:15** · As you know, eval, how you evaluate success matters a lot in how people perform.

**31:22** · And so what NVIDIA does extremely well inside the company is the systems that we create for evaluating architectures.

**31:29** · And flops is too contrived.

**31:32** · Because if it was that easy, then I wouldn't be here.

**31:37** · You have a hard job, which is to try to design an index of different intelligences.

**31:43** · I think when our teams are researching on the NVIDIA architecture, we've got one lab doing coding, another one pushing the frontier of superconductivity and so on.

**31:51** · And they all have completely different evals they're measuring for, but they're all using NVIDIA chips.

**31:56** · So how do you solve that problem?

**31:59** · Your customers all have their own evals?

**32:00** · Yeah.

**32:01** · But the architecture of the underlying platform-- That's why it's so hard.

**32:05** · And it is true, it's that hard.

**32:08** · The problem is this.

**32:09** · If you build something that's too overfit for something, you could be incredibly good at it.

**32:16** · And so you're overfit for this one problem.

**32:18** · You're insanely amazing at it.

**32:20** · But then the problem is that market, that problem space may not be big enough to fund a sufficiently large R&amp;D.

**32:28** · And so you want to be good at many domains, multidomain.

**32:33** · On the one hand, on the other hand, if you're good at everything, then you're good at nothing.

**32:37** · You became general purpose.

**32:39** · And so writing that balance, by the way, is artistry.

**32:43** · That's what I do for a living.

**32:46** · What should we not do?

**32:47** · What should we double down on?

**32:49** · What should we 10x on?

**32:51** · That requires some amount of vision, strategy, some amount of trial and error, some just personal enjoyment and entertainment, iteration, all of that.

**33:03** · Can we talk about the Canvas of Feynman, which is a trip I'm very excited about?

**33:07** · But it's been hard to get info on it.

**33:09** · What's the canvas telling you now about what your art piece is going to look like for the Feynman?

**33:14** · Well, I can tell you the journey that we came on.

**33:16** · And so if you look at Hopper.

**33:18** · Hopper was designed for a problem space that was rather new.

**33:22** · It called pretraining.

**33:24** · And so pretraining came along.

**33:26** · And we came to the conclusion that although the generation before it was fairly significant already, that we should build tremendously large ones, larger than any of the largest scientific supercomputers in the world.

**33:45** · So that's a very big deal, that the largest supercomputer in the world was about $350 million.

**33:51** · And we thought, you know what?

**33:52** · Pretraining is going to be such a large domain and such an important problem.

**33:56** · We should design systems that could be multibillion dollars.

**33:59** · At the time that we're thinking about doing this, it just sounds insane.

**34:02** · You would have precisely zero customers.

**34:05** · And the reason for that is because the most expensive thing that has ever been sold was $350 million.

**34:10** · And you're building something that's multiple billions of dollars.

**34:13** · So you're building for precisely a marketplace of zero.

**34:17** · But we went and did it anyways on first reasoning.

**34:20** · And so Hopper was designed for pretraining, and that was a great call.

**34:23** · The second thing that we did was, we said, OK, well, after training, we're going to keep making training better.

**34:30** · But the goal of AI isn't training.

**34:33** · The goal of AI is inference.

**34:35** · And what kind of a system would inference really care about?

**34:39** · And so we created a system called NVLink72.

**34:42** · And the reason we did that was because decode in processing the neural network, there's the prefill, which is really context processing and things like that, and attention processing, and then the decode, which is generating all these tokens.

**34:55** · The generation of tokens requires really high memory bandwidth.

**35:00** · And the amount of memory bandwidth you need is way more than one chip can possibly provide.

**35:06** · And so we said, why don't we gang up 72 of these things?

**35:09** · And so we had to invent all kinds of new systems for switching, and interconnects, and create all kinds of new \[INAUDIBLE\].

**35:15** · And we created, essentially, the world's first rack scale computer.

**35:19** · It's called Grace Blackwell NVLink 72.

**35:22** · The speedup over the previous generation, 50 times.

**35:25** · In two years, we improved something by 50 times.

**35:28** · Moore's Law would have improved by 2x.

**35:31** · So the architecture and the insight was fantastic.

**35:35** · And decode, and inference, and large language models, and token generation, all of that landed at exactly the time that Grace Blackwell came out, and boom, took off.

**35:45** · So Grace Blackwell, another incredible generation.

**35:48** · Now, the question is, what happened to Vera Rubin?

**35:51** · And what's the big idea?

**35:53** · Well, the big idea is that the goal isn't just to think, the goal is to do work.

**35:59** · And so Vera Rubin is designed for agents.

**36:02** · And so the question is, what is the compute pattern?

**36:04** · What is the processing pattern of agents?

**36:06** · And agents, of course, you have to load a fair amount of memory.

**36:12** · Long memory, he's got working memory.

**36:14** · So long-term memory, we put it into storage.

**36:16** · And we got that storage needs to be able to directly communicate with the GPU.

**36:19** · You can't be copying that data off of the network storage, but you want storage to be connected right into the processor itself.

**36:28** · And so we have storage that's connected to the fabric.

**36:31** · We're going to use a lot of tools.

**36:34** · And so CPUs are going to be really important.

**36:36** · But the CPUs of the current generation was really designed for cloud computing.

**36:41** · And so you have these CPUs with hundreds of cores, like 200 cores.

**36:46** · Well, the CPUs of agents, because the AI is this multibillion dollar system, and it sends off an instruction to use a tool, and that tool is going to run on the CPU.

**37:00** · Meanwhile, this computer, this GPU supercomputer, this multi-billion dollar system, is waiting for this one CPU.

**37:07** · And so that CPU really wants to have extremely low latency.

**37:11** · So we designed Vera, which is for current generation, for multiple core, single-threaded code, it is, by far, the most performant.

**37:22** · And so we created a CPU just for that.

**37:25** · Notice, the way you solve this problem intuitively is, you think about, what is the computing pattern?

**37:30** · How is it different than the past?

**37:32** · You have to have some mental model about it.

**37:34** · And you create a system that you can go and go build to run that.

**37:41** · And so now, agents are here.

**37:42** · We're going to run that on Vera Rubin.

**37:44** · And hopefully, when Feynman gets here, it's going to be all software.

**37:51** · We call them agents today, but it could be modules in the past or submodules.

**37:56** · And so in the future, you're going to clearly have systems of agents, and agents with subagents, and subagents with subagents.

**38:02** · And so you're going to have this swarm of agents.

**38:07** · And what kind of computer does that manifest?

**38:10** · And so that's likely what Feynman's about.

**38:12** · I have one more follow up question on that, which is, one of the things you've always done well is spot bottlenecks one generation ahead, and then try to presolve for that in the supply chain.

**38:21** · A year ago, that was, photonics ended up becoming a huge solution.

**38:26** · As we look at energy as a bottleneck, literally, copper wires are one of the transmission bottlenecks.

**38:33** · How does that get solved in your view?

**38:37** · Energy is just everywhere.

**38:40** · Well, the first thing that we could do that is in our control, as with everything in life, whatever the problem is, whatever the external concerns are, you should do something that's in your control.

**38:55** · And in our control is energy efficiency.

**38:56** · So if you look at tokens per watt, we improved it by 50x.

**39:01** · And then we'll have to keep on improving it by significant factors.

**39:05** · And it compounds.

**39:06** · That's the first thing we can do.

**39:07** · We can control that through codesign, architectures, and things like that.

**39:12** · And the second thing that we could do, the thing we could inspire people, and that's through a lot of education, inspire the ecosystem to get ready for this.

**39:22** · And I've been, over the last half decade, helping people understand the amount of compute that's likely to be coming.

**39:28** · And I just told you guys something about how I reason through how much energy is going to be necessary.

**39:34** · The amount of energy that we need for computing is likely probably, 1,000 times more than we currently have.

**39:41** · And that's an enormous amount of energy.

**39:43** · However, the way to think about that is, in the future, computers are going to be two things-- it's always going to be generated, because it's intelligent, it's contextually aware.

**39:52** · So it's going to be generated.

**39:53** · And the number 2, it's going to be continuous.

**39:55** · And so this generative computing, in a continuous way, compared to prerecorded retrieval-based computing that is only initiated per use, the question is, how do you think about the amount of energy necessary for that?

**40:11** · So I think, if you say, we need 1,000 times, I wouldn't be surprised if we're off by a couple of orders of magnitude.

**40:17** · And so we need a lot more compute, we need a lot more energy.

**40:20** · And so you got to go and explain this to people.

**40:22** · And so I got to explain it to people in a way that's common sense.

**40:26** · And they can observe it.

**40:28** · And there are indicators along the way that, in fact, this is happening.

**40:32** · And notice, as I was breaking it down for you guys, reasoning about it for you, so it's common sense to you.

**40:39** · And so the amount of energy is high.

**40:40** · And then lastly, the source of energy.

**40:44** · Now, there's all kinds of sources of energy, but unfortunately, because of great concerns about the cost of sustainable energy, we under-invested in sustainable energy.

**40:59** · But this is the best time ever in the history of humanity to go and invest in sustainable energy.

**41:05** · And the reason for that is because the market forces are so strong.

**41:08** · Back in the old days, you needed government subsidies to go build solar farms and government subsidies to go build nuclear plants.

**41:16** · And now, you can just market.

**41:18** · We'll pay you to do it.

**41:19** · And so market forces are so powerful right now.

**41:23** · This is our best chance to upgrade our grid, our archaic grid, and add sustainable energy of all kinds.

**41:30** · And this is a great time.

**41:32** · In terms of education, what I've learned as well, we designed the class for the students here.

**41:36** · Turns out, a lot more people, especially a lot of investors and capital allocators, are watching this \[INAUDIBLE\].

**41:41** · Is that right?

**41:41** · Oh, shocks.

**41:42** · Why don't we put it up?

**41:44** · Yeah.

**41:47** · I'm just kidding.

**41:47** · If there's education you'd like to do to that audience, feel free to drop it.

**41:51** · Repeating yourself after a while with capital allocators can get repetitive.

**41:57** · I don't mind that.

**41:57** · So if you'd like to transmit, feel free to-- what is the next question we should take?

**42:03** · The question is, how best to spend \[INAUDIBLE\] faculties over the next few years?

**42:07** · Yeah.

**42:08** · So first of all, on the pain and suffering comment, there's some advice that says, you should choose what you love and what you're passionate about.

**42:21** · That's what your career should be.

**42:23** · And I think that's terrific.

**42:25** · I think that's terrific.

**42:26** · If you happen to know what you're passionate about, if you happen to know what you love-- but I think there are a lot of people who don't know what they're passionate about, and they don't what they love.

**42:38** · And the reason for that is because nobody knows everything.

**42:41** · How could you know what you don't know?

**42:44** · So in a lot of ways, the idea that you would only choose careers that give you passion, that makes you happy is a bar that I think is too high, number 1.

**42:58** · And the reason for that is because, whatever you decide to do for a living, whether you found something that you're passionate about or this is your job-- and in my case, it used to be cleaning toilets and bussing tables, it was my job.

**43:14** · And I will do the best I can in my job.

**43:18** · Whatever you give me as a job, I will do the best I can possibly do.

**43:22** · And I do that today.

**43:24** · Now, there's a misunderstanding that somehow, CEOs, we love our job.

**43:31** · And many say, oh, I'm passionate about my job.

**43:35** · I love my job.

**43:36** · They're lying.

**43:38** · There's not one CEO who can say that from the moment I wake up to the moment I go to bed is just zippity doo dah.

**43:48** · The fact of the matter is, I really love doing 10% of my work, and 90% of my work is hard.

**43:55** · And I do it to the best of my ability, anyhow.

**43:59** · And I suffer through it.

**44:01** · I literally suffer through it.

**44:03** · I prefer to do something else, that other 10%.

**44:06** · But that other 10%, there's only so much quantity of that.

**44:09** · And every company has abundance of problems.

**44:11** · And there comes in different types.

**44:13** · And you're going through life, you're going to have abundance of problems that are going to come in different types.

**44:17** · And you just have to learn how to condition yourself to want to get to a better state, no matter how hard.

**44:24** · To get better, no matter how hard.

**44:27** · And that's suffering.

**44:28** · You don't like doing it, but you're doing it with all your might anyways.

**44:32** · What do you call that?

**44:33** · That's suffering.

**44:34** · And so I think that when you suffer, and you have the benefit of struggle, and you're being presented with many opportunities like that, it teaches you resilience.

**44:46** · And when the time comes, and the world, or your family, or your company, or your colleagues, they need you to be tough.

**44:53** · They need you to be resilient.

**44:54** · They just need you to be able to fight through it.

**44:59** · You don't have that character about you.

**45:01** · You don't have that muscle, unless you've gone through it a whole bunch of times.

**45:05** · And so I'm advising that you not seek for just joy, that you also seek for some pain, some suffering, because you're going to need it, someday.

**45:19** · And then lastly, it's just your job.

**45:24** · As preacher Huang once said, don't wake up with a loser mindset.

**45:29** · The question is, what's your favorite order of Denny's?

**45:33** · Yeah, Corvallis, really, should have a Denny's.

**45:38** · After all these years, frankly, it's about time.

**45:41** · And so there was that one Chinese restaurant and Woodstock's, of course, Corvallis Woodstock's Pizza.

**45:51** · It's still pretty good, isn't it, Woodstock's?

**45:53** · It's all that I like American Dream better.

**45:55** · American Dream is better?

**45:56** · OK.

**45:56** · All right.

**45:57** · I'll be back there soon enough.

**45:59** · And so Denny's, I would say, surprisingly, the fried chicken is really good.

**46:06** · It's slightly on the sweet side.

**46:08** · Superbird is excellent.

**46:10** · It's done right.

**46:12** · And then another one, if they're willing to make it for you, make it like a Superbird, but as a grilled ham and cheese with tomato and mustard, if they're willing to make it for you.

**46:23** · They're willing to make it for me.

**46:29** · Not because I'm an alum.

**46:31** · Hey, you use the bus tables here.

**46:34** · Yeah.

**46:34** · Yeah.

**46:35** · We'll make special for you.

**46:36** · But those are all good.

**46:38** · The grand slam, I enjoy it like a pigs in a blanket, so that's pretty good.

**46:45** · There's a whole bunch of stuff.

**46:46** · Goodness.

**46:47** · I go all day.

**46:49** · At Denny's, I had my first fudge hot fudge sundae.

**46:53** · I had my first apple pie with cheese on top.

**46:58** · For a Chinese kid, it's like, what is that about?

**47:00** · That doesn't make any sense.

**47:01** · But now, you think about it, it makes perfect sense, apple and cheese.

**47:05** · But anyways, I had my first milkshake when I was at Denny's.

**47:10** · I had a whole bunch of firsts.

**47:12** · Denny's was eye-opening for me.

**47:14** · Man, before we lose you to the memory lane, next question, please.

**47:19** · Those are some of the most important questions.

**47:21** · Agreed.

**47:22** · Yes.

**47:23** · The question is about your thoughts on adversarial countries, getting access to NVIDIA chips.

**47:29** · First of all, so you know what we make for a living.

**47:31** · We make GPUs.

**47:34** · And GPUs are used for video games.

**47:37** · They're used for delivering soy sauce.

**47:40** · They're used for medical imaging.

**47:42** · If you had a CT scan done yesterday, I'm fine.

**47:46** · But behind it was NVIDIA.

**47:48** · NVIDIA is in every single medical imaging system in the world.

**47:51** · And so the question is, what is it that you build?

**47:56** · What I'm fundamentally against, and it makes no sense to this moment, is to compare NVIDIA GPUs to atomic bombs.

**48:06** · There are a billion people with NVIDIA GPUs.

**48:08** · I advocate NVIDIA GPUs to all of you.

**48:10** · I advocate NVIDIA GPUs to my family, to my kids, to people I love.

**48:14** · But I don't advocate atomic bombs to anybody.

**48:18** · So that analogy is stupid.

**48:22** · And so if you start from there, you can't finish a thought.

**48:27** · If you start from believing that, you can't finish the rest of the thoughts.

**48:31** · The second idea that I consider completely ridiculous.

**48:36** · Why should American companies go compete in foreign countries?

**48:40** · You're going to lose it anyways.

**48:43** · You're going to lose it anyways.

**48:44** · So why go?

**48:46** · Well, if you guys all apply that same philosophy, why wake up in the morning?

**48:51** · And so I don't prescribe to "We are going to lose anyways."

**48:55** · I don't prescribe to that.

**48:57** · If you want me to lose, you're going to have to deal it to me.

**48:59** · But I'm going to have to put up a fight.

**49:03** · And I put up a lot of fights over the years.

**49:06** · I'm doing OK.

**49:10** · And as you know, the battle, the competition serves markets.

**49:14** · It enhances your company.

**49:16** · I'm not a little bit afraid of having to go and compete in the marketplace.

**49:21** · But the idea that I'm going to lose anyway, so why go compete, makes no sense to me.

**49:25** · And then lastly, the idea that somehow, we should deprive certain countries of general purpose computing, and we can all acknowledge now, NVIDIA is a general purpose computing company, I just gave you a whole bunch of general purpose use cases, is a general purpose computing company, to be deprived of that, so that one or two companies could benefit from depriving other people of it, that makes no sense either.

**49:49** · Why should one industry suffer, so that another one or two companies benefit?

**49:56** · The American technology industry is one of our national treasures.

**50:01** · You are going to be part of it.

**50:04** · And if I do my job, when you are done graduating, you're going to graduate into the mightiest industry in the history of humanity.

**50:15** · But if we give it up for some reason, or we, through policy, decide that we can't go, and sell, and concede 2/3 of the world to other companies, by the time that you graduate, you would have gone into a shell of an industry.

**50:34** · That shell of an industry, we've seen before, a long time ago, the same arguments went against America in telecommunications.

**50:44** · Today, America has no telecommunications fundamental technology anymore.

**50:50** · It was all completely policied out of our country.

**50:53** · And so somebody has to put up a fight for that.

**50:56** · Some of these reasoning systems, to say that AI is going to come, and it's going to be a singularity moment-- that singularity moment, the moment it comes, it's going to be the most powerful thing in the world.

**51:08** · It's come as a flash.

**51:10** · We have no idea whether it's going to come on Wednesday or Thursday at 7 o'clock.

**51:15** · But when it comes, it's going to be game over.

**51:18** · Some percentage chance that it'll be the end of society, as we know it.

**51:22** · Come on, we all watch Dune.

**51:26** · We don't have to repeat it.

**51:28** · And so I think that living their fantasies out, their science fiction fantasies out in public demonstration, when everybody is relying on their words and believing the words, is irresponsible.

**51:44** · It is not true.

**51:45** · It is not true that we have no idea how these systems work.

**51:48** · It is not true.

**51:49** · It is not true that the technology is going to, somehow, in some nanosecond, become infinitely powerful, and therefore, it's going to take over the world.

**51:58** · It is not true.

**51:59** · It is not true.

**52:00** · There is no way to defend against it.

**52:02** · It is not true.

**52:03** · These things are all being made up.

**52:06** · And it's made up in a way that, unfortunately, even harms all of you.

**52:11** · You're in computer science.

**52:13** · You're hoping that when you graduate, people care about computers.

**52:20** · We want to create a future that is optimistic about the technology that you are learning to master.

**52:27** · We want to create that future.

**52:29** · We want to make sure that America, we want to make sure that everybody benefits from AI.

**52:33** · Everybody should have AI.

**52:35** · Nobody should have nuclear bombs.

**52:36** · Can you guys agree with that?

**52:38** · Yeah.

**52:38** · OK.

**52:39** · \[APPLAUSE\] And so young man, thank you for triggering me.

**52:46** · I'm just kidding.

**52:47** · \[CHUCKLING\] I'm just kidding.

**52:49** · I'm just kidding.

**52:50** · I just wanted to get it out.

**52:52** · So we're rational optimists here at AI Coachella, so we believe in optimism.

**52:55** · I'm going to push back a little bit on a different angle.

**52:58** · I completely agree, reasoning by analogy is a problem.

**53:00** · Once you start with bombs, you should do first principles.

**53:04** · What we are observing is that compute-- we are compute-constrained in America.

**53:09** · Independent teams, startups, universities, they can't get compute.

**53:14** · So from a preference order perspective, shouldn't America get first priority to a scarce resource before we start shipping it off?

**53:20** · Absolutely.

**53:21** · That's not happening.

**53:22** · Absolutely not.

**53:24** · \[CHUCKLES\] There's the gotcha.

**53:27** · Yeah, absolutely and absolutely not.

**53:28** · Why not?

**53:29** · The question is, why not?

**53:31** · There's plenty of chips.

**53:32** · If the president of Stanford places an order, I promise you, I'll deliver it.

**53:38** · You guys heard it here.

**53:40** · All right.

**53:43** · Ahead of-- This is not funny.

**53:46** · This is not funny.

**53:47** · We are dying out there.

**53:48** · No, no, this is not funny.

**53:49** · That's right.

**53:50** · This is a serious matter.

**53:54** · It is not true that people are giving me orders, placing orders, and we're not delivering chips.

**53:58** · It is just not true.

**54:00** · You got to place orders.

**54:01** · The fact of the matter is, the fundamental problem is actually something very different.

**54:07** · Stanford needs compute.

**54:09** · Science needs compute.

**54:12** · The fundamental problem is, the system is no longer built to be able to deliver massive scale compute.

**54:20** · And the reason for that is because, just think, all of the research departments here at Stanford, they're all in different departments.

**54:28** · You all raise your own funding.

**54:29** · You all get your own grants.

**54:31** · Nobody's going to go share their grants.

**54:33** · But none of the grants are big enough to have a large enough compute that you use some of the time, but when you use it, you need it to be incredible.

**54:43** · The world moved away from those centralized computing environments towards everybody just using laptops.

**54:49** · This is today's computing environment.

**54:52** · And fundamentally, all the universities-- Stanford is not alone, you don't have a budget for $1 billion compute.

**55:00** · It doesn't exist.

**55:01** · But whose fault is that?

**55:03** · Stanford's.

**55:05** · And the reason why you have to say that is because I'm empowering-- when somebody is at fault, you empower them to solve it.

**55:13** · Do you agree?

**55:15** · Oh, yeah, it's not your fault. Son, it's not your fault. Your failure, it's not your fault.

**55:19** · He's not your talking to me, right?

**55:24** · Hey, son, you're an idiot.

**55:25** · It's not your fault. No, it's absolutely your fault.

**55:29** · And so by saying that, it's absolutely your fault, you're also empowering yourself to solve it.

**55:33** · Isn't that right?

**55:35** · You're empowering yourself to solve it.

**55:38** · You just talked to somebody who feels, I can do something about my future.

**55:45** · You're talking to somebody who believes in that.

**55:48** · And so if I were Stanford, you have to find a way to change the way you do budgeting, the way you deal with computing.

**55:56** · You have to find a way to aggregate and build yourself a linear accelerator, just like Stanford has done in the past.

**56:02** · We need to build campus-wide supercomputers that everybody share.

**56:06** · Now, you could also go and just contract somebody else to do it.

**56:09** · I mean, that's all possible.

**56:10** · But you do need to have $1 billion.

**56:13** · You need to have some reasonable fund to go build something like this, because that's how much you cost.

**56:18** · But that's just what it takes.

**56:19** · I mean, last I checked, we've got, what, $40 billion endowment here?

**56:23** · How would you put that to use if you were starting-- We're going to cut $1 billion of it right away and give it to somebody as a cloud service, and have every single student and every researcher here have access to AI supercomputers.

**56:36** · I would do that right away.

**56:37** · Now, of course, you've got to go plan things.

**56:40** · If you want to buy $1 billion worth of tomatoes, you don't show up to the grocery store and say hi.

**56:45** · And then they don't have $1 billion of tomatoes, and you go, aha, you're withholding tomatoes from me.

**56:51** · \[CHUCKLES\] That's just ridiculous.

**56:56** · And so you got to do some planning.

**56:58** · And so what you got to do is you got to say, next year, we need to have $1 billion worth of computing for Stanford.

**57:03** · And so we'll go build it.

**57:07** · All right.

**57:07** · You know what?

**57:08** · We'll move on.

**57:08** · But thank you for that.

**57:09** · Yeah.

**57:10** · Yeah.

**57:11** · Yeah, exactly.

**57:12** · \[APPLAUSE\] We'll come back to that one.

**57:18** · \[LAUGHTER\] What is the best and worst part of your job?

**57:22** · When you're CEO of a company, you have the benefit of a lot of really fun things.

**57:28** · Like for example, you're really the person who has to conceive of the intersection between vision, and strategy, and execution.

**57:37** · And so you have to live in that world.

**57:41** · And when you're a company with capability, and I'm surrounded by amazing computer scientists, and many of them from Stanford, when you're surrounded by people like that, when you have a vision, it's very realizable.

**57:51** · And because you're with amazing people, your vision is more ambitious.

**57:56** · So I think that's the fun part.

**58:00** · So that fun part, I get to do almost all the time.

**58:03** · I'm always constantly updating my view of the future, and my vision of the future, and our role in it, and how we reinvent ourselves, so that we could contribute more to that future or go invent that future in the first place.

**58:18** · And so as a CEO, you get to live in that world, and that's fun.

**58:22** · It's very imaginative.

**58:24** · It's very strategic.

**58:25** · It's highly complicated.

**58:28** · There's no right answer.

**58:30** · In a lot of ways, it's creativity at its most.

**58:34** · On the other hand, what comes with that power is the responsibilities for a bunch of people who joined you in that spaceship, that joined you in that vessel.

**58:45** · And they want to help you create this future.

**58:49** · And they're part of your team.

**58:50** · And you feel a deep responsibility for their well-being.

**58:54** · And so when the company is not doing well, or the company, in the older days, when we were, in the beginning, trying to find our way, we probably nearly went out of business four or five times.

**59:05** · I mean, literally almost went out of business.

**59:07** · And we were on fumes or we were really flat on our back.

**59:11** · And so during those times, it's embarrassing.

**59:15** · It's humiliating.

**59:16** · It's hard.

**59:17** · You don't what the answer is.

**59:19** · Oftentimes, you're in the dark.

**59:21** · You're afraid.

**59:23** · All of those feelings that we have as humans just multiplied by 1,000, 1 million.

**59:30** · And when you're a public CEO, your face is always out there.

**59:36** · And when you do well, people are happy.

**59:38** · When you don't do well, they're fast to tell you.

**59:43** · And so for me, it's a highly vulnerable profession.

**59:50** · And so you're not naked, but you feel it.

**59:54** · The question is, what's the biggest mistake you've made in the early days of NVIDIA?

**59:57** · And what did you learn from it?

**1:00:00** · Let me give you an example of what somebody might say, and I'll say that that's not.

**1:00:08** · And so anybody who knows our history would know that the first generation of our products, the architecture, the technology we used was completely wrong.

**1:00:19** · It's not a little bit wrong, it's like completely wrong.

**1:00:22** · The fact that smart engineers, and professionals, and we were actually funded, and we created this thing, and it's like, check it out.

**1:00:31** · It doesn't work at all.

**1:00:33** · And so using curved surfaces instead of triangles, no z-buffer instead of z-buffer, forward texture mapping instead of inverse texture mapping, we did everything wrong.

**1:00:44** · We did everything wrong.

**1:00:45** · No floating point inside, we did everything wrong.

**1:00:48** · And so we made a lot of tremendously bad choices.

**1:00:53** · And I'll say that those are technical bad choices, but it led to strategic genius moves.

**1:01:02** · How do you take a company that had that reputation and wasted a bunch of money and a bunch of time, 2 and 1/2 years, doing it the wrong way and surrounded by competition?

**1:01:13** · And now, here we are, the only one remaining.

**1:01:17** · And so that transformation taught me a lot about the importance of-- technology is important, but strategy is so important.

**1:01:29** · And so how you see the world?

**1:01:31** · How you approach competition?

**1:01:33** · How do you approach the market?

**1:01:34** · How do you conserve resources and apply resources?

**1:01:38** · Those decisions, I learned more in my early 30s, through that deep failure and the company almost vaporizing.

**1:01:47** · I learned so much about strategy and strategic thinking, and maneuvering, and things like that, and it's lasted a whole long time.

**1:01:55** · The mistake that I made, that I would say, was a genuinely straight up mistake is, when the PC or when mobile devices took off, we were approached by very important companies that are important in the mobile space, to work on some mobile devices.

**1:02:22** · And the choices that I made, I think the answer when they approached us, the answer should have been, no, not interested.

**1:02:34** · But we decided to shift a bunch of our resources to go build mobile devices.

**1:02:40** · And I thought that we could add a lot of value, but I think, if I were to have thought through it a couple more clicks, the amount of value you could really deliver for the things that we know how to do and what we're good at, it's probably marginal at best.

**1:02:55** · And so I shifted the company to go into mobile devices.

**1:02:58** · It grew into a billion dollar business and that kind of positive reinforcement.

**1:03:03** · And then shortly after, during the 3G to 4G transition, we were just 100% locked out.

**1:03:10** · And Qualcomm was the leader in that 3G to 4G modem.

**1:03:16** · And that's the most important part of the phone, not the SOC, not computer graphics, not even the application processor.

**1:03:23** · The phone is obviously the most important part.

**1:03:25** · And so during that transition, they were able to block us out.

**1:03:28** · I could have probably called it-- if that circumstance were to happen again, I would have said, yeah, it would be a really interesting opportunity for a couple of years, but we're going to get shot out after that.

**1:03:40** · So what's the point?

**1:03:41** · Let's go conserve our resources somewhere else.

**1:03:46** · So we got shut out.

**1:03:47** · We built it up to about $1 billion and then went back to 0.

**1:03:50** · But the recovery was, I took all of that expertise, that extreme low power and energy efficiency expertise, and I shifted all to an application that didn't exist at the time, called robotics.

**1:04:04** · Somebody mentioned Thor.

**1:04:05** · Thor is the great, great, great, great grandson of the chip that we were using in mobile devices.

**1:04:12** · And that entire genealogy, and all the teams, and all the expertise that we built up was really helpful to getting here.

**1:04:20** · And so that's rationalization.

**1:04:25** · Going into that market in the first place was a waste of time.

**1:04:27** · And so that, I think, is a strategic mistake.

**1:04:31** · On strategy, sometimes, strategy is about forecasting, so precisely enough.

**1:04:38** · From a systems perspective, what do you think you've updated your priors on?

**1:04:41** · Or what is the forecasting mechanism you've developed to give yourself some confidence that this fog of war here don't know quite where things are going to go, but generally speaking, we're shooting in the right direction.

**1:04:52** · Is there a systems design advice you'd give folks on when the shape of the future is not entirely clear?

**1:04:59** · Yeah.

**1:05:00** · And in fact, you used all the right words already.

**1:05:05** · The first thing I do is, what am I observing?

**1:05:08** · What am I observing?

**1:05:09** · And based on what I observe, let's reason about it back to first principles, break it all back down.

**1:05:17** · And ask ourselves, so what's going to happen next?

**1:05:20** · And first, so what?

**1:05:22** · Is this a big deal?

**1:05:23** · Hey, deep learning, computer vision, AlexNet, big deal.

**1:05:27** · Is that a big deal or not a big deal?

**1:05:28** · And so the big deal part of it is, my goodness, here's two engineers, Alex and Ilya, and Hinton, of course.

**1:05:39** · And they came up with a neural network model.

**1:05:42** · And boom, it crushed the computer vision capabilities of all the computer scientists, decades before them, in one shot.

**1:05:49** · And so is that a big deal?

**1:05:51** · Is that a big deal?

**1:05:53** · The step up in quality and performance was a big deal.

**1:05:58** · Now, the next question is, so what's going to happen next?

**1:06:00** · How far can you take it?

**1:06:01** · And then if you could do it in this way, what else can you solve?

**1:06:06** · And if this was able to solve some really amazing problems, what does that mean to computers and computing?

**1:06:11** · And so you just keep asking yourself these questions.

**1:06:13** · And so you're just iterating like that, all the way to first principles.

**1:06:17** · And then from that, you create a mental model about the future of computing.

**1:06:22** · And where is it going to be?

**1:06:24** · What can it do?

**1:06:25** · For example, self-driving cars and robotics.

**1:06:28** · How large would models become?

**1:06:30** · And if so, what would computers look like?

**1:06:34** · Processing neural networks, how is that different than processing floating point numbers, and integers, and first principal mathematics?

**1:06:41** · We express everything in FP64 or FP32, but obviously, neural networks don't have to do that.

**1:06:46** · And so you reason through it like this.

**1:06:49** · And then you build up a mental model of the future.

**1:06:53** · And then your company, where you are going to be within it.

**1:06:57** · And then you just work backwards from there.

**1:07:00** · And then now, the question, of course, is, you could be wrong.

**1:07:03** · And oftentimes, if you reason about things properly, you're not completely wrong, but you're not completely right.

**1:07:09** · And so I tend to be very comfortable, saying, OK, these are the things that will likely happen.

**1:07:17** · And these are things that will absolutely happen.

**1:07:20** · And these things may happen.

**1:07:21** · And based on that, I think we ought to go in that general direction.

**1:07:24** · And we'll feel our way through.

**1:07:25** · And now that the skill of building companies then, of being successful along the way is, you're going into this direction, and it's going to take energy, it's going to take time, it's going to take money.

**1:07:37** · And everything, that time, energy, and money, that takes away from something else.

**1:07:41** · So the opportunity cost of pursuing a strategy is the real cost.

**1:07:49** · And so you've just got to ask yourself, how can you be smart enough such that the opportunity cost is reduced and your optionality is increased?

**1:07:58** · And so you're trying to think through all of that stuff all the time.

**1:08:01** · It's no simple answer, but in a lot of ways, you're trying to get the journey to pay for itself.

**1:08:10** · Given everybody's going to mob you for more signatures, that's where we're going to end.

**1:08:15** · Thank you.

**1:08:16** · Thank you very much.

**1:08:17** · \[APPLAUSE\]