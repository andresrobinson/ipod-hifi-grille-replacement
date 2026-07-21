# Development Log

This file documents the design process for the iPod Hi-Fi grille replacement.

The main [`README.md`](README.md) is kept focused on printing and assembly. This file is for the measurement process, prototypes, design reasoning, and lessons learned.

---

## Starting Point

The project started with two Apple iPod Hi-Fi units.

Both were missing the original front grille. One unit also had a faulty 30-pin dock connector, which was later replaced using the dock assembly from the second unit. After the dock swap, the repaired unit worked properly and could be used as the main reference unit for the grille replacement.

The goal was to recreate the missing grille as a practical repair part using 3D printing and fabric.

The design target was not a printed visible mesh. The intended replacement is a hidden support frame covered with fabric, similar in appearance to the original fabric front panel.

---

## Design Constraints

The replacement needed to:

- fit the original front grille opening;
- use the original mounting-hole locations;
- avoid blocking the speaker drivers;
- fit on a small printer, specifically a Bambu Lab A1 Mini;
- be split into multiple printable pieces;
- support fabric installation cleanly;
- allow the mounting pegs to be changed if needed.

---

## Corner Radius

The first challenge was the corner radius.

The overall grille shape looks simple, but the corners are important. If the radius is wrong, the part will immediately look and fit wrong.

Because the iPod Hi-Fi was designed in the United States, the initial assumption was that some dimensions might be based on imperial measurements. A rough measurement suggested that the corner radius was close to 1 inch.

A radius gauge was printed and test-fitted against the speaker opening. This confirmed the corner radius as:

```text
Corner radius: 25.4 mm / 1 inch
```

This became the first fixed reference for the CAD model.

---

## Mounting Peg Offset

After the corner radius was confirmed, the next problem was locating the original mounting holes.

The holes are not located at the center of the corner radius. Because of that, a simple rounded rectangle was not enough. The design had to match the corner curve and the peg location independently.

The mounting hole offsets were measured from each side edge of the grille opening.

Several small corner test pieces were printed to test the relationship between:

- the 25.4 mm corner radius;
- the side edges;
- the original mounting holes;
- the peg position relative to the corner.

These early test pieces were only used during development and are not included in the repository.

---

## Side Assembly Prototype

Once the corner radius and local peg offsets were good, the next step was finding the distance between the mounting pegs along one side.

A side assembly prototype was designed. This part combined two side corners into one printed piece, so both corner peg positions could be tested at the same time.

This verified:

- the distance between the upper and lower side pegs;
- the alignment of both corners with the fascia;
- whether the 25.4 mm radius still fit correctly as part of a longer piece;
- whether the peg locations matched the original holes without forcing the print.

After that side assembly fit correctly, a second copy was printed.

With two side assemblies available, the horizontal distance between the left and right mounting peg locations could be measured and confirmed.

This staged process built the design from known-good references:

1. corner radius;
2. corner-to-peg offset;
3. vertical peg spacing;
4. horizontal peg spacing;
5. full grille frame layout.

---

## Internal Reinforcements

After the outer geometry and mounting peg positions were established, the internal reinforcement layout was sketched by hand.

The goal was to keep the frame flat and stable while avoiding unnecessary obstruction in front of the speakers.

The internal reinforcement layout was drawn around the speaker areas using a pencil, then translated into Fusion 360 for the first full CAD draft.

---

## First Full CAD Draft

The first full design was created in Fusion 360.

The design was split into three main frame parts so it could fit on a small printer such as the Bambu Lab A1 Mini.

The first full concept included:

- three main frame sections;
- screw-in replaceable pegs;
- a fabric retention channel;
- separate retaining strips for the fabric;
- an optional assembly support to help align the frame during gluing.

---

## Fabric Retention

The fabric mounting system was inspired by the documented speaker mesh frame construction in the [`jake-b/iPod-HiFi-Tweeters`](https://github.com/jake-b/iPod-HiFi-Tweeters) project.

The replacement grille uses a fabric retention channel and separate retaining strips.

The idea is:

1. stretch fabric over the printed frame;
2. press the fabric into the channel;
3. glue retaining strips over the fabric;
4. trim the excess fabric after the glue cures.

The retaining strips are glued in place, similar in spirit to the original bonded construction.

---

## Mounting Hole Variation

During testing, a variation was found between two iPod Hi-Fi units.

A 5 mm peg fit well in one unit, but would not fit correctly in the other. On closer inspection, the fascia appears to include a small plastic opening or retaining feature inside the mounting hole.

This feature was probably intended to hold the original grille pegs in place. It may have originally used a rounded or deformable shape.

Because of this, the mounting pegs were changed from fixed printed features to replaceable screw-in parts.

This makes it possible to improve or change the peg design later without reprinting the full grille frame.

---

## Replaceable Peg Threads

The peg system uses printed threads.

Standard Fusion 360 thread profiles are not always ideal for 3D printing, so the project used the [`BalzGuenat/CustomThreads`](https://github.com/BalzGuenat/CustomThreads) Fusion 360 thread profiles.

The selected thread specification is:

```text
Thread diameter: 14 mm
Pitch: 3.5 mm
Profile: 60° trapezoidal
Tolerance class: 0.8 mm
```

The tolerance was selected through test prints. The goal was to find a thread that could be screwed together securely without being too tight.

The pegs screw in from the back of the frame. They can be installed before or after fabric installation because they do not interfere with the fabric or retaining strips.

If the pegs do not need to remain removable, they can be glued in place after final test fitting.

The rounded-peg possibility was also pointed out by Reddit user `u/sparkyblaster` in the Day 2 Reddit thread, and credit is due for that observation.

---

## Assembly Support

An optional assembly support was added to help align the three main frame sections during gluing.

This support is not part of the final visible grille. It is a temporary aid to keep the frame sections positioned correctly while the adhesive cures.

It is optional, but recommended.

---

## Prototype Fabric

For the first successful assembly, very thin neoprene was used.

The neoprene was less than approximately 1 mm thick and gave good visual coverage. It was useful for validating:

- fabric handling;
- the retention channel;
- the glued retaining strips;
- the overall assembled appearance.

However, neoprene should be treated as a prototype fabric. Even when thin, it may not be as acoustically transparent as real speaker grille cloth.

For a final audio-focused version, proper acoustically transparent speaker cloth is still recommended.

---

## Current Result

The assembled prototype fit well and produced a result good enough to publish.

The current public release is intended as a practical first version. Future improvements may include:

- alternate peg designs;
- more fabric testing;
- refinements to the retention strips;
- small fit improvements based on other iPod Hi-Fi units.

---

## Notes for Future Work

Possible future improvements:

- Add more peg variants for units with different mounting-hole behavior.
- Test real speaker grille cloth against the neoprene prototype.
- Add photos of each OBJ part separately.
- Add print orientation screenshots.
- Add a simplified assembly diagram.
- Add measured dimensions if useful for contributors.

---

## References

- [`jake-b/iPod-HiFi-Tweeters`](https://github.com/jake-b/iPod-HiFi-Tweeters)
- [`BalzGuenat/CustomThreads`](https://github.com/BalzGuenat/CustomThreads)
