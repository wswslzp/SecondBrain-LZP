---
title: "Stanford CS153 Frontier Systems | The Road Ahead: Resilience Required"
source: "https://www.youtube.com/watch?v=g50FHC-PzK8&list=PLoROMvodv4rN447WKQ5oz_YdYbS74M5IA&index=3"
author:
  - "[[Stanford Online]]"
published:
created: 2026-07-19
description: "在 YouTube 上畅享你喜爱的视频和音乐，上传原创内容并与亲朋好友和全世界观众分享你的视频。"
tags:
  - "clippings"
---
![](https://www.youtube.com/watch?v=g50FHC-PzK8)

## Transcript

**0:09** · I have two themes that I want to touch on that I hope at the end of this session get a little bit in your brain.

**0:18** · I have been working in technology since the 1990s.

**0:22** · When I got out of school, I moved here to Northern California in 1995.

**0:29** · And when I got to San Francisco in 1995, I was working for the US Department of Justice.

**0:35** · And it was funny, Mike said had asked me, how did you get into doing technology for the government?

**0:43** · And it was because I asked the Department of Justice if they would give me a direct internet connection to my desk.

**0:49** · In 1995, and they said, absolutely not.

**0:52** · We can't let our network touch the internet.

**0:54** · So I just kept asking, and eventually they let me have a separate computer to use on the internet.

**1:00** · And then I was the only person in the office who had a computer that was connected to the internet, and I became the gatekeeper to everything.

**1:09** · But let me tell you a little bit about-- let's see, how do we-- here's my background, so I spent my first eight years with the Department of Justice, and then in 2002, I went to eBay, back then, eBay was the hottest company in Silicon Valley, and it was a really fun place to work for a few years.

**1:32** · Right after I got there, we acquired PayPal, and so I spent a bunch of time for eBay and PayPal, building out both the legal side and the safety and security side of those companies.

**1:46** · And then in 2008, I went to Facebook when it was smaller than Myspace.

**1:51** · It was here in downtown Palo Alto.

**1:54** · We were scattered in a bunch of little-- I was in an old law firm office where I was working with a group of other people.

**2:05** · And it took us years to get to having a campus.

**2:09** · And so I was at Facebook until we became basically the company you know now after we'd integrated Instagram, WhatsApp, Oculus and all that.

**2:18** · And then I went to Uber and became their first head of security.

**2:21** · So at Facebook, I inherited three engineers and built it up to a large group.

**2:25** · Then I went to Uber and inherited three engineers and built it up to hundreds.

**2:29** · And then in 2018, I went to Cloudflare and inherited three engineers and built it up again.

**2:34** · So today, that's a lot of what I do.

**2:36** · I work with startups that need to scale security and technology really fast.

**2:40** · So I have my own company, and we work with three or four startups at a time, helping them scale.

**2:46** · I also advise cybersecurity companies, startups, and some non-security companies on security best practices.

**2:56** · I'm a venture partner at Costanoa Ventures, and I'm the CEO of a nonprofit helping kids in Ukraine.

**3:03** · So that's kind of my background in a nutshell.

**3:05** · But I'm going to take you through, in particular, something that I had to go through when I was at Uber.

**3:13** · If you look at my roles and my career, there's one theme, which is I've been at the intersection of where government and technology companies meet.

**3:24** · And I've spent a lot of time, when I was that federal prosecutor here in Northern California, I would go around all the tech companies and I would say, tell me about your cybercrime.

**3:35** · I want to prosecute it.

**3:36** · And they would all say, we don't have any.

**3:41** · There was no incentive.

**3:42** · If you're a company and you're having bad things happen to you, why would you tell anybody about it, is it good for your brand?

**3:48** · Is it good for your business?

**3:49** · Not at all.

**3:50** · So the companies would always say to me, oh yeah, we have the-- and so they would tell me about all these other issues they had.

**3:57** · I ended up like prosecuting it was actually a guy from Stanford who'd gone to Stanford who was a joint-- he had a law degree and MBA, joint degree from Stanford, and he ran all of business development for Cisco.

**4:11** · And he felt that the CEO of Cisco didn't appreciate him enough, apparently.

**4:16** · So he stole-- as they acquired companies, he created his own subsidiary called Cisco Systems, Inc. Bahamas.

**4:24** · And when they would divide up the stock portfolio, he would put about half of it in actual Cisco and half for himself.

**4:33** · And then eventually we figured it out and so I prosecuted him.

**4:37** · And I was like, that's not exactly cybercrime but it was interesting.

**4:42** · And then I had to build trust with the companies, and then they would actually start telling us about the real issues when they understood they could trust us to actually just go prosecute and not do big negative PR against the companies.

**4:54** · Then I switched over and was on the company side.

**4:57** · And at eBay, our number one problem was trust.

**5:01** · If you remember-- maybe you don't remember before PayPal, but the business model of eBay when I joined was identify an item, win the auction, put money in an envelope, mail it to the seller and hope they send you the goods.

**5:19** · That was literally the eBay business model when I joined the company.

**5:23** · A small percentage of transactions were going through this little startup called PayPal, and we had our own competitor to PayPal.

**5:31** · And then eventually, digital payments caught up.

**5:35** · And now we are able to use credit cards and things like that and have assurances on our transactions.

**5:41** · But I went to 46 of the 50 states for eBay to talk to regulators and trying to get them to work with us and to enable this platform.

**5:50** · I trained law enforcement in a dozen different countries on how they could prosecute somebody for doing bad things on eBay.

**5:57** · So we were trying to pull law enforcement and government to pay attention to what happened on the internet in the early days.

**6:04** · By the time I got to Facebook, it was still the same thing, but there was a little bit more attention.

**6:11** · There was this whole situation with that guy, Eric Snowden.

**6:16** · And he left the NSA and he revealed all these documents that made it look like Silicon Valley was sharing everyone's data behind the scenes with the NSA.

**6:26** · That wasn't the actual full story, I ended up in the middle of all that, basically, as the face of Facebook interacting with the NSA, because I had managed our relationship with them all along.

**6:38** · And so that was the backdrop when I got to Uber in 2015.

**6:45** · And Uber was kind of the beginning of the mobile explosion.

**6:54** · If we think about the transition and how technology has become such a bigger part of our lives in the last 20 years, it was really like phase I was like regular internet.

**7:06** · Oh, we can do ecommerce.

**7:07** · Wow, this is amazing.

**7:08** · And then part two was that mobile explosion.

**7:11** · Uber couldn't exist until there was an iPhone.

**7:15** · And it's led to this next generation of explosion of technology companies really taking over the world.

**7:23** · And when this happens, when technology becomes the most important thing, all of a sudden the government folks really start to care about technology.

**7:32** · And that's what's happened in the last decade.

**7:34** · We've seen a lot more initiative going back to around the time of the first Obama administration, 2008 to 2012.

**7:42** · They really started trying to figure out how do we get closer to Silicon Valley.

**7:47** · President Obama came and visited us at Facebook.

**7:51** · So did George W. Bush and Al Gore.

**7:55** · And so you started seeing a lot more of that interaction.

**8:03** · So I was at Uber, everything seemed to be going OK, and then one day I got this text or email.

**8:11** · It was from Eric Newcomer, who's a reporter at Bloomberg, and he messaged me because he wanted to about me getting fired from Uber.

**8:19** · I had no idea what he was talking about.

**8:22** · I was on vacation with my family up by Lake Tahoe.

**8:25** · It was Thanksgiving week.

**8:26** · I'd taken the week off.

**8:30** · After getting that, this was the headline I saw.

**8:34** · He wrote, published an hour later, "I paid hackers to delete stolen data on 57 million people," according to the news.

**8:45** · And it just blew up across the planet.

**8:47** · My phone started going crazy with people texting me, trying to call me.

**8:52** · And right in the middle of that, my phone stopped working because my phone had been issued by Uber, and my team had put software on that.

**9:02** · And then my team used that software to brick my phone and my computer because the company had decided to fire me.

**9:10** · So I was all of a sudden, the most famous person in cybersecurity for the wrong reason about a decade ago.

**9:20** · And that hurt a lot, I'm still involved in litigation related to that, but I went into hibernation for about two months, grew a beard, didn't want to show my face.

**9:37** · And then in early 2018, I decided I gotta get off my butt and get back going in life.

**9:42** · And so I went out and tried to apply for some jobs, and that was when I got hired.

**9:48** · Well, the funny thing was after going through this, the first three companies to contact me about working for them and running security-- Huawei, WeWork, and ByteDance.

**10:07** · I'm dead serious.

**10:09** · They would love to have me despite all this.

**10:13** · Instead, I chose to go work at a small startup called Cloudflare.

**10:18** · And Matthew Prince, I think, maybe speaks to this class.

**10:24** · Matthew did his due diligence.

**10:25** · He talked to Travis, who had been my CEO and manager at Uber and a lot of other people, and decided he would take a chance on me.

**10:33** · So I went and worked at Cloudflare starting in spring of 2018.

**10:40** · And then 2018 was the midterm elections, in 2016 was when President Trump was elected for the first time.

**10:47** · And then there was the midterm elections.

**10:51** · Cloudflare got so much negative heat because I got doxed, and group of organizations I'd never heard of went after me.

**11:01** · Please don't go to that URL, because you'll see the entire doxing of me because Google refused to take it down even though I submitted a takedown request.

**11:10** · But I guess if you go there, you'll see, I have six brothers and sisters, you can see all of their addresses, you can see my family's information, there's a whole timeline, there's all kinds of information about my mom who worked for the CIA and lots of other stuff that I didn't even know about myself.

**11:32** · And so just me, because of what I'd gone through before I ended up inflicting this on Cloudflare.

**11:40** · And the thing I'll say about Cloudflare that is a company that really cares about transparency.

**11:47** · When I joined the company, I had my first security incident, and I had been through a lot of other security incidents where we don't get to control the communication about the security incident on the security team.

**12:02** · It's a cross-functional thing, you're supposed to work with the communications team and the legal team.

**12:07** · Legal says what can go out, communication team polishes it up, the CEO has to sign off.

**12:13** · That's the way communications work in companies, right?

**12:16** · So at Cloudflare, I had my first security incident.

**12:20** · I called Matthew, our CEO.

**12:21** · It's a Friday night because security incidents only happen on Fridays so that your team has to work all weekend.

**12:29** · It's a science, it's been proven.

**12:32** · And so on that Friday night, I call Matthew and I say we have a security incident.

**12:38** · And he said, who's writing the blog post.

**12:42** · And I always remember that, and I'm like, what do you mean who's writing the blog post?

**12:46** · We're bleeding here, I need to make sure we stop bleeding and make sure that our customers are safe.

**12:51** · And he's like, who's writing the blog post?

**12:54** · I was like, I'll figure that out later.

**12:56** · And so I hang up five minutes later who pops onto the Zoom but our CTO, I'm like, John, why are you on this?

**13:03** · He's like, I'm writing the blog post like our CEO had made our CTO just join my incident response kind of working room just to write down and document everything so we could be transparent.

**13:15** · A year later, we had our first big real outage as a company.

**13:19** · I was over in London, and it was our local team in London pushed a rule to our WAF that basically took down half the internet.

**13:30** · And fortunately, most of the United States was asleep because of the timing of it.

**13:36** · But John and I, we called every large customer that we had, we put out a detailed blog report.

**13:43** · We had literally disrupted the entire internet.

**13:46** · And a day later, if you went online and you looked at how Cloudflare was being discussed, they were praising us for transparency.

**13:54** · Instead of getting slammed for breaking the internet, we were getting praised for being transparent.

**14:01** · And I think there's this constant tension between transparency and not around technology.

**14:08** · What the good and bad of it?

**14:09** · And I think we need to bias more and more the way Cloudflare has towards this transparency.

**14:15** · So after that it's now 2020, and the FBI issues this press statement saying that they have arrested me.

**14:28** · My eldest daughter was moving into her dorm at UT Austin at the time, and she calls me because a friend of hers had heard on NPR that I'd been arrested.

**14:38** · And so she is freaking out and she calls me.

**14:42** · I'm sitting at my desk here in Palo Alto.

**14:45** · I live by Midtown in Palo Alto.

**14:46** · I was sitting at my desk on a Zoom for Cloudflare.

**14:50** · I hadn't been arrested.

**14:53** · So we'd have to add one thing to this.

**14:57** · So I hadn't been arrested, but what I had been was charged with a crime.

**15:05** · So I've never been arrested, but I did get charged, I got charged with obstruction of justice and misprision of a felony.

**15:13** · Without going into all the details, what it basically means I was being personally held responsible for the company's failure to be transparent with the government in 2017 or 2016 when that security incident happened.

**15:28** · So I want to take you through the security incident a little bit.

**15:33** · I'm going to skip the legal stuff.

**15:36** · I went to trial against the government of September of 2022.

**15:40** · One of my daughters drew this picture because you're not allowed to take cameras in federal courts.

**15:45** · So this was during the trial.

**15:46** · This was the person on the stand there was a lawyer from Uber.

**15:51** · Coincidentally, when my daughter drew this picture, this is the chief privacy, the head of privacy, and regulatory for legal and she testified.

**16:00** · It's my team's job to tell the government about security incidents, and my team owns responsibility, and my team was the one that-- and I personally knew about that security incident.

**16:11** · And yes, we did not tell the government agency that was investigating us about the security incident.

**16:16** · So she said all that, but I was the one who was the defendant sitting in the courtroom wearing a mask because it was COVID times.

**16:23** · The jury never actually saw my face through the whole trial.

**16:26** · They only saw a guy in a suit with a mask on.

**16:31** · So what was the case actually about?

**16:35** · I really believe in this concept of responsible disclosure and trying to get the hacker community to work well with corporations.

**16:43** · So when I-- in 2007, when I was at PayPal, we published a responsible disclosure policy.

**16:49** · It was the first time a company published one.

**16:52** · If you do security research what these policies are.

**16:55** · If you don't, you've probably never heard of them.

**16:57** · But what we said in 2007 at PayPal was, if you find a vulnerability, please tell us about it.

**17:05** · We promise we won't sue you.

**17:07** · We promise we won't tell law enforcement about you.

**17:10** · We want to have an open dialogue.

**17:13** · So we did that in 2007 at PayPal, and other companies started to follow suit.

**17:18** · I went to Facebook in 2008, and we published a responsible disclosure policy there right after I got there because it was something that I cared about.

**17:28** · Then a couple of years later, there was this movement in the hacker community that was like, wait, that was nice that you said you won't prosecute us.

**17:35** · But why don't you actually pay us money?

**17:37** · Because you're finding vulnerabilities, we're finding vulnerabilities, we're making you safer.

**17:42** · And I remember the first time I got that email from a hacker and it said, pay us money, and we'll tell you about the vulnerability in your systems.

**17:50** · And if you own the system and you own security for that system.

**17:53** · And you get that message, you get kind of mad.

**17:57** · And I used to be a prosecutor, so I was like this, I get double mad and I start thinking, how can I use the law against you, right?

**18:04** · It's like-- and then my team's like, Joe, shut up.

**18:08** · We should be paying these people and I came around to that.

**18:13** · And so I think it was 2011, 2010 or 2011 at Facebook.

**18:17** · We launched the third ever bug bounty program.

**18:20** · Bug bounty programs are a thing everywhere now.

**18:23** · Google last year paid out, I don't how many millions of dollars in bug bounties, and they just announced a new program where you can get $250,000 for a single vulnerability.

**18:36** · And so the world has been evolving to this place where we recognize that our goal should be the best possible security and that we should cultivate these relationships.

**18:45** · So when I got to Uber in 2015, we published a responsible disclosure policy.

**18:51** · And I should add that when I went from Facebook to Uber, about 40 of my team came with me.

**18:57** · And so we brought not just me, I went not by myself, but over the course of a few months, a lot of my team.

**19:02** · So much so that the general counsel from Meta sent me that warning letter that you sometimes get.

**19:12** · And then we published a bug bounty program, and we had it running in private for a year before we launched it publicly in the spring of 2016.

**19:23** · And in the fall of 2016, this is the email I got.

**19:27** · "I found a major vulnerability.

**19:29** · I was able to dump database and other things."

**19:32** · And I did what I always do when I get this email, because I've gotten a lot of these emails over the years.

**19:37** · I forwarded it to the product security team that manages the bug bounty.

**19:40** · Member of our security team emailed and said, hey, we use HackerOne for our bug bounty program, but we're also happy to work with you, even if you do it other ways.

**19:50** · This is the email from Rob Fletcher, who's now a startup founder somewhere.

**19:55** · But he led the interaction with this person who wanted to be anonymous.

**20:03** · And they showed us that they had actually found a vulnerability in the way our AWS was configured, related to some old databases that my team didn't even existed because they had been deprecated before we got there.

**20:16** · We treated it like a security incident.

**20:19** · We documented everything.

**20:20** · We had a centralized tracker, and all my team's notes are still there from it because I was going to trial over this.

**20:28** · These are all slides from the trial, actually, from my lawyer's closing argument.

**20:33** · It was showing here are all the people in the company who knew.

**20:35** · I went to the CEO.

**20:37** · He signed off on us paying the bug bounty because we paid $100,000 to these researchers.

**20:42** · It was all approved.

**20:44** · Three lawyers were in the loop, two lawyers, the communications team, all in the loop.

**20:51** · And we actually had written formal policies and documentation, and it said legal is responsible, doing the investigation, reporting it, et cetera.

**21:00** · And we ran the whole thing by legal and they said, we don't think we have to disclose it.

**21:06** · The communications team had already prepared documents for if they were going to disclose it.

**21:10** · They put those aside.

**21:13** · I said to my team, these people are still anonymous.

**21:17** · Can we find out who they are and actually go interview them and make sure that they have deleted the data?

**21:23** · So my team did an investigation.

**21:24** · I'm not going to go through all the details here, but long story short, we were able to figure out who they were and where they were.

**21:33** · It turns out at the exact same time that we were doing this investigation, the FBI was also doing the same investigation because these two guys, a 19- and 20-year-old, 19-year-old down in Florida and 20-year-old up by Toronto, who had met in the gaming community, they had found vulnerabilities in a few companies of the same type.

**21:53** · And so they reached out to a few companies.

**21:55** · I think they reached out to five companies and said we found vulnerabilities.

**21:59** · We worked with them, paid them, fixed the vulnerabilities.

**22:03** · Another one of the companies, which was \[? LinkedIn, ?\] decided to contact the FBI.

**22:09** · The FBI then tried to find them.

**22:12** · We didn't know any of this was going on at the time.

**22:15** · The FBI couldn't find them.

**22:17** · My team was able to.

**22:20** · And my team and I still get involved in working with the government on situations like that because we're really good at that stuff.

**22:29** · And so we were able to find these guys.

**22:32** · And I had a retired CIA intelligence officer who's specially trained in interrogation, a top trainer.

**22:42** · He trains other people from the CIA on how to do interrogation.

**22:45** · So I sent him down to interview Brandon.

**22:50** · Well, actually, Matt from my team sent this email.

**22:52** · We basically figured out who Brandon was, where he was living down in Florida, and we sent in an email and said, you got to be really careful in these situations.

**23:03** · You'll be viewed as an extortionist.

**23:05** · We don't think you're an extortionist.

**23:07** · We think that you should be paid.

**23:09** · And by the way, one of my team-- oh, he didn't know we knew his name was Brandon when we sent him this email.

**23:15** · So this was we send you the email, and we sent it to his real email address instead of his Proton Mail.

**23:21** · So imagine your Brandon, you wake up that day and there's an email saying, hi, Brandon, this is Matt from Uber and one of my team members is right around the corner can you guys meet today?

**23:35** · That happened, and then my team member, the trained CIA interrogator, went in and he prepared for me AI think it was like a six page psychological profile of the guy and documented and validated that the data was deleted, that our customers were protected.

**23:53** · So this is a situation where at the end of the day, legal had signed off on the communication side and my team had done the work where I felt comfortable, our customers were protected, and we closed the chapter on the case.

**24:10** · Until 2020, when I got charged with a crime, I didn't until much later that apparently people were agitating behind the scenes from Uber and others to get the government to go dig into this.

**24:24** · So I go to trial, we come through the trial, my lawyers at the end of the evidence say at the end of the government's case, they said, Joe, we don't even need to put on a defense.

**24:34** · We totally won.

**24:36** · I was like, OK, sounds good, but let's just call a couple of witnesses to fill in these little gaps.

**24:41** · We did.

**24:41** · So we barely put on a defense.

**24:44** · And then the jury goes out and they deliberate for a few days, and I'm just like, guys, if it was such an easy slam dunk victory for us, what's going on.

**24:54** · And then this question comes up with regard to this hacking statute.

**25:01** · Does Uber have the right to extend authorization after the access?

**25:06** · So under 18 USC 1030, this is basically the computer hacking statute.

**25:13** · It says so if I access your computer without your permission, I violated the law.

**25:18** · And then there's various levels of significance beyond that point.

**25:21** · And so the legal question was when Brandon and the other guy accessed Uber's AWS, could we after the fact, give them permission, or was it automatically a crime the second that they accessed our computer.

**25:37** · And do we have the ability to unwind it?

**25:40** · All the advice I'd ever gotten, and we discussed this a million times before with lawyers is it's like they would say, oh, it's like the old trespass statutes.

**25:48** · If somebody steps into your front yard and you can be like, oh, hey, come on in that effectively by law means it's no longer a trespass.

**25:56** · And so that was the advice that the bug bounty platforms and our lawyers had always told us.

**26:01** · But then when the jury asked this question, the judge was not so sure.

**26:06** · And the government was arguing at that time, no, we can't-- Uber couldn't give permission.

**26:13** · So the jury basically got the instruction Uber cannot give permission so effectively it just basically gutted our whole defense.

**26:24** · And so I could be held accountable for a criminal obstruction supporting the bad guys even if I had gotten legal approval and didn't think that we did anything wrong.

**26:36** · So we lose the trial.

**26:39** · It's now October of 2022.

**26:44** · I went through that period in 2018 where I had to climb back on my feet.

**26:48** · And in 2022, it was a lot harder because I had just lost the trial.

**26:53** · So I was sitting around at home moping again.

**26:58** · And I called all the different nonprofits who always wanted to work with me.

**27:01** · And they were like, yeah, we can't be associated with you this time.

**27:05** · And so I had been helping Ukraine through my role at Cloudflare.

**27:12** · And I realized that the only people who were willing to work with me in the fall of 2022 were the Ukrainians because they had nothing to lose.

**27:19** · And they didn't care about my case.

**27:22** · So I joined a nonprofit called Ukraine Friends and became their CEO.

**27:30** · I started a program called Digital Wings.

**27:32** · I realized that at every tech company, we have these piles of laptop computers that are sitting behind the help desk because we hire a bunch of people.

**27:40** · Half of them don't last two years, but we're not going to give those computers to the next new employee.

**27:45** · So the piles of computers get bigger and bigger.

**27:48** · On my first trip to Ukraine, a friend of mine was the CEO of Robin Hood at the time.

**27:52** · He gave me 20 of their cleaned up used computers, and so I brought them in my carry on.

**27:59** · When you get to the airport and they're like, do you have any lithium ion batteries?

**28:02** · I'm like, yeah, I got 20, they didn't what to do, they just let me on the plane.

**28:12** · And since I'd already been convicted of a crime, I was like anyway, I'm just kidding.

**28:20** · I actually I really take seriously the shipping.

**28:24** · I've shipped thousands of computers to Ukraine at this point, and I've learned everything about safe shipping of lithium ion batteries, and it's really important you take those things seriously because there have actually been fires and things on planes.

**28:37** · But public service announcement aside, I got to Ukraine with a bunch of laptop computers and I realized what a need there was.

**28:47** · So my nonprofit, we get kids-- we bring computers to kids who've lost a parent in the war.

**28:53** · My last trip to Ukraine was two weeks ago.

**28:56** · I was there two weeks ago for the week.

**28:59** · TD Bank had donated over 1,000 computers, and so I was there to oversee the distribution of those.

**29:05** · And we worked directly with military units so that some of the soldiers in the unit can give laptops to the kids of their fallen brothers.

**29:14** · The people who survive feel like almost a sense of responsibility for the families of those who didn't survive.

**29:22** · And so we like to work with them to help them.

**29:25** · And what the people in Ukraine have been going through, it's incredible the resilience I come back inspired every time I go.

**29:33** · I've been six times in the last three years and I wish I could go more frequently.

**29:40** · So I'm doing this work in Ukraine and I'm waiting and my sentencing keeps getting postponed.

**29:45** · I had the most amazing thing happen.

**29:49** · I'm in this funk, no one will hire me, I'm volunteering in Ukraine, seeing sad stuff, and I'm waiting for my sentencing hearing.

**29:56** · And the government says, we're going to argue that you should get three years in federal prison.

**30:04** · I guess I'd still be in federal prison if they had gotten that.

**30:10** · There's a process that you go through, though, for before you get sentenced.

**30:15** · And that in the federal system is there somebody called.

**30:18** · There's a probation office and they prepare a pre-sentence report where they review your whole life.

**30:23** · And so it's like a 75 page document of everything about me so that the judge can make an informed decision.

**30:32** · And by the time the probation office got through documenting, like Joe's been a volunteer for the federal government 17 different times since he left the government doing all these different things, and involved in these different nonprofits and helping people in Ukraine, et cetera, the probation office came in with a recommendation to the judge-- you should just give Joe probation and let him go live his life.

**30:54** · And the prosecutors, when they heard that, they dropped down and instead they argued that I should get 18 months.

**31:00** · So during that process, I had the most amazing thing happen, which was I got these emails.

**31:08** · And attached to each email would be a letter to the judge.

**31:13** · I got over 200 separate letters to the judge sent to me by people who'd worked with me through my career, by people who were upset about my case.

**31:23** · One letter was signed by 60 people in the cybersecurity community, another by 50, another by 40.

**31:29** · It was like this mass uprising of support because they felt that the case was unfair.

**31:33** · Or even if they didn't anything about the legal stuff, they wanted me to be out and doing what I do.

**31:40** · And so I had a sentencing hearing on May 4, 2023, so literally three years ago and a week.

**31:53** · And the judge said it wasn't a cover-up.

**31:58** · That was the best thing I ever could have heard.

**32:01** · The judge then went on to basically yell at the prosecutor in some sense, saying, if you're charging a company, why wouldn't you charge the CEO?

**32:10** · The CEO was in the loop.

**32:12** · The CEO supported all the decisions.

**32:14** · If we're going to hold corporations accountable, let's start at the top.

**32:18** · He also yelled at the prosecutor like there was no financial incentive for Joe to do this.

**32:24** · Why do you think he would do this?

**32:27** · Do you think he needed to protect himself for his career?

**32:29** · Stuff like that.

**32:30** · He said, I've never seen a case like this in my life.

**32:33** · And then he sentenced me to three years of probation and a small fine and sent me on my way.

**32:39** · So I actually finished my probation a week ago.

**32:41** · I got a letter saying I'm off probation.

**32:46** · Thank you.

**32:50** · I still get secondary inspection every time I come to the country, but my daughter's really enjoyed it the first time they were like, dad, this is so cool.

**33:00** · But yeah, so I landed on my feet.

**33:03** · I started my security consulting business.

**33:05** · I still do the nonprofit stuff.

**33:06** · I've been working with some VCs.

**33:08** · Costanoa made me a venture partner.

**33:10** · I've been advising a bunch of startups.

**33:13** · This slide's actually outdated because well, four of these companies have recently gotten acquired, and so I no longer advise them.

**33:22** · But I was happy they got acquired.

**33:25** · I get to go do keynotes.

**33:27** · I get paid to speak all over the world.

**33:30** · This year I keynoted a big AI conference in January in Tokyo.

**33:35** · This was a keynote in Australia and so I got invited and paid to go do these things that I love to do and talk about things like this case.

**33:48** · And I just want to spend like five more minutes on the cybersecurity-- in the world of cybersecurity has changed so much since I got involved when that Uber case happened in 2016, it was like the worst case scenario data had left the building.

**34:02** · In cybersecurity, that's all we cared about for the longest time.

**34:05** · And then something new happened around 2018 and 2019, which is ransomware.

**34:10** · So now in 2025, 2026, cybersecurity is still we care about data leaving the building, but we also have to care about operational resilience.

**34:20** · Does anybody what happened to Jaguar Land Rover last year?

**34:24** · They got hit with probably one of the biggest cyber attacks.

**34:27** · It was a ransomware attack.

**34:29** · And last-- I think it happened last August.

**34:32** · They literally had to shut down all of production for all of Jaguar Land Rover for three months.

**34:39** · The UK government had to do a bailout of over $1 billion.

**34:43** · A bunch of their supply chain companies.

**34:45** · So a Jaguar is not just all the parts made by Jaguar.

**34:49** · They're made by hundreds of little companies.

**34:51** · When Jaguar couldn't pay them for three months, a lot of those companies went out of business.

**34:56** · So like the impact of a cyber attack cost the UK economy literally billions of dollars, billions of pounds.

**35:04** · And anybody who owned a Jaguar Land Rover during those months couldn't even take their car into a mechanic shop.

**35:11** · So that happened.

**35:14** · Cybersecurity became about operational resilience.

**35:17** · And then also what's going on with AI?

**35:21** · I just got back from spending the last three days in meetings in Washington, DC, because I do some volunteer support for a couple of government agencies now, and used to be like, it's weird.

**35:34** · I'm under-- I'm on probation and under investigation by one part of the government, but I usually am helping it different at the same time.

**35:40** · I have had these conversations where I'd be like in the morning, I'm with the FBI talking about something, and in the afternoon I'm with the FBI talking about them putting me in jail.

**35:48** · It's been pretty surreal.

**35:51** · But so I was there earlier this week, and the amount of pressure the government is feeling right now about AI.

**35:58** · I work with some companies that have access to meet those the Cyber Use model from Anthropic that's so powerful.

**36:07** · And it is as powerful as everybody says, we're finding things that are amazing and scary.

**36:16** · And so the government knows that and really needs cybersecurity to step up in the next six months because that type of model that's being held close right now is going to be publicly available in six months, even if it comes from the open source guys.

**36:30** · So that's the future we're facing.

**36:32** · All of a sudden, every CEO really cares about cybersecurity.

**36:37** · I get a call a day, Joe, this CEO needs a head of security right now.

**36:42** · They need somebody who's has the experience you have, where you're comfortable reporting to a CEO sitting in the exact room co-running a company.

**36:51** · That's the kind of people we need in cybersecurity right now.

**36:53** · And I don't even have enough people to refer.

**36:56** · At the same time, governments are tightening up on the regulatory side.

**36:59** · A lot of other countries are thinking about doing enforcement actions like the ones against me.

**37:05** · So it's this weird situation where a lot of my peers call me like I hear from every CISO in every bad situation.

**37:13** · And I also hear from they call me when they're like, Joe we just had a ransomware, and the CEO is forcing me to sign something to go to all our customers saying that everything's fine and I everything's not fine.

**37:24** · What do I do?

**37:25** · I get questions like that every week from people in the role.

**37:30** · And then the other question they get is like, I'm being asked to take the top seat.

**37:34** · Do I even want it?

**37:36** · Because it's really scary to be a cybersecurity leader in this environment right now.

**37:41** · And the thing I'll say is I've been through a lot.

**37:45** · And one of the things I've realized is that you have to have resilience.

**37:49** · And I don't care if you're going into cybersecurity or what other jobs you all decide to go into, you're going to get punched in the face sometimes.

**37:58** · And you got to think about how am I going to handle getting punched in the face?

**38:04** · When a boxer goes into the ring, they're going to get punched in the face and they think they still have a plan.

**38:11** · I think leadership in 2026 and beyond is about that resilience.

**38:16** · These four people, like ever since I went through my thing and I've had people say like, oh, you're a model of resilience, I started looking there are a lot of really good models like these four people all got punched in the face when they thought they were at the peak of their career, and they thought they were at an amazing place, and then they end up going 10 times higher in their career.

**38:35** · And you can find so many people like that.

**38:38** · And so the thing I would talk I do a lot of work with organizational leaders and I did like a four hour how do I prepare for-- I have literally a four hour program on how do you as an executive, prepare yourself, your team, and your company to deal with crisis before it happens.

**38:55** · I'm not going to go into all that stuff with you, but I want you to think about and remember that we don't write into the job description, resilience, and crisis management.

**39:10** · But if you're working in technology in 2026, we're so highly visible.

**39:17** · There's so much pressure on us.

**39:19** · We have to be ready to get punched in the face.

**39:22** · And that means thinking about what are the key elements for success in a crisis.

**39:28** · I think the number one element for success in a crisis is actually how well you communicate.

**39:33** · I brought up how Cloudflare has handled crisis over the years.

**39:37** · They always err on the side of transparency and it always builds trust.

**39:42** · Companies that choose like say, Uber in 2016 not to be transparent.

**39:48** · It leads to this boiling negativity over time.

**39:51** · So my last thought for you is this, run towards those opportunities, run towards those stressful situations because the more you go through them, the better you'll handle them.

**40:04** · I get invited to work at companies, the coolest companies on the planet, because they have confidence that I have wisdom from having gone through the bad things.

**40:14** · If you try and steer your career to never go through bad things, you'll never get the wisdom and experience you need to really succeed.

**40:22** · So the question is, how do you rebuild your reputation, which is clearly world known?

**40:28** · Yeah, I-- it was interesting.

**40:32** · So I consider I lost the trial in the fall of 2022, but I won the sentencing in the spring of 2023.

**40:40** · And it was really my wife who's here in the front row who's a Stanford grad.

**40:45** · She came along today.

**40:47** · She was there with me through it all and having strong support at home, number one was really important, but then I had a lot of support from the community.

**40:59** · I mentioned those letters, I joke that it was like I got to sit through my own Irish wake.

**41:06** · The idea that I got to hear all these people say good things about me while I was still alive.

**41:14** · And I bring it up a lot with leaders, because what you don't realize when you're a leader is how much the little things you do or don't do your team picks up on.

**41:26** · I had people write in these letters to the judge talking about things that I didn't remember at all.

**41:32** · I was like, I didn't remember.

**41:33** · I had lunch with that guy on my team's kid who was thinking about cybersecurity, but apparently I did.

**41:38** · I didn't remember there were just lots of examples like that.

**41:41** · And so after I won the trial, I reached out to a couple of people.

**41:47** · I decided I should-- I couldn't talk for seven years.

**41:50** · My lawyers wouldn't let me talk.

**41:51** · So I was just all negative for seven years.

**41:53** · And so after it was over, I reached out and-- I reached out to the guy who runs the DEFCON conference who started it in Vegas back, whatever, 30 years ago and he'd started Black as well.

**42:05** · So there's two of the most well-known cybersecurity conferences.

**42:08** · And I said, I'd love to get a chance to tell my side of the story.

**42:12** · And he contacted me back a week later and he said, at Black, we have a CISO summit.

**42:19** · So all the security leaders from the biggest companies will be there.

**42:23** · You can do an off the record talk there if you'll do an on the record talk at DEFCON.

**42:28** · And so those were the first two times I was talking about my case.

**42:32** · It's funny.

**42:32** · My dad emailed me the other day because he found the DEFCON talk and watched it three years later.

**42:39** · And he emailed me about it.

**42:42** · And I was just reflecting on I was so nervous.

**42:45** · I was so nervous because a friend of mine who lives here in Palo Alto, he'd been on the early Facebook team with me.

**42:52** · I went walking with him and he'd said, what are you going to do if you get booed?

**42:58** · And so I, mentally going into the speaking, was worried that I was going to get booed.

**43:04** · But I just did it.

**43:05** · I got up and went and did it.

**43:06** · It was the same thing as in January of 2018, the first time I went to a security conference after getting fired on global news, I felt very sheepish and awkward and uncomfortable, but I got through it.

**43:19** · When I spoke at Black Hat at that CISO Summit, I ended up getting a standing ovation from my peers, the best security leaders in the world.

**43:30** · And so that just gave me the confidence and courage to go forward.

**43:34** · I started my own consulting business, and then I had success doing it.

**43:41** · What I've learned is that I was mostly able-- large companies can't be associated with a felon, although I do work with some large companies.

**43:48** · But they prefer that we keep it under NDA.

**43:53** · And so I started embracing working with startups even more because startups don't care.

**43:57** · They just want to have the best security they can get from somebody who understands them.

**44:01** · So I just have been building it ever since.

**44:04** · Good, next question.

**44:06** · So the question is, what are the security issues around vibe coding, and what should we be thinking about?

**44:11** · Yeah, I actually joined the board of an AppSec company last fall.

**44:16** · And over at the VC, we've been looking a lot at how application security is evolving.

**44:21** · And I've been thinking about it.

**44:23** · And the companies that I advise and work with are obviously in different stages of embracing it.

**44:31** · Financial services is really slow on embracing it, but some of the other companies I work with are really deep in a large percentage of their code is being generated through these tools.

**44:43** · The first challenge is just the sheer volume of code being generated has gone through the roof one small Southeast Bank that we work with.

**44:55** · They went from 250,000 lines of code a month to 1.25 million lines of code a month in, a two month period after.

**45:04** · So challenge number one is the sheer velocity of a code.

**45:08** · Challenge number two is that one of the other companies I work with here in the bay area, their CISO called me and he was like, we just had our first marketing person merge into production, and there was a vulnerability and we tried to kick it back to marketing, and they don't how to fix the vulnerability.

**45:26** · So like whereas a software engineer would actually like, OK, security could send them a proposed fix and then they would tip it.

**45:35** · The typical AppSec model is the security sends a proposed fix, and then the engineer actually looks at it and thinks about the bigger context, but it's somebody from marketing you can't really do that.

**45:46** · So that's the second challenge.

**45:48** · The third challenge is it's not just a vibe coding, but Cloud Code for example, is I mean, which is really Cloud Code with a rapper.

**45:58** · Co-work it's getting non-technical employees to be even more ambitious with connecting externally.

**46:04** · And the way they'll solve problems is if they don't have the API key, they'll go out and try literally they'll go try and set up their own remote external server so that and create their own API key.

**46:16** · And you're like, there's no way an engineer would do this.

**46:19** · So we're seeing all kinds of crazy things.

**46:21** · There is no one silver bullet solution.

**46:24** · I'd say companies are coming at it from two different directions.

**46:27** · Some companies are doing YOLO and then trying to clean up, but a lot of companies and smart companies in particular are starting out with pilots and constraining to just software engineers who know better and then are slowly adding different groups.

**46:41** · I really believe that we can't solve-- and we can't solve the headaches or the security headaches of agents inside our environment just by putting guardrails on them because it's not you can't say, OK, you can have access, you can have write access to my email for purpose A but not purpose B It's like, we just can't do that.

**47:02** · And so we have to have anomaly detection around I think of it like agents inside companies are like toddlers inside a house.

**47:12** · They're running around, they can run.

**47:14** · But every so often if you've ever seen a parent of toddlers, they're kind of running next to them.

**47:19** · It's like real time run time.

**47:21** · And that's what I think we're going to have to get to in agentic solutions is like, we'll put some guardrails, but it's not that they have access.

**47:29** · It's what they do with the access that we have to pay attention to.

**47:33** · Interesting, so the question is, what have you done differently if you were back leading security at Uber?

**47:39** · Yeah, so from a technical operational side, my team, I was so happy that we actually got to get to the trial so that the world could see what my team did, technically.

**47:50** · I think everything we did, I would do the same.

**47:53** · I wish we had more documentation.

**47:55** · I'm actually an advisor to a company now called BreachRX, which creates a platform that forces legal and communications to work more directly with security.

**48:06** · And I started working with them before they even got their seed investment, because I really believe that it is about how you get the different teams inside the company to work together on transparency, like in the middle of a security incident.

**48:20** · The security leader doesn't have the credibility around communication or legal issues to say we should be public about this, you have to work through that stuff ahead of time.

**48:30** · So operationally, I wouldn't change anything.

**48:32** · We should be paying those researchers, we should be fixing things, we should be working with legal.

**48:40** · I think I spend much more time now educating the other executives at the companies I work with, not just the security team.

**48:49** · When you become a leader of a company, you don't actually work on your team anymore, you work on the leadership team of the company.

**48:56** · When I mentor a security executive, I always start out with a question that's actually a trick question.

**49:03** · The first time I'm meeting with someone new, I say, tell me about your team.

**49:06** · And they immediately start talking about, I got this team that does detection.

**49:09** · I have this team that does application security, I have this.

**49:11** · I'm like, no, no, I mean your team.

**49:13** · They're like, what do you mean?

**49:15** · I'm like the other executives at the company.

**49:17** · When I was at Facebook, I had an exec coach, and she told me that I should be spending 50% of my time with the other executives instead of with the security team.

**49:27** · And I actually think for a security leader, it needs to be even more as our world is dark and scary and confusing.

**49:33** · It's not very measurable by metrics, and you only hear the bad stories.

**49:38** · And so it's our job as security leaders to get out and really build trust with the other executives at the company so that in the crisis moment, they'll trust us more.

**49:47** · Yeah, the questions around quantum cryptography?

**49:50** · I'll tell you that this comes up all the time.

**49:53** · I was in Florida last week for a closed door group of 20 security executives, including from a bunch of the large gas and energy world, oil, gas, energy world.

**50:06** · And we had a whole session talking about, what are we doing about the quantum risk and opportunity?

**50:13** · For the most part, companies are not doing a lot right now.

**50:18** · I think the reality is that we could if we look at how the pace of AI has sped up from predictions, quantum seems like it could be here by 2030.

**50:28** · And so arguably we should be doing stuff, but for the most part, when you think about where cryptography exists in our environments, I think that most of the work that needs to be done-- needs to be done at the Google's, the AWS.

**50:46** · The biggest risk probably to most of us right now is that agencies of governments have vacuumed up a lot of historical communication data that has been encrypted by non quantum resistant encryption.

**51:03** · And so if you're part of a terrorist group five years ago you might have some trouble in five years.

**51:12** · That kind of stuff.

**51:15** · Most of our environments that are the main infrastructure companies supporting them are going to be quantum resistant.

**51:24** · And also, if you flip it around, it's a little bit like the Mythos situation.

**51:30** · Once we get quantum, it's not going to be all of a sudden every data center is a quantum data center.

**51:36** · Quantum machines require extreme cold and all this other stuff.

**51:40** · So it's going to be a few people have quantum before everybody has quantum, and then there's going to be a period of time.

**51:47** · And so hopefully it'll be the good guys get quantum before the bad guys and then they can do what Anthropic and OpenAI have been doing with their new cyber models.

**51:55** · Actually, I have a question.

**51:56** · On those models with the Mythos, what is your opinion on how those tools should be released early?

**52:02** · And what's the right process there, do you think?

**52:07** · I have seen it's funny, the cybersecurity community is very critical, self-critical and loves to jump all over each other.

**52:15** · So like the first I think on a mainstream level, Anthropic did an amazing job from a brand standpoint around they were coming out of this fight with the Department of War, and then all of a sudden they're just like being noble and helping the world around cybersecurity.

**52:30** · They nailed that from a communications standpoint.

**52:34** · And then there was this little backlash in the security community I don't have access to the model.

**52:39** · I don't believe it kind of thing.

**52:41** · And this is all hype.

**52:43** · And why haven't we seen a bunch of CVS submitted and documenting it.

**52:47** · What I can tell you, I said, one of the companies I work with was given access on day one, and it's just been incredibly valuable for them.

**53:00** · When companies and organizations get access to these models, it's not like they can just snap their fingers and point the model at their infrastructure.

**53:06** · You have to have built the harness and the technology around the models.

**53:11** · So I think every company should be building those harnesses right now.

**53:14** · And honestly, you could take some of the other existing public models.

**53:18** · If you have the right harnesses, you can find a lot of the same things, if you're intentional about it.

**53:23** · So I don't think-- I'm not critical of Anthropic in the way they've done it.

**53:31** · I will say that they went public with the names of eight companies.

**53:37** · And I think that there was some intentionality about that because they-- imagine you're in their shoes.

**53:42** · If you decide to give the access to one gas company but not another, or one bank, but not another, it's almost like you're picking winners and losers.

**53:54** · And so they have to be very careful.

**53:56** · They gave access to more than they said they gave access to.

**54:01** · I know of organizations that have access.

**54:03** · I know multiple organizations that have access that are not on any of the lists that have been public.

**54:08** · So do I, yeah.

**54:10** · So it's interesting.

**54:12** · They're doing a very public part, but they're doing some behind the scenes.

**54:15** · And then we do hear some European leaders complaining we don't have access, stuff like that.

**54:20** · But some of their peers in Europe actually do have access.

**54:23** · And it's one of those things where maybe transparency would be better.

**54:28** · Maybe this-- and now I think the government is really-- this administration is now thinking a lot harder about how should we get involved in these.

**54:38** · Do we want-- what if next time it's not Anthropic, it's somebody else and they're not as intentional about the rollout, so.

**54:47** · Out of curiosity, where do you sit on that regulatory kind of topic.

**54:53** · Yeah, I mean, I've spent 20 years being the face of companies.

**54:58** · I've testified before congress multiple times on these topics of, should we come regulate PayPal or Facebook because of-- I think we need to have smart regulation.

**55:08** · I'm not anti-regulation.

**55:09** · A lot of Silicon Valley companies and a lot of the companies I work with, in general, the whole public policy team's job is to prevent any regulation at all because stupid regulation definitely gets in the way of innovation.

**55:24** · At a certain scale, though, we need to have regulation to protect people because it's not in the best interest of companies that are just pure existing for money to take care of everybody who has access to their product.

**55:36** · And a lot of products get used in a lot of ways that the companies don't anticipate.

**55:41** · Like when I was at Facebook, I worked with a lot of dissident groups in Africa, in countries that had governments that were very oppressive.

**55:51** · And the only way they were able to stay in touch with each other was through Facebook.

**55:57** · And they were using the product in ways that I'd never imagined that they would use it and it wasn't built for.

**56:01** · And it was putting them at risk.

**56:03** · And then they were like, can you build some other features for us to reduce our risk?

**56:07** · But there's no economic incentive for us to do that as a company.

**56:11** · So you see these weird situations all the time, where governments can make social media for kids.

**56:19** · My daughter, who's 23 now, is like, Dad, you should have regulated us way more.

**56:25** · And so there's no easy answer on it because a lot of the time government shows up and they don't even how to turn on a computer.

**56:34** · And you're like, how could I let these people regulate me.

**56:38** · I mean, the good news is, we have a lot of smart business people going.

**56:43** · Ever since the second Obama administration, when they had that, they really started promoting getting people from the private sector into DC.

**56:52** · This administration is doing it, too.

**56:54** · We were talking about Emil Michael, who's the person at the Department of War who's negotiating with Anthropic.

**57:01** · There's no person I would rather have representing the Department of War in a negotiation with Anthropic than Emil.

**57:07** · I agree.

**57:07** · Right?

**57:08** · Yeah.

**57:09** · Because he's-- I worked with him here in Silicon Valley.

**57:13** · He understands this world and he understands that world.

**57:17** · And we need to have people in those roles like him.

**57:20** · We're going to have actually a meal for office hours later in June, just as a future speaker.

**57:26** · Next question.

**57:28** · I think yes, it is very difficult for any company to put full security around everything they're doing.

**57:35** · I work with a lot of startups, and the number one thing they're worried about is theft of intellectual property.

**57:43** · That's a big difference between the companies I work with and a lot of other organizations-- A lot of the world thinks about security.

**57:49** · Intellectual property theft is a huge risk for a lot of different reasons in Silicon Valley companies.

**57:56** · And so can we fully vet every employee that we hire?

**58:02** · We can't do the level of background check.

**58:05** · We can't know if you have relatives back home in another country who are being held hostage by the government.

**58:11** · I've had situations at companies I've worked at and with where we have known that the employee was put under pressure when they went home and it was like, hey, your parents have a nice retirement right now.

**58:24** · But we have this luxury suite in Siberia that if you don't start showing some patriotism like that, pressure happens all the time.

**58:34** · I've had employees arrested by governments overseas and held in expectation that the company would cooperate to the point said about saying that he was worried his hand is cut off.

**58:48** · There have been executives at crypto companies whose hands have been cut off.

**58:53** · There are lots of these when you think about if you can get access to the vault of one of those crypto banks and a lot of times like the main keys are literally two people's fingerprints have to be involved to be able to unlock it.

**59:07** · And so they'll collect the fingerprints.

**59:10** · Yeah, so I built executive protection programs in the physical security side, and I've seen a huge ramp up in executives needing to be worried about that.

**59:18** · I mean, we heard the story of what happened to Sam Altman recently, there are lots of stories like that don't get as much attention I could.

**59:27** · You could go back 20 years ago, one of the co-founders of Adobe was kidnapped here in Silicon Valley and held hostage, like in the East Bay.

**59:39** · And the FBI went and rescued him like nobody.

**59:42** · That story because I was around then, but most of the world, like we've been dealing with this type of stuff for a while, and it's real because our companies are the most powerful companies in the world in 2026.

**59:53** · And the technology is scary.

**59:55** · So, OK that's the first part.

**59:57** · We can't do perfect security and there is a risk.

**1:00:01** · I do still think that we should be moderating the release in the spirit of doing the best we can to manage the risk of the release.

**1:00:09** · And I think that's what Anthropic and OpenAI have been doing.

**1:00:14** · Could we critique them?

**1:00:15** · Is there could they do better?

**1:00:17** · The more transparent they are about the releases.

**1:00:20** · Hopefully, over time we'll figure out what are the-- it would be nice if we could say, here are the five best practices for rolling out the release of a model.

**1:00:28** · And we will prevent these organizations and they will have signed the right agreements and stuff like that.

**1:00:35** · I think we're walking, not running in that direction, and we'll get better and better at it over time.

**1:00:40** · And governments are going to get more and more involved because they need to.

**1:00:45** · What are the other questions?

**1:00:46** · Open source.

**1:00:47** · And then open source.

**1:00:48** · On the open source point, I don't think anyone knows what the ideal or real world of what models are going to be the best models three years from now are like, I don't know if LLMs are going to be the center of our universe like they feel they are right now.

**1:01:07** · Where do world models fill in?

**1:01:09** · Where are small language models fit in?

**1:01:11** · Where are vertical models like?

**1:01:12** · There are so many different things going on and so many different startups around.

**1:01:16** · Models like, are we going to get to a place where the models stop these large language models stop making leaps every few months.

**1:01:25** · The leaps are going to get a lot slower, the open source ones going to catch up.

**1:01:30** · The economics don't make sense to keep going forever on these large language models, so I feel like it's going to be a couple of years before we even know what the steady state is enough to debate it.

**1:01:44** · So the questions around shiny hunters and the canvas and ransomware.

**1:01:49** · Yeah, so it's interesting. ransomware like let's look at what's the history of ransomware.

**1:01:57** · Ransomware actually started through state sponsored attacks.

**1:02:01** · It wasn't for money.

**1:02:03** · It was for political reasons.

**1:02:04** · If you go back, the biggest early Ransomware situations were not ransomware.

**1:02:09** · They were destructive cyber attacks.

**1:02:12** · Saudi Aramco was taken out by Iran.

**1:02:15** · The Sands Casino was taken out by Iran.

**1:02:19** · North Korea took out Sony.

**1:02:21** · That was actually my team at Facebook that showed that it was North Korea that had taken down Sony in 2012 or 2013.

**1:02:30** · And then we shared that with the FBI.

**1:02:34** · And so it evolved from those attacks into private sector attacks.

**1:02:42** · And right now there's literally so much infrastructure built around the business of ransomware, a lot of companies hire a ransomware negotiator to have them on retainer just in case they get ransomware.

**1:02:55** · I like the idea that there was actually a business profession I negotiate ransomware solutions.

**1:03:01** · It's a thing in 2026, and it's a best practice to have one of them on speed dial.

**1:03:07** · I think that we're in the bad state because government didn't do enough to react and understand the implications.

**1:03:14** · Now that governments like the UK government are doing all these bailouts, now that it's hit companies like healthcare companies in the United States, if you like.

**1:03:22** · The first time cybersecurity really impacted American citizens was the Colonial Pipeline one a whole bunch of the Northeast of the United States.

**1:03:30** · People were lining up and filling up their cars with gas and the block long lines because of a cyber ransomware attack.

**1:03:36** · The government is finally in the last couple of years, realizing we got to get involved.

**1:03:41** · We can't allow these organized groups, whether in Eastern Europe, or in Asia, or in the United States itself.

**1:03:47** · Governments have to get involved.

**1:03:49** · So law enforcement is starting to do a lot of takedowns, and now some other branches of government are thinking about how can we go after those gangs?

**1:03:58** · So how do we go after them before the attack rather than after.

**1:04:02** · If you think about the FBI'S role in cyber, they don't prevent cybercrime.

**1:04:06** · They try and do arrests after the fact.

**1:04:08** · And so we need more government involvement on the prevention side.

**1:04:11** · It's just been hampered by the fact that when our government goes to meet with the leaders of the governments in these countries were often negotiating more about the war in Ukraine or Taiwan.

**1:04:23** · And the cyber stuff is not getting to the top, but because the economic because the CEOs are now so worried about ransomware, our government is starting to become more proactive, and there are starting to be a lot more if you pay attention to the White House.

**1:04:38** · Cyber Czar in the last year, he's talked about allowing companies and organizations to go on the offensive.

**1:04:44** · And that is really a scary thing.

**1:04:46** · But also an interesting thing because it's like, what's your plan when you get punched, you want to be able to punch back or and some people say, the best way to win a fight is to punch first.

**1:04:57** · That was a quote from one of my CEOs.

**1:04:58** · I won't tell you which one.

**1:05:01** · But like you've got to be more proactive than just waiting until the ransomware starts to happen to you.

**1:05:09** · Great, thank you so much, Joe.

**1:05:11** · Come on.

**1:05:12** · It's fantastic.