---
title: "CS153 '26: Frontier Systems - Andreas Blattmann, Black Forest Labs"
source: "https://www.youtube.com/watch?v=TNxXs20yhMQ"
author:
  - "[[CS153: Frontier Systems]]"
published: 2026-04-11
created: 2026-04-18
description: "CS 153: Visual Intelligence Frontiers with Andreas Blattmann (Black Forest Labs, Stable Diffusion)In this CS 153 “Frontier Systems” session, Anjney Midha welcomes Andreas Blattmann, co-founder of Bl"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=TNxXs20yhMQ)

CS 153: Visual Intelligence Frontiers with Andreas Blattmann (Black Forest Labs, Stable Diffusion)  
  
In this CS 153 “Frontier Systems” session, Anjney Midha welcomes Andreas Blattmann, co-founder of Black Forest Labs and co-creator of Stable Diffusion, for a discussion on the visual intelligence frontier and how frontier AI “factories” scale. Blattmann recounts his path from mechanical engineering to a Heidelberg PhD lab, developing latent diffusion to train image generators efficiently and enabling Stable Diffusion’s 2022 release. They contrast earlier unimodal content-creation models with today’s push toward unified multimodal systems spanning images, video, and audio, plus action prediction for computer use and robotics, emphasizing observation and interaction loops. Using Flux as a case study, they cover pre-training, mid-training, post-training, distillation for speed, customer feedback driving image editing and character consistency, and why open weights enable customization. They also discuss Self Flow for multimodal alignment, safety guardrails, EU compliance, data labeling strategies, diffusion vs autoregressive tradeoffs, and skepticism about explicit 3D representations.  
  
00:00 Playlist And Welcome  
00:56 Frontier AI Scaling Loops  
04:29 Meet Andreas Blattmann  
05:46 Early Vision Research  
07:19 Latent Diffusion Breakthrough  
08:57 Stable Diffusion Inflection  
11:32 Natural Vs Text Signals  
15:20 From Unimodal To Multimodal  
19:30 Starting Black Forest Labs  
21:07 Flux Pipeline And Feedback  
24:15 Character Consistency Context  
27:02 Team Execution And Meta Deal  
28:51 Persistence Wins Frontiers  
30:40 Multimodal Models Next Wave  
32:06 Training Stack Self Flow  
35:26 Verification And Open Models  
41:53 Self Flow Intuition  
43:52 Safety Guardrails And Partners  
48:35 Labeling Data And Denoising  
53:39 Distillation And Flux Business  
57:09 Spatial Intelligence 3D Debate  
01:01:00 Closing Thanks And Wrap

## Transcript

### Playlist And Welcome

**0:00** · Quick show of hands, how many people recognize a song that was playing?

**0:05** · The Does the Germans in the house, aren't you?

**0:07** · \[laughter\] I wouldn't have imagined.

**0:08** · Yeah, you're from Germany? Yeah. One of my favorite songs called Bella Napoli. It has been added to the CS153 Spotify playlist. For those of you who aren't on it, for anybody who has music requests for CS153 this quarter, also known as AI Coachella. We've got an \[snorts\] open playlist. Please feel free to add songs there. That one was a request from me in honor of our speaker today.

**0:33** · Who I'm very lucky to call a close friend and is the co-founder of Black Forest Labs, Andreas Blattmann. Thank you for joining us, Andy. Thanks, Ans. Thanks, everyone. Thanks for having me.

**0:44** · Andy's joining us from Germany. A little town called Freiburg, which I think a lot of you will be hearing about more and more as it becomes a hub for frontier research in Europe. If you remember in our first lecture, right, we talked about the anatomy of frontier AI progress. And we talked about three or four important touchpoints in this class you're going to be hearing about over and over again.

### Frontier AI Scaling Loops

**1:10** · One is that there's a a transition happening from the old systems, the old infra stack to a new one. Right? And you got to be open to understanding what those rewrites are looking like and and our speakers are going to tell you which parts of the stack they're helping to rewrite. We talked about the basic AI scaling recipe, right? You've got two sort of loops that are important to run.

**1:32** · Once you do, you get some compute, you get some data, you build a model, and then you do inference, right? That gives you revenue to buy more compute and then context feedback. We've talked about the bottlenecks right? On that on getting those loops scaling.

**1:48** · Which is context, compute, capital, and culture. We talked about context and and compute. We'll talk a little bit about all four today. And then the last was, well, for your projects, which is the the part I'm sure many of you are anxious about is how do you get one of those scaling flywheels going?

**2:04** · Right? And we talked about there being sort of three steps in the journey. There's an incubation phase where you kind of figure out which specific part of the frontier you want to attack with a state-of-the-art system. Right? Then you land with a soda release, a state-of-the-art release, and then that allows you to expand to more and more capabilities on the frontier that you care about.

**2:25** · And if you remember, we did sort of a a field trip into one of the frontier factories, right? In in our first lecture, which was Anthropic. We talked about code as one domain. And today, we have a chance to do a field trip into another frontier AI factory in Germany called Black Forest Labs. And we've got here one of the factory owners, Andy Blattmann, who's a co-founder of Black Forest Labs, also co-creator of Stable Diffusion. How many people here have heard of Stable Diffusion?

**2:54** · All of you. Perfect. Great. You've done some homework. And so, today we're going to talk about the frontier Here last on Tuesday, we talked about the the audio and the speech frontier.

**3:06** · Right? What is audio intelligence like?

**3:08** · What was it? Where is it going with Maddy from 11 Labs? And today we have Andy talking to us about the frontier of visual intelligence, which I think is one actually one of the most exciting frontier, if not the most critical frontier to unlock more progress and if we really want to get these models to work in mission-critical context in the real world.

**3:27** · And so, we're going to spend some time talking about the anatomy of visual intelligence as as Andy sees it as one of the pioneers of the field. And then we're going to talk go back in time a little bit and zoom into how we bootstrap the Flux flywheel together a couple years ago. Flux is the name of the flagship model family from Black Forest Labs. And then we're going to spend some time on the fun part, which is future frontiers. Where are things like now that that where where the unsolved problems where are we right now where you guys can step in and start co-creating this journey in the space.

**3:58** · So, this was the frontier factory, right? We talked about this is sort of the basic template. Again, to be clear, this is a directional heuristic. Every team is different, every research project is different, but to kind of give you a grounding sense of repeating patterns about how some of the best teams are manufacturing intelligence repeatedly. Remember this was the pipeline. We had pre-training, mid-training, post-training with agents in the real world. There's a version of this that that Andy's going to walk us through, but before we jump into that, why don't we just spend some time on on you, Andy? Who are you and how did you get here? Yeah, cool. Thank you, Ans.

### Meet Andreas Blattmann

**4:32** · Thanks again for having me, everyone.

**4:34** · Yeah, I'm Andy.

**4:37** · Started looking into AI, I think in 2019. I was actually originally studying mechanical engineering. Classic German education, I think. You go to school and then you figure out you're kind of somewhat technical and what are you doing if you don't know exactly what what to do.

**4:54** · Studying mechanical engineering in Germany, right? Um And then at Yeah, through through a couple of I think coincidences, I got into computer science and to coding into already robotics back in the days. We talked more about robotics uh later. Um And applied at a PhD in Heidelberg where I met my two co-founders, Robin and Patrick. And that was a really like small lab. Everyone back in the day was doing representation learning with visual models or like for for the visual domain and computer vision in itself that That was 2019 was kind of a a niche topic in this niche topic back then of AI. It was really like people saw the potential already, but but no no one no one had an idea of how how that would explode then later, right? So, it was really kind of a yeah, niche topic we worked on, but we soon had a very good intuition about like how to train models to generate pixels, mainly images back then.

### Early Vision Research

**5:54** · Um and we're competing on a research level as a very small lab with players that were much larger than us. And finally that already back in the day was Google and OpenAI, their research teams, and it was not about building frontier systems. Was foundation models. Yeah, or or even before that, who wrote actually the nicest paper to show that something was was happening.

**6:17** · So, back in the days, it was like This was pre uh That That was pre-Stable Diffusion. That Right. That was That was 20 It was 19.

**6:26** · ones who remember, it's StyleGAN what's StyleGAN, yeah. The images were most often generated with GANs because they had a kind of a good inductive biases for for for kind of this data domain.

**6:38** · And it was generating a 256 by 256 pixels image was a challenge. Like not every algorithm could do that and yeah, it was just a very different world. So, we competed with labs that were much larger than us and we had even back in the day way way less compute.

**6:58** · So, we had to come up with kind of more efficient algorithms to solve that problem because images and not speaking of videos are so much higher dimensional than other representations, say text or something. Text is much lower dimensional.

**7:13** · And and to anchor folks on time, you were still This is when you were at the University of Heidelberg.

**7:17** · Exactly.

**7:17** · Right. Um So, yeah, and then we we spent like 2 years investigating how can we actually find representations for natural data, for images, for video, mainly that are perceptually equivalent to the pixel space or to what matters to us humans in the pixel space, \[snorts\] but much lower dimensional and much more efficient because we didn't have the computer to train a kind of generative model on the pixel space. And it's also super wasteful. And that was what gave rise to a series of papers on latent generative modeling. So, you actually train a kind of a compression model.

### Latent Diffusion Breakthrough

**7:59** · Um Similar to a learned JPEG coder, you could imagine it, to find that perceptually equivalent representation to the pixel space. And you train the generative model there. And that um helped us saving tons of compute, training our models much more efficiently, and with orders of magnitude less compute than our competitors, put out like better like models that were on par or even better than those competitors. And that was what That algorithm, latent diffusion, also gave rise to Stable Diffusion then. So, you proposed the algorithm, saw the potential, set out to search some compute, luckily find that in the open source community, and train Stable Diffusion that was then released in 2022. And pretty much surprised us as well like with all the hype it got.

**8:48** · And I actually was was fun. It was here in the Bay Area it was hyped much more than in Germany. In Germany, still today, not a lot of people know about that model, funnily. Yeah, it There was There was a moment I remember DALL-E 2 was in preview, I think. And and then you guys put out Stable Diffusion. And I remember on Reddit, there was somebody had sketched out uh they'd taken one of their kids' like uh drawings. It was like a crayon drawing and had turned it had run it through the image-to-image transfer on SD. Uh I think it was SD1.

### Stable Diffusion Inflection

**9:22** · And it out had come this beautiful illustration. And I remember taking a screenshot of that cuz I was just blown away. And I tweeted it. And I think it was like a Monday morning. We went into our exec meeting at Discord and then I came out for lunch and the tweet had like three or four thousand likes.

**9:40** · And it was it like a For me, it was a moment where I realized that the technology of generative modeling at that point had crossed an inflection point where it suddenly became legible to people outside the machine learning community because it was so visual. Yeah. Right? I I think it it might be worth spending a couple more minutes here to just take people back in time because at this moment in time in the ML community I would say that there was a bit of a dogma that language modeling was the be all and end all of intelligence. You know, the general consensus at the time was that language is the interface to reasoning to to for intelligence. Which are the way humans reason about intelligence, the way we think is through language.

**10:23** · And I would say that's a philosophical belief that has come and gone in its sort of the strength of its religious zeal. But for those who are in the computer vision community and I I count myself as one of those because my last company as we've talked about was Ubiquity 6. It was a 3D mapping and computer vision company. We were working on 3D reconstruction.

**10:43** · It it was clear that language is was extraordinarily valuable. Don't get me wrong at at at reasoning about certain tasks and fields. But for those of us who are in the computer vision community, it felt incomplete because language is is just one way we communicate, one way we reason about the world. For those of you who are visual thinkers or visual intelligence, who believe in multiple intelligences, right? You just learn better when you see visual representations of things. And so it was quite cool to see stable diffusion coming out and make progress of a different kind legible to both the machine learning community as well as the the broader developer community, the broader consumer community. And and that's when I think we we reached you know, we started working together cuz we were trying to get some of these stable diffusion like capabilities onto Discord. But can you talk about it? You know, you said two things that I think are quite helpful to overlay for the students here, which is the difference between natural and unnatural representations. Could could you speak about that for a sec?

### Natural Vs Text Signals

**11:42** · If we think about ourselves, if everyone you look at me currently, hopefully, and and the medium through which you are perceiving this is clearly video and audio, right? You hear what I'm saying and you're seeing me gesturing here or or talking to so these are these are what we what I call natural representations. If we think about the source of those representations, eventually it's the sun or here we have some some lights that try to resemble what the sun sun does, but it's electromagnetic waves of a source that we humans cannot control.

**12:23** · We can shape obviously the the or we we we can we can control the shape of this world and we can build buildings, but the the electromagnetic spectrum that falls onto the earth we cannot control.

**12:34** · Same for sound. Like natural signals like hearing a river flow or something, that's just some might some some might call it noise or something. That's just natural and it's there. Whereas text is inherently human made. You see this in so many different occasions. If you just measure the the information per sign that text transports, it's so much higher than the information per sign per pixel in an image. And why is that? Because it's human made. It was evolutionarily very important for us to communicate efficiently.

**13:08** · And there is I think that that's also at the heart of why we need to compress images and videos before we train a generative model on them because there's so much redundancy in in it.

**13:18** · In text you don't have this redundancy because it's human made, right?

**13:21** · Throughout evolution we reduced the redundancy and um and made it efficient. For learning, however, it's super important at least in how I see it and how we see it at Stability Labs to consider two things. First, if you think about yourself as babies, how you learn, it's first observing things hearing and seeing and then interacting with things in the physical world, right? This is pretty much the first I would say three, four, five years. I don't know when I learned reading but it's I think that maybe with five or something.

**13:58** · And just the level of intelligence a three-year-old has compared to the level of intelligence a a language model has is very different, right?

**14:06** · And I think that's what what why we care so much about natural representations like audio and video because we we are like absolutely convinced that this will be the fundament of all the kind of higher intelligence that these systems will eventually have. And starting from language and trying to to stack up a bit bit of additional kind of representations on top of that is in my kind of opinion the the the wrong way.

**14:35** · You should start with from first principles, how we humans do it, and that's clearly learning on natural representations by first observing and second, we'll talk about that later, interacting.

**14:45** · These are just from how we think about it, the main pillars of learning and also the main pillars of what we define as visual intelligence actually. So I I think um So this is pretty important because two years ago, three years ago, I would say the consensus was that the way to do generative modeling was roughly this, right? Where you had this these foundation models that were unimodal. They were text to image, text to video. Looking at Stability Diffusion as a Stability Diffusion was a text to image model, exactly. Unimodal based on images. Yeah, but could you could you just talk about what this the what the state of the art was then versus now?

### From Unimodal To Multimodal

**15:26** · So yeah, Stability Diffusion I think it's a perfect example of that. It was a text to image model. You could you could do super nice kind of artistic things that have not been possible before, but it was clearly made for content creation, right? It was a a unimodal model made for the purpose of content creation. You could you could make artistic style transfer. You could you could do you could train a Laura and and do maybe some some kind of character consistent marketing transformation or like yeah, character consistency into the get get character consistency into the model and then use it for marketing or something. But that's all content creation. We currently see that visual models starting to become way more than that.

**16:06** · We don't train a single unimodal model anymore to just like fulfill the purpose of content creation. We're training a unified a uni a multimodal model for natural representations or natural data that then can give rise to so much more.

**16:23** · It's about physical AI. It's about robotics, computer use. We can do these models. We had a couple of demos already like or there were recently a couple of demos that were super impressive. We can do world modeling and simulation and still content creation.

**16:36** · But combining different natural representations and only training on one is the key ingredient because it will give the model a much more natural understanding. As one example, if I if I just see two rigid bodies colliding, I will always have a sound attached to it, right?

**16:58** · There's a correlation between that sound happening and a certain action in physical in the physical world happening and being able to observe this correlation for a model is super important because it will help it that model understand much better what's actually going on. Whereas if I only train at at one single modality, it's much harder to to kind of understand what's going on or just interacting with this bottle.

**17:23** · I think it's super hard for a model to understand what's actually going on if it's not if it doesn't hear that sound. How would that be different for that kind of transparent body compared to to someone um putting their hand through water or something, which is also transparent, right? So um these correlations between different natural data representations are super important for a model to learn kind of at a higher representation of intelligence as well.

**17:52** · Now this this idea you know, for those in the machine learning community is not new. I mean, for a while there was an there was a sense that the progression of technology would be we'd have sort of state-of-the-art systems that were capable at individual modalities and then at some point to make them smarter, we'd have to give them the ability to reason across different domains.

**18:15** · Transfer learning, so to speak, where you can reason about the physics of a of of of this bottle hitting that and and the the sound, the audio emerging. Um but you can't start with everything on day one.

**18:28** · And so could you just take let's let's talk about how we bootstrapped the flywheel. Cuz now today, fast forward two years ago, you know, four years after Stability Diffusion came out you know, Flux is now uh used by millions of people around the world. You guys have hundreds of millions in revenue, blah blah blah.

**18:45** · But for the purpose of the students, I think it's helpful to zoom back in time and say, "Okay, you guys had this clear thesis for eventually models will be good enough at reasoning about all kinds of all of visual intelligence. But you have to start somewhere. Yes. Especially when you have less resources than than the largest companies in the world.

**19:04** · You're a smaller team. You have less data. So can we spend a little bit of time talking about how did you concretize where to start? Yeah. And then how did you initialize that kind of momentum flywheel we talked about from at day one? Yeah. Absolutely. Yeah, I think uh that's one of the most important things when starting a company. Focus matters.

**19:25** · Well, or any research project, right? At at the time actually SD was not even a company. Yeah, yeah, absolutely, absolutely. But let I think I want to as an example, I want to I want to take how we started the company because there we we had this kind of huge experience in image generation unimodal image generation. We've done Stability Diffusion then we worked for Stability AI, put out a couple of more models on that domain. And we pretty much had the recipe to kind of train a frontier model for that domain. Right. So, when we started the the the company, we clearly Oh, we looked at the field and we said, "There's clearly a need for a next generation of image models because so far the models cannot say produce hands that are that are actually having five fingers, right? That that was back in the day, I think. So, we attacked that specific field and said, "Okay, we want to be building a model for for specifically for image that is just 10x better than everything else." And that's what that then we sat down together 3 months. We had all the recipes. We knew what to do.

### Starting Black Forest Labs

**20:28** · We scaled it and what came out of that was Flux 1 that initially had kind of product market fit, you could say. We even before we took our API public, we had a couple of very large customers that that kind of helped us close the feedback loop. Now, talking about the feedback loop because obviously once you can build a technology, but setting that technology out to solve real-world problems will give you the very important kind of data to actually learn from first, what is an important problem to work on, and also how to make the model better for that specific problem, right?

**21:02** · By that, you you have the first kind of uh loop closure for the flight thing.

### Flux Pipeline And Feedback

**21:07** · I mean, let's let's break that um that release down. Flux 1, I think this is the kind of pipeline we talked about, right? So, could you just go through sort of the BFL version of this and explain what's going on at each step within the the company of the BFL sort of pipeline. Yeah. So, I mean, this this is particularly for um for how we would define visual intelligence now, but I think I can also for Flux 1, it was clearly we trained only on unimodal like text text and image, right? Only on those representations. So, the pre-training was just a large corpus of text and image. For the mid-training, we added um high resolution um and like a couple of more capabilities into and then we had this kind of post-training phase where we exposed the model to first, we did a kind of offline post-training before you release an initial model, do some uh distillation to make the model more efficient. You you align it with uh your intuition about what customers would care about. Right. And then you expose it to kind of the real world, but then you get this feedback. And for for Flux 1, a very interesting um observation we made was, \[snorts\] "Oh, wow, so many people are using our text to image models to actually train a Laura and then do character consistency." Like, they they want they they want to they want to have the ability to control the model with more than only text because text is obviously nice and easy and low-key.

**22:40** · Everyone understands it. Everyone can use it, but it's also very ambiguous. If you like And and again, there's there's a kind of disconnect between this kind of artificial representation text and and the natural representation image. So, if I say you an image of a bluebird, there are infinitely many images that that give rise to this kind of um description, right? The bird could be sitting on a branch. The bird could be flying and so on and so forth. And it's actually super hard to apply precise control to um image to to the image you want to be generating.

**23:14** · So, that was that was I think that's a perfect example of the benefit of the loop closure because we what we learned was, "Okay, people want to actually do image editing."

**23:23** · Right.

**23:25** · So, what did we do? We did a post-train on partially on based on the data we got, partially based on new stuff to create an image editing model, which was Flux 1 Context that came out I think pretty exactly a year a bit bit bit less than a year ago um and that was the first image editing model where you could actually in a scalable and fast way get character consistency. So, I now I could take a an image of you, Arash, and say uh and and maybe of me and combine us two sitting together on a lecture hall, but um in a cafe having having a chat. And that's that just has massive potential for everything content creation, right? Marketing needs it to to like get get different product different products into different contexts and it just like supercharged or currently supercharging like a lot of different applications around the creative world. Yeah, so this may not be obvious, but I want to pause here because I cuz you know, Andy did this quite naturally, but for those of you who who were trying out AI image models, let's say 18 months ago, how many of you tried giving it a photo of yourself and then saying, you know, "Give this person a hat." And that came out actually looking like you.

### Character Consistency Context

**24:38** · Yeah, no hands are going up. One one hand is going up. It was a pretty basic capability gap. These image models just didn't have character consistency. You right? You just give it like a photo of yourself and say, you know, "Give him a mustache or whatever." And out would come somebody looking not like me.

**24:56** · And um that you know, that that for many people in the space, that was just a I actually can't I if I had a dollar for every time uh people would would say, you know, that that's just that problem will not get solved. Like, these models are so dumb. Like okay, AI is so dumb. It will never Like it it'll never be able to surpass that capability threshold.

**25:23** · Um I I would just sit there and these are very smart people, including by the way, some of the speakers in this class who over the years have realized they had to update their priors about the the speed at which you can update these capabilities, but it was common consensus at the time that these image models are just not going to get that good. You know, AI is dumb.

**25:41** · It can't reason about the the way that humans do humans do about create you know, faces and specific characters. And I was just in I was shocking to me how very smart people would very confidently proclaim in the industry that I was just not going to get solved.

**25:55** · Meanwhile, you know, here we were in Freiburg um looking at the data where there were people using Flux 1, which was not very good at character consistency, but that that context feedback of seeing how the prompts people were trying to use with the model and the the feedback of them saying, "Actually, that that was not good. Can you please try, you know, doing this better?"

**26:19** · The the the multi-step sort of reasoning chain that we were getting from seeing people out in the wild using it. It was an open-weight model, which we'll talk about in a second, which is quite unique.

**26:28** · Give us a very clear path actually to improving the capabilities. And then actually it was you know, one of our team members, Dustin, uh in in SF, who figured out that, you know, we should just make an update to this that's that's called Context with a K cuz that's the German way to pronounce it. Um that is specifically an editing model.

**26:47** · And I think between the insight that insight was that an offsite in Spain Where where were we? We were in I think it was in um Italy.

**26:54** · In Italy. We were in Italy. You know, uh I I I think chat DALL-E you know, chat GPT-1 image had just come out. We were literally all together. And there was a sense, you know, this is an important thing as it as it as a new team or as a first-time you know, researcher, it can be quite daunting when some lab that has way more resources than you launches something that's that looks way better.

### Team Execution And Meta Deal

**27:16** · And your first intuition is to go, "Oh my god, we're But you got to remember that the mark of a good leader is to not panic, keep calm, look at the data, assess the landscape and then come up with a plan step by step. And often you'll notice that if you're good at at mapping the domain you're you want to be an expert in, somewhere in your intuition, you have a gut feeling that's telling you there's actually some unsolved problems still left.

**27:45** · And you know, Dustin did a great job at that. The team rallied. I think within 24 hours we had redone the the staffing on the team and I think what, 60 days later, Context came out. Yeah. Right?

**27:55** · And revenue from Context doubled I think within 6 weeks. In fact, I think soon after is when um this part is public now that Meta announced a partnership with BFL and said they were going to be using Black Forest models, this tiny team out of Germany. I think the team was you guys were like 25 people? Yeah. To drive image editing for all 2 billion Facebook and Meta and so on users.

**28:24** · I mean, this is not normal.

**28:27** · Right? And and observing I was I was lucky enough by this time, you know, I I I had been an investor with you guys for about a year and a half. And so, we would go to these offsites together and I I had a chance to sort of see how in real time, you know, this this isn't the system's problem often is not just a technical problem cuz actually all the data was available to us. The context was available to us. It's the human system of of organizing the team and the research sort of culture, right? In a way that is not you're not panicking, but you're still assessing kind of the the frontier methodically and being very honest with yourself about how fast capabilities are moving and where you can uniquely sort of contribute to that system is is the key to keeping that loop going over and over and over again.

### Persistence Wins Frontiers

**29:17** · And I I think that's why, you know, BFL is where they are today. They went from zero to several hundred million revenue. It's the company is now worth more than 3 billion. But it can be easy to forget that that wasn't always the case. And there are these moments in your journey, especially in machine learning where things change so fast, that it's very tempting to just give up.

**29:35** · You know, and say, "You know what?

**29:37** · This problem is solved." I mean, it really it is remarkable to me how many teams in image generation just don't no longer exist because they just gave up.

**29:47** · And instead BFL just stayed persistent and today is one of the only leaders left. I would say an independent leader that's pushing the visual frontier. In fact, I I hope some of the projects here push the frontier, too. But, um that's that's I think a learning for me has been it's actually quite straightforward sometimes technically if you have the right leadership to keep advancing the frontier.

**30:08** · But, sort of adrift in your mission, a lack of conviction that, you know, it's worth attacking the problem you you are committed to over and over again in the face of crazy challenges is often just the difference between you know, success and failure. How many people that know that have seen that meme of the guy tunneling uh and giving up right before Yeah, you guys know that meme. We'll we'll we'll put it in the class reading list.

**30:30** · I'm dating myself with with boomer memes here. But, I can't tell you how many times it's felt like that at BFL and then one release later, right? The world has changed.

### Multimodal Models Next Wave

**30:40** · And that that's actually uh I think also a good segue into what what's next. Like now we're seeing this this kind of these models being applied everywhere for content creation. But, again, then you need to think more or like like look forward and and and and think, okay, what's next?

**30:56** · And clearly we now see this insane potential of especially these combined multimodal video audio image models for the capabilities we just talked about, right? Physical AI, um computer use, right?

**31:09** · World modeling and simulation, and still also content creation. And you can you can actually build a single model that is capable of all doing all of that together and you will actually get compounding effects based on this example with with the with the correlation of noise and the action in the physical space. Um you can also make models that are much smarter for generating non regular images or video footage for say again advertising or something.

**31:38** · Well, could could we could you talk a little bit about that? Let's So, let's zoom forward to Um I I actually Could could you talk about you know, how do you take an image a content creation pipeline and add to it what you just talked about, the ability to actually interact with the physical world and learn from the physical world.

**31:58** · You know, what what what does action prediction mean? How is that done? And then maybe you can talk about self flow a little bit since we're going to be assigning that as reading. Yeah, yeah, yeah, absolutely. Um so, yeah, I think first you you need to go from We already talked about this. Unimodal to multimodal.

### Training Stack Self Flow

**32:13** · Right.

**32:14** · And then you get this kind of Yeah, this is this one. And if if you if you go back to the slide here, I think this this is a good one. So, there's a large pre-training on again natural representations. These are the representations we humans used to to learn from in our first years of of of our lives.

**32:31** · Um And there you you Yeah, you just combine everything together and you have these um this combined pre-training that gives you a very very general model.

**32:41** · So, pre-training for us means images, video, audio combining with a architecture or with an algorithm that we've also published um beginning of March, self flow, which allows the model to actually get compounding effects by observing Again, I don't make this this example again. You saw it already a couple of times. But, by observing correlations that that exist between those modalities. That gives you a very very general representation. What we add next in mid-training is additional context. We do new tasks such as conditioning on I can condition a model on an an input image and an audio track and I say I I want to I want to hear I'm saying XYZ in that voice.

**33:27** · Model does this. This is additional context, but importantly for extending the scope beyond pure um content creation you also want to condition the model on actions and you want to have the model predict actions.

**33:43** · And then we can arrive at models like this, computer use models for instance that that are conditioned on a video or an image and they predict the next move based on keystrokes or something to achieve a certain task. Say I want to be opening a new browser browser tab or something, right? So, this is crucial to get to expand the scope um of this kind of very general representation that we get from pre-training, but we actually want to be using it for We want to make use of this kind of general generality of the representation. So, we add additional context and importantly actions.

**34:19** · Um And what we then do This is very important. Or yeah, maybe maybe to zoom out a bit more and come back to the human learning example. Pre-training, mid-training, this is all still observation. All the algorithms that we're training like foundational models with in the early training stages currently are models observing examples. We We're calculating a loss from that. We back propagate that through the network. But, there's no interaction whatsoever.

**34:47** · Right.

**34:48** · So, how do we actually get the model to interact really in the physical world? That's super important for kind of learning higher forms of intelligence as we are all convinced of.

**35:01** · So, what do we do?

**35:03** · We use this model that can actually given a video predict an action to do something and hook it up in the real world on a say on a robot for instance, right?

**35:13** · And then that allows us to inter like allows this model to through a robot interact with the physical world, create data for that again.

**35:23** · And we can pipe that back into the model training and that's when we close this feedback loop uh So, our post-training looks or means interacting with a physical world. Right. So, this is important. If you guys remember we talked about physical ver uh ver verification right? As a key predictor where frontier progress can continue. Wherever you have contacts that can be and performance that can be verified progress can quite reliably be made there.

### Verification And Open Models

**35:52** · Right. So, in software engineering that's verifiable cuz you can write unit tests.

**35:57** · In image generation not very verifiable, right? Because one uh beyond beyond the basic tasks that that um Andy talked about, which is accuracy, right?

**36:08** · Six five fingers instead of six, character consistency, which is more a preference.

**36:14** · Uh But, in that example, how would you measure that at scale um without having a human telling you No, no, exactly. This thing that actually five five fingers and not Well, I think you should talk about how how that verification works. And then what is the you know, in the new world where you have to verify physical tasks in robotics, what does that look like?

**36:32** · Yeah, yeah. So, I I think in it's fun because if you if you Oh, yeah. So, verification for for for images is a super is super tricky, especially when it comes to kind of or for videos and it comes to physical things.

**36:44** · But, once you hook that up in the real world there are just certain things that go that that you can do and certain things that you can't do because a robot arm can cannot just do certain certain joints. So, it's like exposing it to the physical world naturally um applies the boundary conditions that we would expect. So, that that's a very important step and by that you you have the perfect uh kind of environment Right. to to directly inherently model these kind of restrictions.

**37:16** · Whereas in the case of aesthetics or visual preference, how did you guys verify that? How How did you get a model to be better at when just doing content creation? Yeah. Uh Well, that that that that involves like massive massive massive amount of human judgment and then feedbacking that signal through the model again. Right.

**37:33** · But, that's like of often very tedious and also often very dependent on who you're asking. It's like a if I ask you you've looked at so many images by now. You're I would consider you an expert. Um because we always saw that our models, but you're also enjoying it, I guess. Depends on how much spritz you have had.

**37:50** · \[laughter\] Yeah, no, but but but like showing a an image to someone who has no idea of like of of of say image generation versus to myself and I've looked at so many images gives you a very different signal. I would rate something as good or bad that looks very different from what a kind of another person would do, right? It depends on the crowd who you're asking.

**38:15** · So, it's you can ask people. That is very very ambiguous in a way. So, this is a key insight, I would say, because anytime the answer to the eval question of how do you verify is it depends on the audience or it depends on the person consuming the system it should trigger a light bulb.

**38:36** · At least it does for me that the value that you get from the system varies a lot by how much the model can be customized for a particular audience. And that is where open source comes in.

**38:52** · Because the beauty of open models is if you give away the weights and they're good general weights right?

**38:58** · Then you can tell Meta, hey you're welcome to customize the preferences of what of this model as you see fit for your users. And you can tell another government that has different cultural preferences and biases that wants to, you know, be able to deploy content creation for let's say internal teams in a completely different culture and say you can have the control over that last mile.

**39:22** · And I think that's turned out to be a very critical part of the open ecosystem where I often get asked, "And you know, why did BFL open their models up? And just give away all this research for free. Is it just that they want to save the world?" Well, you know, part of it is cultural. As you can tell, Andy you know, Andy was a came from the academic community, enjoyed and and benefited from open publishing, but at the end of the day you got to turn these research products into businesses, right?

**39:48** · And it turns out there's extraordinary value in producing state-of-the-art systems that are then open and customizable when the consumer of the system, the person benefiting from the system has a very different preferences from other people who might be consuming the system. Does that make sense?

**40:07** · Have I lost you guys?

**40:09** · Can I get some nodding if that's making sense? Yes. Okay. This will be a theme consistently, okay?

**40:14** · In the class which is anywhere you have consumers of a system or customers or the people benefiting from the system wanting more and more personalization customization of the system for themselves, that's where open models become extraordinarily valuable.

**40:30** · And you can actually build it turns out a very large business very quickly doing that. So, I actually think there's a false trade-off in the space a little bit about open versus closed. These are both just techniques or tactics for how to deliver value. They they sometimes they get politicized philosophically, but actually just from a very base basic first principles commercial perspective, you know, open makes a lot of sense in some domains where where the aesthetics, the preferences and so on are quite there's a long tail of this the distribution is quite wide and and and um and heterogeneous versus domains where, you know, preferences are actually quite narrow. If there if there's a pretty narrow distribution, then I think, you know, closed models and so on are quite valuable in that case.

**41:07** · I think there's one last piece that we haven't covered, which is the state-of-the-art today. Because as Andy said now the state of the art, right, is about how do you get these systems to reason in a unified fashion across text, image, video and so on in a way that's that has cross So, transfer learning across these different modalities. It's very hard problem. Very very hard problem.

**41:30** · But as is the case with BFL consistently the team has you know, makes these sort of research advancements and then gives away the technology. And so this was actually one example I think what 2 months ago?

**41:40** · No, a month ago. Month ago is self-flow, which has turned out to be a technique now that suddenly magically all my friends at all the labs are calling and saying, "Ansh, have you heard of self-flow?" I was like, "Yes, we have heard of self-flow. You It's on archive."

**41:52** · Cuz Andy and team published it. So, maybe you can talk a little bit about what the intuition behind self-flow is as a mechanism to to solve the multimodal reasoning problem.

### Self Flow Intuition

**42:00** · Um so when training visual generative models it's always been historically um a bit tricky to get representations into the model where they don't only generate pixels in a way Right. but also understand what's actually semantically going on. And there has been a body of work on um so-called all that that worked on aligning representations of generative models with um representation learning representations um that to to to to to get them a bit more understanding of what's actually going on and not only make them stupid pixel generators that just learn to kind of um resemble what what looks consistent in the image. Um that's has been in the last 2 years always been focused on single modality.

**42:49** · So, what people did, they used a pre-trained representation learning model like maybe some of you might know the Dino model for images, um pre-trained model and they tried to just make the representations that the transformer that is a backbone for image generation has internally aligned with the representation that this representation uh learning model um had.

**43:12** · And that is clearly restricted once you want to go multimodal. But as you saw in the last slides, going multimodal is super important to learn kind of higher form of intelligence. It's We want to be multi We want to have models learning multimodal representations because that's frankly what we humans uh have, right? So, we it's cru- crucially needed. So, how can we actually combine learning have having these so-called alignment losses with multimodal representations and the self-flow paper solves exactly that problem in a very natural way.

**43:43** · Really recommended read for everyone. It's it's Assigned reading. su- super super nice.

**43:47** · Yes. Okay, good.

**43:49** · Shall we transition to questions? Okay.

### Safety Guardrails And Partners

**43:52** · Yeah, so the question was um when when when we close the feedback loop, how do we ensure to to um compress this? How do we make sure that actually uh personal data is respected um and um that no no harm is is generated uh based on those models. So, first um we have a lot of content filters on on our API obviously because we our our belief is that these models are powerful tools for humans to to create super super nice and creative outputs and also much more than only content creation as we just saw.

**44:21** · Um and we don't want to have them misused.

**44:25** · So, we we add a lot of content filters that actually um make sure no harm is is generated. Um on the personal uh information, obviously being being based in the uh European Union, we comply with the EU AI Act and there's actually a uh kind of law that that um we also follow that you based on a request. So, if if you put in a um a an image of yourself on our API and you say, "Hey, look, I I I don't want to you you to you to um to store this kind of data, we have to delete it." So, we have systems in place to actually make sure this this basically happens. So, the question is like we had a lot of partners um large companies that we work with like XAI, Meta um backed by Nvidia. And the the question was how do we evaluate um with whom we work and with whom not. Um I think maybe as a general statement, we're working on building visual intelligence infrastructure for um everyone basically. So, from an infrastructure perspective, you really want to make sure you put guardrails around your models um that people cannot misuse those, but then infrastructure is there for basically everyone, right? And and that that that's that's the the standpoint we're also taking.

**45:45** · We care a lot about the safety of the models. That's important. And we do everything we can to prevent misuse, but then um I think it's also us provide putting out the technology there and providing it to to to everyone. And the the it's always hard to take a certain standpoint on like who you're working with, who you're not working with because it you get it gets very tricky to justify in the end Let me try and translate what Andy's saying.

**46:14** · The company basically applies its guardrails to everybody. So, no matter who you are and how big you are and how much money you've got, if you want us to remove our guardrails, sorry. Those guardrails apply to everybody equally. Because being a standard and being infrastructure that people can rely on means you don't treat different people differently.

**46:34** · \[snorts\] And everyone can rely that they're not getting, you know, just because they might have more money or they might be more politically influential, whatever it might be, that they can get the same quality of service as everybody else. And so, that's the position BFL's taken as an infrastructure provider is that doesn't matter who you are. Now, sometimes you have custom needs because you're of the scale that are technical. Hey, we need it to be deployed in this way.

**46:55** · We need some latency requirements that are more technical. But when it comes to guardrails, that applies to everybody. And so, when some partners say we want you to remove those guardrails, say, "Sorry. You can go elsewhere." And that has resulted in sometimes the company losing meaningful amounts of revenue.

**47:10** · And that's okay.

**47:12** · Because in the long term as we talked about in the first lecture, the way you get infrastructure to move stably is you have trusted standards and trusted institutions to enforce them. And sometimes you got to enforce them yourself.

**47:23** · Would you say that's roughly correct?

**47:25** · Thanks, sir. Yes.

**47:26** · \[laughter\] We've had some We've had some spirited debates I would say at the company. And you know, we've talked about culture as a bottleneck on on progress. You know, one of the most one of the secret sauces of BFL is a very united culture. Where there's a lot of debate and dissent on what to do and not to do, but then when they commit, they all commit together.

**47:46** · I And what I mean, how many people have left the company in the entire lifetime of the company? Like two?

**47:50** · Um one. One. They've had \[snorts\] one person leave in the entire history of the company. Not common in the AI space where sometimes you have like co-founders leaving 6 months in. I'm sure you This is the thing This is my one issue with the Bay Area. The culture's forgotten that sometimes to keep to make progress on long-term ambitious goals, you got to stick together as a unit.

**48:13** · And and that that's a great question. I think it challenged, uh you know, I think the culture at several points and I think they turned into uh sort of motes in a sense. Yeah, absolutely. You debate, then you you you disagree, then you commit. You commit. Uh and onwards then.

**48:32** · And there'll be more, I'm sure. Uh next question, yes. Question is how do we deal with um the insane amount of data labeling that has to be done and other than for for text uh images are just like not not not not that straightforward to label. Um I think two answers. First, when we train a model, we start obviously from we just saw this kind of pre-training, mid-training, post-training uh stages. We start with more data and also more noisy data in pre-training and then we like as you progress through training, you reduce the amount of data, but you increase the quality. So, for um in pre-training, it's enough to do automatic au- au- automatic like labeling that you can automate and then really apply it at at massive scales.

### Labeling Data And Denoising

**49:20** · There are systems that that that are available to do this uh also publicly some, but obviously also uh we have some internal uh stuff that I can't talk too much about now. Um but then the more we approach later stages in training, the more we also involve um say human signals and stuff like that because you want to make sure as you say that in the latest stages of training where you actually then again align this kind of very broad and general representation your model learns with what actually matters most to everyone out there.

**49:51** · You want to make sure that this is actually you have annotations that reflect exactly what you want and that's when you when still the the gold standard is involving human labeling then. Where do we see the the the field going in terms of denoising it it like just in general iterative denoising is is it will it still be needed in the future? There are now other um probabilistic approaches that such as drifting models that allow us to do maybe a single step um and yeah I'll answer that very generally. I think it's super interesting if you compare these kind of flow matching diffusion models with language models. Both are iterative. Both are iterative models.

**50:34** · But flow matching models or diffusion models are iterative in a dimension that is orthogonal to the data in this kind of time dimension that we artificial time dimension that we apply that goes from pure noise to to kind of the data you want to be generating whereas language models are iterative in the direction of the data, right? You generate token by token.

**50:57** · And that that has very interesting implications for both the training and the the inference um kind of properties these these models have.

**51:05** · Um for diffusion flow matching type models you have you actually pretty data inefficient because every training example gives rise to infinitely many kind of potential losses because you can pick every kind of um point on the continuous trajectory from clean image to noise and say I want to denoise from here to say the next step, right? And then I can do this super often.

**51:36** · So that that that tells us it's super data efficient in a way compared to language models where we can train on all tokens parallel in parallel or let me specify language models a bit more auto aggressive models where we can train on all tokens in parallel.

**51:49** · On the other side we have at inference it's like the the these two properties being switched so all the effects of these proper two properties being switched when you see language models you have to generate token by token and there are some hacks like such as related decoding and stuff like that um that maybe can can help you but essentially you still have to like you cannot just miss data whereas for diffusion models or flow matching models you can actually distill a model down, right? What we do when we do post training we do distillation. We've written a we've written a bunch of papers on adversarial diffusion distillation where you get down the kind of number of steps from flow matching models from 50 say to four or two and then it actually doesn't make a a real difference anymore if you if you then do a drifting model and you have this then directly at at one step maybe or you maybe take two steps but the pipeline is just more stable and mature when you distill a diffusion model down to two steps using adversarial diffusion distillation, right?

**52:51** · So I think it's it's two things of the same yeah of the same side of the coin but coming back to auto aggressive models that that that's not really the possible for like getting these insane speedups by just distillation in in in the using the iterative nature of the model that's not possible. So I think a very interesting research problem that I'm thinking often how can we combine the data efficiency of auto aggressive models with the kind of inference capabilities or inference properties that these kind of diffusion flow matching type models have. So everyone who's who's doing who's who likes to do research that that's a super interesting problem to work on. Are you guys hiring? And you yeah always always.

### Distillation And Flux Business

**53:39** · And yeah. I I could not I I could not spend the next half hour talking about this but we This this part is a you know latent adversarial distillation is a very um it's a part of the the pipeline at BFL that I would say is is very near and dear to the to the core of the company not only for for two reasons. One is because it actually makes these models extraordinarily efficient.

**54:01** · And for those of you have German friends you know that efficiency \[laughter\] is top of mind and I think that's that's that's a true line through everything uh BFL does is high quality, it's efficiency but it also ended up being a key unlock for our business model.

**54:14** · Because early on you know a big question was well we have this philosophy of we want to be open. We want to produce open weights but we got to find a way to make it commercially sustainable because there's a lot of projects that open models up and then they they just die and then that's not stable infrastructure either that you can rely on.

**54:31** · And so one of the key differences between diffusion models and auto aggressive models is and he's talking about is that a you know the the the model size is actually the same in a diffusion model. And if you look at the first flux family we we released we didn't release flux as a single model. Uh it was actually flux one was was packaged into three different models.

**54:51** · Flux schnell which is a German for fast right? Uh flux dev and then flux pro. And flux pro we put behind an API.

**55:02** · Whereas flux schnell was full Apache 2.0 open weights and then flux dev was open weights but a commercial license where any you were welcome to look at the weights here the model but if you want to make revenue off of it you have to pay. And the key distinction between these three was actually they were the same size model.

**55:18** · Unlike for example language models where you have flux like if you have Claude Haiku Sonnet Opus and so on they're actually different sizes. So in auto aggressive land you distill down the model you you train a big model then you distill down to smaller and smaller sizes. In flux one which is a diffusion model family it was the same size but fewer steps. So I mean you can still do size distillation as well.

**55:40** · still do size distillation but I think it was they were all at this point public, Yeah yeah for flux one it was yeah yeah absolutely. And so we we distilled it down to schnell which was basically a single step model at that point. So it's four steps.

**55:51** · Four steps sorry. Four step model super fast super lightweight um lower quality. Pro more steps super high quality slower right cuz you're iterating over more diffusion steps.

**56:05** · And so \[clears throat and snorts\] that turned out to be this very beautiful kind of packaging of the core technology in a way that was also commercially sustainable because the open source developer community was was thrilled cuz now they had this really fast model for a lot of use cases that you can run locally and all the enterprises who didn't want to deal with customization had a high quality model that was behind an API and developers who wanted the mix of the sort of a mix of both got a pretty high quality model that was also open weights.

**56:29** · That was fast. And and that trade-off you know is is a hard one to make if if you don't sort of foresee the fact that you want to close this loop that we've talked about of frontier research repeatedly. You know up to two years ago the state of the art was train a model put it out put the weights out there let's see.

**56:47** · But when you start thinking long term then you're not thinking in terms of a single model release you're trying to think about it as a system.

**56:54** · That capital can't you know we've talked about all the bottlenecks and you want one iteration to help you unlock the bottleneck for the next one and the next one. And adversarial distillation latent adversarial distillation is turned out to be a a pretty key unlock for that part of the bottleneck two years ago. Um next question. Spatial intelligence yes and whether it's more 3D or um or like how how how I see the the the 3D space where some companies are working versus our kind of more video based um approach um going forward in the future. Um I think I'll I'll I'll take a a kind of opinionated uh view here.

### Spatial Intelligence 3D Debate

**57:32** · Again it comes back to how how how do we humans learn uh in in our childhood. I think we don't have explicit 3D representations of anything in our head.

**57:43** · We just learn based on video and audio and I think that's the way that that will or I I I don't know if anyone have at least myself I I don't I can I I cannot look into people's heads but I I don't have an explicit kind of 3D coordinate representation of something in my head.

**57:57** · I just I see you. I have a kind of my my eyes are doing a bit of triangulation obviously but it's still pretty much a a kind of projection onto onto those two eyes. Um so I think it's it's I don't have an explicit 3D model of of like say Ansh this bottle or something else.

**58:16** · I just learn it from video and I can obviously move my head around or I can interact with this object and that's all we need. So I'm not a I'm not a kind of um so like I don't believe too much in these explicit 3D representations. It's also a data problem at some point. Do we get all the data kind of labeled with 3D representations? I don't know.

**58:34** · Just learning based on natural representations and then interacting with it as I already said like before is in my view the the kind of way to go forward.

**58:44** · I I I I'm going to I'm going to express a somewhat contrarian opinion to it and which is which is actually not totally disagreeing with you but I I would sharpen it to say I think what we have learned empirically is that these static 3D representations and I have a strong point of view on this cuz I I I started a company that failed at this.

**59:02** · Ubiquity 6 was a 3D mapping company. We tried to map the world with uh reconstructions in 3D using a bunch of deep learning priors and what we learned was it actually don't get me wrong the technology worked and it was valuable but explicit 3D representations are very narrow inflexible and static.

**59:19** · Especially when you take the temporal the the time element out of it their uses are quite limited and niche. And so there are these applications for 3D representations that are useful don't get me wrong especially when you're getting human like machine perception you know, point clouds for example are great at having robotics, you know, do indoor positioning in GPS denied environments. But when it comes to when you're trying to build a system that can be interacted with by humans, it turns out point clouds, 3D meshes, the these are all sort of intermediary representations and in a sense hacks to you know, that that are less than general and flexible than representations that can integrate naturally time and audio and all these other modalities cuz that's how we reason. Now, I cuz I actually disagree with you Andy. I I do think I have a 3D representation my head of certain things. Like I I if I if I it is it explicitly I I are you are you thinking in in in terms of coordinates?

**1:00:12** · I don't I don't think so. Well, I think about this lecture hall.

**1:00:15** · Like when I'm planning a lecture, you know, I I often have a 3D representation spatially. But it's it's just one input representation as part of a broader set of But but but but you're not it like there's there's no kind of prior that enforces you to to to think think about this uh kind of Yes. It's implicit. You learn it. You learn it You learn it based based on like what you're perceiving Right.

**1:00:35** · and what you're interacting with. That's right. And then And obviously we could we could maybe maybe a network could in in its weights represent this kind of uh implicit 3D structure if it needs that. But I think the interface like we're talking about the interface, right? Do we do we need these ex Ah, okay. Yes, at the human interface level no. It's it's it's quite unnatural to reason in in explicit 3D priors. I wouldn't do that.

**1:00:57** · Welcome to our late night conversations.

**1:00:59** · \[laughter\] Thank you so much Andy for coming. Thanks for having me. Thanks everyone.