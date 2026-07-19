---
title: "Stanford CS153 Frontier Systems | Scale, AGI, and the Future of Everything"
source: "https://www.youtube.com/watch?v=F_7M4Hc-usM&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=2"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=F_7M4Hc-usM)

## Transcript

**0:09** · Please join me in welcoming Sam Altman.

**0:12** · \[APPLAUSE\] This class was designed as an inspiration from a set of different experiences while I was a student here.

**0:24** · One of them was Terry Winograd's intro seminar CS-47M, Computers and the Open Society.

**0:31** · But a second one that was a pretty formative experience for me, and a lot of my friends and peers on campus at the time in 2014, was CS-183, How to Start a Startup by Sam.

**0:43** · And so it's really cool to have you back.

**0:45** · What's it like?

**0:46** · How's it feeling for you to be back?

**0:48** · I was thinking as I was walking in, if I had just a little more time, I would do an update to that class because I think everything about starting a startup has changed so much, and I have not seen anyone do a good version of how you're supposed to make a starter now.

**1:02** · So I had that-- just walking in here, I had that, oh, it'd be fun to do it again.

**1:06** · So, timeline wise you thought that in '14.

**1:10** · I think OpenAI was founded in 2015?

**1:13** · Is that right?

**1:13** · '16 basically.

**1:14** · '16, OK.

**1:15** · So then you went-- it was like you were-- it felt to me from an observer perspective that you had come up with your working theory for how to do it right, and then you went and tried to implement it.

**1:26** · Is that a fair assessment or is that not the case?

**1:29** · OpenAI was like the strangest startup of the last, maybe, a couple of decades in Silicon Valley because it started as a research lab.

**1:38** · It was really not a company at all.

**1:39** · And the kind of normal course of startups is that you start a product company, and then it grows for a while, and then growth slows down, and then you start a research lab and you like bolt that on, and you try to figure out the next thing to do.

**1:54** · And we were the opposite of that.

**1:56** · We were a research lab first that later had to bolt on a startup.

**1:59** · And I don't really recommend that.

**2:02** · It's kind of an unusual thing, but that's not quite what I meant.

**2:06** · What I meant is we still followed the pre-AI rules of a startup because we were trying to make it.

**2:12** · We didn't have it yet.

**2:13** · But now, watching what the best startups do is so different than how startups work even a couple of years ago that I think someone-- I'm probably not going to do it-- someone should do that class again.

**2:25** · And what would be the biggest updates you'd make based on your data?

**2:35** · With an affordable amount of spend on tokens, you can do what a 100-person, incredibly great engineering team would do as a startup.

**2:45** · And that was just totally impossible.

**2:46** · That was not in the set of options for a startup, and now it is.

**2:52** · So I think what you can take on, the level of ambition you can have, the speed of which you can move, the amount of stuff you can do at once, it's just totally different.

**3:00** · And does that change the shape of the problems you feel like you assign at the end of the class for people to attack at the end of that quarter if you were teaching it again?

**3:11** · I don't think assigning problems to attack ever works because if you like-- if I can think of a problem-- if I can think of a really great startup idea, if it's, obvious, enough to me, then it's probably obvious to a lot of people.

**3:25** · When we started OpenAI, we were one of maybe-- generously speaking-- four AGI efforts in the world.

**3:32** · And you want to find something like that.

**3:34** · And I'm sure that there exists something today that just wasn't possible at all pre, like, automated coding era that is totally non-obvious, that will be a multi-trillion dollar market soon.

**3:47** · And that only four companies are working on it right now, but I don't know what that is.

**3:50** · It's much more likely you all know what that is than I know what that is.

**3:54** · My brain is like taken over by OpenAI.

**3:57** · But, the kind of idea someone can assign you to work on is probably not what you want.

**4:02** · Yep.

**4:03** · OK, so that's fair.

**4:05** · But I think it would be helpful, since this is a systems class, to maybe reason about a particular problem that you have to reason through so that they can then apply the shape of the techniques used to break down from a systems perspective, that problem into solutions to their own problems.

**4:21** · And a concept that you had started to tease in the class back in 2014 and then clearly you've talked about publicly over the years is scale.

**4:32** · Scale is its own beast.

**4:34** · Its quantities, its own quality.

**4:37** · Scale as a concept has been something it seems like you've empirically investigated in all kinds of ways over the last 10 years or so.

**4:46** · Could you help us, first unpack what you mean by scale now, 10 years later, how would you deconstruct that as a systems design attribute to apply, whether it's as a tool?

**4:57** · Can we start there?

**4:59** · Yes.

**5:01** · So I don't know why the following observation is true.

**5:05** · I offer no theory that I find satisfying to explain it, and that makes me a little bit nervous to suggest you follow it, but I'm going to anyway because, empirically, it does seem to be true, which is all of the most interesting things I have observed in my career in watching other things happen.

**5:26** · All of the most interesting ones have had something to do with emergent properties that scale or scale continuing to provide returns far beyond what the consensus thinks will work.

**5:40** · And this, obviously, happens with scaling laws for AI models, but this happens with getting more smart people together to think about one problem in a research setting.

**5:53** · This happens with companies and the economy of scale you can get all in all these different ways.

**6:00** · I really learned this at Y Combinator when it became clear to me that everybody was saying, oh, Y Combinator has gotten too big.

**6:07** · It should shrink.

**6:08** · We should fund less companies per batch.

**6:10** · The best times of Y Combinator, when it was like 10 companies per batch.

**6:13** · And a lot of very smart people were saying this, and it was like tempting because it would have been much less work.

**6:21** · And the theory was that the best companies are always kind of obvious, and then you fund the rest and it's not as helpful.

**6:27** · But a huge part of the magic of what made YC work were-- was the network effects inside of the batch.

**6:35** · And that was an emergent property at scale that just hadn't been discovered before.

**6:38** · No one had tried to fund startups at scale in the same way, and thus no one had ever happened upon this observation of when you do that.

**6:48** · There's something important that happens that just didn't exist at all at the 1/10 but 1/100 of a scale.

**6:57** · There's a bunch of other examples like this, and I'll skip them in the interest of time.

**7:05** · But I would say, again, I offer no explanation for why, but empirically speaking, when you find a time that you can push on-- you can push something to a scale people have not tried before, and it's already working in some interesting way at the smaller scale, more often than not, that seems to be a good idea.

**7:23** · And that also seems to be something that most people don't do enough.

**7:30** · And I don't offer an explanation for this either but when we were, like, we're really going to scale AI models, all of the geniuses in the field, most of them were, oh, this isn't really working.

**7:41** · That's barely a scientific result.

**7:43** · It's not interesting that it gets better at scale.

**7:45** · You've already shown that, why keep scaling it?

**7:47** · So I mentioned the YC example, I've seen a lot of startup founders where they're like, well, there might be something interesting would happen if I scaled this up, but I'm a little worried about it for non-specific reasons.

**8:01** · And, again, looking back at a huge data set of people that have scaled their companies in all these different ways, there's almost always interesting stuff there.

**8:10** · So I think, directionally, that's like an interesting thing to push on and severely underexplored.

**8:19** · On the systems design part of that, I think one reason people don't do it as much is stuff breaks at an accelerating rate and in an unpredictable way as you scale it.

**8:34** · And if you are going to really scale something, it's always like a little bit broken.

**8:41** · There are always very smart people who say why you shouldn't do this, don't get too ambitious, don't get too big, let's try this smaller, and so breaking that down is a systems problem.

**8:51** · I'll use the thing of when we were scaling up AI models, there was technically can we do this at all?

**8:56** · This seems crazy.

**8:57** · Like, no one had ever thought about trying to do a run across 10,000 or 100,000 GPUs, and that was going to require stacks of engineering talent.

**9:04** · There was the capital requirements and what it was going to take to do this.

**9:08** · And like, how is there ever going to be a business?

**9:10** · How can you think about taking this risk?

**9:11** · There was this sort of cultural stuff of researchers saying, well, if we're going to get all this compute, why do we put it all into this one project where we're not going to learn something?

**9:19** · Why not divide it up among all these projects?

**9:21** · And this also happens in every area.

**9:23** · I've looked at almost every area for scale, and breaking it down into each difficult area or each reason not to do it and trying to address them one at a time, yeah, that's been really important.

**9:38** · I'm going to push on that a little bit because there's very few people who've been able to repeatedly scale new products and systems the way the OpenAI team has over the years, but it seems like one of the issues is there are all these prior conditioning sort of mental models and expectations humans have, and you said things break.

**9:59** · And one of the things it seems often breaks that's the hardest to refactor is the human side of the systems design, wherever there's human implementers or there's human participants in that.

**10:13** · And so what have you learned about humans at scale-- organizing humans at scale to participate in a system that may not be just a redo of some past system that they get naively on-- at a priori on first blush?

**10:29** · I think a clear goal, a clear plan to get there, and a clear answer to the way that you're going to get there and how you're going to make decisions along the way, that's very important.

**10:45** · So if we go back to the example of when we decided to scale up models, there were a lot of people who were like, ah, this isn't really going to work.

**10:53** · It's going to have these problems.

**10:55** · It's also not-- we need a more diversified portfolio.

**10:57** · But once we say, no, we're going to make a bet on scaling deep learning.

**11:00** · That's our thing.

**11:01** · If we're wrong, we'll fail, but we're going to do that, here's why we're going to do that, here's what we believe about what the state of the world can be like if we get there.

**11:08** · That's very powerful.

**11:11** · And then for whatever reason, we did not evolve to be good at thinking about exponentials.

**11:21** · People have a hard time imagining that scaling laws are going to continue exponentially, that revenue will grow exponentially, that an organization can take on exponential complexity, and, in my experience, it takes a lot of time to really reason through first principles with people about why that can happen.

**11:39** · Can we take two examples to walk through that?

**11:42** · The first being ChatGPT and the second being Codex, both of these have transformed-- can everyone hear?

**11:49** · I'm going to try to project it.

**11:50** · Yeah?

**11:50** · OK.

**11:51** · So, let me put in a frame and you can challenge both the assumption, and then we can hopefully reason through example what happened.

**11:58** · In the case of ChatGPT-- for a long time in scaling of models, a big mental block that seemed to be prevalent in the space is what are these things going to be useful for.

**12:09** · It's a research solution-chasing a problem, research-first approach.

**12:14** · It's not a product.

**12:16** · And then ChatGPT came out and it proved to the world that that chat experience was a killer app for general models at scale for consumers.

**12:27** · And then a couple of years later, it's clear that coding has been the killer enterprise app.

**12:32** · So, how would you compare and contrast the systems you guys used to discover those use cases, ship them, scale them, monetize them?

**12:40** · Any salient learnings from those two systems?

**12:42** · Yes.

**12:45** · So, we had made GPT-3 and we needed to make money because we wanted to go scale up to a billion and multi-billion dollar computers.

**12:54** · And we had GPT-3, and it was kind of interesting.

**12:56** · It was a cool demo, but we couldn't figure out a product to build around it.

**13:00** · And we had been thinking, thinking we just couldn't do it.

**13:02** · We had tried a few things, they hadn't worked.

**13:05** · And so we knew the models were going to get better, but we also wanted to start a revenue engine sooner.

**13:10** · And we said, well, since we can't figure out what product to build, we're just going to put this into an API, and we're going to hope that somebody else can figure out what product to build.

**13:19** · And so we launched in like-- I don't know, something in the summer of 2020-- the GPT-3 API.

**13:25** · And, initially, it kind of got no traction at all.

**13:30** · And then about a month later, randomly, as far as we can tell, it went viral on Twitter.

**13:36** · On the same day, a few different developers kind of got it to do something cool, posted it, other people started trying.

**13:43** · And then a lot of people started trying the API, but it was shockingly bad.

**13:49** · If you go back and use GPT-3 or 3.5, you will be astonished at how bad the models were then, relative to the amount of excitement they generated at the time.

**14:02** · So people tried all of these things, and, really, the only business that people got to work in a significant way with GPT-3 was copywriting.

**14:10** · And that was, like, not that great and not that exciting.

**14:13** · And we were kind of like, ah, it's just going to have to wait for a better model.

**14:16** · But although that was the only business that was working, developers had figured out how to put in a prompt and be able to chat with it.

**14:26** · And we saw this a lot.

**14:28** · Like, more people were using-- they couldn't get the API to work for their business, but they were using their API key to just chat.

**14:35** · And we said, well, we can build a good chatbot.

**14:37** · People clearly want that.

**14:39** · And we had a new model.

**14:40** · We actually had GPT-4 done but we had a new model we were ready to release in between called 3.5, and we had figured out a new kind of post training where we could get the models to do a good job with instruction following so it can make it easier to chat with.

**14:53** · And we said, well, the API is not working great-- maybe it was like a $10 or a $20 million run rate kind of business-- but there is this thing that people love.

**15:04** · And under the YC principle, see what your users love and do that, we said we'll build a chatbot around it.

**15:10** · And we put that out.

**15:11** · And we still didn't think it was going to do that well.

**15:13** · It was really meant as a research demo to convince other people that they should build chat-like products and pay us for the API, but that went crazy viral.

**15:24** · And another thing I had learned from YC is when something really starts growing and it's not very good, you have a guaranteed hit on your hands.

**15:32** · And so we had like five days where the traffic would shoot up, fall off and everybody would be like, well, that was just a hype cycle.

**15:38** · But then the next day it would get to a higher peak, fall off again, later in the day people would say that's a hype cycle.

**15:43** · By the fourth or fifth day I was like, I know how this works.

**15:46** · I know what's going to happen.

**15:47** · Like, we have the potential here at a killer product, and we knew we could make it much better.

**15:55** · We knew we could-- we knew we had GPT-4, we knew we could keep scaling, but by that fifth day, we got everybody together and said, this is an emergency.

**16:06** · This is the good kind of emergency, but we have to build a company and a product all at once.

**16:12** · We then had two months of crazy scaling, and then we said, we have to figure out a business model later.

**16:19** · For now, we're just going to charge people so that we don't run out our compute bills, but that's, obviously, not the long term answer.

**16:25** · That also turned out just to work.

**16:27** · And that was the story of ChatGPT.

**16:29** · And then there was so much utility that people just had not gotten over the activation energy to find that that has worked really well.

**16:37** · And then Codex-- actually, the plan before ChatGPT was that we were going to go all in on code.

**16:44** · We knew these models could write code.

**16:46** · We knew that they could be really-- and we knew that would be a valuable area, but then we had this incredibly exciting thing happen.

**16:54** · But our internal belief at the time was that coding was how these models would control things on computers and robots were how these models would control things in the physical world.

**17:05** · And if you made a smart enough model that had the actuators of writing code and robot-- and driving a robot, you could then actually get this intelligence to do stuff for you in the world.

**17:16** · So then it took us a while to get there.

**17:18** · And then I think Codex got really good by early this year, but with 5.5 is when we saw this real inflection point where people are now like doing just incredible things with it.

**17:31** · And earlier in the class, we've talked about how the capabilities pipeline is starting to look-- it's starting to become somewhat more legibly standard across different research groups.

**17:43** · You've got pre-training, mid training, post training, then you've got the RL and supervised feedback loop.

**17:48** · Do you think that's roughly like the shape of the pipeline that allowed Codex to go through a capability jump and that will basically stay stable now and consistent, or are we going to go through a major rewrite of that pipeline?

**17:59** · I think that is definitely the current pipeline.

**18:01** · I expect we will go through a major rewrite.

**18:03** · I don't know when it'll happen or exactly how, but it is a little odd to me that it's so happens as a pipeline and it doesn't quite feel like the optimal solution.

**18:17** · What would be an optimal solution in your head?

**18:20** · I think that's a research problem for the AIs to figure out.

**18:23** · I think we're at a point where-- and we've set this goal that by September of this year, we will use 500,000 A100 equivalent GPUs-- like a lot of computing power-- as an AI research intern.

**18:34** · And by March of 2028, that we will have a full end to end, very talented researcher figuring out completely new architectures.

**18:43** · So I think we are going to get-- with the current pipeline, the current architectures, I think we're going to get over the line of when AIs can do incredible work.

**18:53** · One of the things that you just described there is you-- we've been talking a lot in the class about systems, frameworks, and analogies to make concepts from one domain legible to other people who may not have all the context in another, but sometimes because of the translation problem, reasoning by analogy is not helpful because then errors compound.

**19:16** · Yeah.

**19:17** · Right there you said, our goal is to try to use it as an AI intern, which, obviously, is a very useful metaphor within the context of Silicon Valley, a class that understands how these pipelines work and so on.

**19:28** · And then as you scale, actually, that metaphor globally, people who might not have all that context go-- start analogizing these models in ways that they shouldn't be.

**19:35** · Like, how should we think about the limits of that-- what are the limits to scale of-- what are the product analogies, the research analogies you find most useful within the valley?

**19:47** · And which one of-- what have you found about the limits of those analogies scaling?

**19:52** · And now how do you navigate between those two problems?

**19:56** · I've been very interested in studying how-- I think what is happening is we are in the process of creating a new utility.

**20:06** · This doesn't happen very often.

**20:07** · Electricity is utility, internet is utility, the water, I guess-- there's not a lot of these.

**20:12** · And so there are not a lot of examples that we can study for good metaphors or learnings about how to explain this to the world.

**20:20** · But I was recently looking at what happened when electricity became a utility.

**20:27** · And it's a good analogy for many reasons.

**20:29** · It's imperfect, of course, too, but the electricity companies-- at least the ones I could find information about-- they didn't talk about selling electricity because no one knew what that was or why they wanted it.

**20:38** · It sounds very scary.

**20:39** · It's this thing that's like going to come into your house and it can kill you in this gruesome way, and it feels very different than the world before.

**20:48** · And maybe they tried to sell electricity or market electricity first, I don't know.

**20:53** · But in any case, that didn't work.

**20:54** · And then what they started marketing, selling to people was light at night.

**20:59** · We are going to-- what you are getting from us is not electricity.

**21:03** · It's light at night.

**21:04** · By the way, you can use the same thing that lets you get light for all these other things, but people are like, well, why would I want that?

**21:09** · And they're like, well, it'll wash your clothes for you someday.

**21:12** · And, no, it won't.

**21:13** · That's too far of a jump for me.

**21:15** · So, I don't know what our analogy for this should be, but I suspect that even if we're totally right and intelligence is going to become this new utility, that every company, every customer, every government just who needs access to and is going to use on all sorts of incredible ways.

**21:36** · And you will have a OpenAI token subscription that you will plug into everything and use to access everything, and you have running for you all the time and doing this amazing stuff.

**21:45** · I kind of don't think-- at least right now-- the right way for us to analogize that is we're selling intelligence because people are just, like, somehow not resonating.

**21:54** · I don't know what our equivalent of we're selling you light at night is going to be, but I think if we're going to become a utility, we need to find a way to explain to the world what it means to have this intelligence pike that you can just do whatever you'd like with.

**22:09** · So, one question that has emerged-- an emergent property of this class of having a diversity of different speakers is that the utility analogy has come up several times, but in reference to different things.

**22:23** · So Jensen likened compute to a utility and why there should be access, and so on, and talk about how Stanford should pool budget and so on, and procure that as a utility for everybody on campus, whereas you just likened the intelligence part to utility.

**22:38** · Are both of these things true?

**22:39** · Is one of them true?

**22:40** · Is one more likely to be true?

**22:42** · How should people reason about compute as a utility versus tokens as a utility?

**22:45** · And compute I mean here chips versus tokens.

**22:48** · Does that make sense?

**22:50** · I think as a consumer, as a business or an individual, you will think in something closer to tokens or probably even one level up from tokens.

**23:00** · I don't think you'll care very much about, where the hardware is, what particular chip it is, what's powering it.

**23:07** · I think that stuff will be abstracted out.

**23:09** · And what you will care about is when you're interacting with the system, can you use it a lot?

**23:16** · Is it cheap?

**23:17** · Is it doing a good job?

**23:18** · So right now it's like tokens.

**23:21** · It may get-- as we move into a world where we all just have this constant agent running for us, being useful to us all the time, you may think about it as even one level up, but, yeah, my guess is when you pay for your cell phone bill, you're like, all right, I'm buying access to airtime and some number of gigabytes.

**23:41** · And, it's going to do all these things, and I'll use all these apps and whatever else.

**23:44** · But what you think about paying for that kind of internet utility in this case is just like access to the whole system.

**23:51** · And the particular hardware at the base station and how it connects to the internet, you don't think about that as much.

**23:59** · I know I could nerd out about utility infrastructure for a long time, but I want to make sure we switch a little bit to being relevant for the students.

**24:05** · Usually we have questions but we're not doing this today, unless you're comfortable with it.

**24:10** · Oh, OK, great.

**24:10** · How about that, improv.

**24:12** · OK.

**24:14** · So one final question to start getting the creative juices flowing is the final project for this class, according Project 183 is the one person frontier lab.

**24:23** · So everybody here is working on projects where they're simulating being an individual as a lab with access to all the right tools, they've got hundreds of thousands of dollars of credits from Cloudflare.

**24:33** · I think we've got some OpenAI tokens maybe, but there's a bunch of compute at their disposal.

**24:38** · If you were in the class, what would you be working on for your one-person frontier lab project?

**24:44** · First of all, I think that's an awesome project.

**24:48** · I think this is top of mind because we were just talking about utility framework frameworks.

**24:56** · I think there's a lot of very smart people working on great training ideas, and we're going to have incredible models.

**25:04** · No matter what you all do, we're going to have incredible models, I promise you, pretty quickly.

**25:09** · But I think we have not invested enough in being able to deliver at scale huge amounts of cheap intelligence, so maybe I would go work on the inference part of the stack.

**25:20** · And how are we going to get this incredible intelligence to be cheap and abundant, I think that's under-invested.

**25:27** · And I think all of the frontier labs are going to have to become insurance companies to a significant degree.

**25:34** · OK.

**25:35** · It might be too late to pivot your projects, but better late than never.

**25:39** · Work on whatever you want to work on.

**25:42** · OK, let's start doing questions.

**25:43** · And I'm going to moderate and try to be not-- please try to be productive and not spicy, et cetera.

**25:49** · Remember it's a CSS class, but up to you Sam.

**25:51** · It's fun.

**25:52** · It's Fine.

**25:53** · Oh, we've got questions.

**25:54** · Oh, perfect.

**25:54** · All right.

**25:55** · First one.

**25:56** · The questions about your views on Yann LeCun's view that LLMs are a dead end.

**26:03** · First of all, in terms of achieving human level intelligence, these models have already far surpassed human intelligence in some ways, and then they're wildly worse than others.

**26:12** · Like, for example, they seem much worse than people are at very long horizon, kind of, high judgment signal and tasks.

**26:25** · On the other hand, yesterday we had one of our models discover-- or disprove a conjecture one of the hardest problems that had-- smart people had worked on for a long time.

**26:36** · And a lot of people, a lot of smart scientists-- I don't know if LeCun was one of them or not-- had even quite recently said something like that was not going to happen, and then the model just did it.

**26:47** · And now you have all these mathematicians saying like, is math over?

**26:50** · What does this mean for our field?

**26:51** · So, clearly LLMs are capable of figuring out new knowledge, and clearly they are capable of doing some things that-- some intelligence tasks that humans just can't do.

**27:03** · They are going to scale much further, so how much better and what distribution of the tasks they can do better than humans?

**27:09** · We'll find out, but I suspect it's a lot.

**27:11** · And in terms of this lack of a belief in the exponential we were talking about earlier, I think the field was, honestly, held back by a generation of scientists who just were way too certain on what wouldn't-- what scaling was not going to produce.

**27:27** · And then some people just looked at the graphs and said, well, it looks like it's continuing beautifully.

**27:31** · Let's keep going.

**27:34** · I think world models are clearly important.

**27:37** · And we'll need that for things like robotics, but betting against LLMs scaling at this point feels quite misguided to me.

**27:52** · Does it get annoying to be the, I told you so guy?

**27:55** · No.

**27:55** · I mean, there are these like Twitter trolls that for years have just been like, it's not going to work, it's not going to work.

**28:03** · This is so dumb.

**28:04** · This is fraud.

**28:05** · This company is going to fail.

**28:06** · This research approach is going to fail.

**28:08** · And I used to get more bothered by them, but I don't even like feel the, I told you so at this point.

**28:12** · It's like you were just-- Like, choose Nirvana.

**28:14** · You're still going on about it.

**28:15** · Like, the data is quite strong on our side.

**28:21** · And I don't think it'd be that fun to say I told you so, also the fact that you're still saying we're wrong doesn't really bother me.

**28:28** · Just move on.

**28:29** · There's that saying that insanity is doing the same thing over and over again when presented with data that is not working.

**28:34** · And if they keep repeating that, in a sense, it's a form of insanity, I think.

**28:39** · I think there's something that happens, which is if you make your identity about a particular thing is going to work or not work, and you associate yourself with that belief, and then the science or the empirical results disprove you, and you're like too hung up on your identity, you can't let it go, you can't see the truth.

**28:59** · And I think this is an important reminder in both directions.

**29:03** · How do you see education?

**29:08** · It clearly has to super adapt.

**29:10** · And I am worried-- I thought by now it would have.

**29:15** · I think if we continue to teach and evaluate students as if we were in a pre AGI world, it's not going to work and it is going to lead to atrophy of learning how to think or whatever.

**29:28** · And I thought that was going to be obvious enough that I wasn't that worried.

**29:32** · When ChatGPT launched, I was like, yeah, we're going to have one year of students cheating and not learning that much and then the educational system is just going to redesign itself, and we're going to teach people so much better.

**29:43** · People are going to really get projects where they have to use AI to be able to do it, but they still have to stretch their brain more and think more and figure out new things to do.

**29:53** · And, honestly, I struggle to point to any significant systemic change that I've seen in the education system at large in the three and 1/2 years since ChatGPT launched, and that was a prediction error for me.

**30:06** · I thought that would have happened.

**30:07** · So I have no doubt that we can likely have done with every other technological leap before, redesign how education works so that you still have to learn how to think.

**30:19** · And there will be some things.

**30:20** · Like, I am a person who thinks by writing, and I write a lot of stuff that I never show anyone else but it's still important to me to figure something out and so I'm grateful that I learned to write.

**30:31** · People say the same thing about programming.

**30:34** · So there will be some things that we teach people to do that machines can do better just because it's helpful to teach them the meta skill of thinking and learning, and that makes sense, but there are a lot of other things where we should just totally teach-- totally change how we teach or how we learn or how we evaluate.

**30:51** · And if we don't do that, I think there will be significant atrophy in people's critical thinking skills.

**30:58** · Question is, what was your favorite class?

**31:00** · And what do you wish you'd taken when you were at Stanford?

**31:03** · Did Stanford still do intro Sims?

**31:06** · I did like all the-- I did like three intro Sims a quarter of my freshman year, and I loved all of them.

**31:11** · They were all super different.

**31:13** · But looking back, the fact that I was able to get such a broad exposure to stuff and have a very shallow understanding of lots of different fields was an incredible thing.

**31:27** · If it had not been for that, I just would have taken like CS and physics classes, which still would have been great.

**31:32** · But I think more about the stuff-- the classes I took that were totally random and unrelated to what I do now but in some important way gave me a perspective, that I think I would have liked learned to program, no matter what.

**31:52** · And I didn't think that at the time I was kind of like, this stuff is all cool, but it's mostly going to be about learning CS.

**32:00** · I only did two years of school, so there was a lot of stuff I wanted to take that I didn't get to, but that's the surprising thing.

**32:08** · My question is, what is your spiciest steak of all?

**32:17** · I think with more time to think, I could come up with a much spicier one but I think AI is just going to keep going.

**32:29** · And I think this is considered-- I don't think this is widely believed yet.

**32:36** · And I think if this were widely believed, there would be significantly more reverberations that are happening through society right now.

**32:44** · Maybe I don't have the-- or actually, maybe this is the high order bit that if AI progress continues on the exponential that it's on for another-- it's been three and 1/2 years since ChatGPT.

**32:56** · Even if it were another three and 1/2 years on that same trajectory, the world, the potential-- the way that society-- what society is capable of are just completely different.

**33:06** · Well, let me try to prompt you in more thinking tokens on that one.

**33:11** · If we treated you as a model, as a frontier model, and you have some inherent capabilities-- and we're going to try to elicit capabilities that people don't know about for the next few minutes-- one of them is that you've been post trained now on-- you've been continuously RL on OpenAI, as well as the external feedback loop of the world on what doesn't work and-- what works and doesn't work.

**33:32** · So now, if we're going to treat you as a prediction engine for a sec, the prompt is what are the three most likely forks of the universe you see over the next 10 years?

**33:42** · And what is your probability assessment on each of those?

**33:45** · Does that make sense?

**33:47** · One that feels very important is how much is this technology going to be very widely democratized versus how much is it going to sit in a few companies.

**34:00** · I think a world-- there are all of these reasons why you could imagine the default is that this gets concentrated to a few companies and they become like a significant fraction of the wealth on Earth.

**34:11** · That would, obviously, be terrible, and we work super hard to push against that, but I think that's going to require the will of the world to really avoid because there is a sort of attractor state there.

**34:22** · And I think part of the reason that we need to push to this kind of utility model of the world is that, A, it's quite unstable and quite bad and will feel quite unfair if a few companies have all of this.

**34:32** · But, B, I think there's a real alignment failure and a very fragile world.

**34:37** · And the best way to get to a world we want that represents everybody winning and everybody's values being represented, everybody having agency is to just push this technology out into the world, but there will be a very strong argument against that around safety and stability.

**34:52** · And I think that will be a big fork.

**34:55** · And it's very important.

**34:56** · And I encourage all of you in your careers to push hard that this is a technology-- it can bring us an incredible sci-fi future.

**35:04** · Life can be unbelievably much better.

**35:05** · We are going to incur some risk to get there, but the risk of keeping is concentrated in a handful of companies, even though we would be one of these companies is not something we should tolerate.

**35:14** · So I think that will be a big fork.

**35:17** · In terms of probability, I think it's-- the world should have such an interest in it happening this way that I think it's like 80% we end up on the Democratic path, but there will be a very strong safety message and there will be a lot of power seeking people who want to concentrate the power.

**35:35** · And one of the problems with forecasting this-- or that you have and we all have as humans is once you make that forecast, then you have agency to affect the forecasts and the forks?

**35:49** · Well, I mean, we're clear on what we're going to use our agency for.

**35:52** · Like, this is what we believe in, we think that we're going to do everything we can to push it in this direction.

**35:58** · We see the forces in the other direction.

**36:00** · Maybe a related fork, there's a lot talk about future economic models and are we going to do universal basic income?

**36:08** · Are we going to have everybody gets to own a slice of every company?

**36:12** · Like, is it capitalism and no change?

**36:15** · Is it, like, full on communism?

**36:17** · There's a lot talk about this.

**36:19** · One thing that I think is not talked about much is how-- specifically how we distribute compute.

**36:26** · So, maybe a lot of the economy can work in a way that it's going to work.

**36:31** · I've become much less of a even short term jobs doomer.

**36:33** · I've always been optimistic we'll find new things to do, but this may not even be as disruptive as I originally thought in the short term, but we are seeing compute shortages now.

**36:45** · I can imagine them getting much worse, and I can imagine compute being like the most important utility that people need.

**36:52** · So if the price of compute from a supply and demand perspective gets way out of whack, then I think there will be a very interesting fork about what it means to equitably distribute compute.

**37:02** · So, there are two very interesting things there which you said.

**37:05** · On the economic side, we might have need universal basic income.

**37:09** · Everybody owns a piece of shares.

**37:11** · One of the speakers in this class is Nicolai Tangen, who runs the Norwegian Sovereign Wealth Fund.

**37:17** · He's awesome.

**37:18** · He's awesome.

**37:19** · Yeah, the Norwegian Sovereign Wealth Fund owns 1.5% of all publicly traded companies on the planet.

**37:23** · They also have effectively universal basic income.

**37:26** · You could argue there's flavors of this already today because the largest employer now in the United States is the government.

**37:31** · And you could argue large sections of that are a way for the government to redistribute income from taxpayers.

**37:37** · So are these solutions that actually need to be novel or just reimplemented for this era?

**37:43** · How do you think about the novelty of those solutions where we often, in Silicon Valley, have this tendency to be like reinvent old things from first principles?

**37:52** · And so should we just look to existing systems and tweak them?

**37:54** · I don't think that these things require deeply new ideas, although I will say, I am much more excited about people having some ownership stake than a fixed monthly cash dividend.

**38:09** · And I funded like a big universal basic income study a while ago.

**38:16** · I've also watched what happens when people invest in startups, and I know which model I think hits human psychology better.

**38:24** · So what I would love to see is as leverage in the world shifts from labor to capital-- which I think is going to keep happening-- that we find a way to have something like a citizens wealth fund in the country or in the world, eventually, where you basically own a slice of capitalism, you own a slice of these companies.

**38:45** · And then on the second fork there on compute bottlenecks, you said at some point when compute prices get out of whack, between January and this year-- my current understanding is based on data-- we've seen that H100 prices and Blackwell prices, the spreads between long term reservations and spot is like 5x.

**39:03** · I don't know if it's that high anymore.

**39:05** · I think it got a little better, but yeah, it's high.

**39:08** · Or if you could even find H100s because they're pretty much all gone for this year.

**39:12** · Does that sound right?

**39:13** · No argument.

**39:14** · There's a gigantic compute shortage, yeah.

**39:16** · So, that's a good example of a systems problem right now that's live.

**39:21** · At least to some folks it feels like COVID, but for the compute era, like all the toilet paper is gone, why are people not freaking out about this?

**39:31** · Well, I think people assume we will make big inference gains on the hardware we have.

**39:35** · I also think there is a tsunami of hardware coming, but maybe the demand tsunami is even bigger and I think people should be freaking out somewhat.

**39:43** · And would you say it's fair-- like, how long are we going to exist in a compute shortage, at least, based on current data you have?

**39:53** · I think other-- you can't talk, really, about worldwide demand for electricity without talking about the price.

**40:01** · Like, there's an extremely different demand about how much energy people need in the world if the price comes down by a factor of 10 or goes up by a factor of 10.

**40:09** · And I think AI is like that too.

**40:16** · If we can make models sufficiently smart and at sufficiently low cost, I think demand is kind of uncapped.

**40:26** · And so in some sense, as long as we can continue to make progress on this, there will be a shortage forever and things will be a bit above what the price we think should be even though people are getting better, smarter, more whatever, intelligence just because you can use-- if we make really great personal agents, you can have 10 of them running and working for you all the time, or you want 100, I think.

**40:53** · It's a lot of inference, a lot of-- awesome.

**40:56** · With that, I'm going to give you the swag for the class, which is-- \[APPLAUSE\] Thank you for coming.

**41:03** · Thank you.

**41:03** · Thank you, all.