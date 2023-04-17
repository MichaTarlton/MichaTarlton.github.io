---
aliases: []
type: [project, event]
project: MLSS^N 2022 Krakow
status: open
priority: p5
creationtag: 2022-05-30 15:11
infotags: "Summer School"
url: "https://mlss.mlinpl.org"
---
# Dataview
## Pages
```dataview
TABLE without id rows.file.link AS "Related",
rows.file.ctime as "Created",
rows.infotags as "Tags"
FROM ""
WHERE contains(project,"MLSS^N 2022 Krakow")
OR contains(project,"MLSSN") AND !contains(type,"lecture")
GROUP BY type
SORT file.ctime asc 
```
## Lectures
```dataview
TABLE without id file.link AS "Related",
file.ctime as "Created",
infotags as "Tags"
FROM ""
WHERE contains(project,"MLSS^N 2022 Krakow")
OR contains(project,"MLSSN") AND contains(type,"lecture")
SORT file.ctime asc 
```
# General
https://www.youtube.com/channel/UCmXKn-Xeq1ZTAQBTwsYw4AA

[MLSS 2022 – Machine Learning Summer School Cracow](https://mlss.mlinpl.org)

[Slack Channel](https://app.slack.com/client/T03FUNX284Q/C03F7BASRKN)

[https://mlss.mlinpl.org/wp-content/uploads/Info_MLSSN.pdf](https://mlss.mlinpl.org/wp-content/uploads/Info_MLSSN.pdf)

[[Info_MLSSN.pdf]]




# Videos
**Day 1 (Monday)** - [https://youtu.be/N447XbErsGE](https://youtu.be/N447XbErsGE)

**Day 2 (Tuesday)** - [https://youtu.be/raNmQkiIvLs](https://youtu.be/raNmQkiIvLs)

**Day 3 (Wednesday)** - [https://youtu.be/1eFzU_Qr1SQ](https://youtu.be/1eFzU_Qr1SQ)

**Day 4 (Thursday)** - [https://youtu.be/ZV362uRi67o](https://youtu.be/ZV362uRi67o)

**Day 5 (Friday)** - [https://youtu.be/gRAMMvfqY7g](https://youtu.be/gRAMMvfqY7g)

**Day 6 (Saturday)** - [https://youtu.be/ha_uflUZMfA](https://youtu.be/ha_uflUZMfA)






# Schedule
> the official programme of the summer school **starts at 9am Monday 27th June and ends 5pm Saturday 2nd July**.

So plan on **Sun 26 - Sun 3rd**

![[image-20220530151745627.png]]



# Accomodations
- [x] Created some arrangements in berg hansen. See there for flight and hotel once approved. #p1 ✅ 2022-06-07

> I am Aleksandra (you can also call me Ola), and I am one of the organizers of the MLSS^N. I am currently working on some information sheet for students coming to Kraków, but until it is finished I want to give you some tips about accommodation and public transport.
> 
> In general, we do not provide any accommodation for the students, so you need to select a place that suits you best on your own. I am attaching some tips in the file below. Kraków is a very beautiful city with a wonderful historical site and many tourist destinations. It was once the capital of Poland, with the Wawel Royal Castle being the residency of Polish Kings. 
> 
> Therefore, **I would advise you to stay near the Old Town or the Kazimierz Districts**.
> The best trade-off between commuting to the Campus and being close to the city center is to find a place near the Grunwald Roundabout (“Rondo Grunwaldzkie”). It is a rather large communication hub, so you can get to the Campus with a direct connection (trams 52/73 or bus 194), at the same time being a walking distance away from the Wawel Castle .
> **The Info sheet is available at:**  
> [https://mlss.mlinpl.org/wp-content/uploads/Info_MLSSN.pdf](https://mlss.mlinpl.org/wp-content/uploads/Info_MLSSN.pdf) (edited)

## Hotels
[hotels rondo grunwaldzkie – Google Hotel Search](https://www.google.com/travel/hotels/Rondo%20Grunwaldzkie,%20Krak%C3%B3w,%20Poland?q=hotels%20rondo%20grunwaldzkie&g2lb=2502548%2C2503771%2C2503781%2C4258168%2C4270442%2C4284970%2C4291517%2C4306835%2C4515404%2C4597339%2C4649665%2C4722900%2C4723331%2C4733969%2C4741843%2C4754388%2C4757164%2C4758493%2C4762561%2C4786153%2C4786958%2C4789857%2C4791627&hl=en-NO&gl=no&cs=1&ssta=1&ts=CAESCgoCCAMKAggDEAAaRwopEiU6I1JvbmRvIEdydW53YWxkemtpZSwgS3Jha8OzdywgUG9sYW5kGgASGhIUCgcI5g8QBhgaEgcI5g8QBxgDGAcyAggBKhEKDWIECAEQACgBOgNOT0saAA&rp=ogEjUm9uZG8gR3J1bndhbGR6a2llLCBLcmFrw7N3LCBQb2xhbmQ4AUAASAI&ap=SAAwAVrFAQoFCNIGEAAiA05PSyoWCgcI5g8QBhgFEgcI5g8QBhgGGAEoALABAFgBaAFyBAgCGACaASUSI1JvbmRvIEdydW53YWxkemtpZSwgS3Jha8OzdywgUG9sYW5kogETCggvbS8wNDkxeRIHS3Jha8Ozd6oBDgoCCCESAggVEgIILxgBqgEGCgIIYhgAqgEHCgMI9QEYAKoBCgoCCBwSAghHGAGqAQoKAgguEgIIDBgBqgELCgIIUBIDCIQBGAGSAQIgAaoCAggBaAA&ictx=1&utm_campaign=sharing&utm_medium=link&utm_source=htls&ved=0CAAQ5JsGahgKEwjg_Mmfq4f4AhUAAAAAHQAAAAAQmwE)
Around 800 - 1200 kr

## Flight
[Oslo to Kraków | Google Flights](https://www.google.com/travel/flights/search?tfs=CBwQAhooagwIAhIIL20vMDVsNjQSCjIwMjItMDYtMjVyDAgCEggvbS8wNDkxeRooagwIAhIIL20vMDQ5MXkSCjIwMjItMDctMDNyDAgCEggvbS8wNWw2NHABggELCP___________wFAAUABSAGYAQE&hl=en-NO&gl=no&tcfs=Ei0KCC9tLzA0OTF5EgdLcmFrw7N3GhgKCjIwMjItMDYtMjYSCjIwMjItMDctMDMYAiIYCgoyMDIyLTA2LTI2EgoyMDIyLTA3LTAzUgA&g2lb=2502548%2C2503771%2C2503781%2C4258168%2C4270442%2C4284970%2C4291517%2C4306835%2C4515404%2C4597339%2C4649665%2C4722900%2C4723331%2C4733969%2C4741843%2C4754388%2C4757164%2C4758493%2C4762561%2C4786153%2C4786958%2C4789857%2C4791627)
NOrwegian air : 2698kr



# Costs
(all in nok)
Registration:   1 611,73
- See pdf of credit slip in download folder
- 
Accommodation:
	Hotel: 1200 kr
	x 7 Nights: 8400

Travel
	Flight: 2698
	Taxi: 1200
	Public: 124
	to-from OSL: 450
Food:
	avg meal: 89 
	x7 days x3: 1869
Discretionary spending:
	1000 a day isn’t too weird but I honestly don’t know
	I’m not adding this to the sum total for now

Sum: 16353 NOK
