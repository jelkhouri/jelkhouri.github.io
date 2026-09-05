---
title: "1990 Suzuki DR250S Restoration"
date: 2026-09-04
excerpt: "Reviving an old dirtbike"
thumbnail: "/assets/images/suzuki-dr250-restoration.jpeg"
tags: [motorcycles, mechanical-repair, restoration]
---

![Suzuki DR250S](/assets/images/suzuki-dr250-restoration.jpeg)

## Introduction

I recently purchased this motorcycle, a 1990 Suzuki DR250S, as a part-time restoration project.
When I purchased it, it had been exposed to the elements for at least a year, and was not
running. This bike features a 249cc single-cylinder motor which puts out around 20 horsepower and
a six-speed transmission. It features front and rear disc brakes, a tall seat height, and
forgiving suspension, suiting it well towards offroad use. As a "dual-sport" bike, it originally
featured all the necessary street equipment for legal use, but in its current state, only has a
headlight. In Summer 2026, I gave it some much needed maintenance and began the cosmetic and
mechanical restoration process.

## Original Condition

Upon purchase, this bike was non-operational. In order to troubleshoot the issue, I adopted a
linear framework. In order for gasoline to combust in the motor and start the engine, four things
are necessary:

1. **Fuel** — verify that gasoline is actually reaching the engine so that it can combust.
2. **Air** — for any combustion to occur, there needs to be an ample amount of oxygen.
3. **Compression** — in order for combustion to move the piston and turn the output shaft, which
   powers the rear wheel, there needs to be a proper amount of compression in the cylinder to
   harness the energy of the combustion.
4. **Spark** — finally, when the prior three ingredients are combined, a spark is provided which
   ignites the gasoline fumes.

If any one of these four are absent or insufficient, a motor will not start.

## Troubleshooting

I performed simple tests to confirm the presence of air and compression. This can usually be done
in a few minutes by visually checking the air filter, and then attempting to turn the engine over.
If you feel resistance to turning over the motor, there is likely enough compression.

Next, I turned my attention to the fuel system. Older dirtbikes use vacuum carburetors, which
create a mixture of gasoline and air to be injected into the motor. Inside of the carburetor are
multiple small jets through which the mist travels. Since the bike was left for a while, remaining
fuel in the carburetor had evaporated, leaving behind residue. This clogs up the jets, and makes it
so that the engine does not get sufficient fuel.

I took the carburetor apart, replaced all the jets and gaskets, and managed to get the bike
started. The bike shifted successfully through all the gears, and started back up easily once
warmed up.

However, it is still very difficult to start cold, and takes a long time to warm up. I have put a
few thoughts on why that is the case, and my future plans to fix that, at the end of this article.

## Touch-Ups and Cosmetic Work

I think the most cathartic part of this process was the plastic restoration. This bike was
discontinued in 2005, and as such, it is hard to find replacement body panels. Mine were in pretty
rough condition, so I went about restoring them. Here is a before/after:

<div style="display:flex; gap:1em; flex-wrap:wrap;">
  <img src="/assets/images/suzuki-dr250-restoration-2.jpeg" alt="Body panel before restoration" style="width:48%; min-width:220px;">
  <img src="/assets/images/suzuki-dr250-restoration-3.png" alt="Body panel after restoration" style="width:48%; min-width:220px;">
</div>

As you can see, the surface had yellowed and had a good number of stains and scratches. To remove
the impurities, I went over each panel with a razor blade, which allowed me to scrape off the layer
of plastic on the surface that was unsightly. Then, I used a fine grit sandpaper with water to
remove all lighter scratches, and to make the surface a bit porous. Finally, I went over it with
white plastic polish.

I thought changing the tire would be easy. It was not easy at all, but after I learned the proper
technique for prying at the rubber, it was more manageable.

When I attempted to put the wheel hub back into its place, I found that it no longer fit. Here, I
learned about an interesting mechanism called a cush drive.

![Cush drive schematic](/assets/images/suzuki-dr250-restoration-4.jpeg)

Part 17 in the schematic is fitted with a circular array of rubber pieces (18) which mesh the rear
sprocket to the wheel hub, as seen in the next picture. They are designed with a very loose
tolerance, and absorb any rapid accelerations between the sprocket and the wheel. This absorbs
shock and protects both mechanisms.

When assembled, these are slightly compressed, and they gave me immense trouble when I was trying
to reassemble the rear wheel. To re-compress them slightly, I used some zip ties, which gave me
just enough clearance.

![Rear wheel hub and cush drive](/assets/images/suzuki-dr250-restoration-5.png)

I also fitted it with a new chain and handgrips.

![New chain](/assets/images/suzuki-dr250-restoration-6.jpeg)

## Future Work

I am pretty happy with how this went, but still need to discover why it is difficult to start. The
bike can only cold-start effectively when the engine gets spinning fast.

![Stator and flywheel schematic](/assets/images/suzuki-dr250-restoration-7.png)

Single-cylinder bikes like this use something called a stator in order to generate power. The
flywheel (3) in the diagram is connected to the engine's crank, and spins with the motor. As the
engine turns, the flywheel interacts with the magnetic field created by magnets on the stator (1).
This creates a potential in copper wires around the magnets and provides power to the CDI. As the
flywheel turns faster, it interacts with the magnetic field at a faster rate — by Faraday's law,
the faster the wheel spins, the higher the induced voltage.

It is possible that, on a ~40-year-old bike, the wiring or magnets have been damaged or
deteriorated. This could lessen the voltage, or it could be making spark in a deceiving zone, where
the spark is bright enough to observe, but not strong enough to easily cold start the bike. More to
come!
