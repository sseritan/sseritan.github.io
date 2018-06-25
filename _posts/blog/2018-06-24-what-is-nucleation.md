---
layout: post_page
category: blog
img: CNT.png
title: What is Nucleation?
description: What do rock candy, Coke + Mentos, and my first chemistry paper have in common? Nucleation!
---
## What is Nucleation?

Nucleation is the first step in the transition from a metastable phase to a new phase with a lower free energy.
Everything in thermodynamics wants to go downhill, but the original metastable phase was "trapped" somewhere up the hill.
Nucleation is what allows the system to get out of the trap and go downhill to a more stable phase.

My favorite example for nucleation is making rock candy.
By adding sugar to boiling water, you can add more sugar than you could to room temperature water.
When you cool the water back down, all the sugar stays dissolved, even though it wouldn't dissolve before!\\
This is now a metastable state - the system wants to remove some of the dissolved sugar back into the undissolved solid,
but it is currently trapped in a supersaturated state.

Microscopically, tiny clumps of sugar are growing and falling apart.
Eventually, one of the clumps (called a nucleus) will reach a critical size and will start growing much
faster than it falls apart.
At that point, it is easier for the sugar to attach to the growing crystal rather than try and nucleate themselves -
this is why we end up with a huge chunk of rock candy instead of the individual pieces of sugar that we started with.

There are other examples of nucleation that you may be familiar with.
Ever seen "flash freezing water", where someone takes a bottle of liquid water, gives it a sharp tap, and then the whole thing turns into a giant ice cube?
This is also nucleation, where the metastable phase is supercooled water and the two final phases are solid and liquid water.\\
Everyone's second favorite science experiment of dropping Mentos into Coke and watching the whole thing explode also involves nucleation.
This time, the nucleation is happening on the surface of the Mentos and involves the carbon dioxide trapped in the soda coming out of solution as a gas extremely quickly - thus the explosion.

## What Controls Nucleation?

According to classical nucleation theory, there are two factors that matter: the bulk free energy and the interfacial free energy.
The bulk free energy favors nucleation because the new phase is lower in energy, and scales like volume: $$V \propto r^3$$.
By contrast, the interfacial free energy dislikes the creation of two phases, and scales like surface area: $$SA \propto r^2$$.
The end result is that eventually the bulk free energy will win, but first we have to overcome a barrier caused by the interfacial free energy, as shown in the post image above.

At last, we get to the point of the paper: If we can control the interfacial free energy by adding a small amount of a third component into the system (i.e. additives), then maybe we could control nucleation!

## But Why Do We Care?

Well, chemical producers probably care, and they make a lot of the things we use on a daily basis.
Fractions of a percent in production efficiency can cost (or save) industry millions or even billions of dollars because chemicals are produced in large quantities.
Industrial processes are extremely complex and many factors influence the efficiency - however, being able to enhance or slow down nucleation would certainly help.
Maybe you would no longer need to go to extreme temperatures and pressures to get phase separation of their product by making it easier to nucleate.
Or maybe you could prevent your catalyst from precipitating out of solution by increasing the barrier to nucleation.

Either way, it is a scientific question worth pursuing.
If you are interested in the work that I have done on nucleation, you can check out [this paper]({{ site.baseurl }}{% post_url /papers/2015-01-07-nucleation %}).
