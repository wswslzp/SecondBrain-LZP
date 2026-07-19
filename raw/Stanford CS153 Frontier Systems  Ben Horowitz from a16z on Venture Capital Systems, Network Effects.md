---
title: "Stanford CS153 Frontier Systems | Ben Horowitz from a16z on Venture Capital Systems, Network Effects"
source: "https://www.youtube.com/watch?v=B8NvdfssGac&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=8"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=B8NvdfssGac)

## Transcript

**0:09** · Please join me in welcoming Ben Horowitz.

**0:12** · \[APPLAUSE\] Thank you.

**0:17** · So how many of you heard the song that was playing right before?

**0:21** · Does anyone know the name of that song?

**0:23** · Yeah.

**0:24** · "We Are the World."

**0:24** · Yes, that's correct.

**0:26** · "We Are the World" is a 1985 single by a supergroup of musicians that all came together to raise-- It was a charity single that was produced to help raise funds for the famine in Ethiopia, I believe, in 1985, Lionel Richie made a good documentary on it if you're interested.

**0:52** · Correct.

**0:52** · Yeah, yeah.

**0:53** · The reason I'm bringing it up is because Ben is known for many things.

**0:58** · He's the founder of Andreessen Horowitz, co-founder of Andreessen Horowitz.

**1:02** · I'm very lucky to have called him my boss for a few years.

**1:05** · Yeah.

**1:06** · He's also been a founder or CEO.

**1:09** · He's built several technology companies.

**1:11** · He's behind one of the reasons venture capital still exists today after many moments when there were times when it got threatened, including the SVB financial crisis.

**1:20** · But the thing I've learned most about Ben is from a documentary that Ben told me to watch about a year and a half ago.

**1:28** · Yeah, yeah, yeah, Triple OG, yeah, yeah.

**1:30** · It's called The Greatest Night in Pop.

**1:33** · And I would really recommend folks who haven't read it-- sorry, watched it to go watch, And we're going to put it in the reading assignment for this class.

**1:41** · It's on Netflix so anyone can go watch it.

**1:43** · But it is the documentary about the making of that song you just heard, "We Are the World."

**1:50** · And there's somebody in the documentary that you'll observe if you watch it by the name of Quincy Jones.

**1:59** · How many people have heard of Quincy Jones?

**2:02** · OK, About 30%.

**2:03** · So we need to school of kids a little bit on it.

**2:06** · Yeah, he was the greatest-- And I didn't-- Great human being.

**2:13** · Great human being, and more importantly, great leader.

**2:17** · Yeah.

**2:18** · Well, that was the thing he could do.

**2:20** · He was the best at handling super talented, difficult to handle people of all times.

**2:28** · No question.

**2:28** · Yep.

**2:29** · And you can see it in the doc.

**2:30** · Yep.

**2:31** · There's a moment in the documentary where the camera is following Quincy around.

**2:37** · And he's walking into the studio where the musicians all are.

**2:42** · And he points to the top of the door, and he says, read that.

**2:46** · And there's a sign above the door that he's scrawled on a piece of paper, and he's stuck up there.

**2:53** · This is at around midnight before the recording session supposed to start.

**2:58** · And it says, check your ego at the door.

**3:01** · I think it says, leave your ego at the door.

**3:03** · Yeah, yeah.

**3:03** · Leave your ego at the door, sorry.

**3:05** · Yeah, yeah.

**3:06** · And if I had to summarize Ben Horowitz in one line, I would say he's the Quincy Jones of technology.

**3:14** · That's a lot.

**3:16** · High bar.

**3:16** · Yeah, yeah.

**3:17** · That's hard to take that credit.

**3:19** · He is.

**3:19** · amazing, yeah.

**3:20** · Ben thank you is known for many things, but I think the thing he will be most known for throughout history will be his leadership, the lessons he's left with a lot of people over the years, many leadership lessons which I think are still not legible to the world yet and will only become clear over time.

**3:47** · But today, Ben, I think it would be helpful to take everybody here a little bit behind the scenes of what it took for you to become the Quincy Jones of tech.

**3:58** · You're not supposed to be blushing this hard, Ben.

**4:00** · \[LAUGHS\] Yeah.

**4:02** · Again, you got me and Quincy.

**4:04** · Yeah.

**4:05** · Having known him, he's a very high bar.

**4:08** · That's a high bar.

**4:09** · OK.

**4:09** · Thank you for being here, Why don't we start with-- let's zoom back all the way to the founding of Andreessen Horowitz.

**4:16** · Let's start there.

**4:17** · Yeah.

**4:17** · This is a systems class.

**4:19** · Andreessen Horowitz ended up being one of the most important innovations in the systems design of venture capital, of how capital should be deployed.

**4:29** · Where we'd love to contextualize this is the students have heard that three or four of the largest bottlenecks to progress are context, feedback, compute capital, and culture.

**4:43** · And we haven't talked that much about capital and culture.

**4:46** · So today, I hope you can take us a little bit to the frontier of what's going on in capital and culture, especially in labs, in startups, in teams that are pushing the frontier.

**4:56** · But I think to get there, we should rewind a little bit and start with what was the system that you created to even allow capital to get to this point?

**5:04** · Yeah so we started the firm back in 2009.

**5:09** · And at that time, there were a couple of ideas about venture capital that, I would say, we thought were dated.

**5:19** · One was it was mostly an investment idea.

**5:23** · So the product for investors, LPs, was really good and that they had very high returns, but the product for entrepreneurs I thought was pretty bad in that they didn't do much for you other than give you money.

**5:39** · So that was kind of idea, one that we thought we could just build a better product for entrepreneurs.

**5:44** · And then the other idea that was very, very prevalent in venture capital was this idea that in any given year and the historical data really supported this, there would only be 15 technology companies that would ever get to $100 million in revenue.

**6:02** · So the whole industry was just about getting invested in as many of those 15 as you could.

**6:09** · And that just limited the size of the whole industry and the capital in the game.

**6:14** · And we really thought that was going to change, because, look, at that time, we thought a software was going to eat the world.

**6:23** · And every company that was going to be interesting, every new company was going to be a technology company, and therefore there were going to be more like 200 companies a year that would hit that bar, not 15.

**6:35** · And so we decided that one of the things that I did as the CEO of the operation was to say, OK, how do you scale this?

**6:48** · Because venture capital firms notoriously didn't scale because they didn't have to.

**6:55** · It was I remember Dave Swenson, who was the most famous LP, said, yeah, a good venture capital firm is like the size of a basketball team, five guys and then a six man or something like that.

**7:10** · And that was not going to be enough to have a great product for entrepreneurs and then also invest in such a large number of companies.

**7:22** · And so to get to scale, there was a couple of ideas that we had that-- or sound very, very simple but ended up being important.

**7:31** · The first was, normally, in venture capital, It's a partnership, and the partners share economics and control.

**7:42** · And the problem with that idea, and you experience this in your career at other venture capital firms, is if you share control, then it becomes very, very difficult to change the organization, because everybody's got to agree.

**8:02** · And if you anything about running an organization, the one thing about a reorg is some people are going to hate, it because it's a redistribution of power.

**8:13** · And it's not necessarily the people who aren't good.

**8:16** · It's just some people are just going to hate it, because nobody likes to lose power.

**8:19** · And if people get a vote, then there's no way to effectively reorg a business.

**8:27** · And so our idea was like, you can't share control.

**8:32** · We'll share economics, but we'll centralize control.

**8:35** · And that ended up enabling us to reorganize and enabling us to get into many, many more categories like American dynamism or crypto or bio or these kinds of things, because we could change the organization and scale it and so forth.

**8:51** · And that ended up being an important systems idea.

**8:55** · And then we also-- because investing is always a conversation, and you need a very, very high-fidelity conversation to get to the truth, you never want more people in the room than can have a conversation.

**9:14** · And so you can't have a conversation with 30 people.

**9:16** · It's not possible.

**9:17** · That's a presentation.

**9:20** · Over the years, what do you think is the optimal construct of a truth-seeking conversation when you're trying to understand the future of a technology that's super complex?

**9:27** · Yeah, I think that if you have really good chemistry and rapport, it can be like seven.

**9:34** · But if you don't, then even that gets problematic.

**9:39** · But yeah, you just can't do it with a large group.

**9:41** · And so what we ended up doing is we just kept splitting the firm into smaller and smaller groups over time, and each group would address a certain part of the market.

**9:54** · And that ended up being very effective.

**9:58** · And to contextualize for folks.

**10:00** · So when you started the firm, the first fund was about $300-something million? $320?

**10:05** · $300 million, $300 million.

**10:07** · And you had all these institutional folks like David Swensen and so on who had these long-held, for whatever reason, priors and assumptions.

**10:14** · Yeah.

**10:15** · What did you find was the most effective way to realign them, or get them to revisit those assumptions or update those priors in a way that was aligned with your mission Well, succeed.

**10:26** · I mean, that's all it is.

**10:28** · I think one thing.

**10:29** · You think another thing.

**10:31** · We're going to find out if I'm right.

**10:33** · So then the first thing that happened was we invested a quarter of that $300 million fund into the Skype buyout, out, which everybody thought was insane, but there was a bunch of things we knew that other people didn't know.

**10:53** · So the first thing that made it insane was like the deal itself.

**10:59** · When it spun out of eBay, eBay didn't own the IP.

**11:03** · They own the company but not the IP, which how they ended up there is like a crazy dumb story.

**11:10** · By the way, never do that.

**11:11** · Never buy the company without buying the IP.

**11:13** · So the founders had this hold on them where they could have sued them and shut down the service.

**11:20** · And so everybody was like, oh, that's an unbuyable asset.

**11:23** · But we knew the founders, Janus and Niklas.

**11:26** · And we knew the one thing they had in life that defined them was Skype so they weren't going to shut that thing down.

**11:34** · It was just a matter of how much money did they want?

**11:36** · Did they want to be on the board?

**11:38** · The IP at the time was basically the Skype client and the user base?

**11:41** · It wasn't the client.

**11:42** · It was the underlying library that controlled the protocol.

**11:45** · Oh, sure, yeah.

**11:46** · The communications protocol.

**11:48** · Yeah, which was very hard to replace and all that kind of thing.

**11:52** · So anyway, we bought it, and everybody goes, OK.

**11:55** · Well, even though we thought you were nuts, maybe you're not completely insane.

**12:01** · There's so many interesting parallels to that era now.

**12:04** · But one property of that era was the explosion of networks.

**12:10** · Yeah.

**12:10** · The idea of network effects became legible for the first time as a systems concept.

**12:14** · So can you talk a little-- take us back.

**12:16** · I think it's hard for people now, or we just take these for granted.

**12:18** · But at the time, can you talk about why was it novel, why were people resistant to it, and what were the insights that then led to the architecture, the firm being a network effect-driven firm?

**12:29** · Yeah, I mean, I think people just didn't understand network effects as well.

**12:33** · So the big era of networking started with the internet.

**12:36** · And then people thought the internet itself was just like a unique network.

**12:40** · And it was weird.

**12:41** · It was different, because nobody-- people got value from things built on the internet, but the internet was not owned by anybody.

**12:51** · It was like the first, real, decentralized network.

**12:55** · And so people didn't what to make of networks that like Facebook early on had-- there weren't a ton of people giving them money for the first round.

**13:09** · That's why Peter Thiel was able to do it at a really good price.

**13:14** · And then the same thing with Twitter, and so forth.

**13:18** · People just didn't know basically how invincible those things got when you got them up to strength so that the bigger-- it's basically like an N squared value so every node you add kind of increases the value by N squared.

**13:40** · So if you have five people on the network, that's 25.

**13:44** · But if you have 6, that's what?

**13:46** · 36 and so forth.

**13:48** · And the value, if you get up to internet size, is just invincible.

**13:51** · Nobody's going to ever build a rival to the internet or very unlikely.

**13:57** · And so at that point, us being involved in the internet and Twitter and Facebook and so forth, we had a really good understanding of that.

**14:07** · And so we always thought of the firm as a network.

**14:13** · And so from the very beginning, we thought, OK, the more relationships that we have, the stronger our network effect.

**14:22** · And so we ended up doing things that other firms didn't do like we tried to build relationships with every engineer in Silicon Valley and every executive and every everything and then every corporation that bought technology and so forth.

**14:38** · And we were, in our minds, creating this network effect that would just make us the best place to raise money from, because we were like an automatic you could tap into that network and become extremely powerful, right off the rip.

**14:54** · And I think a lot of people didn't understand how hard that was to do.

**15:02** · And then the bootstrapping of any network is always the most difficult thing.

**15:06** · So, yes, if you have a network with a billion people on it, it's going to be very valuable.

**15:10** · But how did Alexander Graham Bell sell the first telephone when there was nobody to talk to?

**15:17** · That part is actually really hard.

**15:19** · And so figuring that out and how to bootstrap the network effect, coming from behind in venture capital was the idea.

**15:26** · Well, I mean, could you say a little bit about how you bootstrapped it?

**15:29** · What were the things that maybe now lost to the annals of history, where they were individuals or asymmetric-- one of the things we talked about in the first class is often the students get excited about the speakers like you up here, but we reminded them that one of the most valuable assets they have is the people sitting next to them.

**15:45** · It's the relationships they build.

**15:46** · When you were bootstrapping-- I think that's getting more important, by the way.

**15:49** · Exactly.

**15:50** · If there's anything that's going up, it's that value.

**15:51** · But if you zoom back, when you were starting that bootstrapping and you didn't have the largest firm in the Valley, you didn't have the most capital, you had no track record as a venture capitalist other than your angel investors, what were the moments where that may not be legible to folks here, that you used something that was asymmetric, that allowed you to bootstrap the network?

**16:10** · Well, the really simple idea was we knew, like venture capitalists made a lot of money.

**16:14** · So they would take the fee money and then they'd pay themselves big salaries.

**16:17** · And so we were like, well, what if we didn't pay ourselves anything and we just took all the money and we basically spent it on building this network?

**16:27** · So we would hire people to bring people in with our kind of, how do you get relationships with every big corporation, FedEx and this and that and the other.

**16:38** · And the trick that we had there was we had sold the previous company to Hewlett-Packard.

**16:46** · And so we knew the people in their enterprise briefing center.

**16:49** · And so we would call them every week and say, who's coming to the briefing center this week, and can we get their numbers?

**16:55** · And we would call those companies, and we would have them come to our briefing center, and we'd just show them all the startups.

**17:01** · So it would be like-- and we'd have everything they like, all the donuts and all that stuff.

**17:06** · So it was very unventure capital-like, but the corporations loved it.

**17:10** · So all of a sudden, we knew more big companies than VCs who had been around 50 years because we had this hack through the HP enterprise briefing center.

**17:21** · I think it's very poetic that we're sitting in Hewlett 200, by the way.

**17:23** · This is the name of the auditorium.

**17:25** · It all comes back full circle.

**17:26** · So when you started doing that, usually when somebody new shows up on the block with an insight like that, from a systems perspective, what we've observed is often the antibodies come out.

**17:40** · The immune response of the existing incumbent system comes out.

**17:44** · Yeah At the time, I was across the street with Mike, actually at Kleiner.

**17:47** · And I remember there was-- a16z was in the headlines all the time.

**17:53** · And our CMO at the time, great great lady.

**17:56** · But I remember taking one of the headlines to her and saying that we should do this too.

**18:00** · And she said, Anj, this executive briefing center, oh, that's just marketing.

**18:05** · And I said, yeah, that's your job.

**18:09** · This is working.

**18:10** · And I've been consistently shocked by the number of times a16z has done something from a product insight, deliver that to the entrepreneur, and then everybody else just says, oh, that's just marketing.

**18:21** · Am I being overly facetious, or is that true?

**18:24** · And what were the immune responses like that that you were experiencing and how did you deal with them?

**18:28** · Yeah.

**18:29** · Well, it's funny, because every time we meet with our investors, our LPs, they would say, every time we meet with another venture capital firm, all they want to do is talk about you and say mean things.

**18:42** · And I'm like, well, that's fantastic.

**18:44** · That's great.

**18:45** · The best form of flattery.

**18:45** · That's good.

**18:46** · They used to call us a-ho.

**18:48** · That was their nickname, the other VCs.

**18:50** · They hated us.

**18:52** · But some of it was my fault, though.

**18:54** · Because when we started, I was coming from enterprise software, which was a very competitive, bare knuckle kind of there's no such thing as coopetition in enterprise software.

**19:04** · It's just kill or be killed.

**19:06** · So I did it like-- I wrote this blog post called forth things that VCs do that I don't like where I just attack them all.

**19:16** · And then I did this big-- Sarah Lacy had this big, big event.

**19:24** · And she interviewed me on it.

**19:25** · And she was like, well, you seem like you don't like other VCs.

**19:29** · And I quoted Lil Wayne, and I said, when I see another VC coming at me with a peace sign, all I see is the trigger and the middle finger.

**19:37** · And everybody hated me for that.

**19:42** · But it worked.

**19:43** · Because they hated me so much, they weren't willing to copy what we were doing, even though what we were doing was working.

**19:50** · So it backed-- I would have been that antagonistic again, but it worked, so you can't argue with it.

**19:58** · Well, OK.

**19:59** · Well, I think we should come back to that later, and then what do you do differently.

**20:02** · Yeah.

**20:03** · So great.

**20:04** · You bootstrapped the network effect.

**20:06** · That allows capital deployment to start scaling into a bunch of startups.

**20:11** · Now, It really does feel like a Back to the Future moment a little bit, right?

**20:15** · Yeah, yeah.

**20:16** · What's going through your mind right now?

**20:18** · Yeah.

**20:19** · I mean, so the big thing that's changed is that-- or the most fundamental thing that changed from a VC standpoint in my mind is it used to be-- I mean, for my entire career, the one thing that you knew about technology companies is you couldn't throw money at the problem.

**20:41** · So if somebody had a two-year lead on you, you could not hire 1,000 engineers and catch them.

**20:48** · That was never going to work, because nine women can't have a baby in a month.

**20:53** · There were just things you could not parallelize and then the communication overhead would kill you.

**20:58** · And my favorite joke used to be, you know, what's a \[INAUDIBLE\]?

**21:01** · It's like 700 IBMers before lunch.

**21:04** · It's nothing.

**21:06** · You can't catch that that way.

**21:09** · With AI, that's really changed and that you can throw money at the problem.

**21:14** · Because if you have enough GPUs and enough data, you can basically solve most problems right now.

**21:20** · t That just is what it is.

**21:22** · And so now, the capital race becomes a real thing and you have to think through, OK, code is not really a moat the way it was in the past.

**21:36** · And user interface isn't really a moat and so what is your barrier to entry?

**21:43** · What is the thing that differentiates you over time?

**21:47** · These have become really, really different.

**21:49** · And it's happening at the same time that.

**21:52** · demand for the technology is unlimited, because the products work so much better than anything we've built before.

**21:58** · These AI, I mean, many of you are too young to remember the products of old, but none of them work this well before.

**22:05** · This is wild how well this thing works.

**22:07** · Oh, you mean companies didn't always go from $9 to $30 billion in run rate in six weeks, yep.

**22:11** · But the reason they go that fast is like you use them and you go, wow, this works perfectly.

**22:18** · How can I do more with it?

**22:21** · Whereas in the old days, if you bought Siebel Systems software, it took two years to deploy the thing and $1 million at minimum.

**22:29** · And so that's going to limit demand.

**22:33** · There is no limit on demand when technology works as well.

**22:36** · So you would say, Anj, the technology is working in a way that collapses the gap that existing incumbents might have as a result of their human capital investments over the last, whatever decade of software.

**22:53** · There's willingness to pay at levels that are exploring it?

**22:57** · I mean, the return is crazy.

**22:58** · So I mean, if you make an engineer 20 times as productive.

**23:01** · And you're paying that engineer-- well, if you're Zuck, you're paying that engineer $1 billion.

**23:06** · But if you're paying whatever, it's going to be at least several hundred thousand dollars a year.

**23:14** · That's a hell of a return.

**23:15** · Right.

**23:15** · So that creates this-- so the final project for the class for the students is the one-person frontier lab, because what we're trying to get everybody to realize is there's actually an extraordinary amount they can accomplish with the right tools.

**23:28** · Yeah.

**23:28** · Right?

**23:29** · But-- And we have an entrepreneur like that right now, building a global VPN by himself.

**23:34** · By himself, yeah, yeah.

**23:35** · And this started to become more common, I would say, when we were seeing pictures almost a year and a half-- two years ago now, right?

**23:42** · Yeah.

**23:43** · What does that mean for folks here who don't have necessarily access to the most capital, may not have access to a ton of compute either but want to make a difference to the frontier?

**23:57** · Well, I mean, I think saying just be careful, a little careful with people who don't have access.

**24:06** · Anybody with a great idea these days has-- trust me-- have access in that.

**24:15** · There's unlimited money for good ideas currently.

**24:19** · Maybe that changes over time, but it's definitely there.

**24:24** · And I would just say this.

**24:27** · The world is changing, and you can just think of it as like the jobs we had before the Industrial Revolution are all gone and we've been living with the post-Industrial Revolution and then the post-computer age jobs since then.

**24:47** · And we're going to get to a whole other class of jobs and a whole other class of companies over the next 10 years that replace most of what we have now.

**25:00** · And so if you're young, that's the best thing possible for your career and for your life.

**25:07** · Because in the opposite scenario where it's all the same companies, then you got to start at the bottom and work 30 years to get yourself to be a mid-level manager, and you've got a politic and then the old people who aren't as smart as you get all the money and that sucks.

**25:25** · But in this world, it's the old people who will have the challenge because how to do the old thing.

**25:30** · They don't how to do the new thing.

**25:32** · And you can walk in and learn anything.

**25:34** · I think that the main thing is just understand the future and then the future is yours is the way I would think about it if I was 19 or 20 years old.

**25:44** · Well, you said something pretty important there, which is for the right ideas, there's unlimited capital.

**25:50** · Could you talk a little bit about what do you think is the shape of good ideas today that's emerging in your mind?

**25:58** · Well, look.

**25:58** · I mean, I think that it always comes down to like, can you build something, a product, an organization, a culture, an offering that people want?

**26:13** · And then if you don't build it, is it getting built by somebody else?

**26:18** · Or do they need you to do that?

**26:20** · Does the world needs you to do that, or it doesn't exist Is always the best entrepreneurial idea.

**26:26** · And so anything that needs to exist that doesn't otherwise exist is a good idea.

**26:33** · And, look, that was the whole story with the venture capital firm.

**26:36** · Now, did the world need another venture capital firm?

**26:40** · Generically, no.

**26:42** · Did it need a different kind of venture capital firm?

**26:44** · Absolutely it did.

**26:46** · And so that's what we built. Now, I think that's true for-- I mean, if you look at OpenAI, they weren't the only ones trying to do AI like Google.

**26:59** · It was assumed Google was just going to own AI.

**27:02** · And it was panicking everybody.

**27:03** · And that's why Elon, by the way, co-founded it with Sam.

**27:09** · And Elon is still mad about what Sam did with it, but that's a different, longer story.

**27:14** · But it was one of those things where we need an AI, we need an alternative.

**27:18** · The world needs this alternative to Google, and, that becomes a really, really good idea.

**27:25** · And, look, the world is changing so fast that the new needs are going to multiply.

**27:31** · There's going to be many, many, many things that need to be done.

**27:35** · I mean, if you look at-- I think the old-- the one thing that's interesting about the SaaSpocalypse is it's definitely true that the barrier to entry on building software and user interfaces is getting much smaller.

**27:51** · But by the same token, the most boring thing in the world is to just rebuild Salesforce.

**28:03** · Salesforce had a half the cost or a quarter of the cost isn't nearly as interesting as like, what do you really want for your sales organization?

**28:11** · Because it's not that.

**28:13** · I mean, I don't think.

**28:14** · And then the question is, can you build it before they can?

**28:17** · But do you really want your salespeople entering data in a crappy user interface and then most of the things that they work on aren't captured in the system and this and that and the other.

**28:29** · So going to the future, figuring out in a world of AI, what does that look like, yeah.

**28:36** · One of the traps that students often fall into is I call it the dorm room problem which is you've got direct visibility into problems that are in the light cone, so to speak, of your visibility, which is quite narrow when you're still a student, right?

**28:59** · Yeah.

**29:00** · And sometimes, when your friends are high in the dorm room and you have that conversation, it sounds really good.

**29:05** · It's not actually that good.

**29:06** · You should at least sleep for one night.

**29:07** · Yeah.

**29:07** · I've seen a lot of those over the years.

**29:10** · Yeah, yeah.

**29:10** · Make sure it sinks in, and you still think it's a good idea.

**29:13** · At least one night of sleep.

**29:14** · Yeah, yeah, yeah, yeah.

**29:15** · But just because you're a student in a dorm doesn't mean you don't want to have an impact on big problems and work on things that have an impact at scale.

**29:28** · And sometimes these things are mission-critical things, health care, financial services, the economy, selling the enterprise, but these things are not directly in your line of sight when you're very young.

**29:40** · And how would you advise folks to-- in particular, to bring it back to these AI systems, the context feedback loop we've talked about is quite critical but getting access to those context feedback loops when they can make a huge difference is challenging when you're young in your career and you don't have a big network and so on.

**29:55** · So how would you go about bootstrapping that problem?

**29:57** · Yeah.

**29:58** · Look, I think the main thing is to just solve a problem.

**30:01** · And what tends to happen is when you go to solve a problem, particularly if it's a hard problem, you find some other problem that's more important.

**30:10** · And this is well known in scientific discovery.

**30:12** · Penicillin was an accident.

**30:15** · They weren't trying to solve that one.

**30:17** · It just rolled off of the side.

**30:19** · And then, by the way, Meta was an accident.

**30:24** · He was building Hot or Not.

**30:25** · And he stumbled into, this much bigger idea.

**30:31** · And my friend Drew at Dropbox, he was literally tired of having USB where he'd have to move his presentation from one thing to another.

**30:44** · He was just solving a problem for himself.

**30:46** · So I think the best way to come on a really important idea is to go try and solve something, not necessarily build a company, just try and solve the problem.

**30:57** · And then in that problem, if it's like a problem that you have, that means it's probably real.

**31:03** · And then in solving it, you'll probably-- or you'll likely find something much bigger.

**31:09** · And then that may force you to build a company.

**31:13** · And those are the things that work the best that we've seen are these big things.

**31:17** · I mean, it's really hard to-- and even Elon Musk didn't start his career trying to build Tesla.

**31:23** · He was solving a much smaller problem, and that's generally how you build up to that I think trying to swallow the Earth from the beginning with no experience doesn't usually work, It's good for your pitch deck, but it's not good for your company.

**31:42** · I think Elon's first attempt was like a yellow pages competitor or something like that.

**31:46** · Yeah, yeah, yeah, exactly.

**31:47** · Yeah, yellow pages and then PayPal and then Tesla and then SpaceX.

**31:54** · Well, so on that point, the time horizon on which sometimes you find entrepreneurs have an impact on humanity is quite long.

**32:04** · They bootstrap the impact-- I would say or let me put it this way.

**32:08** · One of the old ways we've seen the generation of entrepreneurs that belong to Elon's generation is that they feel like they have to start, somewhat with a narrow scope and then bootstrap, bigger and bigger scope with every successive project.

**32:21** · But just a few minutes earlier, you said, actually, things are going through a lot of change.

**32:25** · Yeah.

**32:26** · You can have a lot of impact very quickly relative to incumbents who may have had to be a little bit more measured in their approaches.

**32:34** · How do you resolve these two?

**32:35** · I think thinking of it like how big a thing am I going to do is the wrong way to think about it.

**32:42** · You have to start with, what problem can I solve?

**32:47** · And then If you can solve that problem, that's where to start.

**32:53** · You have to size it to you.

**32:54** · Not everybody is the same.

**32:56** · Different people have different capabilities.

**32:59** · You become your full, most effective self at a different age.

**33:05** · Some people are really good when they're-- by the way, Zuck is way different now than he was when he was 20 years old.

**33:12** · When he was 20 years old, it's a miracle.

**33:16** · If he didn't have a network effect business, that wouldn't worked at all.

**33:19** · He just wasn't very good.

**33:22** · But he developed that entirely over the year.

**33:25** · And because he had that kind of business that had a vertical takeoff, he could develop into that.

**33:32** · And, look, so if he didn't have that he might have been better off, finishing Harvard or whatever.

**33:38** · That was just one of those things where he happened to solve a problem at that age that was important enough that it created a company.

**33:45** · So I want to take it in a slightly different direction, which is-- or analogous, which is when Facebook was getting started, it had a very unique culture and-- Some good, some bad.

**33:59** · Yes.

**34:00** · And it's not always clear what is good and what's bad until much later.

**34:04** · I think my friend Sean got in trouble with the law with that culture, but yeah.

**34:08** · Well, didn't he get in trouble for Napster?

**34:10** · Wasn't that one culture earlier?

**34:11** · Sean got in trouble at Facebook also.

**34:13** · At Facebook as well.

**34:14** · OK So I don't know-- And that was a different problem with the law at Facebook.

**34:17** · I see.

**34:18** · Yeah, he generally tends to get into trouble a lot, but-- He is a genius, though.

**34:24** · Well, this is the thing.

**34:25** · With genius where you often find outlier technical and/or any kind of outlier capability, often you find-- one of the problems I'm discovering today in the field is that you often have really talented teams try to start a new lab or a new company.

**34:41** · And sometimes they fall apart.

**34:44** · They just don't get very far.

**34:45** · And from the outside, you'd be like, oh, this is totally going to succeed, star entrepreneur, lots of capital, great problem.

**34:51** · And then 6 months in to 12 months in, teams are just struggling a lot to make progress.

**34:58** · And sometimes people leave.

**35:00** · They got a-- why is that?

**35:02** · What do you think?

**35:03** · It is about the right cultural initialization that sets apart teams that can do this and hit that takeoff versus stumble along and how do you skip the painful parts?

**35:12** · Yeah.

**35:13** · So I think there's a few things.

**35:15** · First of all, building a company is hard.

**35:19** · And no matter what era or whatever, the press always makes it seem easy, because they hate entrepreneurs.

**35:27** · But it's not easy.

**35:29** · It's always extremely hard so some are going to fail.

**35:32** · I just say that up front.

**35:36** · But in terms of the team and the dynamic and so forth, yeah, it's a combination of leadership and culture.

**35:43** · And culture is a very amorphous thing, but it ends up being very important.

**35:50** · So basically, the way to think about it is it's not like-- people think of culture as corporate values or some bull \[MUTED\].

**35:59** · But it's not that.

**36:02** · It's not, we have integrity.

**36:04** · We have each other's backs or like some of these whatever platitudes that people say.

**36:10** · It's like, how do we behave exactly?

**36:13** · What are the behaviors?

**36:15** · This summer, I have a great line, which is a culture is not a set of beliefs, it's a set of actions.

**36:21** · And so what do we mean by behaviors?

**36:24** · Well, do we come to the office or not?

**36:28** · Do we go home at 5:00 or do we stay longer?

**36:36** · If somebody asked me a question, do I get back to them instantly or in a week?

**36:44** · All those kinds of things end up mattering like, do we believe the best idea wins, or does it like matter who was the founder?

**36:55** · All that stuff, you have to agree on as a team and like very specifically not just some highfalutin idea.

**37:09** · And then you have to live by it.

**37:11** · And then if you have that, if you have a standard, if you have a cultural standard, then if somebody's not living up to that standard, then it's a simple thing.

**37:20** · If you have no standard and people aren't living up to where you want them to, then you're pissed.

**37:28** · But then that just starts infighting.

**37:29** · Then it gets political, because it's like, well, why \[MUTED\] is he going home?

**37:35** · Well, we never said that he needed to be here.

**37:37** · We never agreed on that.

**37:38** · He has a date or whatever, or he's got a family.

**37:44** · He's got to go home.

**37:45** · We never said what that was.

**37:47** · And then people stop liking each other.

**37:49** · And then you hit the first, hard issue and it's like, F it.

**37:54** · I'm out.

**37:55** · OpenAI is going to pay me a lot of money.

**37:56** · Screw you guys.

**37:57** · Screw you guys.

**37:58** · I'm going home, as Cartman would say.

**38:01** · But what happens if you started by standardizing on some set of beliefs, set of actions.

**38:07** · And then the world changes?

**38:10** · And what you thought was going to be the right standard six months ago in a world where stuff changes so fast, needs to be updated?

**38:18** · Yeah, yeah.

**38:18** · Look, cultures can evolve, but you have to evolve together.

**38:23** · And you need a leader.

**38:26** · Having this is why I hate the idea of co-CEOs or like, we're all equal or we're going to run a Communist organization.

**38:35** · It doesn't actually work in a company, because you need somebody who's going to break the tie.

**38:41** · OK yeah.

**38:41** · You want it to be that way.

**38:42** · You want it to be that way.

**38:43** · We're going this way.

**38:44** · If you don't like it, out.

**38:46** · That's how you have to run an organization in order for it to succeed.

**38:51** · And I think we culturally got away from that idea in Silicon Valley a little bit.

**38:59** · In the end of the fat, happy network effect era.

**39:03** · But it's back now so I think-- Could you say more?

**39:05** · What do you mean by that?

**39:07** · Well, everybody wanted a vote on what the company values were and this and that.

**39:13** · And then CEOs caved to that and that ended up not working well for any-- Right, right.

**39:21** · Companies are not democracies.

**39:22** · They are-- Yeah.

**39:23** · Well, I think a dictatorship always beats a democracy in a competitive battle.

**39:28** · And so because it takes a long time to decide things in a democracy.

**39:33** · Now, look, for a country, it's different.

**39:36** · There are things when you have to last several hundred years that no matter how good the monarch is, if they die and a worse monarch comes into play, that could be an issue.

**39:52** · Well, I'm going to push a little bit on this assumption that it's different for countries versus companies, because something I've learned from you is the way you approach-- the businesses I look up to the most, especially the ones in the a16 portfolio, are often with leaders who are thinking so long term.

**40:09** · The way they talk about their impact on humanity is not that different from the time scale sometimes of political leaders.

**40:16** · In fact, arguably, some of the entrepreneurs are thinking longer term than political leaders these days.

**40:22** · Well, it is longer term.

**40:25** · So if you have a king-- let's say you had a king running the United States.

**40:29** · If it's a great king who was not interested in their own, enrichment or their family or their friends and so forth, that works like-- Who cared about the public benefit basically?

**40:43** · Who cares about the public benefit, I think that works better than our current system.

**40:48** · The problem with it is as soon as you get somebody who's not like that, that's just too much power so you're better off decentralizing power so that the system is resistant to bad leadership.

**41:01** · I think a country has to be resilient to bad leadership and that, look, if a company goes away, OK fine, whatever.

**41:13** · Well, Dave Packard and Bill Hewlett, they're gone.

**41:18** · They passed away.

**41:20** · The new leaders weren't so good.

**41:22** · That's the end of the company.

**41:24** · Fine, whatever.

**41:25** · It's a company.

**41:26** · Yeah.

**41:26** · They did their thing.

**41:27** · They did their job.

**41:28** · They fulfilled their mission.

**41:30** · A country has to persist beyond that.

**41:32** · And so I think we already see that here be it like on the nation level, on the state level.

**41:41** · Even on the city level, you can see like eventually you get politicians who just start giving stuff to their friends and then everybody suffers.

**41:50** · At least you can vote them out.

**41:52** · At least you can do something.

**41:53** · Whereas in a company, you want to be as efficient as possible while the sun is shining.

**42:03** · I know I could keep going forever, but we probably have a bunch of questions piling up.

**42:06** · So I'm going to ask you one more question and then we're going to switch to the students, yeah, which is you talked about David Swensen and he had some strong assumptions that then you felt-- these were leaders of the previous generation that you felt just didn't get it.

**42:23** · Well, I just think that, not that he-- by the way, Yale is still an investor in us today.

**42:32** · So I just think you can't let your investor-- by the way, including us-- run your company because you're on the ground in real time seeing what's happening.

**42:44** · They have knowledge of the past, and they have a light knowledge of what you're doing but not full of context.

**42:52** · So they can be-- it's an interesting conversation, but the investor can't run the company.

**42:58** · And then that's just the way it was with him and us, yeah.

**43:01** · Well, so my question for you is what prior do you feel like you now have to update so that given that you felt like Yale at that time, needed to update their priors faster today, what do you feel is like the biggest assumption that you've changed about the venture capital industry that maybe was a strong belief you held 10 years ago?

**43:23** · Well, I mean, like I said, I think-- well, one, I mean, there are so many things that are changing.

**43:31** · And I talked about like you can throw money at the problem.

**43:34** · That's a massive change.

**43:36** · I think that the bottlenecks have moved.

**43:40** · So we used to have a bottleneck on software engineers.

**43:44** · I think we've got bottlenecks on things like electricity now.

**43:47** · So I think that changes how we think about investment.

**43:51** · And then companies are so big in the private markets that they now require things that venture capital firms didn't previously provide.

**44:04** · So when you get up to $1 billion in revenue, then you have to be multi-country, multi-channel, multi-product.

**44:12** · These capabilities, most VCs just have never had, but I think now we have to have them.

**44:22** · And then I think, the private capital markets don't have all the functions of the public markets so, that needs to be addressed.

**44:31** · So there's a lot of things that are changing.

**44:33** · This is definitely not a new question.

**44:35** · It's a follow-up to that, which is you said culture is a set of actions.

**44:38** · Yes.

**44:39** · By the way, this is on the wall at a16z.

**44:42** · And every day, I would go to the office in San Francisco.

**44:45** · And I'd rent one of these.

**44:46** · We could all book our own offices.

**44:48** · And the one that was my favorite was in the back corner closest to the bathroom, because I could dash to the bathroom between meetings.

**44:54** · But in that corner, it says from the Bushido, culture is a set of actions, not just beliefs.

**45:00** · Yeah, I mean, look, I tell people when they come in like, I don't care what you think.

**45:02** · I don't care how you feel.

**45:03** · I don't care what's in your heart.

**45:04** · I just care what you do.

**45:05** · And what you do matters, and that's why you have to your own organization, or you get into this.

**45:12** · So I mean, that's my follow-up is a culture is often also what you don't do what you say no to.

**45:18** · Yeah.

**45:18** · What are the things that you've had to say no to because you're like, well that's just not-- that.

**45:23** · could be an interesting opportunity.

**45:24** · It might even help an entrepreneur out, but that's just not in our mission.

**45:28** · That's not us.

**45:29** · Yeah.

**45:29** · Well, so I'll just give you one example.

**45:31** · So the biggest one that got proposed to me like 18 times was, well, with AI, AI is like-- it's very much like when the spreadsheet happened, that launched private equity because all of a sudden you could go in and make all these big companies much more efficient by having them adopt this new technology.

**45:54** · And AI, even more so.

**45:56** · You can go in, and you can go into an old company and you can make it much more efficient with AI.

**46:03** · And there's many VCs who are going with that idea.

**46:08** · And for me, I would say two big reasons I didn't want to do it.

**46:13** · One is it's culturally the opposite of venture capital so-- Like leveraged buyouts, basically.

**46:21** · Yeah, LBOs.

**46:21** · So venture capital is about investing in entrepreneurs with new ideas and focusing on how they can grow fast.

**46:31** · Leveraged buyouts are about entry price, making it more efficient, firing people.

**46:39** · And I don't really want to grow it.

**46:42** · I just want to make more money out of what it is.

**46:47** · And so if you're in the venture capital mindset, you're looking for the great entrepreneur to go build something amazing.

**46:57** · If you're in the leveraged buyout market, you're caring about like, OK, I'm going to bring in a professional.

**47:02** · I'm going to have them run this more efficiently and so forth.

**47:04** · So it's the opposite motion.

**47:06** · And so for me, I was like, well, I don't want to split the culture that way.

**47:10** · I think that's not going to be a good idea.

**47:13** · And then the other thing is like, I don't want to do that with my life.

**47:16** · I have the opportunity to fund the greatest, new ideas that are going to push humanity forward or like that.

**47:22** · It's not stupid.

**47:23** · I think it's a good business, but it's not a business for me.

**47:26** · So sometimes you're saying it's OK to impose bottlenecks on your own growth, because that's just not what is fine.

**47:32** · You don't have to be in every business just because there's money there.

**47:38** · Look, I believe in like you build a company to do something larger than yourself and make the world a better place.

**47:46** · And then if you do that, you will make money.

**47:50** · But if you are in business just for making money, look, that's not for me.

**47:58** · There are a lot of people who think that way, and I'll let them do that.

**48:02** · But I think that great companies don't think that.

**48:06** · To me, companies that you would want to be part that I would want to be part of don't work that way and so I'm not going to build that thing just because like, oh, there's money over there, or let's go run to the money.

**48:19** · We're going to switch to questions.

**48:21** · So the way it's going to work is they've been putting their questions in Discord, and they're all voting on each other's questions.

**48:26** · And the top ones that get voted by each other, we'll go through them one by one.

**48:30** · First question.

**48:31** · The question is, if I was a college student, where would I put my energy and effort and what do I think about encouraging people to drop out of college?

**48:43** · So I think that if I was in college now, I would put a tremendous amount of-- I would view AI as a very powerful tool set.

**48:55** · So almost think of it like-- I think the best analog is electricity so like, OK, if you knew electricity was coming and you wanted to do something interesting in life and you were in the pre-electricity world where it's six o'clock.

**49:11** · We got to be at home, because it's going to get dark.

**49:14** · We're not going anywhere like that world.

**49:16** · Sounds like San Francisco.

**49:17** · \[LAUGHS\] Yeah.

**49:18** · Well, yes.

**49:22** · So then, OK, this whole new world is coming, let me really understand this technology and then what is interesting to me in the world, and that could be biology.

**49:34** · It could be material science.

**49:36** · It could be rocketry.

**49:37** · It could be anything, but you want to have those tools in your bag when you go do that.

**49:44** · Or it could be-- by the way, it could be in the creative field.

**49:47** · So people, I think, misunderstand what's about to happen in the creative world.

**49:53** · But somebody who in my era would have been a pretty good guitar player, can now make a sci-fi motion picture scored and everything by himself.

**50:07** · And so the world is really, really different.

**50:10** · So I would definitely figure out what I'm interested and then master this new tool set and apply it together.

**50:19** · I think that's probably the thing that's definitely going to work.

**50:24** · In terms of dropping out of school, I think that this is very individual-based.

**50:34** · You'd mature at different points in life.

**50:38** · I finished college myself, and that was good for me.

**50:44** · I think it was good for Zuck to drop out, given the idea he had and given the kind of company he was able to build.

**50:54** · And so I think that with career advice, let me just say this, that nobody can give you good career advice.

**51:04** · They can give them good career advice.

**51:06** · So I can give you good advice for me.

**51:08** · I can't give you good advice for you.

**51:09** · And particularly your friends are going to give you good advice for them, not for you.

**51:15** · And so don't listen to your friends and figure out who you are and what the best path for you is, I would just say on that.

**51:23** · Yeah.

**51:24** · So by the way, so just on political donations, I also donated $5 million to the Kamala Harris campaign.

**51:32** · Important fact.

**51:33** · Yeah.

**51:33** · Often not reported on.

**51:36** · Well, it is reported out on Twitter every time the MAGA people get mad at me.

**51:41** · Look. on politics-- or let me just tell you where that came from and how I'm thinking about it, in general.

**51:51** · Tech had very little voice in Washington, DC, and that had extremely severe, negative consequences for tech and specifically so I can go through a few things in the Biden administration.

**52:03** · One is they basically almost ended the crypto industry by enforcing things that weren't even in the law to shut down companies.

**52:13** · And then the same thing was happening with AI.

**52:18** · So the last Biden administration executive order was to require for all sales of GPUs worldwide that any time you sold one, you would first need government approval, US government approval.

**52:34** · So that would have basically taken us out of the AI race entirely.

**52:38** · And the issue behind that was basically that we had no voice.

**52:46** · The whole industry had no voice in Washington.

**52:49** · So we launched a very, very big effort to have a voice in Washington.

**52:54** · And I would say that it's worked very well.

**52:58** · So we have much better AI policy, much better energy policy, and much better crypto policy now than we did before we got involved.

**53:08** · So I'd say I'm very happy about that.

**53:10** · And then all the money and conversations have been about that.

**53:16** · Look, I mean, the other thing is-- like I said, I gave money to Kamala, because I'd known her for 15 years.

**53:24** · She's been to my house 17 times.

**53:26** · My wife sat next to her in church the whole time so I knew her, so I knew I could talk to her.

**53:31** · Biden, we never could get a meeting with Biden for the whole time he was in office.

**53:39** · And if you speak to Tim Cook or Sundar Pichai or Dave Ricks, who runs Eli Lilly, none of them got a meeting with him in four years.

**53:48** · Now we all know why now.

**53:50** · But at the time, we didn't.

**53:52** · And the result of that was tech had no voice in Washington for those times.

**53:56** · So I guess the answer is, yes, I'm happy with that.

**53:59** · \[LAUGHTER\] Oh, here we go, Ben.

**54:08** · That's a good question.

**54:09** · So the question to repeat the question for the podcast is how do I think being in a rap group in college affected me and then can I rap for us now.

**54:21** · So the story of that was I had a friend who got shot in the face and became blind.

**54:30** · And so we started a-- and he was very, very depressed so I would send him rap music.

**54:36** · And in those days, rap had just gotten started.

**54:40** · And that cheered him up over time so we started a rap group called the Blind and Def Crew, D-E-F.

**54:49** · And we became a group and I wrote some rhymes.

**54:52** · So one of the rhymes was the blind, def crew, you know we're fly.

**54:57** · Three of us, but we got four eyes.

**54:59** · Because he got his eyes.

**55:01** · All right.

**55:01** · \[APPLAUSE\] Thank you, Ben.

**55:05** · \[LAUGHS\] There are so many very memorable and intriguing pitches.

**55:15** · Well, one of the most memorable was actually Databricks, because it was so bad.

**55:20** · So the pitch was the-- Ion Stoica, who was a professor at Berkeley, presented the company.

**55:27** · And the slides he made.

**55:28** · It was like going to a computer science lecture that you couldn't understand in college.

**55:35** · That's what the Databricks pitch felt like.

**55:38** · So that was very memorable.

**55:40** · It was memorable because of that.

**55:41** · And then it was memorable because of what it turned into.

**55:46** · But-- Well, if you couldn't make sense of it, why'd you invest?

**55:51** · Well, the whole reason I had them come in to pitch is because Scott Shenker, who was another professor at Berkeley who I knew, had called me and said, Ben, I have the best distributed systems guy that we've seen in the last 10 years in academia.

**56:06** · His name is Matei Zaharias.

**56:09** · Do you want to meet him?

**56:11** · And I knew as soon as he said that to me, I was going to invest in the company, yeah, yeah.

**56:16** · But that pitch scared my partners.

**56:20** · Thank God they didn't talk you out of it.

**56:22** · Yeah, yeah, yeah.

**56:23** · Yes, it's funny.

**56:27** · So the question is about Cluely and what do I think about it now in terms of momentum and this and that and the other.

**56:35** · Look, I think that an easier way to think about it is we invest in founders.

**56:42** · And, you want founders who are original thinkers and have breakthrough thinking on whatever it is they're working on.

**56:53** · And I think those guys had a bunch of breakthrough ideas, including marketing.

**56:58** · I think they are marketing geniuses in a sense in that you know about them.

**57:07** · They're not the biggest company in the world, but they're the one that you know about.

**57:12** · There's something to that.

**57:13** · So what it becomes from here and where it goes, we'll see.

**57:18** · But like, hey, I say these things are early.

**57:21** · And there's only one unforgivable sin in business, and that's running out of money.

**57:27** · And until you've run out of money-- I don't count any of these companies out, by the way.

**57:35** · Slack was in dire straits before he figured it out.

**57:39** · He had built a game on flash called Glitch, and Steve Jobs outlawed flash on the iPad.

**57:46** · And it was an iPad game.

**57:48** · And I'm like, that's how dead he was.

**57:50** · And he had $6 million left.

**57:52** · And he turned it into Slack.

**57:54** · But that Stewart Butterfield, he's a great entrepreneur.

**57:57** · So companies go through changes and this and that.

**58:01** · If you're a special founder and you don't run out of cash, I'm still for that and would bet on that.

**58:08** · Question is given the SaaSpocalypse and given that we have a long time horizon, how do you think about-- how can you invest in anything, because Anthropic is just going to one shot at all?

**58:18** · This is the Wall Street view.

**58:19** · By the way, anytime Wall Street thinks one thing and Silicon Valley thinks another thing, that arbitrage is worth a lot of money and Wall Street's always wrong, so I think there's actually a lot of opportunity now in that case.

**58:35** · Look, I think some of these things are-- the whole moat is the code and the UI.

**58:45** · And I think that's a difficult position to be in right now for sure.

**58:52** · But there's a lot of companies-- most of the new companies-- nobody's coming in with new SaaS companies at this point.

**59:01** · People know like, OK, that's not that defensible like you can build it and so forth.

**59:07** · So that's not the new idea.

**59:09** · So then if you go to the old ones and you go, well, are they all dead like Wall Street thinks?

**59:15** · I think not really.

**59:17** · So I'll just give you one example of a company that I'm on the board of.

**59:20** · So I'm on the board of a company called Navan.

**59:22** · And Navan is a software travel agency for businesses.

**59:27** · So in a company, your biggest variable expense is travel so you need to have very tight policies around it and so forth.

**59:36** · And then to build a travel company, you actually need to have supply chain relationships with, not every airline in the United States, but every airline in the world, every hotel in the world.

**59:49** · And if you scrape their websites and do that kind of thing, they literally cut you off.

**59:53** · They send you a cease and desist.

**59:55** · And they sue you, and you're out of business instantly.

**59:59** · So it's not that hard to build all those global supply chain relationships.

**1:00:04** · And then you can't sell to any significant company that travels worldwide if you don't have all of them, because I need to be able to travel everywhere.

**1:00:14** · And then you've got to integrate with whatever they're doing for their cruddy other systems in their company.

**1:00:22** · And then the channel to sell it, you're actually selling to somebody called the travel manager, which, by the way, like Anthropic is like the chance that Anthropic would build a channel to sell to the travel manager when-- there's gold bricks everywhere.

**1:00:41** · They're not going to pick up a silver brick.

**1:00:43** · They're just not going to do it.

**1:00:44** · I can tell you, Anj can tell you.

**1:00:46** · That's the last thing on their mind.

**1:00:48** · In fact, they've got an open req now to hire a travel manager at Anthropic to manage the Navan relationship.

**1:00:54** · \[LAUGHS\] Nonetheless, I think they'll be fine for a very long time.

**1:00:59** · So it's just one of those things where-- and there's a saying on Wall Street.

**1:01:03** · When the paddy wagon backs up to the house of ill repute, everybody goes to jail, not just the people who are committing crime.

**1:01:11** · And so in the SaaSpocalypse everybody's in jail whether or not they should be in jail so just be aware.

**1:01:18** · What do you think it's going to take for the markets to realize that not-- Time.

**1:01:22** · Time.

**1:01:23** · It's just time.

**1:01:25** · And education, I guess, Yeah.

**1:01:28** · And you learn.

**1:01:28** · Well.

**1:01:29** · So the way Wall Street works is-- and Warren Buffett always says, in the short term, it's a voting machine.

**1:01:37** · In the long term, it's a weighing machine.

**1:01:39** · Well, why is that?

**1:01:40** · Well, the reason is it's a narrative.

**1:01:44** · They buy the narrative.

**1:01:45** · They don't buy the facts.

**1:01:46** · They buy the narrative.

**1:01:47** · So if the story, this is a victim of the SaaSpocalypse, barring any new results from that, that's going to be a winning story because it's like such a good story.

**1:02:00** · And by the way, all the portfolio managers who own SaaS companies got fired so nobody wants to jump into that, kind of thing if you got the new job.

**1:02:11** · And so that story is going to hold for a while.

**1:02:14** · But eventually, when the quarters come in, the weighing machine will go, well, maybe that narrative wasn't right for that company, because why are they making so much damn money if they're a victim of Anthropic can one shot them.

**1:02:28** · That doesn't make any sense.

**1:02:29** · Don't the customers the one shot is coming?

**1:02:32** · And so then the narrative will change and a new narrative will win.

**1:02:36** · And then it becomes a weighing machine, and that's true for, by the way, every company.

**1:02:42** · What advice is super overrated today?

**1:02:45** · I don't what advice.

**1:02:46** · That's a good question.

**1:02:47** · I'm not sure.

**1:02:48** · What kind of advice are you getting?

**1:02:51** · Oh, what I get?

**1:02:53** · I mean, look, I think you have to pay much more attention-- I think the thing that is true is you can't ignore.

**1:03:01** · I remember before the internet came, which I was also alive for.

**1:03:11** · There were a lot of tech companies.

**1:03:13** · And anyone that ignored the internet was just gone.

**1:03:17** · You can't ignore a change that big.

**1:03:20** · There's no way that something that worked before AI can ignore AI and survive.

**1:03:26** · So that part is true.

**1:03:28** · And so if you're starting a company and you're not dealing with not only AI today, but what's likely to happen, as the models get bigger and so forth, it's just not going to be a very interesting company.

**1:03:41** · So that part of advice is very correct.

**1:03:46** · I think the part of the advice that's wrong is there aren't going to be any employees and companies aren't going to hire people, and it's just going to be AI bots running everything.

**1:03:58** · By the way, all the data is going in the opposite direction of that.

**1:04:03** · Even software engineering jobs are growing very fast, despite what Dario says.

**1:04:08** · And by the way, they're growing very fast at Anthropic so it's like, at what point do you call on that idea?

**1:04:20** · I think sometimes things get taken out of context.

**1:04:22** · With the political donation question, what was missing context was that your donations to both sides.

**1:04:27** · I think one of the things that gets taken out of context with Dario is he's often saying, hey, during the transition, some types of jobs that are low skill, those will go away.

**1:04:37** · And those people will then have to take new jobs.

**1:04:40** · Yeah, so there will be a job-- so Dario is very right on that.

**1:04:43** · There will be a job change.

**1:04:44** · So not the advice Dario gives but how it gets written up.

**1:04:47** · Exactly.

**1:04:47** · It's the tweets.

**1:04:49** · It's the tweets.

**1:04:50** · The tweets are the problem.

**1:04:51** · Yeah so those tweets turn out to be I would just say very overblown and not representative of what's likely going to happen so, don't-- and in general, the doom and gloom, I just think it's overstated a lot on AI.

**1:05:16** · By the way, the most dangerous thing I think, on AI by far, is that we fail as a country.

**1:05:23** · We get too scared.

**1:05:24** · We overregulate.

**1:05:24** · We do what Bernie Sanders recommends.

**1:05:27** · Some of you are Bernie Sanders fans, but like we put a moratorium on data centers.

**1:05:31** · And then China wins.

**1:05:34** · And look, I think a world Where-- by the way, either China has superintelligence and we don't or we have it and they don't is a much more dangerous world than having some kind of balance to the power.

**1:05:51** · Concentrations of power historically have been the worst thing for humanity.

**1:05:56** · And so I think that would be the thing to be scared of.

**1:06:00** · So I think the fear could cause actually a worse problem than what people fear.

**1:06:05** · Well, here at AI Coachella, we are rational optimists.

**1:06:08** · All right.

**1:06:09** · That was good.

**1:06:10** · So thank you for coming to AI Coachella, Ben.

**1:06:12** · All right.

**1:06:12** · Thank you.