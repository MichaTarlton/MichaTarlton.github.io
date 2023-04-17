---
type: [development, results]
status: active
priority: p4
project: SBF-automata
creationtag: 2023-02-10 13:22
infotags: [SBFA, experiment, results]
people:
date:
---
For simplicity adding the results from both variants here, 
Split out into own docs later




---

### Variants
#### Weighted Majority Vote
- See detailed description and formalization here [[Weighted Majority Vote Version 27.01.23]]
#### Normalized Automata
- See detailed description and formalization here [[SBFA - Normalized Automata Vote]]

# Top Comments
- If we are approaching this from the energy argument, the non-prime RPs have the  agent pulling wayyy too often
- Where on the primes, it appears to quickly arrive at the solution early on
	- Again, need a time to solution variable
- I bet this is the fault of including lower primes which are then overweighted and very likely to over-contribute too often
- Try again but seeing if we can target a correct distribution of phases to timescale
- This perhaps cells for the penalty introduction
- Primes and other low-factored (number of factors which divise evenly) RPs are not evenly distributed in tries



# Initial Conditions
Shared initial conditions for both variants in order to compare.
- $T = 10,000$
- $RP = 50:61$
- $Oscillators \ Phases \ (n) = The \ first \ 25 \ primes$
- $Epochs = 100$
- $Initial \ weights \ (w_i) = \frac{1}{N}$

**Normalized Automata Only:**
- $Control \ Parameter \ (\alpha) = 0.5$

---

# Weighted Majority Vote

## Plot of Mean (over all epochs) Pulls (Weight of Raster)  for each Reward Phase (Y) over time (X)
![[image-20230210144657980.png]]

“Assemble of experiments” 

## RP =  59
### weights sorted desc
[1.00000000e+00 6.75366893e-19 7.24338168e-25 1.32971940e-29
 2.13446205e-31 5.11102456e-33 2.54891228e-33 2.56835088e-34
 1.01282259e-34 8.56722923e-35 7.93507283e-35 3.31322436e-35
 2.42698136e-35 2.42682525e-35 1.60488371e-35 1.21651798e-35
 1.21506334e-35 1.21339468e-35 1.21339468e-35 1.21339468e-35
 1.21339468e-35 1.21339468e-35 6.34863382e-36 6.06697341e-36
 6.06697341e-36]
### sorted highest value oscillators 
[59  2  3  5  7 11 13 17 19 23 31 29 41 37 53 43 47 67 71 73 79 83 61 89
 97]
 
### First 1000 Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators), for RP:  59
![[image-20230210144515074.png]]




### All Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators for RP:  59
![[image-20230210144529174.png]]




### Plot of Pulls for Each Epoch (Y) for RP:  59
![[image-20230210144653076.png]]
Pull distribution over all%%%%


### plot of mean pull density for each reward phase (over all epochs and oscillators)
![[image-20230210144829718.png]]
### Normalized to RP/T Plot of mean pull density for each reward phase (over all epochs and oscillators) 
![[image-20230210144949028.png]]


Mean pulls over time and epochs 
[0.319306 0.185251 0.263469 0.032032 0.374484 0.139666 0.292495 0.182679 0.244364 0.032086 0.31686 ] 

Normalized to amount of times reward period occurs RP/T, Mean pulls over time and epochs 
[0.00159653 0.00094478 0.00137004 0.00016977 0.00202221 0.00076816 0.00163797 0.00104127 0.00141731 0.00018931 0.00190116] 

sorted highest pulls rp [54 60 56 50 58 52 57 51 55 59 53]

---

## RP = 60 
### sorted highest value oscillators
[ 2 3 5 7 11 13 17 19 23 29 31 41 37 43 47 53 59 71 79 83 61 67 73 89 97]

### First 1000 Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators), for RP: 60
![[image-20230210150125121.png]]



### All Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators for RP: 60
![[image-20230210150130248.png]]



### Plot of Pulls for Each Epoch (Y) for RP: 60
![[image-20230210150139700.png]]





### plot of mean pull density for each reward phase (over all epochs and oscillators)
![[image-20230210150148990.png]]



Mean pulls over time and epochs
[0.319306 0.185251 0.263469 0.032032 0.374484 0.139666 0.292495 0.182679 0.244364 0.032086 0.31686 ]

Normalized to amount of times reward period occurs RP/T, Mean
pulls over time and epochs 
[0.00159653 0.00094478 0.00137004 0.00016977 0.00202221 0.00076816 0.00163797 0.00104127 0.00141731 0.00018931 0.00190116]

sorted highest pulls rp
[54 60 56 50 58 52 57 51 55 59 53]

---
---

# Normalized Automata
Note, not perfectly normalized. The control parameter creates a slightly uneven distribution, especially if split into different reward / penalty 

## Plot of Mean (over all epochs) Pulls (Weight of Raster)  for each Reward Phase (Y) over time (X)
![[image-20230210145057090.png]]

---

## RP = 59 (note prime)
### sorted highest value oscillators
[59 19 31 29 43 23 17 37 47 11 41 13 2 53 7 5 3 67 61 71 73 79 83 89 97]

### First 1000 Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators), for RP: 59
![[image-20230210145722998.png]]



### All Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators for RP: 59
![[image-20230210145735685.png]]



### Plot of Pulls for Each Epoch (Y) for RP: 59
![[image-20230210145742726.png]]





### plot of mean pull density for each reward phase (over all epochs and oscillators)
![[image-20230210145954175.png]]



Mean pulls over time and epochs
[0.337328 0.202682 0.280794 0.064101 0.395555 0.158655 0.310535 0.20175 0.263236 0.069428 0.329071]

Normalized to amount of times reward period occurs RP/T, Mean
pulls over time and epochs 
[0.00168664 0.00103368 0.00146013 0.00033974 0.002136 0.0008726 0.001739 0.00114998 0.00152677 0.00040963 0.00197443]

sorted pulls index
[ 4 10 6 0 8 2 7 1 5 9 3] 

sorted highest pulls rp
[54 60 56 50 58 52 57 51 55 59 53]


---

## RP = 60 
### sorted highest value oscillators
[ 2 3 5 19 17 13 23 11 29 7 31 43 59 37 53 67 41 47 79 71 61 73 89 83 97] 

### First 1000 Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators), for RP: 60
![[image-20230210145019402.png]]

### All Time-Steps: Plot of Mean Weights (over all Epochs) for the top 10 Oscillators for RP: 60
![[image-20230210145023362.png]]

### Plot of Pulls for Each Epoch (Y) for RP: 60
![[image-20230210145043232.png]]



### plot of mean pull density for each reward phase (over all epochs and oscillators)
![[image-20230210145216944.png]]

Mean pulls over time and epochs
[0.337328 0.202682 0.280794 0.064101 0.395555 0.158655 0.310535 0.20175 0.263236 0.069428 0.329071] 

Normalized to amount of times reward period occurs RP/T, Mean
pulls over time and epochs 
[0.00168664 0.00103368 0.00146013 0.00033974 0.002136 0.0008726 0.001739 0.00114998 0.00152677 0.00040963 0.00197443] 

sorted pulls index
[ 4 10 6 0 8 2 7 1 5 9 3] 

sorted highest pulls rp
[54 60 56 50 58 52 57 51 55 59 53]