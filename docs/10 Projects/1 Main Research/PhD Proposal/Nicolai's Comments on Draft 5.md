---
type:  comments
status: active,
priority: p4
creationtag: 2022-05-21 18:40
infotags: Nicolai
---

I had a look at your phd project description, here's some unsolicited feedback :P 

I think the general direction that you're aiming at is awesome (and I understand now even more why you're eager to discuss, hehe). In particular, you want to address one - if not the - biggest issue in (Deep) RL, but now in a spiking system. 

If you solve it here, you'll also solve it there. You just need to be aware that people who have knowledge of this might be afraid that you aim very high.

I'm not saying that's an issue, quite the contrary I love it when people have a vision for what they want to achieve, but some might perceive it critically. 

In any case, the introduction might need a few improvements regarding wording or "flow" of the document (for instance, you talk about neuron-to-neuron communication, then whole network, then neuron-to-neuron again). 

I'd also be careful with stating that SNNs are "naturally online learning". They are only if they are endowed with adequate methods (STDP, or some other Hebbian learning).

I particularly liked the Research Questions Section. You could base the research questions also on some observations or models from/of the Hippocampus. For instance, there is evidence of time cells in the Hippocampal formation, i.e. cells that respond for certain time intervals. 

There's also the idea that place cells encode multiple scales regarding time (I forgot the paper title, but the author was Ida Monennejad). 



For Section 3, the reference for synfire chains is Abeles et al. 1993, Dynamics of neuronal interactions in the frontal cortex of behaving monkeys. I didn't understand what you meant by "rolling windows" though ;) Btw the idea of synfire chains can be extended to proper Hebbian Assemblies in spiking neural networks. This is to some extend elaborated on for instance in Wennekers & Palm 2000, Cell Assemblies, Associative Memory, and Temporal Structure in Brain Signals.

Also of interest might be Wennekers & Palm 1996, Controlling the speed of synfire chains. Btw. Günther Palm was one of my former profs, which might explain why I'm so interested in what you'll be working on ;) And by coincidence, I'm currently re-reading their papers as well. So, generally speaking again, I really look forward to all the cool stuff you'll be doing!


btw I think it make sense to address the credit assignment issue over long time scales in a spiking neural network, and even think it is beneficial to do so and not in a "classical" deep network. 

Reason being the temporal dynamics exposed by spiking networks, which on the one hand disallow to use backprop through time in a classical sense and thus forces to look for alternatives, and on the other hand also forces to think about computation as "computation in time by exploiting temporal dynamics". So, win-win situation more or less (at least in my view)


> You
> I guess we'll have to discuss synfire chains as I do not really understand them. I had earmarked them as an instance of time representation in SNNs but have not yet had time to read about them.

The idea is actually rather simple. Imagine you have several neurons chained after another. So for instance neuron 1 is connected to neuron 2, neuron 2 to 3 and so on. If you have this chain of neurons, and you make the first spike, then neurons 2,3,... will spike in sequence. 

That's more or less the smallest synfire chain you can build. Usually, however, you would assume that it's not just one neuron per "step" but a bunch of neurons. 

So, say bunch 1 is connected to bunch 2 and so on. This is essentially a synfire chain. These "bunches" of neurons are usually called assembly, though, and multiple assemblies can be within one set of neurons. 

You see, it's essentially just nesting populations of neurons in bigger populations. There's still a bit more to it, e.g. a neuron can "participate" in multiple assemblies, i.e. overlap with multiple bunches, but that's not required. 

Looking at this whole thing, if you were go start the chain by firing the 1st assembly of neurons, then the second would fire in autonomously. There are some ideas how to control the sequence, I think the relevant paper is Wennekers & Palm, Controlling the speed of synfire chains. If you want to know more about synfire chains we can also just talk as soon as your head is free again :)