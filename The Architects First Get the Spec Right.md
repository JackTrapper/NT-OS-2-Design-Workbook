The Architects: First, Get the Spec Right
========================================

Posted: March 06, 2000	

*Once upon a time ... there was NT OS/2.*

*Every month, Nadine Kano prowls the halls of Redmond to profile the real folks behind Windows 2000 development. This month: **David Cutler** and **Mark Lucovsky**, who helped guide the operating system from its infancy.*

*"Well, we were just about to leave,"* David Cutler says from behind his desk.

I'm five minutes late to my interview with Cutler and Mark Lucovsky, two of the original architects of the Microsoft Windows NT operating system.

As I wilt into the carpet, I realize Lucovsky must have mentioned to his colleague how nervous I was about approaching them. After all, who the hell am I to be talking with these guys? They are developers’ developers — two of the visionaries behind the operating system that began as NT OS/2 and has evolved into Windows 2000. Cutler refuses virtually all interviews with the press, but he and Lucovsky are willing to talk to me, a program manager from down the hall. They probably find my nervousness amusing.

Build it, ground up
-------------------

I was a college senior when Bill Gates personally recruited Cutler, Lucovsky, and others from Digital to begin the NT OS/2 project at Microsoft. Their quest was to build, from the ground up, an advanced PC operating system, something far beyond MS-DOS. NT signified "New Technology."

One of my engineering classmates, David Treadwell, joined Microsoft to work on NT. I remember how excited he was to be a part of this obscure little development effort that none of us really understood. Remember that 1989 was before Windows 3.0. In 1989, Windows was still a nonentity.

I sputter a bit as I look at the clock on Cutler’s desk, smile, and take a seat.

To begin the interview, I want to set the context. What was the team’s initial vision for an operating system?

*"We had five or six major goals,"* says Cutler. He pulls a copy of Helen Custer’s book Inside Windows NT from his bookshelf and flips through the pages. *“Portability, reliability, extensibility, compatibility, performance. I think that’s right. Let me see."*

He goes back to the bookshelf to retrieve a thick black binder. The label on its spine says "NT OS/2 Design Workbook." He flips through some pages.

*"Here,"* says Cutler, casually handing me the volume. *"Why don’t you borrow this? As long as I get it back,"* he continues. *"I think it’s one of the only copies left."*

Four inches of spec
-------------------

Inside the binder, separated by a dozen neatly arranged tabs, are 4 inches of documents that make up the original specification. Dated 1989 and 1990, they bear names like Kernel Chapter, Virtual Memory, I/O Management, File System, and Subsystem Security. Page 1 of the introduction, written by Lou Perazzoli, reads: 

> The NT OS/2 system is a portable implementation of OS/2 developed in a high-level language. The initial release of NT OS/2 is targeted for Intel 860-based hardware, which includes both personal computers and servers...

I try to keep my expression casual as I set the volume on the table next to me. I know these guys find reverence irritating. I hope it’s not raining. How will I get the spec back to my office? Doesn’t this binder belong in a museum? God, I hope it’s not raining.

*"Do you think you achieved these goals?"* I ask.

*"We certainly achieved extensibility and portability,"* Lucovsky says. *"We tested ourselves by not doing the x86 version first. We did the RISC (Reduced Instruction Set Computing) stuff first. It would have been so easy to drop the RISC support; everyone in the company wanted to. But the only way to achieve portability is to develop for more than one platform at a time. It cost us a lot to keep portability alive, but we did, and that has made it easy for us to respond to things like Merced,"* he says, referring to the 64-bit chip from Intel.

No embedded semantics in the kernel
-----------------------------------

At every step, Cutler and Lucovsky explain, the team prioritized design. They knew that the code they were building had to last for years. This meant thinking ahead, understanding, for example, that hardware would evolve — perhaps drastically.

*"We tried to create a system that had a good, solid design, as opposed to one that would run optimally on hardware of the time,"* Cutler explains. *"When we started, we were working on 386/20’s. At the time that was a big, honking machine. Since our design had to be portable, we didn’t allow people to optimize code in assembly language, which is hardware specific. This was hard for the Microsoft mentality at the time. Everyone wanted to optimize code in assembler."*

The original vision kept the operating system nimble. *"We didn’t embed operating-system semantics into the kernel,"* Cutler explains. *"So when we switched from OS/2 to Windows, we didn’t take a major hit. If we had built OS/2 threading or signals into the kernel, we would have been in trouble. Instead we built the OS in layers and created subsystems to handle OS/2, Windows, and POSIX."*

Not everything can top the list
-------------------------------

But the original vision also required tradeoffs. The team’s engineering philosophy was to focus on one major area at a time. *"*That’s why we wrote a spec,"* says Lucovsky. *"The way we see it, write down what you’re going to do, and then execute on it. Don’t stand around dreaming, telling yourself, ‘Wouldn’t it be nice if…’ We spelled out what we planned to do right there,"* he says, pointing to the spec sitting next to me, *"and we stuck by what we said we would do."*

*"For example, we went with a client-server design, though at first things like context-switching rates and cache misses were too high,"* Lucovsky recalls. *"Things were slow. But we didn’t let ourselves get concerned with the size of memory. Not everything can be at the top of the list. We consciously put performance lower on the list than extensibility and didn’t pay close attention to memory footprint until (version) 3.5."*

We talk about how the operating system evolved with each release, from memory optimizations and Power PC support in versions 3.5 and 3.51 to kernel-mode GDI and User, plus a new user interface in version 4.0. *"The basic, internal architecture has not changed, except for Plug and Play,"* Cutler says.

*"We wanted a good design from the beginning so that, ideally, people could put anything on top of the system once it was there. We focused on the underpinnings. We wanted to minimize the need to add to the base or to tear up the base, because doing those sorts of things creates a lot of bugs. If moving forward you don’t have to touch the basic code except to make small tweaks, then you know you got it right."*

Some things must wait
---------------------

At the same time, Cutler admits, *"Nothing is ever architecturally correct."* Needs evolve, and it takes time to build an operating system. Although support for distributed computing and clustering were part of the original vision, features such as the Active Directory haven’t come to fruition until Windows 2000. *"If we tried to give customers everything with the first release, we would never have finished it,"* Lucovsky says.

Cutler elaborates on this philosophy. *"If what we desire is to have a mature operating system, then we need to achieve revolution through evolution, through incremental improvements. Within five iterations of an operating system like Windows NT, you see a big difference."*

Both Cutler and Lucovsky see taking advantage of every opportunity to increase quality as the top priority for Windows.

Reliable is cool
----------------

*"I’d much rather see the most reliable and usable operating system than the most whizzy-bang operating system,"* Cutler says. *"To increase reliability we have to make choices. For every 10 bugs we fix, we may introduce three more. But do you want to ship with 10 bugs, or do you want to ship with three?"*

*"Do you want one more new feature,"* Lucovsky concurs, *"or do you want to fix more bugs?"*

*"When the Internet was first catching on, it was OK if your browser crashed once in a while. But these days, if you go to an e-commerce site and you hit the ‘Buy’ button, things had better work. When you’re dealing with a leading-edge piece of technology, you can play fast and loose with it. But as the technology matures, playing fast and loose isn’t acceptable anymore. This is characteristic of the maturing process for a product like Windows. People will put up with more from the bleeding edge."*

*"What I think is cool,"* Cutler interjects, *"is that the system doesn’t crash, and it doesn’t lose my work, and it has functionality. I could care less that the visuals are flashy if my 32-gig hard drive goes away."*

Communicating quality
---------------------

*"And if you’re a consumer,"* Lucovsky responds, *"you want even better reliability."* He concludes: *"Quality is the most important vision that everyone working on this product needs to share. It isn’t always easy to communicate how we’re going to do this, particularly as the team gets bigger."*

The growth in the number of people working on the project over the last 10 years has other downsides, Lucovsky notes. *"When you have a bigger group, quality problems become especially detrimental to productivity. Say it takes 10 developers and testers to fix one bug. Whoever put that bug in there just caused 10 people to lose time. We’re working to make sure our development tools keep up with the growth in our system and our team. We’re streamlining the process in ways that will make a dramatic difference in the way we build the code."*

*"If we want to stay competitive,"* agrees Cutler, *"we have to invest money in tools and mechanics as well as features. We need to put guidelines on paper so that people stay good at planning. Simple things like writing a good spec are basic to software engineering."*

Museum quality
--------------

It all comes back to the spec.

As I leave Cutler’s office, I wrap the NT/OS2 spec in my jacket and head back to my building. I have three computers with lots of whiz-bangy, new fangled things running on them, but for a few hours it’s the spec that holds my fascination. As a Microsoft geek, I feel like I’m holding a piece of history. And it turns out I am. This fall, the spec I borrowed for a time will join the Information Technology collection at the Smithsonian Institution’s National Museum of American History in Washington, D.C. It’s another good reason to write a spec.