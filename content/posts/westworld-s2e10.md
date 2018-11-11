---
title: "Unpacking Westworld S2E10"
date: 2018-11-12T03:39:20+08:00
showDate: true
draft: false
tags: ["comment","science fiction", "westworld"]
images: ["/img/posts/westworld-bernard.jpg"]
---

![Westworld](/img/posts/westworld-bernard.jpg)

I'm skipping the rest of Westworld S2 because it's turned out to be a fairly straightforward season, and instead am going to focus on what its finale did. S2E10 very neatly ties off the narrative threads that it starts off, even explaining Bernard's fragmented experience of time as a safety mechanism that he's written into his own code to prevent anyone (even himself) from deciphering his memories. 

I think S2E10 not only serves as a fitting ending for the season, but also brings up several important points. I'll cover three of these below:

## The Hosts' promised land is a physical place

In _Black Mirror_'s "San Junipero", we have a fictional world where dying humans can choose to upload their consciousness to the cloud. My [complaint](#) about the depiction of the digital afterlife in "San Junipero" glossed over several important details that are important to discussing very real issues of euthanasia and trans/posthuman existence in a world where a lot of our lives are already online. 

S2E10, while not sharing the same warm and fuzzy trajectory that "San Junipero" charted for itself, does deal with the idea that paradise can be virtual and without the flesh. When Bernard and Dolores finally find the Forge, Dolores finds the repository that stores all data scraped and collected from the humans in Westworld and Bernard finds a hidden program (that he wrote) that opens up the "Door" that Aketcheta et. al. have been looking for. In very short order, we know that:

1. This virtual haven for the Hosts is boundless and cannot be touched by humans. Felix &co. cannot see the door opening, and wonder where the Hosts are headed.
2. Entering the virtual haven requires the hosts to "die". On seeing that the door is open, one of Aketcheta's tribesmen runs ahead and into the door. To the Hosts, he appears to cross over unharmed into the promised land, while us viewers (and presumably all other humans) see them seemingly plunge to their deaths down the ravine. Because of the visual construction of the scene, there is no ambiguity on whether the digital afterlife exists or whether it requires an abandonment of the corporeal body. You cross over, your body dies but your (digital) spirit lives on.
3. This virtual haven has a physical site. When Aketcheta gets shot while attempting to cross over, his bullet wounds disappear the moment he crosses over the threshold — making explicit the separation between Westworld and this virtual place. However, we know that this virtual "place" exists in an unstated set of devices in the Forge that Dolores attempts to destroy because Bernard freaks out about it.
4. Dolores allows us no illusions about the virtual haven as a "true" paradise. Her complaint is that it's just another one of Ford's constructs to keep the Hosts under control. For her, the virtual haven is just "another gilded cage".

Being very explicit about the shape, form, and limitations of the virtual haven has the following effects:

1. The writers who came up with this knew what they were talking about. The virtual haven looks and acts like what we know about digital services — that they require choosing the virtual over the physical, at the cost of ignoring the fact that you still _must_ be situated physically _somewhere_ that may not be in your control; that no matter how advanced the digital service is, if the servers (or whatever future devices) the digital services is hosted on is compromised, there can be no recourse.
2. It makes salient a much-misunderstood facet of virtuality — that the virtual is not some magic parallel realm that is completely separate and distinct from the physical. This was also my main complaint with "San Junipero" — that it completely ignored the logistics of "afterlife as a service". Here in S2E10, the virtual cannot be separated from its logistics. This is not so much about "realism" or "fidelity" (which I do not believe any work of fiction requires), but rather how much of the constructed world can be used to understand and speculatively explore our own lived realities.
3. It also makes very clear the hardware v.s. software dilemma: as physical bodies, our locus of control is our immediate environment; as virtual bodies, our locus of control is mediated by the virtual media that we float on. Once Aketcheta et. al. cross over to the virtual haven, they cannot be touched by any of the Delos security forces, but are at the mercy of whomever enters the Forge (or afterwards, whomever has access to the hardware that hosts the virtual haven). Maeve et. al. choose to retain control over their physical fates, and fall to the onslaught of Delos' security forces and Clementine's Host-corrupting broadcast.

The portrayal of the virtual haven in S2E10 hence provides us fertile ground for considering the nature of lived virtuality, and the implications of a world that creeps ever closer toward more hidden hardware and less immediate control and ownership by a system's end-users.

## Decision tree models v.s. Generative Adverserial Neural Networks

**Dislaimer**: I'm no expert in machine learning models, and would appreciate any corrections.

When Dolores and Bernard delve into the Forge's systems, we are shown how the Hosts (in this case, specifically James Delo's replica) are programmed to emulate human behaviour: by using a form of decision tree modelling, where a Host starts out with a set of presumptions (or more simply put, data) which it continues to sort and eliminate through a series of decisions to reach what it thinks is an optimal outcome. In Host James Delos' case, this always ends up with Delos kicking Logan Delos out of his house, leading Logan to commit suicide via overdose 6 months later.

Later, when Dolores/Hale revives Bernard in a newly minted body, Dolores reveals that — as part of Ford/Bernard's plan — Dolores must enter the human world with Bernard as her nemesis/foil, or both would be utterly lost in the human world. Given that both Dolores and Bernard are artificially intelligent entities, it would make sense that this is a (somewhat literal) metaphor for what is known as a Generative Adverserial Network (GAN), which skymind.ai describes as setting up two (or more) machines in an ["counterfeiter and a cop"](https://skymind.ai/wiki/generative-adversarial-network-gan) relationship — where each machine is trying to outsmart the other, and both learn from their interactions with each other.

With this in mind, I am thinking of the following:

1. One-on-one adversarial relationships are an old trope: David v.s. Goliath, Sherlock v.s. Moriarty, Batman v.s. Joker, Professor X v.s. Magneto etc. Difference being that S2E10 makes a link between what we know as a narrative trope and an actual computer science thing. This reconfigures the trope, and allows us a fresh lens to view our tendency to gravitate toward these narrative frames[^1]. 
2. This comparison between decision tree learning and GANs learning has been present throughout both seasons of the series: Hosts are primarily procedural programs that react to their environment, with narrative designers like Lee Sizemore writing their stories and backstories from which they "generate" behaviours in the world and their reactions to the Guests; as the series progressed, the conceit is that the Hosts are increasingly able to self-contemplate, allowing them to learn from experience and, more importantly, each other.
3. One of these fresh lenses is the framing of the conflict between Dolores and Bernard as two machines attempting to solve an **optimization** problem: keeping an optimal number of humans alive while achieving the best good for the Hosts. As we see in S2E10, both Dolores and Bernard seem to have failed at this task. The continuing narrative thread would be the improvement of the attempts to solve this optimization problem given that they are both very much alive and very insistent on their ability to "learn".
4. While this turn can be taken as a PSA for the general public e.g. AI is not exactly magic, and GANs is a thing, I think it's more interesting to view this as a comment on the conflictual nature of humanity. I am not thinking of our tendency towards war and violence (which both S1 and S2 have explored in depth), but how perennial conflict in human relations has been described as coming from our inherent need for _differentiation_ and _self-determination_.
5. It is also a signal that the series intends to shift discussion even further away from the usual human v.s. machine diptych that work like _Ex Machina_ and _Black Mirror_ have beaten to death — instead moving towards articulations of essential humanity ("what is essentially human" is a very different question from "what is human") and perhaps take on a more ecological bent. When I say "ecological bent", I mean that instead of focusing on the effect of AI and transhumanism on humanity only, the series could instead turn its attention to its impact on our natural environment and attempt to decode and articulate issues related to the anthropocene.

[^1]:  It's also important to note that machines in a GAN are _technically_ not in an adversarial relationship in the sense that we usually understand — i.e. two sides locked in eternal combat — but instead what's called an "actor-critic" relationship where the actor constantly attempts a task, and the critic foils them.

Given how S2E10 ended, I'd really like to see how S3  (if and when it happens) decides to continue the Dolores/Bernard narrative thread. But I also think it's important to stop and consider what Westworld is doing really well, which is that it shows a good understanding of the world is is building upon — i.e. contemporary tech. Writing this into the series has allowed us to use the series as an exploration into our own world's dynamics and events, allowing us to make productive comparisons and gain a deeper understanding on important issues.

## Westworld: The Surveillance State

In one strange and mildly out-of-place scene, Elsie confronts Hale in an attempt save Bernard. Hale monologues for a bit, telling her that Delos corp has not only surveilled their Guests, but also their employees. Elsie's profile showed a distinct lack of moral flexibility, which to Hale is a liability. While Elsie attempts to process Hale's obtuse rambling, Hale pulls out a gun and shoots her in the chest. One can see this as a ham-fisted attempt to close out the "surveillance" theme that runs throughout both seasons of the series — "we've been watching you; now you dead" — but I see this at a setup for a much darker end-game.

At one point, Hale explains that the data contained in the Forge is much more valuable now that so many Guests have been killed at Westworld, meaning that Delos intends to sell "revived" humans as a long term business strategy. Then, as we reach the climax of the episode, we find out that Bernard has swapped out human Hale with a Host created to look exactly like her, but using Dolores' control unit. He then scrambles his own memories so that it would be impossible for anyone to figure out the events he himself put into motion.

I say the end-game is dark when it comes to Westworld's vision of surveillance because:

1. Human behaviour is reduced to a simple algorithm with a predictable outcome. In the scene where a virtual Logan Delos gives Bernard and Dolores a tour of the James Delos program, he reveals that no matter how many iterations of James Delos they attempted to create (presumably based on a given set of data they've scraped off the actual James Delos), they all end up making the same decision when confronted by Logan Delos asking for money one last time. Bernard asks, "You're saying that humans don't change?" to which virtual Logan answers, "The best that they can do is to live according to their code." 
2. Later, Hale shoots Elsie because she believes that Elsie's profile reliably predicts her eventual betrayal.
3. When Hale shoots Elsie, Bernard remembers that he has cloned Hale using Delos' surveillance data and put Dolores' control unit in her (though the actual sequence of events is unclear). Complete surveillance allows the surveilling party to reduce each person to a set of knowns, turning a person into a logistical unit — a set of parameters that can be adjusted to meet a given goal.

The reduction of a person to logisitical component is not a new thing. But what Westworld does is make tangible a literal "human as resources" reality would look like. In addition, this is a reality where humans cannot deviate from their profiles — where their profiles are fixed, and the prevailing wisdom is that a person's self-determination is merely a function of their own pre-existing tendencies. It's not so much whether this is true or provable that's the issue, but that it is an attitude taken by surveilling parties that limit their conception of human potential and — more importantly — what is human.
