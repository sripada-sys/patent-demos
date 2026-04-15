# Patent Research Brief — EP0682786
**Method and Apparatus for Operating Geography-Altering Machinery Relative to a Work Site**
Assignee: Caterpillar Inc. · Filed: December 8, 1993 · Granted: May 22, 2002 · Expired: November 18, 2014
Searched: April 15, 2026 · Sources: Google Patents, Wikipedia (GPS, Differential GPS, Caterpillar Inc., Trimble Inc.)

> **Episode 1** of "Build the History of Machine Guidance"
> Target demo file: `demos/ep0682786-guidance-demo.html`

---

## 0. ELI5 — Explain Like I'm 5

Imagine you are building a giant sandcastle, and someone draws a picture of exactly how tall and wide each part should be. Before this invention, workers had to walk around constantly sticking measuring sticks in the sand to check if the bulldozer was digging in the right place — and the bulldozer kept knocking the sticks over. This invention put a satellite receiver on the bulldozer and a screen in the cab showing a colour map: red means dig more, blue means stop digging, yellow means perfect. For the first time, the machine knew exactly where it was and exactly how far it was from the plan — without anyone walking around with a stick.

---

## 1. The Problem Before
*What pain existed before this invention? What did people or machines have to do instead?*

Before this invention, earthmoving sites were laid out using physical grade stakes driven into the ground every 25–50 feet, topped with coloured ribbons indicating target elevation at that point. Surveyors used optical line-of-sight instruments in a static, point-by-point method to capture coordinates and build a 3D site model, a process requiring repeated equipment setup moves around the site. Operations were halted periodically so survey crews could re-measure actual terrain against the design model to assess progress, interrupting machine production. Large skilled survey crews were required on-site throughout construction to set and re-set stakes as machines disturbed them, and to direct operators toward target elevations. Machine operators had no real-time knowledge of how their cumulative material movement compared to the finished design — they relied entirely on the height and colour of nearby stakes, which were regularly run over and destroyed.

---

## 2. The Invention in Plain Language
*What does this patent actually claim? Strip the legal language. What is the core idea?*

The patent claims a system that stores two 3D digital maps of a construction site — one representing the target design and one representing the current actual terrain — and uses real-time GPS to continuously compare them, generating signals that tell the machine where to cut or fill. A machine-mounted GPS receiver computes the blade's 3D position within a few centimetres, approximately once per second, without the machine ever stopping. A fill-in-the-polygon software algorithm interpolates the blade path between consecutive GPS readings, so the actual-terrain model is updated even at machine travel speeds. The difference between actual and desired models is shown to the operator as a colour-coded plan-view display — red grid cells require cut, blue require fill, yellow are at grade — with coarse (1.0-foot) and fine (0.1-foot) scalar indicators. Alternatively, the same difference signal closes a control loop directly through the machine's existing electrohydraulic actuators, controlling blade height automatically without operator input.

---

## 3. Science and Engineering
*Why was this hard? What physics, mathematics, or engineering had to be understood or solved?*

The central engineering challenge was achieving centimetre-level 3D positioning for a machine moving at walking speed across a dusty, vibrating construction site — an environment hostile to sensitive electronics and continuous satellite reception. Phase differential GPS measures carrier-wave phase rather than code timing and can achieve sub-centimetre positioning, but requires continuous satellite lock and on-the-fly ambiguity resolution while the machine is in motion, a capability that was a live research frontier in 1993. GPS achieved Initial Operational Capability of its 24-satellite constellation in December 1993 — the same month the priority applications were filed — while Selective Availability simultaneously degraded civilian C/A-code accuracy to approximately 100 metres, obligating the system to rely entirely on a local reference receiver radioing real-time corrections. The differencing algorithm had to compute blade-tip position from cab GPS position plus surveyed antenna offset geometry, account for machine heading and pitch, and update a grid-based terrain model at 1 Hz without missing ground traversed between samples at 18 km/h. Storing and differencing two complete 3D site models in real time on the 8 MB RAM, 486DX computers of 1993 required explicit attention to data structure efficiency across potentially thousands of grid elements.

---

## 4. Who Built It and Why
*Assignee context. Why did this company file this patent at this moment? What competitive or market pressure drove it?*

The patent was filed by four named Caterpillar R&D inventors: Adam J. Gudat, Daniel E. Henderson, Gregory R. Harrod, and Karl W. Kleimenhagen. Caterpillar had been building GPS-based vehicle navigation patents internally since at least 1989, giving it six years of prior GPS positioning research to draw on. A five-month UAW strike ended in 1992 and a 17-month UAW strike began in 1994 — December 1993 was the single window of labour peace between them. Caterpillar simultaneously filed US5471391A (same priority date) extending the identical architecture to compacting machinery, confirming coordinated multi-machine IP capture in one sprint. Komatsu had filed its own GPS construction machine patent in Japan in 1988. and Spectra-Physics had filed a competing real-time earthmoving patent in 1993 — the competitor landscape that drove Caterpillar to file broadly and quickly.

---

## 5. What It Displaced
*What technology, method, or job did this invention make obsolete or significantly less necessary?*

The invention displaced the physical grade staking system — wooden hubs and offset stakes placed every 25–50 feet — along with the surveying labour needed to place, maintain, and replace them as machines destroyed them. It displaced laser plane grading systems (Spectra-Physics, US5375663A, 1993) which projected a spinning laser beam to create a flat reference plane — geometrically incapable of guiding complex 3D contours and dependent on line-of-sight through dust and machine vibration. The static optical total station — which required a tripod setup, backsight, and manual move for every new survey point — became unnecessary for real-time progress verification on GPS-equipped sites. Grade checkers — workers who walked earthmoving sites with grade rods after each machine pass and radioed corrections to operators — were functionally eliminated on machine-control-equipped operations. Manual re-staking after each machine pass, which could consume a full survey crew's day on a large earthworks project, was replaced by a self-updating digital database that persisted to disk and resumed the next morning.

---

## 6. Economic Impact
*What did it cost before vs. after? Who gained? Who lost revenue or market position?*

Before GPS machine control, earthmoving contractors typically required 2–3 machine passes over any area because operators without real-time feedback chronically over- or under-cut, consuming extra diesel and machine hours on every project. The commercial products descending from this patent (Cat AccuGrade, Trimble GCS900) retailed for $50,000–$100,000 per machine installation in the early 2000s, but enabled contractors to cut total grading passes by 30–50% on adopting sites, producing fuel and schedule savings on large projects. Spectra-Physics lost its position as the leading earthmoving guidance technology vendor as GPS machine control became commercially established through the Caterpillar-Trimble partnership. Trimble's annual revenue grew from approximately $270 million in 1999 to over $1 billion by 2007, a period during which the CTCT joint venture machine control business was a primary growth driver. Caterpillar's position as market share leader for grading equipment was reinforced by offering integrated machine control as a differentiated feature that competitors without comparable GPS IP portfolios could not immediately match.

---

## 7. Human Capital Shift
*Which jobs disappeared, changed, or were created? Who had to learn something new? Who was no longer needed on the job site?*

Grade checkers — semi-skilled workers who walked earthmoving sites with grade rods after each machine pass and radioed cut/fill measurements to operators — became structurally unnecessary on GPS machine-control-equipped sites, eliminating a labour category present on every substantial earthworks project. Survey crews that provided day-long staking and re-staking services lost that ongoing billable scope; their role compressed into a one-time digital model setup at project start and a reduced verification role at closeout. Machine operators required new training to interpret colour-coded machine control displays, read coarse and fine grade indicators, and trust automated blade control to override their own manual inputs — a skills transition documented in operator certification programs introduced by Caterpillar and Trimble. Project engineers gained the ability to download the machine's accumulated actual-site model at end of day for progress verification, replacing the daily survey crew deployment that had previously served that function. GPS machine control technicians and system calibration specialists emerged as a new field trade category by the late 1990s, since each machine required a precise antenna offset survey, periodic calibration, and radio link maintenance to sustain centimetre accuracy.

---

## 8. What Came Next
*What did this patent directly enable? What are its immediate successors — in the patent family, in the industry, in the technology?*

Caterpillar's US5471391A, filed the same month (December 1993) with the same priority date, extended the identical twin-model GPS architecture to compacting machinery — confirming the system was designed as a platform, not a single-machine solution. Trimble and Caterpillar began commercial collaboration on GPS receiver hardware for construction vehicles in 1995, with the first blade-mounted GNSS tool for bulldozers produced that year. The Caterpillar Trimble Control Technologies (CTCT) joint venture, formed April 1, 2002, commercialised this technology as Cat AccuGrade and Trimble GCS900 — the dominant paired commercial products in global earthmoving machine control. EP0682786 accumulated 201 citing patents spanning Caterpillar, Trimble, Komatsu, Wirtgen Group, Topcon, Leica Geosystems, Carnegie Mellon University, and Stanford University — mapping the entire subsequent machine control and autonomous construction equipment industry. The twin-model, real-time-differencing architecture became the structural template for all subsequent machine control extensions — excavators, scrapers, pavers, motor graders, and compactors — through the 2010s.

---

## 9. Demo Angle
*What is the core claim a student can implement with a phone or $20 hardware? What is the minimum faithful reproduction of the invention?*

The core demonstrable claim is a system that compares a defined desired-terrain model to GPS-measured actual positions in real time and colour-codes the difference: red above target, yellow on grade, blue below — implementable with a phone browser using the Geolocation API, no hardware purchase required. The student defines a simple sloped plane as the "desired" model (three corner elevations), then walks a 10×10-metre test plot while a web app continuously compares incoming GPS coordinates to the target and renders the colour-coded cut/fill difference on screen. To replicate centimetre accuracy: connect to a free NTRIP corrections feed from a national geodetic service, replicating the patent's base-reference-station-plus-radio-correction architecture using modern internet delivery instead of a local radio link. The minimum faithful reproduction of the display claims requires no machine at all: one person walking a grid holding a phone displaying a custom web app that renders real-time cut/fill colour. For the automatic control embodiment, connecting the cut/fill signal to a servo-actuated model grader blade on an RC vehicle replicates the electrohydraulic control claim for approximately $30 in additional servo hardware.

---

## 10. Script Hooks
*Three facts from this research that would stop a viewer cold.*

1. When Caterpillar filed this patent in December 1993, the GPS constellation had achieved Initial Operational Capability that same month — the system designed to replace surveying stakes with satellite signals was invented while the satellite network it depended on was not yet certified as operational.

2. Selective Availability — the U.S. military's active policy of deliberately degrading civilian GPS to 100-metre accuracy — was in full force on the day this patent was filed, so the inventors built a local radio correction link into the core architecture specifically to defeat their own government's intentional sabotage of civilian navigation.

3. Caterpillar filed this patent bracketed by a five-month UAW strike that had just ended and a seventeen-month UAW strike about to begin — the technology that ultimately reduced on-site construction labour was engineered in the single brief window of labour peace between two of the most significant strikes in the company's history.

---

## Sources
- https://patents.google.com/patent/EP0682786
- https://en.wikipedia.org/wiki/Global_Positioning_System
- https://en.wikipedia.org/wiki/Differential_GPS
- https://en.wikipedia.org/wiki/Caterpillar_Inc.
- https://en.wikipedia.org/wiki/Trimble_Inc.
