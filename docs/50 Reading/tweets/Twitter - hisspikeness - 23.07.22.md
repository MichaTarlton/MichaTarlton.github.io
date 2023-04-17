---
type: tweet
citekey: rossbroichFluctuationdrivenInitializationSpiking2022
author: "Friedemann Zenke"
handle: "@hisspikeness"
source: "https://twitter.com/hisspikeness/status/1539862963863134209"
date: "June 23, 2022 8:48 AM"
likes: 14
retweets: 7
replies: 1
---
See [[@rossbroichFluctuationdrivenInitializationSpiking2022]]

# Friedemann Zenke ([@hisspikeness](https://twitter.com/hisspikeness)) - June 23, 2022 8:48 AM

1/4 Surrogate gradients are a great tool for training spiking neural networks in comp neuro and neuromorphic engineering, but what is a good initialization? In our new preprint co-led by [@j_rossbroich](https://twitter.com/j_rossbroich) and [@JuliaGygax4](https://twitter.com/JuliaGygax4), we lay out practical strategies: [arxiv.org/abs/2206.10226](https://arxiv.org/abs/2206.10226)

[@j_rossbroich](https://twitter.com/j_rossbroich) [@JuliaGygax4](https://twitter.com/JuliaGygax4) 2/4 Neurons in the brain often fire seemingly stochastically due to large membrane fluctuations. We take this as our inspiration and show that initializing networks of LIF neurons in the fluctuation-driven regime constitutes an excellent initial state for subsequent training. [pic.twitter.com/XYC1FdMbcT](https://twitter.com/hisspikeness/status/1539863106381172736/photo/1)

![3_1539863032293105664](https://pbs.twimg.com/media/FV6xRPKWIAA3a1b.jpg)

[@j_rossbroich](https://twitter.com/j_rossbroich) [@JuliaGygax4](https://twitter.com/JuliaGygax4) 3/4 Deep spiking nets require even more care at initialization to avoid vanishing surrogate gradients. We show that firing rate homeostasis is an effective mechanism that refines the initial weights and restores activity propagation and thus training performance. [pic.twitter.com/tIL66Qnutd](https://twitter.com/hisspikeness/status/1539863232076255233/photo/1)

![3_1539863164799668225](https://pbs.twimg.com/media/FV6xY8yX0AEAGgw.jpg)

[@j_rossbroich](https://twitter.com/j_rossbroich) [@JuliaGygax4](https://twitter.com/JuliaGygax4) 4/4 In summary, we provide practical heuristics for fluctuation-driven initialization of deep recurrent and convolutional spiking nets (including networks obeying Dale’s law) that enable training to close-to-optimal performance across datasets. [pic.twitter.com/xrzGueNJbb](https://twitter.com/hisspikeness/status/1539863367673954304/photo/1)

![3_1539863301416525824](https://pbs.twimg.com/media/FV6xg5uXoAANS9k.jpg)

[Thread link](https://twitter.com/hisspikeness/status/1539862963863134209)