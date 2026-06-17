---
summary: 'Guide to reading and interpreting turbocharger compressor maps for matching turbochargers to Honda engine performance goals.'
tags: [tuning, rom, sensors, reference]
applies_to:
  obd: [0, 1, 2]
  models: [accord, civic, crx, del-sol, integra, nsx, prelude, rsx, s2000]
  chassis: [ap1, ap2, bb, cb-cd, da, dc2, dc5, ef, eg, eg-eh, ek, em-ep, na1-na2]
complexity: intermediate
sources:
  - name: 'pgmfi.org wiki'
    title: 'Turbo Compressor Map'
    url: /pgmfi/wiki/library/turbo-compressor-map
    license: 'CC BY-NC-SA 1.0'
    license_url: 'https://creativecommons.org/licenses/by-nc-sa/1.0/'
    adapted: true
---

# Turbo Compressor Map

Some common turbo compressor maps are here: [https://www.borgwarner.com](https://www.borgwarner.com)

---

Reading turbo compressor maps is pretty simple, and is something that anyone who is turbocharging their car should know how to read. A turbo compressor map tells you several things about a turbo's characteristics that helps you match the correct turbo to your particular engine setup. A turbo compressor map looks like this: [T-3 Super 60 ](t3-60.jpg)1) pressure ratio. This number represents the boost you intend to run, it makes up the Y axis of the graph. The numeric pressure ratio value is calculated by taking your target psi (15 psi for example) then adding 1 Atmosphere(14.7psi) and dividing the total by 1 bar(14.7 psi). The equation looks like this for our example: 15 + 14.7 = 29.7 29.7 / 14.7 = 2.02 2.02 is the refrence number that you would look at on the Y axis. __2) The X axis of the graph represents airflow in pounds per minute. As a general rule, `each` pound of air generated represents 10hp. This is flywheel hp and not wheel hp, so don't confuse the two. When looking at this be sure to account for driveline losses when you estimate your power output. HINT: use CFM X.075 to get the lb/min numbers. The graph shown is in LB/min, while other graphs are in CFM. How do you tell? CFM graphs have numbers on the x-axis that are in the hundreds (i.e., 400) as apposed to the tens (i.e., 26) like the LB/MIN graphs. 3) The third area represents the efficiency island. This is the target area you want to keep your boost at. This is where the turbo is at it's peak efficiency and thus runs the best. 4) These are the outer rings of efficicncy or wheel efficiency. As you can see from the numbers, `each` ring drops in efficiency and thus drops in power output. The percentage of efficiency lost and power loss vary from turbo to turbo, but as a rule of thumb you want to remain as close to your efficiency island(center island) as possible. 5) This dashed line is the surge limit. Any points to the left of this line indicate that the compressor wheel in quesation is too big for the expected boost and power output you are planning for. There would not be enough exhaust gas volume to spin the wheel fast enough to make useable boost. 6) This area to the right of the graph plots overspin choke. This means that the compressor wheel is too small and will have to spin too quickly to make the target boost/power. At these extreem speeds, efficiency goes out the door because the wheel chops the air so badly, this will likely cause a dramatic loss of power. 7) This is the compressor wheel speed in rpm. This measures the shaft speed of the compressor wheel. The faster it is spinning the hotter the outlet charge will be, and thus the lower your power output becomes. This is where a good intercooler comes into play.
