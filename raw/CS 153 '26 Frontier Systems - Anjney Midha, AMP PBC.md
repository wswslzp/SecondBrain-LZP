---
title: "CS 153 '26: Frontier Systems - Anjney Midha, AMP PBC"
source: "https://www.youtube.com/watch?v=mZqh7emiz9Q"
author:
  - "[[CS153: Frontier Systems]]"
published: 2026-04-04
created: 2026-04-18
description: "Anjney Midha opens the quarter of Stanford’s CS 153 Frontier Systems by framing the course as a speaker-led “AI Coachella,” emphasizing relationships, fun, and “obsessing over what you love” as a life"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=mZqh7emiz9Q)

Anjney Midha opens the quarter of Stanford’s CS 153 Frontier Systems by framing the course as a speaker-led “AI Coachella,” emphasizing relationships, fun, and “obsessing over what you love” as a life heuristic. He introduces his background and the course goal of real-world preparedness, then outlines the modern AI stack from capital and data centers through chips, cloud, models, applications, and governance. Midha reviews how AI development has industrialized—especially reinforcement learning and continuous post-training—and argues that “context” and verifiable feedback loops determine where progress accelerates and where value accrues, citing examples like IDE access conflicts and sovereign AI needs. He then deep-dives on compute infrastructure, showing how capabilities and revenue correlate with compute buildouts, why GPU prices can rise, how infrastructure cycles resemble past commodity booms, and why compute remains non-fungible without standards and institutions.  
  
00:00 Coachella Icebreaker  
00:13 Course Headliners Preview  
01:49 Swag And Viral Tweet  
02:14 Life Scaling Laws  
07:47 Class Purpose And Bio  
10:21 AI Stack And Origins  
12:08 Great Transition Era  
14:23 Manufacturing Intelligence  
16:45 Bottlenecks Framework  
19:37 RL Primer And Context  
24:34 Context Wars Example  
30:03 Mistral And Sovereign AI  
33:35 Cloud Act and Sovereign AI  
34:23 Unbundling Cloud Oligopolies  
35:11 How to Start the Flywheels  
36:33 Recursive Self Improvement Systems  
37:15 Limits of RL Debate  
39:06 Verification Creativity and Taste  
41:53 Three Blue One Brown Lesson  
43:58 Scaling Laws Meet Markets  
47:40 Compute Crunch and Rising Prices  
51:06 History of Infrastructure Cycles  
57:42 Compute Not Fungible Yet  
01:00:55 Standards Institutions and Your Role  
01:05:00 Final Thoughts and Bonus GPU

## Transcript

### Coachella Icebreaker

**0:00** · How many people have been to Coachella?

**0:02** · Oh my god, we got to do a field trip, Mike. I know. Yeah. Okay, maybe final project, surprise project. Go off. Yeah.

**0:10** · Yeah, off-campus field trip.

**0:12** · So, usually when you have a um uh when you go to a concert, for those of you we will I will we will make sure that you get to a concert, a real one.

### Course Headliners Preview

**0:22** · Uh when you have a headliner you need an opening act.

**0:26** · Right? To warm up the audience. And so uh today I'm your opening act for the rest of this quarter. We're going to have Mike uh in the coming weeks as well, who's going to be doing uh a deep dive into a bunch of confidential computing stuff. But, I'm here to give you some context about the speakers and the rest of the class. And then we're going to do a bit of a deep dive into the area of the world I understand most, which is compute infrastructure. Okay?

**0:49** · But both today uh and for the rest of this quarter, these really are your headliners.

**0:55** · \[snorts\] Yeah? Make sense?

**0:58** · Recognize some of these names?

**1:00** · Woo! All right, woo. Yeah. For for um the ones you don't recognize I I would recommend looking them up cuz over the next few years you're going to hear about them a lot more.

**1:11** · Um one extra thing we are considering because many of you asked uh given the just insane amount of demand we've had both from speakers as well you guys to add more topics and more coverage we might add a virtual um office hours every Friday from noon to 2:00 p.m. especially for speakers from who are zooming in from around the world and can't make it in person. That will be optional extra credit. But, a quick show of hands, how many people would actually like that?

**1:41** · Oh, okay. I guess we got to do it, Mike. All right, cool. More more details coming. More work. More work. This is the swag for this class.

### Swag And Viral Tweet

**1:51** · Uh I forgot who it was, but somebody sent me a tweet, a brand new saw there was a tweet that went viral yesterday about this class. It said um be what was it? Be wary of taking classes that sound like AI Coachella. Uh and there there's lots more serious AI classes on campus you can take.

**2:09** · Totally agree.

**2:11** · And by the way, I I thought that was pretty fun. I think AI Coachella is pretty fun. So, as you guys know, I did my undergrad here, uh did grad school and uh look, I I think um we're going to be talking a a lot about technical stuff. But, we also get to talk in this class about life and leadership.

### Life Scaling Laws

**2:29** · And so, um I thought before we jump in to technical stuff you know, we talked a lot about scaling laws last time and we're going to talk a lot about that in this quarter. But, I thought I'll I'll give you a little less sort of in preview into Andre's uh life scaling laws. Um you know, I I think that you should take life seriously but not so seriously that you forget what's important.

**2:59** · You know, don't forget how to have fun and remember what makes life worth living cuz look right now you might feel like you have uh all the time in the world. And sometimes you don't know uh when you don't have that much more time left. So enjoy while you can. Don't take for granted. It's a really magical time you guys are in right now.

**3:25** · Um my view is it's very simple actually to uh live life and scale yourself, scale your impact, which I know many of you want to do.

**3:42** · Uh a lot of times a lot of you the students we've taught over the last few years have come to office hours and asked Andre, Mike, you've been so successful, blah blah blah. How do you plan your future?

**3:54** · Uh how you know, it's very similar to how do you plan a training run? Right? You want to you want to really knock it out of the park on capabilities. You want to scale capabilities and revenue like we talked about last time. And it's hard to forecast these things. So, I I've actually found a pretty simple heuristic on how to navigate that journey, which is just have fun. With people you enjoy hanging out with.

**4:16** · You know, that's pretty much it. I found empirically, remember we talked about how scaling laws are empirical, not predictive. I found empirically that's worked out pretty well. So if there's one thing I'd love for you all to take away from this this quarter, you know, this is the last lecture I'm going to be giving this quarter. We'll have lots of speakers and so on.

**4:38** · Um but this is the I just want to leave you with this one, which is the most important people in this class aren't really Mike or me or the speakers.

**4:51** · It's you guys.

**4:53** · You know, look look around and see uh how special it is. You know, I am Wow, sorry. I don't know why I'm getting so emotional. I I need some water. Do you guys have? Oh.

**5:08** · Thank you.

**5:10** · Cool.

**5:18** · Really invest in these relationships. Cuz you won't uh realize how they come in and help you in all kinds of ways in in life. You know as you guys saw uh I met my wife here as a sophomore.

**5:32** · Say hi, Viv.

**5:34** · We've been together 13 years. Um and just uh and I mentioned I got to start two companies both with former roommates from Stanford. Uh one of them is my current one, Amp. And you should just uh you know, the world is a uh messy place. It's a can seem like it's there's a lot of crazy stuff happening in the world. We're fighting wars.

**6:05** · There's a lot of violence, a lot of chaos. Uh but you guys are in a very special moment in time. You know, just think about all the things that had to come together for all of you to be sitting in this room. So, just um generally see how special and lucky you are you know, to be here.

**6:23** · And uh you know, we talked last time about how it can feel I think somebody asked I forget who it was who asked the question, Andre. You know, with all these AI labs and big companies spending so much on AI and infrastructure, how could we possibly create something interesting or novel or new in science and engineering?

**6:40** · Uh and remember I said like use them. Do things that don't scale or be asymmetric about your bets. And one of those is you know obsess over the things you love. Because uh that doesn't there's some things that don't scale well, especially in large organizations.

**6:57** · And so, throughout this quarter, just remember that you actually do have some special weapons. And one of those is the uh the obsessions, the love, the trust you have for each other the friendships, the relationships you'll build here and over the next few years cuz that will come in very handy and it'll be things the those kinds of things are assets that don't scale uh as as you join larger and larger companies or organizations.

**7:20** · Okay, I'll stop being uh an uncle now and I will say maybe go to the real Coachella while you still can. Uh one of my biggest regrets is uh when I was in campus, we were working so hard and staying so focused on on projects and coursework. I I've never been to Coachella, turns out. And so, maybe we will go with you guys. Okay. Shall we Shall we proceed? Yes? Okay.

**7:44** · \[applause\] Thank you, guys. Quick recap.

### Class Purpose And Bio

**7:49** · Um yeah, for those of you who are joining us for the first time, I'm Andrej. I'm one of your co-instructors. There's Mike. He's going to introduce himself during his lecture as well.

**7:59** · Um my full name is pronounced Andrej.

**8:01** · Friends call me Andrej. Uh I was born in India, uh went to high school in Singapore, came over for college here at Stanford many years ago. Um and then I ended up staying. Uh this is now my home. I live in San Francisco with my wife uh in Presidio Heights and you guys are all welcome to come by anytime you'd like.

**8:18** · I've been in love with applied machine learning for the better part of of last 15 years. I came here as an undergrad. I took a bunch of coursework in economics and a major that I don't think exists anymore called mathematics and computational science. And then for grad school, I did bioinformatics over at the med school, which is essentially machine learning applied to health care.

**8:35** · Um I've always been a very applied thinker. I've always found that it's really exciting to look at what uh machine learning systems when taken out into the real world at scale can tell you about the world, which is often actually a pattern you see not just in computer science, but in physics. Right?

**8:48** · Physics is about trying to understand how the world works, looking at large patterns, empirically trying to figure out are there laws we can derive about the world. Um this this is the applied physics uh part of of of uh the discipline, of course. And uh I still actually spend some of my time on campus uh at the physics department as a visiting scientist, where we've been doing a bunch of benchmarking on frontier models and how they're good or not at physics and science reasoning.

**9:12** · Feel free to ask me about that anytime. We'll have office hours. Um over that time I've had a chance over the last 10 15 years to invest, co-found, be part of the early days of over 10 AI labs. Some of those you guys know, Anthropic, Mistral, Black Forest.

**9:25** · You'll be hearing from many of these in this class. And um as as we just talked about, I I'm I have a deep deep uh I'm deeply thankful for what Stanford has done for me. Sometimes I uh should post on Twitter. Don't uh um believe everything you read on Twitter, but if you're ever ever wondering what my shower thoughts are, that's where you can find me. My uh handle is Andrej Mitha.

**9:53** · Okay. This if If guys remember, for those of you who were here last time, this is a cheat code to the rest of the class and I think the rest of the uh the next 2 years at least in the industry outside of Stanford, okay? This is not just a CS153 thing. Hopefully, this will give you a bit of a framework for how to navigate life after college because if you remember, we talked about the goal of this class is preparedness for the real world. The goal is not internships.

**10:17** · Goal is preparedness, okay?

**10:19** · Um what is happening?

### AI Stack And Origins

**10:23** · In the infrastructure world, in the CS systems world, we are going through a massive change. Over the last 10-15 years with the rise of um distributed systems, cloud infrastructure, a some a somewhat stable stack had emerged about how we create, ship, and scale software.

**10:41** · Right? And these are the different layers of the stack that I would roughly say dominate the industry. We start with capital, which is quite flexible. You can put money in everything. Then you have land, power, shell, right? Energy production, data centers construction.

**10:52** · On top of that, you or in the data centers, you put chips. You then have some software infrastructure called a cloud that makes those chips usable. And then you start we we hook up all these chips together, we train a model, sometimes you call them agents, we then put them into an application, we deploy them as solutions, and then lastly, um we try to figure out how to actually govern these things. What's the safety, the security, the trust, the frameworks we need to actually make sure that these these technologies get deployed to the real world. When Mike and I started this class 4 years ago, it was called security at scale. At the time, I was running the platform org at Discord. How many people have heard of Discord?

**11:26** · Perfect. Great. We did our jobs. Uh and Mike was running infrastructure at Apple at the time and both of us had started to realize that security was becoming an increasingly critical topic in the world, but there just weren't that many places for people like you guys to learn what the frontier or the cutting edge problems of security were because you don't get to see those at on campus. And so this is this start this class started as the missing systems class that I wish had existed when I was an undergrad. And so um that's where this all started.

**11:53** · Since then, it's evolved. We started with 50 students, we're now 500. Thank you all for for for joining us. I think we have another 50 waitlisted and a few thousand people following along online.

**12:01** · I'm not sure when else we'll get to teach this class again. So let's try to make the most of it, yeah?

**12:06** · Okay.

**12:07** · We're going through the great transition.

### Great Transition Era

**12:09** · Because we have this new technology called AI um that has unlocked extraordinary value and is about to unlock way more value, everybody at every every leader or every major team or or I would say um people who care about the future at every layer of the stack are wondering how do we unlock the bottlenecks? How do we make this stuff go faster and safer and more secure?

**12:32** · And what we're learning in the industry as it is that it takes revisiting a lot of basic assumptions about how the stack works, where in the value chain you are, what your job is, what your technical function is, what your economic function is. And I think you should start you will start to see you all you probably al- already are feeling what I'm calling the great transition.

**12:51** · Um to to driven by this this urgent need across all levels of society, right? You saw the the sort of diversity in names we have. We have people like Jensen Huang um and Lisa Su at the chip layer coming in to talk to you guys. We have um folks like uh Satya Nadella who runs Microsoft, right? Who who's at the cloud layer. We have Sam Altman. How many people have heard of Sam Sam Altman?

**13:16** · Yeah, there we go. Okay. Um he's coming by, right? To talk about models and and how they're deploying stuff. So this is a really big shift that's happening, right? For the first time at least in my life, I can't remember a time when there was such a big revisiting of assumptions up and down the stack where everyone's trying to figure something out. And that's really cool. Because that creates an extraordinary amount of opportunity for you guys.

**13:39** · Cuz in times of uncertainty, that's when things change. And people who who understand where the world is going, who have a point of view, get to redesign the systems that have stayed quite static in the past.

**13:51** · Okay?

**13:53** · I don't know what the new world's going to look like. I don't think anybody does. But for the next 10 weeks, you are going to hear from some of the most um I think uh dynamic, talented, and capable leaders reasoning through how to really unblock the bottlenecks at each part of this ecosystem.

**14:12** · Every week.

**14:14** · Cool? Sound good? Should we keep going?

**14:16** · Okay. No, you don't need to clap for me every time. Don't worry.

**14:19** · \[laughter\] I got to I let me let me let me earn my my keep. Okay, so quick recap. Remember we we said, "What is going on at the frontier?"

### Manufacturing Intelligence

**14:29** · Right? The What what is this this whole thing about called intelligence?

**14:33** · And a few years ago, uh when I was starting to get calls from friends who I had gone to grad school with or who were running research at places like OpenAI, I started getting calls saying, "Andre, you know, we think there's an opportunity to really take some of this research out of the lab and turn it into products and services that could impact hundreds of millions of people."

**14:51** · And at the time, it was a pretty craft bespoke process, right? And we talked last time about pretty simple recipe on how to manufacture intelligence.

**14:58** · Compute, data, algorithms.

**15:00** · Pretty simple algorithm, transformer. Do a little bit of pre-training, some fine-tuning. Good to go. Plug it into an app, you got ChatGPT. Right? We're going to have Liam Fedus from chat the co-creator ChatGPT uh come by and talk to you guys later this quarter. Things that look very different now, right? In four short years, we've taken what was a pretty like I would say uh bespoke process and turned it into an industrial engineering process at scale.

**15:27** · Right? Back then, 3-4 years ago, uh it the the the sort of frequency of creating a new model was maybe once a year, twice a year.

**15:37** · And today, we have this industrial scale production process where we do, you know, base model training at least two times a year on 100,000 GB uh B300 equivalents. Um and then we do post-training with about 10% of that compute, right? Uh so mid-training, we add more capabilities into that and that happens about two to four times a year with about 10% of that compute. And then we do this thing called continuous post-training, right? With supervised fine-tuning and RL. And I won't bore you with all the details that we talked about last time. We'll have assigned readings, slides will be up, but I'll let you guys go do the math uh on how much compute and and and money is being spent on these systems.

**16:12** · Um what's the most recent, of course, development in all of this is that the last mile of this, the reinforcement learning part, is now consuming almost as much compute as all of the rest of the step pipeline combined. Okay? And that's very exciting.

**16:29** · Cuz when it's new, but it also means that things are changing fast and resources and strategies are consolidating. And so our hope over the next 10 weeks is that you get a bit of a window, a front a front row seat into that part of the ecosystem.

**16:42** · Okay?

**16:44** · Okay, so what what does all this mean actually for progress? This is where we stopped last time and this is where I'm going to pick off pick up today.

### Bottlenecks Framework

**16:51** · Uh quick disclosure list uh and sort of like any good scientist, you you start by disclosing uh the experiments you've run, right? Uh this is a list of teams that I've been ha- I've had a chance AI lab teams that I've had a chance to work with. Many of these were literally co-authors on a paper that then we teamed up on to turn into a company or a project out in the real world. Some of them I was involved in as an angel investor, some as a co-founder, and you'll hear from many of these people over the rest of this quarter.

**17:18** · Um but this is also disclosure list. I'm biased. Naturally, all my you know, when you're when when you're observing an empirical experiment, you are naturally biased by the data that you're fed, right? And so between Mike and myself, what we've tried to do is at least augment our individual biases and work experiences with a diverse sort of uh as uncorrelated of a set of perspectives for you all across the ecosystem as as we could for in 10 short weeks. Okay.

**17:47** · Um So this is the crux of the class, right?

**17:50** · Of of this lecture. What are the bottlenecks on these capabilities?

**17:56** · Uh many of you are excited about these capabilities. I certainly am. You know, I as we talked about last time, you can use them for everything from um you know, having a conversation when you're uh by yourself, doing your homework. That use case is banned for this one uh for this class. Though if you do use any of the coding models for your assignments, just tell us about them.

**18:17** · That's all fine. But it's a pretty diverse sort of it's a pretty general purpose technology, right? AI found these foundation models.

**18:25** · Um and so for the next let's say 40 minutes or so, what I'm going to try to do is is break down in detail at sort of a systems level what is going on and what in in in terms of the the the inputs required to keep these models and these systems continuing their blistering pace of progress so we can all benefit, apply these this incredible technology, you know, beyond chatbots to new areas like curing uh novel diseases, discovering new materials, you know, I'm of the opinion that there's like there's an extraordinary number of new frontiers to be explored and developed uh with AI.

**19:06** · Um but it it would it's not going to happen without us sort of as a society um figuring out how to unblock progress in all the domains that we care about.

**19:16** · Okay.

**19:18** · Again, the recipe is pretty simple. I'm going to break down the bottlenecks into four major areas. Context, compute, capital, and culture. And we'll see how much we can reason through this today. I'm going to start with context and compute and then we'll go from there. Okay, might have to do an extra overflow office hours or something.

**19:35** · Okay.

### RL Primer And Context

**19:37** · Context.

**19:40** · Couple of pre- pre-reqs you're going to need to understand the next few slides. Reinforcement learning. Very simple technique, super powerful, driving a ton of the progress at the frontier today.

**19:49** · We talked about it last time. If you've had a pet or you've had a sibling who you've had to teach to stay away from your room, you are a successful uh frontier model trainer of language reinforcement learning. The key idea is that when you have a system that you want to improve at a given set of tasks, you don't tell the the agent or the model how to do it, you just tell it what you're what to do, what task you want to reward, and when it completes that successfully, you give it a reward.

**20:14** · If it doesn't do it successfully, you would hold the reward, and then you rinse and repeat, right?

**20:20** · Very simple idea, it's been around for a long time. Started really working, I would say in earnest, um at scale about 2 years ago.

**20:28** · And that was because when you initialize a reinforcement learning environment with an agent like an LLM that's smart enough has smart enough priors about the real world, it turns out that these systems learn much faster than usual, and and the capabilities tend to continue scaling the more compute we throw at them, and the more um sort of environmental harnesses and context we give them, which is pretty novel, pretty new.

**20:49** · Earlier, uh over the last 70 years of computer science as we discussed uh about the bitter lesson, you know, in in lecture one, um RL would would plateau pretty fast in different domains, chess, right, go, etc. Um it would it would sort of surpass human performance, but then the rate of progress would sort of plateau. And the reason it seems, again, this is I I would say an open area of debate, is that the the the the the priors, the the previous sort of inbuilt reasoning capabilities of of the the models were just not general enough to continue learning. In a sense, you know, after a while, you you guys know uh you've heard the phrase, you can't teach an old dog new tricks, uh whereas it turns out you you can sometimes teach a Stanford student to come back and teach new classes, right? That's my dad joke kicking in as well. I'll I'll try to stay away from from the puns. But so that's this is the core philosophical tension of RL, right? It's working much better than expected.

**21:47** · It seems to be because LLMs have enabled a new era where the the the models, the language models are smart enough to then give us new capabilities when you use post-training to improve them on some specific task, benchmark, or um capability.

**22:03** · Making sense? Everybody following me?

**22:06** · No, I'm not seeing Okay, we're going to might we might have to do an RL tutorial, but I would encourage you to uh how many people have taken a machine learning class at Stanford already?

**22:15** · Okay, keep your hands up. How many of you have at least uh done one Pset with an RL problem?

**22:23** · Uh okay, there's Okay, that's the issue. All right, we're going to have to about 30% or so. We'll do an office hours on that. And and you know, you're going to have some of the coinventors, some of the pioneers around RL actually come talk to you. So, uh they'll probably do a better job than me.

**22:36** · But to recap, where does where does this fit in to what's going on in the industry? As we talked about last time, you know, I got a call from some friends, Dario and Tom, who were running research at OpenAI. Four years ago, they said, "Andrej, we want to leave and start a new lab."

**22:50** · Um can we figure out how to build a business around this? And so we spent some time fleshing out how do we turn the scaling of capabilities into a business, right? And this was the simple recipe we came up with.

**22:59** · Raise some money, buy some compute, augment it with data, uh pre-train, put out a model that's good enough, considered state-of-the-art that some people, like programmers, want to use them, deploy it, do inference, you know, run the model, and that gives you two loops. The inference hopefully gives you enough money to buy your next round of compute, and gives you context feedback you can observe, in the case of a pair programmer, when is the model actually accomplishing the task you wanted to or not. It has your mono repo, you'll get uh history, your uh local files, right? And then you pipe that back, that we call that context the context feedback loop, back through RL hundreds and thousands of as many times as you need, with as much compute as you need, to improve the capabilities of that of that system in that domain.

**23:44** · Pretty simple recipe, right? As I discussed last time, we made 22 introductions. Uh I I I I was an angel investor at the time at Anthropic, made 22 introductions to friends up and down Sand Hill Road. They came back with 21 no's.

**23:57** · A lot of them just said, "Sounds Sounds theoretically cool, Andrej, as an idea, but do you have any empirical proof? Do you have proof?"

**24:05** · Well, as you guys know, 4 years later, we do have proof. I won't bore you with all the slides we talked about last time with the um Anthropic revenue, etc. And I think we do have one slide later when we talk about compute, so I'll come back to that. Um But it But to fast forward now, I think if you believe, right, that that recipe works, as you know, Anthropic's gone from 9 to 20 billion in revenue, Gemini is doing well, OpenAI's, you know, started to produce extraordinary revenue. There's lots of proof that this recipe works.

**24:33** · The question I keep getting over and over again is, "Okay, well, who wins?

### Context Wars Example

**24:39** · Who wins in this That's going to If If everybody's going to be applying this scaling recipe, Andrej, and it's so easy and repeatable, then where does the value accrue?"

**24:47** · And at least one opinion I I've started to observe through all those empirical experiments I talked about with you guys earlier, is that context is critical here.

**24:58** · Context or the environment of the agent, right? We talked If If you're training your dog, it's to to fetch in a park, that park is the context, it's the environment. All the people in the park, the kids that may be running around, the grass, the physics of rain coming down, all of those factors of the environment influence the ability for you to improve and train the system, your pet, to perform better and better in the real world.

**25:25** · Okay?

**25:27** · And so I find myself explaining this pretty frequently to folks, and I hope it'll make sense to you, is that one, where will to to answer the question of where will frontier progress uh continue most rapidly? And this is relevant for all of your projects, cuz many of you must be going, "Okay, coding seems to be well on its way, and uh image generation is is also well on its way. You will have um Andrej uh Andreas from Black Forest Labs who created Stable Diffusion come by. But where else can I make a difference?" And one question I would ask is, "Well, where is there context, right, that can be reliably measured and verified when you're working with an agent?"

**26:05** · And I think wherever in life we have verifiability, you know, code is very ver- verifiable, you can write unit tests, and your code passes or not.

**26:14** · Um material science, it turns out, is quite verifiable. Again, you'll hear from from you'll you will hear from Liam and Dozh at PI Labs about how they're using RL from physical verification to discover new superconductors. Very cool stuff. There's a bunch of robots at a 30,000 square foot facility in Menlo Park nearby that maybe we do a field trip or something.

**26:32** · Um But where else is the context and the environment capable of verifying the accuracy of the task as performed by the agent? That's the question I would be asking if I was you.

**26:47** · The second question that falls out from that is, "Well, who's going to capture that value?"

**26:53** · Right? Cuz you you don't want to just be researchers, you guys actually want to do sustainable frontier system development, right? Not just one-off model drops. You want to scale these things. Okay. Well, it's the teams that will have unique and defensible access to some context. If you get there first, or maybe you have some insight, that's where teams will, I think, capture the most value.

**27:17** · Right? So that those are the teams I think are going to win.

**27:20** · And then who's going to lose?

**27:23** · Um my view is that the teams that get locked out of contexts that are essential to improve these models and the capabilities on some some domain will not have a chance. Now, to bring that to life, I thought I'd just give you a few examples, right, of this context these context loop wars beginning.

**27:42** · Uh I think just about a year ago, uh there was a an uh a news site a news um drop that OpenAI tried to acquire an IDE uh that many of you probably use for your um for your coding work called Windsurf.

**28:00** · How many people have heard of Windsurf?

**28:02** · Oh, okay.

**28:03** · Cool.

**28:05** · I mean, we'll be happy to hear about that. Um A few days later, right, after it was announced that Windsurf was being acquired by OpenAI, Anthropic shut off model access to Windsurf users.

**28:18** · Doesn't happen often.

**28:20** · You don't You don't In In In our industry, we don't usually shut off an API to users without warning.

**28:28** · But it made total sense, right?

**28:30** · Because if your competitor needs access to your model, the context, and can distill from observing how you help out uh customers that you want to attack, that's leakage, right? You have context leakage there. And so to those of us in the industry, this was very clear. I mean, it was very very normal. I was not surprised. But I think for a lot of people started updating their mental model again.

**28:52** · Remember that stack diagram?

**28:54** · That if you're a model provider, and then you're an application company, you can always rely on your model company to keep giving you intelligence, well, that was one assumption that that stopped scaling then.

**29:06** · Okay?

**29:08** · Um and this is happening across the economy in different contexts. Whether it's consumers, creators, companies, countries, at every part of the economy, there's a battle that's raging for these context feedback loops. And over the next 10 weeks, you're going to hear from many of these people. In fact, you're going to hear opposing views.

**29:29** · And uh that's our job here. As instructors, our job is not to try to convince you of our views, it's to try and educate you uh with an independent uh view as much as possible, so you can, you know, derive the conclusions you believe about where the future's going. Cuz look, this is an open problem. This is not a This again, we're running the grand experiment of how to keep Frontier progress going around the world.

**29:54** · It's making sense?

**29:56** · Yes, okay, good. People are nodding.

**29:58** · Can I hear a yes?

**30:00** · Okay, thank you.

**30:02** · So let's deep dive for a second one of these.

### Mistral And Sovereign AI

**30:06** · How many people have have heard about of llama?

**30:10** · Great. One of the the creators of llama was a guy by the name of Guillaume Lamp who spoke in our class last year his lectures up on YouTube go check it out.

**30:18** · Guillaume and his college friend Arthur who Arthur Mensch who is going to be speaking here a few weeks teamed up a few years ago Arthur was a researcher at DeepMind he was one of the lead authors on a paper called Chinchilla. Chinchilla scaling laws have been assigned as reading so I'm a good professor never asks if students have done the reading I'm going to assume you guys have good faith honor code. Definitely read that before Arthur shows up.

**30:45** · It'll tell you a lot about his view but Mistral was a new Frontier lab started in Europe by the co-creators of llama and Chinchilla and their view was very simple. They said hey there's going to be an extraordinary amount of progress in closed source models because that context is just not that sensitive. And people won't mind piping their software engineering context if you're a developer in Silicon Valley to a cloud server somewhere. But if it's a mission-critical context what they call the sovereign context it matters to a government national records defense and so on well you kind of need to start locking that down locally.

**31:21** · And that means you need models and weights that run locally on your infrastructure that you can control and so they started Mistral as a way for um companies organizations that needed control over their own context to deploy models open source models locally.

**31:35** · So that and and and and the reason I think this is worth talking about is because it's quite um hard in the world of infrastructure especially software infrastructure to beat the the relentless sort of uh flywheel of the decreasing marginal cost of production in storage in networking in servers the history of cloud over the last 15 years has basically been decreasing marginal cost right when Amazon and Google who both had sort of extraordinary businesses serving consumers right Google and search Amazon and shopping they were just piling up lots and lots of servers for their own needs and they started realizing hey you know what it doesn't cost that much for us to add another server and another server another server and basically just rent that out to other people because at some point the scale of your own first party needs is so high that you can pass on the benefits of that scale to third parties and that's how we got AWS GCP Azure Mike helped start Azure sorry to date you Mike but that's that you know basically 15 years of of sort of relentless uh consolidation in the cloud infrastructure world because of the economies of scale.

**32:44** · Right?

**32:46** · For the first time in 15 years that's changing. You know why do you have President Macron the head of a country and uh Jensen the world's richest man or was I think last quarter probably still is um sh showing up on stage in Paris uh next to a 33-year-old scientist who's never run a business before saying this is the future of Europe. It's because of context.

**33:16** · There are governments and mission-critical you know workloads that are just too sensitive to be run on cloud infrastructure overseas.

**33:25** · There's a we talked last year um in the class about the Cloud Act. How many people have heard of the Cloud Act?

**33:30** · Okay.

**33:32** · Zero. Hmm.

**33:34** · We got to assign that as reading. The Cloud Act is a um is policy that says that if you're running workloads on United States uh servers um whether it's or it's a company run by um or its servers run by a United States company globally the government has the ability to access that data. To some people around the world that's not okay.

### Cloud Act and Sovereign AI

**33:56** · And so now suddenly AI workloads have gone from being cool you know chatbot assistants to being mission-critical systems. Remember we talked about RL? RL has started to work with a level of precision and accuracy in mission-critical context and that's why you have a huge um sort of reshuffling of cloud infrastructure globally. And you'll start to hear this word sovereign AI and infrastructure independence a lot more over the next few years.

**34:20** · Okay.

**34:22** · Uh just to wrap that point that's what's allowing startups to sort of unbundle monopolies in the infrastructure world or let me call them oligopolies cuz some of our guests won't be happy when I say monopolies.

### Unbundling Cloud Oligopolies

**34:34** · Um at scale at speed and scale and this is very exciting cuz you guys get to participate in this revolution too and so you know one one clue you could have about where to spend your time is where there's a unique context that hasn't been available to you because you're not at scale but that you can do something unique and get ahead of and start um sort of being a participant in that re restructuring of of that industry.

**35:02** · Okay, make sense? Yes?

**35:05** · Come on guys it's spring. Yes, okay, thank you.

**35:10** · Okay, so how do you actually get this going after doing this for 10 years and mostly five of intense uh investing company co-founding nowadays people call me the founding investor basically means I'm neither the uh the the the CEO which is all the many of the talented folks I get to work with who are usually scientists but I'm not sort of a traditional venture capitalist I don't really write a check I typically co-found these companies on day one with these teams and I do this one at a time my current um uh project is Periodic Labs as we've talked about but I've observed a pattern over and over again which is you you you you you sort of formulate a state of the art mission.

### How to Start the Flywheels

**35:48** · What is a frontier that we'd really want to advance material science coding whatever it might be and that you make that your mission. We want to move the frontier we're going to create state of the art intelligence in a particular domain.

**36:00** · Okay? You then get enough compute that's research compute you do some experiments you figure out how can we actually get something novel out to the world that doesn't exist and often in the new domain it's that's it's actually not that hard to do because we're early.

**36:14** · Ship it get it out into a context that you have access to run the feedback loop and then remember we talked about that scaling the those two flywheels?

**36:24** · Then just keep them going keep them going as long as you can cuz that is the gift that keeps giving cuz they reinforce each other. Okay. Eventually at some point when these flywheels get good enough they start propelling themselves that's what many people in the industry call recursive self-improvement. Sometimes people like to call this the path to AGI or ASI.

### Recursive Self Improvement Systems

**36:44** · Um well I'm an infrastructure guy so I I think more at the level of the system I don't necessarily think in terms of a model but you can often have a company that's you know hitting takeoff because they've just figured out as a good execution team and how to keep recursively improving themselves. It doesn't have to be an actual model that's super intelligent or whatever I mean that's that's one view that's fine.

**37:01** · You guys should ask our speakers if that's how they they view it but I I sort of think about recursive self-improvement at the systems level that's that's attacking the state of the art mission not really at an individual model or API level.

**37:13** · Okay.

**37:14** · Um so the big question where does this leave us right on the context question is what are the limits to RL?

### Limits of RL Debate

**37:23** · Um and this is a very exciting open question. I don't I hope this will be answered um over my lifetime. It may not be I don't know how much time we have to really figure this out but there's two views on it today that I hear in the industry. One is a philosophical the other's the the empirical view.

**37:40** · The philosophical view is that hey given the right context given sufficient compute these agents should be able to learn anything.

**37:49** · So once you get that like recursive sort of takeoff happening why don't you just ask the agent to construct if it is you have a coding agent right and the coding agent's not very good at material science but at some point if it's good enough you just tell the coding agent please build yourself a material science environment and then go do the RL loop yourself. And so on and so forth. That's one view.

**38:12** · Um it's not clear right now to me that RL is generalizing outside of task distributions which means outside of the domain that you started that frontier flywheel in right the context feedback. It's not clear to me that models are generalizing from let's say coding to material science to biology etc. I think within the narrow distribution of coding and so on what we're seeing is basically relentless progress it doesn't look like it's stopping anytime soon.

**38:38** · And look this is a big area of debate billions of dollars being invested in trying to figure the answer to this question. My view is closer to the second one which is that empirically what I've observed is that life is messy.

**38:52** · Um progress is fastest in easily verifiable domains and so in domains like coding which is verifiable you will start to see sort of the idea of a narrow superintelligence or you know exponential progress but in areas uh in the world where progress is not as easily verifiable a great example of that is aesthetics beauty love like how how what are these how how do you verify right like what is good a good a a good verifiable construct for beauty or love or aesthetics and this is why how many of you have tried writing a uh like a message to your friend like an extended blog post or something with with Claude or ChatGPT?

### Verification Creativity and Taste

**39:35** · Only four or five people okay clearly you guys have real work to do unlike me writing blogs all the time.

**39:42** · Um it's terrible.

**39:44** · These models are not good at long-form writing, at creative writing. They hallucinate. They They make these clichéd hyphens and so on, right? They They see the m dashes and the It's not It's This is This is a game changer. Ever ever heard of that phrase or the It's not just X.

**40:03** · It's Y.

**40:06** · I I sent a a blog post I was writing like a bit of a manifest about infrastructure to a friend 3 weeks ago, who was a founder you'll hear from in this class. Said, "Can I get your sanity check on it?"

**40:18** · Writes back in 30 seconds.

**40:20** · Did you use Claude for this?

**40:22** · I was like, "No." He's like, "I don't believe you." Well, it turns out I'd written the outline myself and then I'd asked Claude to like flesh it out, you know? We've all done it, right?

**40:31** · And he could tell immediately. And since then we have an internal rule at Amp. We don't send each other AI-generated uh documents. We think We sit. We write. And we share with each other even if it's uh raw. So, many of the speakers you're going to hear from at in you know, working in the model level are innovating here, trying to answer this question. And I'd encourage you to do some research on them.

**40:57** · A lot of people share openly about their strategies online. So, so do your homework. Come prepared.

**41:03** · Push them on these questions. Yeah?

**41:05** · The more you prep you do, the more work uh the more value you're going to get out of these lectures. And more importantly, I think you guys can innovate here, too.

**41:15** · Cuz it's early.

**41:16** · And there's so many domains that maybe you only you understand. And only you can verify because of your obsession, your love, your taste, your sense of beauty, your your culture.

**41:28** · And I think we're that I think that's the most uh valuable thing you could be doing. When I When I get a call from a new team that wants to me to invest or help them build a business, that's what I'm often looking for is what is the unique um sort of frontier that they can verify for humanity. I had one of my uh favorite He's He's He might not like me sharing this. Well, I'll share it anyway and we we'll publish after getting his um permission.

### Three Blue One Brown Lesson

**41:53** · How many people here have heard of the YouTube channel 3Blue1Brown?

**41:57** · Whoa.

**41:58** · Okay, I did not realize. I'm going to have to call Grant. Uh Grant Sanderson, who is the uh the creator of 3Blue1Brown 3Blue1Brown, oh. And I were uh undergrad drawmates. He lived in FroSci Co, I lived in Ugh. Uh there were four of us who were good friends and then we drew into Crothers together.

**42:18** · Yeah, Crothers. Uh but uh Grant and I have stayed in touch over the years and he came by. He crashed over at my house for the last 2 days and um he unfortunately had to fly out this morning at 6:00 a.m., but we you know, we were talking late into the night last night about what would it take to create um sort of a truly world-class educational um you know, learning space of the kind 3Blue1Brown does for science and math, but for anything, you know? And it was so clear to me while talking to him that that what's unique about is is his brilliance of how and his taste for what is is the right way to deconstruct a really technical topic and really understand it from a from the first principles. And that's I would say the true magic of of frontier research is is is distilling the insight of somebody who's really world-class at what they do and being able to share that with the world.

**43:13** · And RL is just one technique to get there. I think we'll invent many other techniques.

**43:17** · Okay.

**43:19** · Making sense?

**43:21** · Oh my god, guys. Yes. Thank you. Okay. Now, compute. This This is the exciting stuff for me. I'm I'm a compute nerd. I'm an infrastructure nerd. As you know, guys, as I talked about earlier, I studied both economics and computer science and up statistics and bioinformatics and I love the intersection of multiple domains. And com- compute and infrastructure is really where a lot of that comes together. How How long do we have? Quick time check.

**43:49** · 30 minutes. Okay.

**43:50** · Where's Anthony? Sorry, Anthony's last year. Dice, can you keep me honest and give me a heads-up when we have 10 minutes left? Okay, thank you.

**43:57** · So, what is the big idea with scaling?

### Scaling Laws Meet Markets

**44:03** · It's that scaling works predictably, right? Capabilities scale predictably with compute. This is a uh set of public estimates that overlay Anthropic's revenue over the last 4 years correlated with the amount of compute that they brought up at the company.

**44:20** · What do you notice?

**44:23** · Anything Anyone notice something about the shape of the curve?

**44:28** · Exponential.

**44:30** · Every time I You know, I wouldn't even go I wouldn't go that far. I wouldn't say it's exponential, actually. It It is It is correlated strongly with the compute.

**44:39** · Right?

**44:40** · Um it's predictable.

**44:42** · Every time the company brought up new compute, roughly 60 to 90 days later there was a capabilities jump and then a revenue jump. That is quite special. Dollar in, dollar out. Dollar of compute in dollar hard assets, land, power, shell which in the financial markets usually trade at three to four times revenue being turned into a dollar of software revenue, which usually trades at 30 to 40 times revenue.

**45:14** · From a systems perspective, what's going on?

**45:19** · We have developed a predictable way to transform one input into another predictably that humanity considers a lot more valuable than the input. The output here is roughly 10 times more valuable to the world, to the markets, than the input.

**45:37** · Remember, this class is called frontier systems. We stopped calling it security at scale and infrastructure at scale for a reason, cuz we are now in the full stack rewrite and I need you guys to start thinking up and down the stack, not just as engineers, not just as uh or a com- computer scientists or electrical engineers. I need you to start thinking like full stack thinkers. Think about the the capital markets. Think about the business, cuz if you want to keep sustainably doing research at the frontier, you've got to run the whole loop. Run it back.

**46:03** · Okay?

**46:04** · So, what's an example of that in production?

**46:08** · If you look under the hood, Claude code, these These are commits that uh the agent has been making publicly on GitHub.

**46:17** · Beautifully correlated with the compute buildout, right?

**46:20** · So, this is not just revenue. Somebody asked I think last time, "Anj, is this just like revenue pumping?"

**46:25** · This is real usage. Sure, over here there's probably some verbose Claude uh you know, commits, overeager commits. But by and large, this trend has been pretty reliable over the last 4 years. And so, even if you took revenue out and you just looked at usage, right? This is very real, fast-growing exponential usage in coding. For this reason, the great tran- What What What I've called the great transition in infrastructure started last year.

**46:58** · Once this this predictable scaling not just of capabilities, but of revenue of this infrastructure trade became legible to the capital markets, everything changed.

**47:11** · Right?

**47:13** · Over the last 3 years, the five largest tech companies have decided to spend more on infrastructure, land, power, shell than they have in the preceding 30 years combined. Last year, they're going to they They I think they spent 300 billion. This year they're going to spend 600 billion. Next year they've announced in their earnings reports they're going to spend 1.2 trillion dollars on CapEx. These numbers are kind of hard to fathom.

**47:39** · So, what happens?

### Compute Crunch and Rising Prices

**47:42** · What happens when all the big boys start spending? What do you do?

**47:48** · Step one, acknowledge reality.

**47:52** · For the last 4 years, I have I have lost enough count of the number of times people have called me and said, "Anj, why are you spending all this time on compute?

**48:01** · It's a commodity.

**48:03** · Just give the company some money.

**48:04** · They're going to go be able to rent from GCP, AWS, and so on. They'll be That's how the world works, right?"

**48:09** · Not quite.

**48:11** · This is a chart that we've been aggregating at Amp of rent GPU rental prices quarter by quarter across a number of estimates. We have an internal system we call the Amp grid, whose job it is to try and understand what's going on in infrastructure and try to forecast intelligently so that our teams and our companies that we work with can get a bit of a empirical view on where infrastructure is going.

**48:34** · What do you observe about the price trend of H100 prices, a chip that's over 2 years old?

**48:41** · And over the last 90 days?

**48:47** · Somebody, come on. This Yes, thank you.

**48:50** · Going up.

**48:52** · It's pretty simple.

**48:55** · Anybody who told you chips are commodity should probably get a phone call from you and ask them what they think about this. Because chip prices are not going down.

**49:06** · They're going up.

**49:10** · 2 years ago when I was calling friends at Clouds up and trying to rent them for our teams, you know, I was the the the average H100 price per hour was $1.73.

**49:21** · This morning, where's Sebastian? Sebastian here?

**49:25** · I had a friend message and say, "Oh, hi, Amy."

**49:28** · Can we give her a quick round of applause for Sebastian and Amy?

**49:33** · \[applause\] The reason I'm doing that is cuz you're going to be thanking later. Sebastian is your chief compute intern for this class. For your final projects, when you need compute credits, he's going to be provisioning them for you. And so, if you have any bugs and so on, please don't come to me. Go to Seb.

**49:49** · Seb and Amy, who are also married and I think uh and met at Stanford here, been married longer than Viv and me. Um we're our undergrad friends and uh Seb was my master of rituals in AKPsi, which I pledged mostly to be able to date Viv. Okay. Um And Seb Seb is my co-founder at Amp. So, you can bother him anytime you want.

**50:12** · Okay.

**50:13** · This morning, we had a founder who's raised, I think like what, $700 million, a billion dollars?

**50:20** · I wish I could show you the screenshot. Said, "Ansh, we're in a compute crunch."

**50:25** · Yes.

**50:27** · Need H100s ASAP.

**50:30** · How many do you need and when?

**50:32** · Take them right now. Price not a problem. It's a good time to be a drug dealer.

**50:42** · Right?

**50:44** · This is a fundamental assumption the entire industry has been built on, that chips are commodity.

**50:49** · All chips depreciate.

**50:51** · Entire publicly traded companies are running on this assumption. Meanwhile here, ground zero in Silicon Valley, I can tell you it's a very very different picture that's emerging.

**51:01** · Okay. So, where what does that mean?

### History of Infrastructure Cycles

**51:06** · I like to look at history to get clues about where the world is going to go. And I'm starting to realize that we've seen this before. We've lived through cycle after cycle of the invention of new infrastructure, general-purpose technologies. And then you invent ways to turn that technology into useful products, steam engine. Right? Make cars, make shoes, whatever it might be.

**51:32** · And that results in what is often called the golden age or the gilded age, where few people who start hoarding those resources get to profit at scales we've never seen before. And I think that's roughly where we are relative to the industrial revolution.

**51:51** · So, what happens next?

**51:53** · Right?

**51:55** · Like I said, let's look at the history of infrastructure for some clues. This is the econ nerd in me coming out, but I promise we'll bring it back to computer science. I just thought I'd pull some I asked our friend Claude to pull some charts together. So, if there's some wrong numbers here, I'm not to blame. Though I guess I'm not following my own rules here.

**52:13** · But with steel, 1867 to 1895, right?

**52:18** · There was, if you notice, this increase in prices. Then there was this panic of 1873, where there was a lot of hoarding of the steel and prices were going up. Then suddenly there was a panic, "Oh, the steel actually isn't worth very much. We we hoarded too much steel." Suddenly the prices collapse. Super annoying for everybody involved. Companies go down, people are backstabbing each other, markets up and down, wars are being fought, blah blah blah.

**52:48** · Eventually, as a society, we get together and say, "Okay, this isn't good. We don't want panics. We want stable production of steel, stable consumption of steel. Let's figure this out." And that's what you what results in this sort of plateauing of uh of steel.

**53:04** · Same with fiber optics. I'm sure everybody here is tired of hearing the word AI bubble. Um everybody's asking about the fiber optic overbuild and all these companies like Cisco, Lucent, Nortel, WorldCom. Is this you know, are these chip companies the same?

**53:17** · Why? Because all the economists, all the people writing op-eds in the Wall Street Journal are just looking at all the same data. Oh, okay, the prices go up and they come down. It's a bubble, boom, bust, blah blah blah, right?

**53:28** · Same thing with DRAM. Very violent semiconductor cycles. Memory was invented DRAM was invented. People go, "Okay, this is really important for personal computing." People start hoarding it. Then there's uh some something happens. Usually it's a panic at some Usually, honestly, it's not something not that big. It's like some some stupid news or some world event.

**53:52** · There's always world events happening, but triggers a panic. And that results in a self-fulfilling sort of sell-off of infrastructure stocks, assets, supplies. And then you get back up and people realize, "No, actually this there's inherent valuable technology with this. There's new capabilities here. We can do something with it." And then you either get another rise or you have a stabilization of that resource.

**54:13** · This is the Baltic Dry Index with shipping. Same thing. These slides will be up. I'm not going to bore you with it.

**54:19** · Uranium.

**54:21** · When we were living through the nuclear energy boom of the 1970s, same thing.

**54:27** · Right?

**54:28** · And often what happens, and with uranium this is very clear, you have an uh the intervention of the government to allow the stabilization of that resource. And so, if you look over and over again, and then okay, and this is our our friend the H100 GPU that we talked about.

**54:45** · Prices were dropping after the chip came out in June all the way till August of 2024, and since then they've steadily been rising. This is actually a bit out of date, but as you know, they're back up, right?

**54:57** · So, what does history tell us?

**54:59** · One, infrastructure does is cyclical. So, at least we got some clues, hopefully, unless this time is so different, which it may be, and which is what I should I would encourage you to to quiz our speakers about, cuz many of them are at the frontier of these markets. Hopefully, we as a society can figure out how may ideally we just skip the whole boom and bust thing. Not fun for anybody.

**55:26** · But assuming that's where we're at the start of another sort of like panic run on compute, the question of course, right, is how do you stably get to the other side as fast as possible, so we can all start building useful frontier labs and projects without having to go wait at the around the corner and and bother Larry and Sergey for compute.

**55:45** · \[clears throat\] Now, the usual timeline, if you just look across the digital era, you know, the internet and bandwidth build-outs, between these cycles is about 3 years.

**55:57** · 2.8 years.

**55:59** · For physical infrastructure, it was 6.3 years. And my best guess is that what and this is the thing about AI that's so novel. It's a combination AI scaling is a combination of massive You have to marshal massive physical resources, right? Like land, power, shell, um the chips, to produce this very digital thing called software revenue. Intelligence is is is is bits. But but the production is atoms. Those worlds don't like colliding.

**56:31** · And that's what's new here and scrambling and confusing a lot of people is how do we actually coordinate these two things in a way that's sta- stable, reliable, and so on.

**56:43** · The central question, of course, right, is how do we get compute or is compute, rather, just a commodity?

**56:50** · Right? That those are the that's the tension we've been talking about over the last 15 minutes. Is compute a scarcity?

**56:56** · Is it something where all of you should be spending your time wondering should you be making chips?

**57:03** · Should you be making more better interconnect?

**57:06** · Or should you be spending time on distilling your aesthetics, your creativity, your intelligence, like 3Blue1Brown, into how to teach the world new kinds of science and math and physics?

**57:18** · That's the core tension, right?

**57:20** · Good news is this class covers both. So, for those of you who are electrical engineers and want to go into chips, you're getting that uh exposure. And for those of you who want to be frontier model researchers, you're going to get that exposure. You can decide. Okay? We're not here to decide for you. But here's my view on it as one participant. Macro, I today, unlike electricity or coal, compute is not fungible.

### Compute Not Fungible Yet

**57:49** · Electricity is fungible, right?

**57:51** · Megawatts are megawatts are megawatts everywhere. Pipe into a grid, you get them out. It wasn't always the case, and I'm going to talk about that in a sec, but today, compute is not a commodity. The prices are rising and they're not fungible. This chart shows that there's varying prices for different chips Let Forget chips from different companies like AMD and Nvidia. Chips from the same manufacturer are not fungible.

**58:17** · Right? The H100 is different from the GB200, which is different from the B300. These numbers may not mean anything to you. It's what I spend all day talking about with my research teams. So, number one, the problem or the indicator that compute is not a commodity is that compute is not fungible today. And two, forecasting compute at the micro level is very very hard.

**58:41** · Unlike electricity, where we've developed pretty stable mechanisms for how to forecast our consumption, barring hurricanes and so on there, we're generally like we have power here, right? I grew up in rural India in a boarding school called Rishi Valley, and we used to have power outages roughly once in the summer like every other week.

**58:59** · Today, luckily, I think they've put a transmission like a they built a generator backup generator there. But in the in in most parts of the world, we've had stable forecasting of energy and therefore the stable production of that energy and supply for what, at least 75 years?

**59:16** · That's not the case with compute. Because inside of these research labs, one team finds it very hard to reason about their needs. Training is a is a is a spiky thing.

**59:27** · You think about, "Okay, how do I create a new capability like a frontier model for coding?"

**59:33** · you take an algorithm, you play with it on sort of small scale. If it starts working, then you spike up for your hero training runs. Inference, when you deploy your chatbot, turns out a lot of people you if especially if your chatbot's deployed in the US, a lot of people use it during the day, no one's using it at night. Inference is cyclical, too.

**59:53** · And so we're in that part of the of humanity where um not only is the most valuable input to production of intelligence not fungible, it's also super hard to forecast.

**1:00:05** · And as a result, um we have those hoarding cycles going on. Remember I showed you those uh sort of the the big boys buying up as much land power shell as they can in the next 4 years going, "Look, there's a pretty reliable trade we can make, right, for hardware to software revenue. Not sure which research, which model, which breakthrough will actually do that, but we might as well just buy it all up."

**1:00:28** · So, the question I spend a lot of time recently thinking about, and I think you guys should, for those of you who are interested in infrastructure, is what what did it take in history to turn this scarce monopolized production resource into uh a productive sort of accessible commodity for everyone who's working or innovating in the field?

**1:00:53** · Okay?

**1:00:54** · And my view is again, history tells us that there's two key things you need to solve the fungibility and the the access problem. One, you need standards.

### Standards Institutions and Your Role

**1:01:05** · ACDC, right, TCP/IP.

**1:01:10** · These standards that we convene on over and over again to say, "You know what?

**1:01:13** · This is infrastructure, it should be stable. Let's all agree on a standard, a format for this infrastructure to be produced, and so we can all consume it, no matter where it is." And the second is you need institutions to enforce those standards because inevitably, humans are misaligned at some scale. And somebody needs to coordinate and align human beings to adopt those standards at scale. That's roughly where we are right now.

**1:01:40** · So, what makes a commodity fungible?

**1:01:42** · It's pretty simple. Commodity needs a This is all How many people have taken econ 1A?

**1:01:48** · Oh, wow. Okay.

**1:01:50** · We're going to do some econ assignments, too, for those of you who want to work at the frontier. This is a pretty standard textbook definition of a of of fungibility.

**1:01:58** · What makes a commodity fungible?

**1:01:59** · Commodity needs a common unit, it needs a standard delivery interface, needs interconnection and pooling, needs metering, control, and settlement, and the buyers can substitute one supplier's unit for another. Okay? You should uh really understand this definition if you intend to train any kind of frontier models. Cuz this is not the case today.

**1:02:21** · So, this is my point. Technical standards and fungibility don't come easy. They need institutions to enforce them to reallocate away power from those who benefit from hoarding and instead prioritize the public benefit.

**1:02:36** · That's what we need more and more of in these infrastructure cycles is somebody or some group of people need to start stepping in and saying, "You know what?

**1:02:43** · Good for you, great. You have enough compute. Those folks over there don't. Let's pool, and let's figure out an optimal allocation of this resource across society, across the country, across the world. That's what we um call the public benefit.

**1:03:00** · Yep.

**1:03:01** · 10 minutes. Okay, perfect. I will try to zip through this. We're al- almost at the end. So, the punchline is pretty simple. We are in the pre-standardization of compute era. Right? If you just look at all the previous cycles, railroads from 1886, electrification 19- 1907, telephony, aviation, internet, semiconductors, new new general purpose technology, huge explosion in in infrastructure needs, usually consolidation among three or four players.

**1:03:31** · Hop- sometimes industry step in and self-regulate, and they come up with standards if they can get along. Other times, they a government an institution has to come in and say, "These are the standards." And we're at that moment roughly in history for for compute. So, food for thought for this quarter. This is your assignment, and there'll be some readings, but I'd like you to keep this at the back of your minds.

**1:03:53** · One, what will it take to ensure a peaceful transition on compute over the next couple of years?

**1:04:02** · \[clears throat\] And two, what is your part in this?

**1:04:08** · You can be a part of this change cuz remember I said at the start of this lecture, you are extraordinarily lucky to be alive at this moment in time. It may not be clear to you, and it's always uh you know, it's easier to connect the dots in hindsight, but think of yourselves not just as students, but as active participants.

**1:04:27** · And part of the goal and the design of the um the project this quarter is to try to make you more and more active participants in this stack. You can blog, you can tweet, you can write, you can share your thoughts with the world on what are the standards you wish, you know, you emerge so that your job could be easier.

**1:04:45** · And uh hopefully um \[clears throat\] some of the people in this room who are going to come talk to you, who are running many of these institutions, who can can help evangelize these stand- standards, adopt them, coordinate them, will hear from you.

**1:04:59** · Cool.

### Final Thoughts and Bonus GPU

**1:05:01** · All right, that's all I've got. Um I have a bonus. This is from last year.

**1:05:07** · This is a screenshot of RTX 5090 prices in USD over the last 18 months. Who knows what the RTX 5090 is?

**1:05:15** · Okay, cool. Some gamers in the audience. This is Nvidia's gaming chip.

**1:05:21** · It was also the grand prize for the best project last year. When Jensen came by, he signed five 5090s. I think this is Abel, whose team made a really cool gaming uh product and and and pretty valuable chip, right?

**1:05:39** · So, I'm not going to ask Jensen this time for for more 5090s cuz they're a little bit more valuable this time around. But we'll see, maybe there'll be surprises. Okay, thank you, guys.