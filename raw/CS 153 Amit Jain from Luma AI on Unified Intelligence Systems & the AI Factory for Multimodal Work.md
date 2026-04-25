---
title: "CS 153: Amit Jain from Luma AI on Unified Intelligence Systems & the AI Factory for Multimodal Work"
source: "https://www.youtube.com/watch?v=WNNrUuMQkl8"
author:
  - "[[CS153: Frontier Systems]]"
published: 2026-04-18
created: 2026-04-18
description: "In week three of CS 153, the instructor hosts Amit Jain from Luma to discuss “Unified Intelligence Systems” as a follow-up to a prior lecture on visual intelligence. Jain recounts his Apple work on Li"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=WNNrUuMQkl8)

In week three of CS 153, the instructor hosts Amit Jain from Luma to discuss “Unified Intelligence Systems” as a follow-up to a prior lecture on visual intelligence. Jain recounts his Apple work on LiDAR for projects including Titan and Vision Pro, and how early exploration of generative models and differentiable 3D led to founding Luma with an initial focus on large-scale 3D capture. Luma then shifted to generative video in 2023 to leverage the scale of internet video data, releasing the Dream Machine model in March 2024 and rapidly reaching millions of users, while building preference-based feedback loops and human annotation pipelines. Jain explains Luma’s multimodal AI factory—pretraining, post-training, deployment, and reinforcement learning—its security constraints for studio clients, and a move toward unified transformer architectures that jointly reason across text, images, video, and audio to enable end-to-end creative and professional workflows.  
  
00:00 Welcome And Guest Intro  
01:32 Luma Origin Story  
05:33 Differentiable World Learning  
06:36 From 3D To Video Scale  
10:40 Dream Machine Flywheel  
13:48 Inside The Luma Factory  
21:11 Studios And Data Privacy  
23:04 Unified Models Explained  
25:42 One Backbone Architecture  
30:17 Deploying End To End Agents  
31:15 Why Unified Mega Models  
32:29 Tool Harness Skills Stack  
34:02 Slide Demo Layer Mapping  
35:19 Funding and Capital Intensity  
38:23 Creatives Adoption Shift  
40:46 Creative Leverage and Exploration  
43:03 Sora Shutdown Focus Thesis  
45:33 Copyright and Platform Duties  
47:08 GANs Diffusion and Hybrids  
49:30 Human Creativity in Skills  
51:19 Hollywood Business Model Reset  
55:01 Making Video Models Intelligent  
58:01 Closing Thanks

## Transcript

### Welcome And Guest Intro

**0:04** · All right.

**0:06** · Welcome gang to week three of CS 153.

**0:11** · We have today with us Amit Jain from Luma.

**0:16** · Thank you for joining us, Amit. Thanks for having me.

**0:19** · Okay.

**0:20** · \[applause\] Uh Amit is going to be talking to us today about unified intelligence systems. You're going to be hearing a lot more about this. I think it's a very relevant follow-up to the visual intelligence systems lecture we had last week from Andy Blotman at Black Forest Labs.

**0:42** · Quick show of hands, how many people here are new to the class?

**0:47** · Okay.

**0:48** · Okay, great. So, almost everybody here stuck cuz we had the drop deadline I guess last week, but most of you are still here. Great. If you haven't for whatever reason if this is your first lecture, I would recommend watching Andy's lecture last week as an intro to what's going on in the visual frontier cuz then everything Amit's going to talk about today will make a lot more sense. All right. Thanks for joining us, Amit.

**1:11** · Um quick recap on the class and today we're going to talk about Amit.

**1:18** · And today we're going to do a field trip into what I think is also one of the most exciting uh factories working on how to get work done, especially visual and creative work done in the world called Luma. But before that, why don't we start by talking about Amit a little bit. I had the privilege to get to know Amit a few years ago when he was still an engineer at Apple.

### Luma Origin Story

**1:41** · And uh I was at Discord at the time and Amit I got an email from Amit saying um "Hey, I heard you have a bunch of 3D data.

**1:51** · Uh can I have it?"

**1:53** · \[laughter\] I remember that.

**1:54** · And I said, "No, you can't."

**1:56** · Because Discord had acquired the data, but I started asking Amit what why he needed the data. If you guys remember, um I covered this in our first lecture, but Ubiquity 6, the company I started about a decade ago, was a 3D computer vision mapping company and we had uh we'd had millions of people around the world who were capturing the world in 3D using their smartphones and all that data we terabytes of data um uh that were 3D representations of the world that we'd reconstructed from 2D images.

**2:22** · And Amit said, "Well, I want to build um a 3D service that uh that is generative. I want to allow people to create gender the same kinds of meshes and point clouds and 3D representations of spaces, but through generative models because that's where the world is going."

**2:38** · Um and I s- got interested cuz I kind of agreed with him and he was ahead of the curve. And so, I had a chance to invest as an angel investor at the time and then a few years later I had a chance to partner with Amit again at a16z when I was a general partner and had a thank you for letting me lead your series B. B. Um Amit was also one of the first customers of the a16z compute program called oxygen and actually helped name oxygen as well.

**3:04** · Um I think the quote was he said something like, you know, "If we don't have compute on day one Let's can't really breathe." Yeah. So, um tell us a little bit about what Luma is and how what were the dots that led from the insight at Apple that generative modeling was the future that led here. My background very briefly, so at Apple I was working on first the lidar systems that actually now is on our iPhones.

**3:30** · This was called the Jasper sensor if any of you are familiar. And we were trying to build um we were trying to actually build like, you know, what comes after the after the camera. This sensor was built now I can talk about it because, you know, that project is no more for the car uh which was called Titan.

**3:45** · And we started to work on Vision Pro after that because, you know, the car project got got canceled and the Vision Pro had had a bunch of lidars on it.

**3:52** · And during that work it started to become obvious that like, okay, you know, um the computers of the future we still don't know what they would look like. Uh you know, maybe they will have AI or what what not. The computers of the future will need very different interfaces. We'll need very different kind of media and we'll need very different kind of of ways of actually capturing and creating and building those things into the system. So, in 2020 uh at Apple we started exploring generative models. Um and and think about it, it's 2020, so you know, before language model scaling was known to be working and before um actually it was before DALL-E, but NeRF had already come out from Matthew Tancik from Berkeley.

**4:29** · So, we started to explore those generative systems and uh that led me to thinking that, okay, if language scaling is working and here is is a method where we differentiable 3D is possible, what would happen if all of these things are combined together, right? That would basically mean you have the full footprint of every observation in the universe and you will be able to like, you know, differentially learn about them. If you can differentially learn about them, you can understand them and then finally you can generate them. So, that was the genesis of Luma. And at that time because of of the pedigree we had, 3D seemed like the most logical way of going forward because first of all 3D tells you 3D has a lot more information than images do.

**5:11** · Uh naively we assumed at the time 3D has a lot more information than videos do as well and that 4D would be very easy to capture and scale, but again I say naively because as you will learn in in a few seconds that that was a bad assumption, but that's kind of where we started with the idea of building what we now called a world simulator. Uh at the time it was just like, all right, like, you know, if you can learn this and generate this, we would have something that would allow us world understanding.

### Differentiable World Learning

**5:33** · And okay, you you talked about you you said this phrase which is important you know, learn the world in a differentiable manner. What does that mean? Right. So, I mean, if you're \[laughter\] I'm sure you guys are all familiar with like, you know, how transformers work and how AI models work. Differentiable means you can put it in a training loop and you can have a loss function that can be done iteratively optimized. So, differentiable allows you to do that. If the function is non-differentiable, then like, you know, you just really can't do gradient descent on it and if you can't do gradient descent on it, then deep learning doesn't work. So, the tools that we have for this era, for this generation, is basically compute and gradient descent. Um and yes, transformers are things that are very very well susceptible to gradient descent, but the actual, you know, thing underneath it is gradient descent and compute. So, how can we take a lot of data, a lot of compute and gradient descent and produce something useful out of it?

**6:27** · Differentiability is the core characteristic of that problem, those problems basically. Yeah.

**6:31** · That's helpful. Can you just connect the dots on how what that insight led to then what Luma's doing today?

### From 3D To Video Scale

**6:36** · So, we started when we started the company, the idea was we will will you know, capture an ungodly amount of 3D data, build a flywheel that allows people to capture that and like, you know, for us to be able to use it and then like, you know, build build world simulation systems with it. So, we released an app which is called Luma 3D capture. It actually was very very popular because one, the results were really really great. It was for the first time that NeRF and Gaussian splats were productionized and Matthew you know, he joined our team actually to really push forward the the frontier of of that sort of the world. But very soon we realized it doesn't matter how many people use the app, it will never reach the scale that was necessary to learn enough about the universe.

**7:16** · Why is that?

**7:17** · Because think about it, right? The number of people that are writing on the internet, that are taking photos on the internet, that are are are capturing videos on the internet substantially outpaces anything one company can actually distribute. Also, there's like, you know, decades and decades and decades of that information that is already available.

**7:36** · So, it's all about data. It actually you you can make the case that like, you know, this particular modality of data is better for learning versus this or versus that. It really doesn't matter, that's a moot point because you're running against the physics of scale.

**7:48** · So, wherever there is scale in data, that's the only thing that's going to work. Mhm. And you have to design the algorithms around where the data is, not the other way around, right? You come up with some pristine algorithm, but you don't have any data, then like, you know, what's the point? Robotics is coming up against this problem right now where like, all right, we're going to build like, you know, these action systems, but well, where is the action data? There's no internet of action data.

**8:09** · You can have huge labs in in China and India and and Vietnam and and and everywhere gathering this data, but the scale is really not comparable. So, you have to just design the systems around data. So, that's what that's what we learned.

**8:21** · Um so, in 2023, after that realization and after you know, Nvidia Hopper architecture was announced, uh we started to build the foundations of um you know, generative video because video is three-dimensional. It has two dimensions of space and one dimension of time and human brain actually like, you know, learns about 3D representation through that time proxy. So, when Hopper architecture came about, we started to think like, all right, it might be possible actually to learn video and to learn the world representation through video. So, in 2023 uh Jamming joined us. Jamming was a you know, at Nvidia at that point.

**8:57** · He's a Stanford grad and a few other people from Stanford and Berkeley uh started to join the company with this idea of like, all right, let's learn from video.

**9:04** · And we started to build that infrastructure and in February, sorry, in March 2024 we released the first video model that was called Dream Machine and uh you know, in in the first three weeks, four weeks actually we got up to 6 million users from that because people had never seen generative video. Sora was announced, but never released, so people had never experienced it, so people really wanted to actually try that out. So, we started with video that that point.

**9:25** · And then we have had the similar realization again in 2025, early 2025, just like annual cycle of now, that just video is not enough because video is good, but it doesn't pair human logic. It doesn't pair why an event is important, what is the sequence of events and what does that actually lead to. Just having language models in the middle that are like, you know, being used for embedding is not sufficient.

**9:46** · You need unified intelligence, so that's kind of where we are now. Yeah, these are the dots. Well, um yeah, so th- this is not the first time the class has heard that when you close the loop, you have to you have to sort of evolve the the mid-training, the post-training pipeline, the interface. And so, can we spend a little bit of time? So, I don't think it's a surprise for people to hear that there was sort of an iterative loop every year as you got more and more data from customers.

**10:11** · Yeah.

**10:11** · But, can we talk a little bit about that first you know, the final projects for the class this time are the one-person frontier lab where they're going to be bootstrapping their own flywheels. That's pretty cool. Um and the first, you know, before I remember you know, how nerve-racking it was for you and for the team when when you had the realization that video was going to be the future, but you didn't have a video model out in the world yet. Yeah. And you didn't have a state-of-the-art system to start collecting that um that context feedback loop. Yeah. So, let's let's let's take a bit of a journey back in time time travel to uh the launch of Dream Machine 1. Yeah. Can you just tell folks how you went about kickstarting or bootstrapping the the video flywheel at Luma?

### Dream Machine Flywheel

**10:53** · So, I think the core problem that you want to think about whenever you're building these really really large systems, they have a wild distribution, right?

**11:02** · Like, you know, if even if you're talking about language models, well, they have all of language models language model data, and what is good, what is bad, right? So, you want to think about, okay, from this really raw distribution I get from pre-training, how do I get to a model that humans can use?

**11:18** · And what humans find useful is a very narrow band within that distribution. And that narrow band is not like you know, a predictable linear band. It's just like, you know, pockets of of of greatness that humans think are great. Some other species might find it very different, right? But, we have our own aesthetics, we have our own use cases, we have our own value systems, so we find those those distributions valuable.

**11:41** · So, now the question becomes, how do you find or how do you basically get that distribution out of the model?

**11:47** · So, we started to think about that problem. And and with Dream Machine, the because there were so many users that were using the model, the question became, all right, can we learn something about that? And and preference or like, you know, preference feedback at that time, by the way, um SFT, right? Like, you know, it was just started to being thought about.

**12:04** · RLHF was the hot thing where people were thinking about like, all right, like, you know, human feedback loops.

**12:09** · So, we built a system where um videos that people were liking and people were downloading, we considered that to be a signal of like, all right, this is something that people prefer. Um it was not 100% accurate because some people were downloading really bad videos as a showcase of how bad AI is at video. Right? So, our model also learned a lot of that. So, we had to then build systems for uh humans to be able to uh go and filter out like, uh people we pay. So, then it started to emerge what a frontier lab actually looks like. A frontier lab has these components of data, these components of compute, and algorithm, but it also has huge parts of of what we call skills and trainers and tutors and people who are doing the labeling of data and all of these systems.

**12:50** · If you don't have that, that is actually not complete.

**12:53** · And a part of that is also the product you built. Can the product actually give you enough information to make sure that the next model is better than the previous one? And hence the experience is better, and hence more people will use it, and hence you'll get more data from it about this preference of of human distribution, and can you make the next model actually better? So, I mean, it took us a long time to learn actually how to gather that feedback, how to, you know, and then now the system we have in in in the latest Luma agent system, ungodly amount of feedback actually we get from from um what people are doing.

**13:26** · Every interaction that is there, we learn from like, you know, whether they like it, dislike it, in what way they like it, what way they dislike it, whether the full chain of thought that that the model produced and the full chain of work that the model produced is any good, which elements of that is not good. And then that's how you actually start to get good at it. Well, let's um why why don't we do a double click on how that's that actually works? So, to remind everybody about the field trip we're about to take, right? Um this is the the very basic standard AI factory we've talked about, right? Frontier AI um sort of pipeline. We got pre-training, mid-training, and then we've have post-training and deployment. And so, today we're going to hear a little bit from Amit on how the the Luma version of this works. Why don't you go ahead and just kind of talk us through Yeah.

### Inside The Luma Factory

**14:16** · what's what's actually going on under the hood at Luma. Absolutely. So, um let me talk about what is informing the design decisions for our architecture and for our models. Um Currently, we're seeing huge amount of alpha coming from from language models being used for for adjacent tasks like coding, for adjacent tasks like, you know, system design and and those kind of processes.

**14:39** · But, when we start to think about tasks that require more context than what is available in text. So, creative work, right?

**14:48** · Huge amount of things a huge amount of information that is in in visual domain, huge amount of information in auditory domain, actually huge amount of information in the trace of how you arrived at the final output, right?

**14:59** · That.

**15:00** · When we think about robotics, you can definitely start to build a robotic system just based on text models or VLMs or VLAs that people are starting to do now, but they will not generalize just the same way that like, you know, autonomy autonomous driving didn't generalize until people started to build full end-to-end systems that that had language, that had video, that had like, you know, all of the control signals, all of these things in there. So, that's the problem we are coming up with that the real world is way more complicated than coding. Right? I mean, coding is a really valuable task, but not everything can be done in coding, right? Like, otherwise programmers would be the only profession that would be left. Uh uh and now they're also, you know, endangered species, actually. But, I'm not sure that's true, but I understand your point. Yeah. As as a programmer, uh it's really fun Well, the job has evolved, for sure, to become a trainer and a tutor. Yeah. It's a really fun fun time to be that way. Uh I started coding like, you know, when I was 13 years old in order to build simulation systems, in order to do like, you know, so my background is in physics, and in order to actually build like, you know, simulation systems for for electromagnetism and those kind of things to see how these systems behave.

**16:05** · That's why when I learned to start coding. And even at that point, it was really obvious that I cannot teach those systems from any observations. Mhm. Right? We can write the code, but that is like approximations that we have in our in our models or in our in our equations, but we can't actually teach those models from any data. So, all of this is informing how we build our systems.

**16:26** · So, even early on, we started to think about, okay, in our pre-training, how can we learn from all of video, all of images, and all of text, right? It's a really hard problem because they're really different modalities and they're expressed very differently. If if you think about the encoding of these modalities, text is discrete, and text performs the best when you encode encode it in a discrete manner, at least that is our understanding today.

**16:53** · Video is kind of somewhere in between. And audio and images are best performed in in continuous space. So, our factory, as you call it, is built around this idea of like, how do we learn jointly from all of these systems? In 2025, these were disparate towers that we built. Language tower, image tower, video tower, audio tower.

**17:15** · And then like, you know, we would unify them together um using just like, you know, some some fusion techniques so that like, you know, they will do better.

**17:23** · Uh if you look at like, you know, the work from uh Andy's lab, right? Like, you know, Stable Diffusion, those kind of things. That's what it does as well where you have a tiny little language component um and and you learn embeddings from that to be able to understand the human instructions.

**17:37** · It was just not sufficient. So, when we talked to our customers, when they tried to use our system, so where where are systems being used, right? For instance, currently, large studios. So, actually, I'm very very very excited about um a new show that is coming out on Prime Video. Uh the trailer's out. Uh it's called um um Old Stories. Uh it's about Moses, right? So, it has um Sir Ben Kingsley is the star of it. Uh it's it's a proper production, it's not an AI video. Uh it's a $4 million sorry, $4.5 million per episode production, basically.

**18:06** · And it's all pretty much all produced using Luma agents. So, they're using it in these like really high intense situations where they want to be able to model the whole world and the physics of the world and light and and and and fluid and interactions and all of these kind of things. Now, when you do that, is this not sufficient to build an image model or a video model? You need a model that understands time and causality and and language, right? And it it understands like proper instructions.

**18:32** · Okay, well, like, you know, uh um this looks good, but what if like, you know, the the shirt sleeves had like, you know, this particular thing right here? Mhm. How do you express that instruction? Okay, in time, when this person actually walks uh through the door, the whole scene explodes. All right, what does walking through the door actually mean? When the person walks through the door, what does this explosion of the scene mean? Give me more instructions, right?

**18:54** · The deeper you go into these kind of problems, this is a very very very big market, right? It's about 120 million creators in the world whose this is their job, right? Like, you know, these are not people who paint for a hobby or all these kind of things. These are people who actually are employed in this industry. So, about uh you know, two times, three times by estimation of coders. Um their work every day goes into replicating the physics of the real world into computers.

**19:19** · So, we want to build systems for them.

**19:21** · And if you want to do that, you want to build what we are now calling unified models that have the same understanding and intelligence of a language model, that can follow context, that can remember, and the physical understanding and the world model understanding of video models and image models. So, that is what the output, that is what the things we want to produce. This was 2025. And now in 2026, when the models got really good, what people want to do is like, they want to do the full work end-to-end.

**19:49** · You know, it's like, all right, why is it only producing 5-second for me, right? Why can't it make the whole shot?

**19:54** · Mhm. If you go to like, you know, people in advertising, well, why can't it make the whole campaign? If you talk to robotics companies, why can't it actually produce the whole action and then judge its own outputs and then tell me when this is the right action and incorrect action. Like, you know, why can't I get the right force and all of these kind of problems? So, people want end-to-end results.

**20:13** · So, now the Luma factory is about building systems that can do end-to-end work in multimodal domains. So, that's that's kind of what we do. We have massive reserves of like, you know, multimodal data.

**20:27** · In about the final trainable outputs are in in about 30 petabytes of, you know, scale. We train them on on, currently, H100s and very soon GB300, uh, uh, you know, GPUs in the 010K scale, basically. So, pretty much the same as as a second-tier language model training. Like, you know, so, we're not at 1 trillion parameter yet because that scaling hasn't been figured out. But, we're going to get there.

**20:51** · And then we do post-training on this stuff using huge amount of customer data and huge amount of user preference data as well as data that comes from our own human annotations. And finally, we put them in production and we do reinforcement learning and and continual learning on those systems. So, that's the shape of the factory currently at Luma.

### Studios And Data Privacy

**21:11** · And could you talk a little bit about you know, when you started deploying these systems in in the first lecture we talked about mission-critical context, right? One type of mission-critical context is a large studio Yeah. for whom their data is super sensitive.

**21:26** · Yeah.

**21:26** · They don't want, you know, they're happy to have you train their data, but with their data for them. Yeah. But, they don't, if I'm running a studio, I don't want my data being used by another studio. So, how do you how did you navigate the deployment sort of restrictions Yeah. of these of these professionals? So, we work with two arch nemeses at the same time, Netflix and and Amazon Prime Studio, right? Which are the two giants of streaming war at the moment. Um, so, basically, then then you have to build systems that are guaranteeing that there is no way that there's any data overlap.

**22:03** · We have internal controls and systems that like, you know, are are some of the standard ones like SOC 2 and those those kind of things things and then specific ones that are for AI labs on how do you not train on this on this data. So, for instance, if you're producing the next blockbuster, you don't want the next Iron Man, for instance, right? Like to show up into the training data. So, we have guarantees around that like, all right, whenever certain stuff is marked or projects are marked, they will never show up in training data. They will never show up in in any of these loops, basically. But, we still learn from like, you know, what users are doing in the product, which is different from the the visual artifacts that they're producing, but rather the traces they're producing. We we were still able to use them and learn from them, actually. This is the interaction data That's right. when people are working with the interface of the agents.

**22:49** · That's right. Okay, there's some limitations on on these kind of high high sensitivity projects.

**22:53** · Um, yeah, I think you have, you know, sort of a Well, one, could you talk a little bit how you created these slides cuz these these, I believe, were created with with Uni 1. That's right. Is that right?

### Unified Models Explained

**23:04** · So, these are, you know, I I basically gave it, actually, let me start from that first. And then I will actually actually talk about unified models as well. So, here, I created this, like, you know, on the top what you see, I created that um, mind map, whatever you want to call it, in our product. And then I basically asked, if you see on the right, I asked it like, you know, and I also gave it aunt slide that like, you know, the one right here. Sorry, not this one, but Okay, I don't know. The first one you saw of the factory slide, actually.

**23:35** · I gave it that and asked it like, hey, in this style, actually produce the outputs. And now, this is actually a very very good example of what unified intelligence that I'm going to talk about means. People, when they think about image models, video models or or any models not text, they think they are just they produce beautiful images, right?

**23:55** · But, that is a really big mental gap that the world has in this area. Just like language models produce words, right? The words can be beautiful. You can just say like, hey, it's a poem and it could mean nothing, right? And and simultaneously, you can have a mathematical proof of Erdős problem number, pick your take your pick, right?

**24:11** · 1152.

**24:12** · They all are words at the end of the day. But, how you string them together determines the information content and determines the informa- uh, the intelligence of those.

**24:21** · Just like that, how you arrange the pixels determines what they're conveying and how how intelligent they are. So, unified models that we are producing now, and I'm going to talk about that in a second, are about how you express intelligence in whatever medium is convenient for the person that they are actually, you know, who's using it. So, if a language is language output is convenient, fantastic. If it is slides and images, fantastic. If it's a video explainer, great.

**24:49** · They're all basically outputs that are intelligence. So, that's what we call unified models. So, here, basically, it was one shot. It produced those slides.

**24:57** · It produced one that I didn't like and I deleted, but before you asked me to take a screenshot of that. But, that that was pretty much about it. If I would have asked it to do a very detailed overview of that, then that's what it it would have done. So, end-to-end work. This is what we call end-to-end work, right?

**25:11** · So, just to break down what happened, you gave it you gave it my original slide as a prompt, a screenshot of that prompt. You then gave it instructions on the right in the chat. And then you gave it a little bit like guidance. Is it that that's what you did?

**25:24** · my my my thoughts up there. Right.

**25:26** · The top half of the screen is like, you know, my my thinking. Right. And then the output below was essentially the slide one-shotted from that.

**25:33** · Correct. Okay. And why was that not just possible trivially? Why can't an LLM do that? And why wasn't why did it take so long to get here? What's the hard part about this? Right. So, I mean, that's a good segue into unified models, basically. So, um, well, LLM, first of all, doesn't generate images. Right. I mean, it's a language model. You can ask an LLM to use a computer and try to generate images. But again, it really falls apart because it doesn't see anything.

### One Backbone Architecture

**25:59** · So, when it tries to reason spatially, when it tries to produce like, you know, any visual outputs, they're blind models. They see everything as a full sequence, right?

**26:08** · Like, you know, even the grid nature of of of images and visual information is not apparent to LLMs. So, when you started to do VLMs, which are vision-language models, right? Like, you know, you started to teach them a little bit about image part of it. VLMs are still not generative. VLMs understand images, but VLMs can't generate images.

**26:26** · So, we have on this world where like, you know, you have understanding in language and and generation of text, and then you have uh, models like Flux, which are good at generating images, right? Which are great models, by the way, right?

**26:37** · But, then they don't have any of this understanding. Right. Right. And I think Andy talked about that last time as well that like, there's this big chasm in between these two things. Understanding is separate and and and language is separate. Oh, sorry, generation is separate. But, in language, that's not true. An LLM is good because it understands text and generates text all in one go.

**26:55** · Mhm. Right. There's no there's no delta in between. There's no two models that are actually doing it. If we want to solve world understanding and quote-unquote world models that people are calling it, that's what we need to do. But, um, we've, I mean, for at least about a year, I guess, we've had models that can generate language tokens and image tokens, right? Like with Nano Banana. Right. But, they they was like, Nano Banana was still not able to generate remember trying to generate schematics like this. Huh. I I tried to generate the factory slide Yeah. with Nano Banana and I couldn't. Okay. Why were the capabilities still not there with basic sort of like these jointly trained models? So, from what we know of Google's architecture, Nano Banana is still a few-shot architecture. Where like, you know, there's a large diffusion tower that is generating images and there's a large language tower that is generating text.

**27:43** · And there's like a thin bridge in between them. So, like, you know, you generate huge amount of text that's called EP, enhanced prompt. And that text you take and give it to the image model. And that image model's job is now interpreting that text using a very thin narrow VAE, right? Like, you know, and and some encoder.

**28:01** · I don't know what Google uses for their internal encoders, but these encoders are like 700 million parameter, 800 million parameters. That's the best you're able to actually get out of it. What we are building in unified architecture is different. So, our approach is, well, transformers are probably the single thing like, if you know, I was coming back in time, this is what I would bring with me, the transformer architecture.

**28:21** · And I would give it to people that like, all right, you know, go go go play with this.

**28:25** · Transformers are very good at they don't care actually what kind of information you're passing through them, right?

**28:30** · Continuous, discrete, actually, it's all okay. It's the pre and the post of it that like, you know, the encoders and decoders when actually things start to fall apart. So, in unified architectures, what we are building are these Actually, let me I didn't order it correctly, but anyway, this is a pretty bad diagram of that because again, it is a I didn't try to go with the architecture diagram, but that's that's kind of the idea.

**28:54** · One single transformer or maybe one single backbone, you encode this information in the same space, whether that is audio, image, text, code, doesn't matter, really. And then you reason about them all in the same backbone. Just like the human brain, right? So, human brain, while it has, you know, different different different areas for processing image information and or visual information, auditory information, those kind of things. But, those are just encoders.

**29:23** · All of that information then goes into the neocortex or maybe a little stages before that, but anyway, it ends up in your cortex and reasoning and thinking and and and all the judgment happens in one single place. This is how we build the next generation of great models, right? Like, you know, that are able to do more tasks than what LLMs are able to do.

**29:44** · It took us about a year to come up with this architecture. A huge number of failed attempts. You probably know, right? I don't know how long I've been talking about this.

**29:52** · Huge number of attempts at trying to scale them, all of that things. But now we are at a place where we are pretty comfortable and confident at building like you know hundreds of billions of parameter models out of this architecture and we know that it is going to scale. So now there's efforts within the company at all of these modalities, but one single model, one single architecture including language. So yeah, that's unified architecture for Luma. Makes sense.

**30:14** · Yeah. Did you have any more before we switch to Q&A? Uh yeah. So actually let me talk about how we deploy these architectures first of all. So this is what we are trying to build. If you wanted to do end-to-end work, this should be very familiar. Like you know, if you've taken CS class, it's the rebel loop, read eval print loop. This is how computers work, have worked for a very very long time. If you think about the Von Neumann architecture, it is built around like you know the rebel loop generally. It was not thought about at the time this way, but now we think about it this way.

### Deploying End To End Agents

**30:40** · If you want to deploy models to not just produce like you know text tokens or image tokens, but actually to do work, end-to-end work. How do you build these systems? So how do you do that rebel loop? One way is doing the left one, where like you know there you have different models for each kind of things and there's like two schools of thought.

**31:00** · You produce federated models or like you you have this kind of like tiny models that are each doing specialized work. And then you you make them come back you just pass outputs from each other and you probably have a judge model on top that like you know judges and orchestrates all of that work. That's approach one.

### Why Unified Mega Models

**31:17** · And approach two is that you have these like you know mega models in the middle and where they have they share this like you know deep connective tissue and they can reason in one single space. And you give them, you know, inputs and you expect outputs of them. They're iterative models, so it's not like you know one shot all the outputs that are going to come out.

**31:36** · But we are betting on this second approach. And the reason is very simple because we think intelligence is not this pipeline architecture problem. If you think about the systems of intelligence, the systems of intelligence don't look like you know this kind of big database problem. The systems of intelligence look more like the human brain where you let information itself design the architectures and circuits inside it like what we do during training and hopefully very soon in continual learning these circuits will change as we as we are actually you know using these models.

**32:07** · And then you sort of step away from that. Mhm. You manage context outside. You you know manage memory sometimes outside, sometimes inside like how you do with caches in in CPUs today.

**32:19** · But the actual processing unit are these unified models. So that is sort of our approach of how we how we think about building them. And how we think of improving them is a little bit like this. So if you want to think about like what is a computer of the future looks like, actually what is every agent product today it's some version of this basically.

### Tool Harness Skills Stack

**32:36** · Like you know this is not a big revelation. This is how things are being built. So you have like you know a tool harness in the middle. I'm going to go from the middle up. This tool harness means systems that can use Linux, systems that can use you know call APIs, all of these kind of things.

**32:52** · But then how does it all work? How does it actually full work gets done?

**32:55** · So you have this like fat stack of skills on the top. These are domain specific understanding, right? So you want to teach a robot like you know how to assemble something, right? That's not a normal thing, right? Like you know if you want to think about like how is an iPhone assembled? This is a very domain specific thing.

**33:11** · You can give it all that information. It doesn't need to be in the model. It doesn't even need to be in the tools. You give this information as context. And you can do this across huge amount of verticals, huge amount of like you know different tasks in those verticals.

**33:26** · Then you have tool harnesses where you give it as general ability to call tools and things like that. And finally orchestrating all of that and thinking through all of that is this unified model at the bottom that is interpreting all of this multimodal information, generating tool calls, understanding which skills to use and producing the outputs. So this is how we think the architecture of the future of computers will look like and this is what we have built the current product basically on. This is this is basically built on this kind of architecture. So yeah.

**33:55** · So actually could you just do a one-to-one mapping through here where where was the harness, where was the skills, where was the model? So actually when it generated these slides, right?

### Slide Demo Layer Mapping

**34:05** · Someone on our team who's really really good at producing greatly designed slides wrote a I don't know about it a 50-page document on what it means to design good slides. Right? And if you see actually I don't know if the prompt is there. Um I've got a clear picture and I'll kick off planning and generation. Okay. So after this it would have uh said like oh let me look up the skills I have access to.

**34:29** · Ah so that was the skill. That's a general purpose um slide skill. Like best in class slide creation skill that was created internally by a human and then uploaded for anybody else to use. Exactly.

**34:39** · Automatically. Exactly.

**34:41** · Uh so that's the skill layer. Then the model layer is obviously the one that is generating and generating tool calls and all of these kind of things.

**34:48** · And the tool layer here so not many tools were necessary, but I I I think like you know your image that that you gave that was also passed as context and we probably ran OCR on it. Just like you know see like you know what what kind of things is. So this was not a very tool call heavy thing. But had you asked it to make an interactive web page Right.

**35:06** · that like you know animates all of this stuff, then it would have gone and called you know coding tools, tools to like you know run that code, deploy that code, all of these kind of things. So it will have done all of these things. But it's the underlying model that is orchestrating all of that. Okay. I'm going to ask you one last question before we switch.

### Funding and Capital Intensity

**35:22** · Which is Okay. So it took a couple years to put the whole system together, which is a fairly high scale system. Can you talk about the business for a second? I know it's earlier this year I think you raised about a billion dollars. 1.5. 1.5 billion. Yeah, total. Yeah. Over the lifetime Luma's raised about a 1.5 billion of that I think a billion was raised this this these last 12 months.

**35:43** · Um you know why does why is this such a capital intensive effort if it's not as high scale as language?

**35:49** · If you really want to do it correctly, it is larger scale than language.

**35:53** · Because it is strictly a superset of like you know the work that is going on in language. But currently we don't care as much about coding for instance. So we don't have to spend that much effort towards it. We can go towards all the areas that language models are not good at. And that means we can actually have a subscale compute infrastructure, subscale data infrastructure, things like that. So it doesn't require 100 billion yet. Like you know we can do with 1 billion what like you know generally takes 5, 10 billion annual run rate to be able to produce.

**36:23** · But if you think about it like where things are going, you know, in 1 year, 2 year, 3 years time we believe that these systems will far surpass language systems just because of the access to more data. More data is better, right?

**36:38** · Just because of their understanding of more domains. So I'll give you an example. One of our customers who is using these systems, they work in energy industry. You can guess who that is.

**36:47** · Um Right. And now suddenly like you know our systems have no idea about like you know grid systems. Like all right, like you know how the energy grid actually works and and and how they want to be able to do that. So what we did is we started to ingest their energy grid diagrams, energy grid code and all of these kind of things. And suddenly our systems are better at producing schematics and planning than Anthropic's coding models are because they can't actually read all that information. They can't actually see like you know how the things are laid out. That's our problems. It's a very small example.

**37:19** · Studios have another big example where like you know yes LLMs they have had forever, but a story is not just text. A story is all of the physical stuff that is happening. If it has visual understanding it can do much better. So we believe like you know especially as the age of robotics comes about you will need these systems to be general and these systems to be able to do everything including writing code.

**37:38** · And and that's kind of where we're going to go. But today this gives us a very great business where language models are not really playing.

**37:46** · Um currently we are like you know when we started the company, I mean we were very small. Today we work with some of the largest studios in the world. Now we work with the largest advertising agency in the world, Publicis. They're just deployment channels for us. We work with the second largest brand in the world, Coke, who is moving $3 billion of annual production of of content to Luma basically. And um in addition to that like you know in in in some of the areas like how do you do work just in a company, how do you communicate information visually? They're they're starting to be like you know these new areas in which previously only designers and and artists could work. Now everyone is starting to do that work. Yeah. So this was you know you had an event earlier this year. I mean like \[clears throat\] I think it was 3 weeks ago.

### Creatives Adoption Shift

**38:28** · Yeah.

**38:28** · I in SF and I came by and the thing that shocked me was that it was all artists and creatives. And you I mean you spoke for a little bit off the stage, but then they got you off the stage. And then a bunch of folks from Hollywood came by, a bunch of designers and it was the first time I'd seen so many artists and creators.

**38:45** · Not not like machine learning people, but but creatives excited about using tools. Why has that that's and that's very new. But you know there was a lot of like fear, uncertainty, doubt a couple years ago that this was going to actually take away jobs in the creative industry. Um but for whatever reason these folks and these are some of the biggest names in in creative in the creative world.

**39:08** · Right. Um some of whom were actually opponents of of the technology a couple years ago.

**39:12** · What what what changed? I think the technology at that time was not good enough. And they were just looking at it from the angle of like it's first of all it's using all our data and it's not good enough. So what is the point of all of that?

**39:25** · But through all of this work that we have been doing, now the value is starting to become just it's in their face, right? So when we go and talk to companies about our work and and and what the products are doing, what we do is very simple. We actually sit right there and someone will open a board and and start to produce their stuff. Actually, this happened recently at a a gaming company, SciPlay Games. And you know, they produce Monopoly Go and some of the most played games in the world. And we were talking about it and everything was hypothetical. It's like, "Oh, it will scale up production. It will reduce cost." All of these kind of things. And then like you know, I was just I took a couple of like you know, their assets and we produced like you know, about a 500 scale campaign while we were sitting and talking about it, right?

**40:05** · Like you know, it's like, "You can do it for all of these different different things." And we showed it like right there.

**40:09** · When you see that, it's the same thing that coders are having that moment today. It was all slop before, right?

**40:14** · Slop just means when someone says slop, it means they have never seen or used a good AI system before, right?

**40:20** · When you see the results and you're like, "This is as good or better than what I can produce." Or at the same same in the similar ballpark at least, their minds change. Hollywood studios were and and still are like very apprehensive, but now when they start to see like you know, the production that we have coming out, we actually show them and they're like, "There's no way this is AI generated."

**40:38** · And then we show them the back backstage production of it, right? Like you know, and then that changes my hearts and minds. So, the best way to change hearts and minds is to just do good work and actually show them.

### Creative Leverage and Exploration

**40:46** · why does that Does that mean the existing folks in those jobs have more productivity or they're getting stuff done faster? Like what What is the benefit to the creative? Let's put the business people aside for a second. The actual The creatives who are using these tools, what what's the benefit to them? Yeah.

**41:04** · I think it really changes the game of what they're able to do. So, in in a couple of ways. First of all, right now, execution is at a premium.

**41:12** · So, you do so much work to validate the idea ahead of time and like you know, this is all across AI by the way, not just like you know, for Luma. You do so much work like, "Oh, is this the right idea once we put the execution resources on it?" Right? Like you know, but think about it. It just It just changes the equation completely. It's like, "All right, let's execute on all of them."

**41:28** · And produce the thing and we'll see which one is great one.

**41:31** · When you think about some of the best creatives in the world and I I don't mean creatives like just visual creatives, right? Like you know, people who made anything, they end up being prolific. If you look at their life afterwards, right? Like you know, if you look at Einstein's work, right? Yes, relativity is huge, but there's also like you know, huge amount of work that went into like you know, Brownian motion. Huge amount of work that went into light and like you know, lasers and which you forgot, photoelectric effect, right? If you look at Archimedes, incredible \[snorts\] amount of work. If you look at Mozart, you know, just ungodly amount of work.

**42:01** · Some of them was good, some of them was not so good, right?

**42:04** · People who are great at what they do are not just one-shotters. Like they they actually produce a huge amount of stuff.

**42:10** · Currently, if you look at just our industry, artists and creatives are stuck in this industrial system that measures every action they do by the by the like you know, output that they're producing. This is no way to do great things. If you want to do great things, you should have the liberty to just like explore basically, you know, unconstrained. Then they start to use our stuff.

**42:31** · They feel unconstrained.

**42:33** · And I think that is what is bringing a lot of creatives on board.

**42:38** · Cuz you can paralyze exploration. Exploration, I see.

**42:41** · Right? And then you get to produce better things than you could ever do. It's more enjoyable because you know, you're not in the slog of like every single pixel and all these kind of things. You become come at a higher level. This is what the moment coders are having too. It's like, "All these ideas I had, they're not just stuck anymore. They're not I can just try them out." Right.

**42:59** · Okay. I think we should switch to Q&A.

**43:01** · I'm sure there's lots and lots of questions. So, the question is, "What is my hypothesis why show Sora shut down? Whether it's a business reason, it's an architecture reason. And two, what impact does it have on us in the industry, but also like you know, on creatives?"

### Sora Shutdown Focus Thesis

**43:16** · So, I mean, I can only give you a hypothesis. I don't know really what is happening inside OpenAI. But I mean, the the the one word here is really focus.

**43:24** · \[snorts\] OpenAI at the core of it is a large language model lab. What they do really really well is produce models that are very good for chat particularly, right?

**43:35** · Chat is a vertical that has about 8 billion customers, right? Maybe not little kids, but if you maybe they too, right? Like you know, because they want to talk to computers. So, pretty much all of humanity is a good customer of chat.

**43:46** · Executing on that is a really hard problem. Executing on anything at that scale, you need to go into the depths of hell to be like you know, get everything working really really well. When you do everything, that's really hard to do. I mean, Luma also had that problem actually, right? Like you know, in early days when we we were not really clear about how do we execute on this. So, we tried a lot of parallel paths.

**44:10** · But doesn't matter how much money you have. Doesn't matter how much how many people you have. This was also a lesson from Apple. This way more things that Apple that they choose not to do than they choose to do, right? That is because doesn't matter the money, doesn't matter the people, the organizational physics still come into play. Less is more.

**44:25** · Exactly. There's only so much attention you have as a company, not as a person, but as a company that you can actually devote to making something. So, OpenAI doing literally everything is not good for their business. And I think that is a realization that is setting in. And I think this will not be the last thing that they have actually canceled, right?

**44:42** · There might be actually even more. Um one thing I will challenge is OpenAI was not the largest player in the market. It is actually Google that is doubling down on on video, on images, on visual generation, right? Like you know, Gemini are Gemini's great models that that do pretty much all of these things actually.

**44:57** · It doesn't indicate actually anything on the size of the market. It just indicates that they are getting their ass kicked because of less of lack of focus by Google, by Anthropic and those kind of things. And they have to focus if they want to go IPO, right? And that's the market that we are actually entering at this point. For Luma, what does this mean? I mean, this is great news. This validates like you know, our our our thesis that like you can only do so many things at a time. And um this is the area that we have chosen to go in because this is a very very big market with huge number of people that call it their profession. So, it actually gives us very good footing in in the same market. So, that's what I would say.

### Copyright and Platform Duties

**45:33** · So, the question is, "Given that anyone can make a video about anything and content about anything, what happens to copyright? Right?"

**45:44** · So, I think \[laughter\] copyright and the ability to produce something are orthogonal problems, right?

**45:51** · If you're talented enough, you can make Mickey Mouse in Photoshop, really. And you can actually produce great stuff about Mickey Mouse. Like let's say you're DreamWorks. You don't have rights to Mickey Mouse, but you have all the people who can actually produce anything related to Mickey Mouse. But you don't. Why? Because the law exists that like you know, prevents you from doing that. So, I think none of that has changed.

**46:12** · Has it become easier to violate other people's copyright? Yes, I think so, right?

**46:18** · You didn't ask me like what the responsibility of platforms is. Again, the responsibility of platforms is the same as it was for Photoshop, right?

**46:23** · Like you know, it's not Photoshop's responsibility to prevent you from producing Mickey Mouse. It's your responsibility as a law-abiding citizen to not violate the law of the land. So, I think it is pretty much orthogonal basically. Like you know, generative AI doesn't change copyright in any way, shape or form um at least on the output side of it.

**46:42** · But it's specific that if there's a law that says you can't do XYZ, you'll you will adhere to it. Absolutely. If we get a DMCA notice, we'll take it down.

**46:50** · All right? Like you know, if you're hosting it. Um if that person used to create it and we get a call of like, "All right? Like you know, this person made something." It is not our responsibility to point law enforcement to them, right? Like you know, because that's not the law of the land. All right. I see. You you have You you protect the users in that case.

**47:06** · That's right, right?

### GANs Diffusion and Hybrids

**47:08** · So, the question is, "GANs were very popular in 2017, 2018.

**47:12** · And now, you know, the world has shifted pretty much entirely towards the fusion models. What is the space of GANs in today's models or today's architectures basically?"

**47:21** · That's a great question actually. We still use GANs quite a lot. We use techniques from GANs quite a lot. But GANs are one of the most finicky architectures to ever work with. So, GANs if you don't know, are generative like you know, adversarial networks.

**47:34** · And as the name says, they're adversarial networks. Like you know, you you design the the objective in a very different way to the fusion models, right? Like you know, where you have a very predictable gradient. It's not I mean, they still explode sometimes, but it's a very predictable system. GANs are still actually used quite heavily in distillation networks. Like you know, if you want to do distillation, like GANs are actually pretty useful.

**47:54** · Um if you wanted to do a real-time system, you would still go to GANs quite a lot. But because GANs are just not very predictable, researchers don't want to work on them. And that is the laws of like you know, physics in in AI. What researchers want to work on is generally what will get worked on, right? Like so, I can I can make the case that like, "Hey, Rust is more efficient." Doesn't matter.

**48:15** · Everybody wants to code in Python. So, that's what will be done. But also, GANs have not shown the kind of scaling that we are seeing with transformers, right? GANs are primarily, you know, unit-based and and and convolution-based models.

**48:29** · And \[clears throat\] they just don't really show the kind of learning that you can get from transformers. Can GANs be implemented using transformers? Yes, there are some papers about it. But at that point, you're really really trying very hard to like you know, just just do GANs. And and that's okay. But diffusion models also now are on the way out. So, I know this will be a little bit controversial if people are thinking about it.

**48:48** · But diffusion models have physics that is not actually bearing out on scaling side of it. So, Luma and and some of the companies are actually moving away to hybrid auto-regressive and diffusion regimes. That's what our our unified models actually are. Because diffusion models actually have some really really bad habits that are hard to unlearn and hard to like you know, get out of of the system. So, they're also on the way out actually.

**49:12** · So, yeah. It's a very uh I've If you realize, basically when we first start teaching the class, like there there were debates about what the right programming language was for for security and it feels like architectures have come full circle basically. Don't I'll good note for office hours this week.

### Human Creativity in Skills

**49:30** · The question was, "As models get more and more powerful, what is the space of human creativity? Especially in these unified models that can do pretty much all tasks, visual tasks, language tasks, all these kind of things. My stance on this has been actually very, very sterile from day one. I don't think anything the model is doing is creative or not creative. Whether it's creative or not creative is for humans to judge.

**49:52** · That judgment alone is the act of creation, right? What you choose to do is an act of creation. What how I tend to spend my time is actually a very creative endeavor, right? Like you know, it because it will produce outputs that people will generate consider creative or not creative. But more importantly, in a practical physical system that is an AI system, where is human where is the role of human? It's in that fat skills area.

**50:14** · This is why our slides look good because someone who knows this really, really well went in and taught the model a million times over that like, you know, this is what good looks like to humans and this is what bad looks like to humans.

**50:29** · This is just like programmers, right?

**50:31** · Like you know, before artists never had this kind of huge leverage. They did something once and it will run a billion times, right? Programmers have always had this leverage. You write the program once and it will run again and again and again and again on everyone's computers, on everyone's phones, many, many times over and produce value. Artists produce one thing and then that's one thing.

**50:48** · That's it, right? Now other creatives in the world, not just programmers, have this leverage because of this architecture. You teach the model once and they are able to produce like, you know, huge amount of really, really great things in different contexts. This is actually an explosion of creative potential that this never has been, right? So, the skills and human creativity are much more important. Actually, it will weed out people who were mediocre and it will like elevate people who are really great to even greater heights because now their work will be rerun a trillion times over.

### Hollywood Business Model Reset

**51:19** · Okay, so Hollywood is default dead right now. Right? And that has nothing to do with AI. Uh that is really nothing to do with any of the technological changes recently.

**51:28** · Hollywood's business model has been deteriorating for the past 30 years and COVID really accelerated it and then the writers strike just was a nail in the coffin. Um at this point we are at a place where like, you know, this production that I'm talking about is the first production in LA proper in last 5 years. First production because all production has moved out of Los Angeles. Think about it. Hollywood doesn't make movies anymore. Hollywood finances them but doesn't make them.

**51:56** · Where where are they being made? In Greece, in in Canada, in in Ireland, wherever you get tax incentives you're going to make it there. So, what is the so solving this problem actually mean, right? First of all, Hollywood has to stop thinking like PE.

**52:11** · Currently, Hollywood's business model is like a private equity. Oh, Guardians of the Galaxy was a great hit. Let's make number two, number three, number four, number five, number seven, number 10, number 20, right?

**52:20** · How many Avengers are there now? I don't even know, right? And how many crossovers of Avengers and Spider-Man and I'm won't be surprised if like, you know, Tintin isn't there one day, right?

**52:30** · Like some multiverse thing. As a physicist, that's a really troubling thing for me, the multiverse universe, right?

**52:37** · That's not how it works at all.

**52:40** · But it is emblematic of a PE mindset where like, all right, we created a franchise, we created an asset. How do we rent seek that asset the most we possibly can? But you know, audience don't think like that. More and more people want to watch great things, want to go to theaters, want to actually like, you know, watch things on their phone. That is emblematic in Netflix's growth. I mean, the on Thursday you're going to see like, you know, their their this quarter results. I'm not saying buy or sell anything.

**53:06** · Uh but like, you've seen the growth of Netflix and they produce 800 productions a year compared to like, you know, the the five, 10, 20 that large studios are producing right now. That is a PE mindset. So, those 800 productions don't have $500 budget, right? They have uh uh like, you know, they're they're like 10 million, 20 million, 30 million, 50 million dollar budgets and this is how they're scaled. What does this allow?

**53:26** · This allows different kinds of and more kinds of stories to be told and that means it appeals to wider audience. So, your platform then becomes more appealing to more people.

**53:36** · Are they making again a Harry Potter?

**53:38** · Yes, I'm very happy about it, by the way, right? But this is also PE mindset that like, why are we making Harry Potter when we have so many other great books that should be made again and again and again and again, right? They should sorry, shouldn't be made again and again. So, Hollywood has been default dead for a long time. If nothing changes, this not about AI again. If nothing changes, all those jobs are actually already gone.

**53:59** · Right?

**54:02** · The the people in those industries know that. AI is a chance to actually change the business model once and for all.

**54:08** · Because you can move away from these massively expensive production methods, you can move away from these huge, huge uh you know, time and capital sinks and go back to an era where like, you know, many, many ideas can be tried and one has a shot of building people into the you know, into theaters. Ryan Gosling from Hail Mary, if you have not seen it, great movie, makes a great point. It's not the audience's job to come to the theaters to you know, keep Hollywood alive. It's Hollywood's job to make great things so the audiences want to watch it. You can't blame your customer if your product is right? I think.

**54:41** · Um what I'm going to do is that was well said and I think the PE mindset is is is going to come up over and over again where capital markets where wherever they look for predictability Yeah. um we tend to find stagnation of innovation and I think that's that's hurting a lot of people. That's a great question and that's the one that like, you know, the whole company spends all their time thinking about, honestly. So, the question is, what is the delta between where we are to getting to a place where world models, video models, whatever have you are as generally used and useful as language models are today, fair?

### Making Video Models Intelligent

**55:13** · Right? So, if there's only one word basically, intelligence. That's the delta. So, currently image models and video models that are not unified models are really, really stupid. And and I mean that in in non-derogatory way of that, right? When I say stupid, I mean in in this way like, when you work with a person who you don't consider to be intelligent, what are the signs? They forget what you said. You have to tell them the same thing again and again.

**55:38** · They don't actually understand what you said. They kind of are a facsimile of understanding, right? They say, you said something but they're like, but that's not what I said. Like, you know, yes, you you kind of interpreted my words literally but that's not what I'm saying. You have no context of what I'm saying. They are able to do small things but like, you know, when you ask of more of them then they can actually do that.

**55:58** · This is what today's video models and image models are, all of them basically, right? Um that's what we tried to solve with UniOne.

**56:05** · They need to be as intelligent as language models are. They need to have multi-turn, right? So, when you when you ask it something, afterwards it needs to be able to go back and say, all right, this is what I generated, this is what you had asked. I I have memory. Let me iterate on it and let me fix it. How annoying would ChatGPT be if you only had one turn on it, right? And then you had to repeat the thing and then another turn and repeat the thing and then another turn. That's ridiculous, right?

**56:27** · Nobody uses that. See, that was the difference between LLMs being a research project and them becoming generally useful. That was RLHF, right? That enabled chat multi-turn. So, that was number one. Number two is is how much intelligence did they actually have? So, current image models and video models are beautiful pixel generators. They have really no understanding of what the hell they're generating, the physics of it, then any introspection on it, all of these kind of things.

**56:58** · Unified models are designed to solve this kind of problem. So, when you use them in in things like education for us, right?

**57:05** · Like, you know, these slides could sorry, not this one but the ones I had could easily be used for by teachers, right? With probably a lot more density and I can show you really good examples of it producing really high density things. Videos are some of the best explainers in the world, right? Imagine a history class that is not taught as drab text but you can actually see and most importantly, you can do alternatives.

**57:27** · What if the Rubicon was not crossed, right? What if Caesar was not murdered?

**57:32** · What if like, you know, these things didn't happen? What if Archduke Ferdinand was not shot in 1914, right?

**57:36** · Like, you know, would there still be World War I? I posit yes and like, you know, we can go into that. But what if you see that flow out, you had this level of like, you know, temporal understanding and coherency and these kind of things. Language models are getting there. Image and video models don't have that.

**57:51** · That's what we need to solve. So, that is the distance between them being just tools that can produce almost stock footage to things that can do end-to-end work. Awesome. Thank you, Ahmed, for being here. Thanks for having me.

### Closing Thanks

**58:04** · \[applause\]