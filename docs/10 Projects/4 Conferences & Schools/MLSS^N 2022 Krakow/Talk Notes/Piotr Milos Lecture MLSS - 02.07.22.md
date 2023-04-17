---
type: lecture
status: open
priority: p4
project: MLSS^N 2022 Krakow
creationtag: 2022-07-02 09:09
infotags: [MLSSN, CL, continual learning]
people: "Piotr Milos"
date:
---

![[image-20220702090943210.png]]

Against [[catastrophic forgetting]]
- claims this is sorta solved

![[image-20220702091530410.png]]

![[image-20220702091906882.png]]


“we are not IID, that is we are changing distributions over time”

- [ ]  Hadsell et al. Embracing Change #reading

![[image-20220702091954650.png]]


![[image-20220702093033806.png]]

- Perhaps should put a B here for task B
- This is a regularization method

![[image-20220702093056915.png]]

Q: do you need an input telling the task
A: no defined protocol. Some define task ID, some specify that it does not. Packnet uses id

Q: is the only training happening on the pruned nodes?
A: Part of the data is kept 


![[image-20220702093731295.png]]

You record your solutions and then come back to them when they are available

![[image-20220702094026269.png]]

![[image-20220702094032793.png]]

![[image-20220702094140689.png]]

Maximize over actions

![[image-20220702094558459.png]]

![[image-20220702094922951.png]]

most of their experiments done on a cpu w/out gpu

![[image-20220702095208963.png]]


![[image-20220702095626421.png]]
In each case we choose the best task to transfer from

Q. 
What is the 0.46 here

A.
We look for the best transfer number and then sum over tasks(?)


![[image-20220702095826718.png]]
Q: Does it use experience replay?
A: You throw out the experience replay from task to task

![[image-20220702100858131.png]]

Better *than* MultiTask, training all the tasks at once

![[image-20220702101257576.png]]

Q.
MultiTask. Can you view CL

A


![[image-20220702102148575.png]]

![[image-20220702102949550.png]]



![[image-20220702102959356.png]]






