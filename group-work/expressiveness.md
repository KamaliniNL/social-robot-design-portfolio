# Expressiveness – TouchDesigner Puppeteering Workshop

*Group work – Session 3*
*Collaborators: Anna Hornman, Flim de Jong, Liz van Ginderen, Oyindrila Sen Gupta, Sarah Mans, Nelaturi Kamalini Saugandhika*

---

## Context

This session introduced TouchDesigner as a tool for puppeteering a physical robot arm (SO-101) via a MIDI controller. The core question was: how do you make a robot feel expressive rather than just mechanically correct?

For our case( a MiRo-E robot with young adults and/or students) expressiveness is not an addition. The robot needs to communicate mood and intent through motion. A hesitant nudge to take a break reads very differently from an abrupt interruption. This session gave us hands-on vocabulary for that design space.

---

## Assignment 1 : Setup & Familiarisation

**What we did:** Connected the SO-101 robot arm to TouchDesigner via USB, loaded the workshop patch, and verified the MIDI controller was correctly mapped. The first 6 sliders on the controls board directly drive the 6 joints of the robot arm through a `fan_robot_angles → robot` operator chain.

**Setup photo:**

![Workshop setup: SO-101 robot arm, HP laptop running TouchDesigner, Korg nanoKONTROL2 MIDI controller](../assets/setup.jpeg)

**Observation:** Direct joint control feels very raw that is, every slider movement translates immediately and literally into a joint angle. There is no smoothing, no personality, no sense of intention. Moving one slider at a time produces stiff, robotic motion that feels nothing like a natural gesture. This is a useful baseline as it makes clear just how much processing is needed before a motion can read as expressive or even comfortable to watch.

---

## Assignment 2b : Trigger Play Animation

**What we did:** Loaded a pre-recorded animation (`backaway_degrees`) and triggered playback using the MIDI play button. The `trigger_play` operator takes a recording and plays it sequentially whenever triggered.

[![Video 1 – Trigger play animation](https://img.youtube.com/vi/-jLR6cxwmew/0.jpg)](https://youtu.be/-jLR6cxwmew)

**Observation:** Having a pre-recorded motion that can be triggered on demand immediately changes the feel. The robot moves with a coherent arc rather than a series of disconnected joint jerks. However, playback is always identical - the same pose, the same timing, the same endpoint. This rigidity became obvious quickly. If the robot arm starts from a different resting position, the animation still plays relative to the recorded start, which can look clashing in terms of joint speed. Pre-recorded animation alone is not enough for a robot that needs to respond naturally to a student's context.

---

## Assignment 2c : Expressive Overlay (H / M / L modes)

**What we did:** Inserted the `expressive_overlay` operator between `trigger_play` and `robot`. This operator adds dynamic characteristics (damping and natural frequency) to the motion. The MIDI board's H, M, L buttons switch between three presets - Happy (larger overshoots, bouncy), Sad (slow, heavily damped), and Default (clean motion tracking).

[![Video 2 – Expressive overlay H/M/L](https://img.youtube.com/vi/g_BfVAyUK1U/0.jpg)](https://youtu.be/g_BfVAyUK1U)

**Observation:** This was the most immediately striking exercise of the session. The same recorded motion felt completely different across modes like the H-mode had an energetic overshoot that read as excitement or eagerness, M-mode felt defeated, L-mode was neutral and precise. What struck us was that the *content* of the motion did not change at all; only its physical character did. This maps directly to our MiRo-E case: the robot checking in on a stressed student should probably not bounce eagerly into their space (H-mode energy), but a very damped, slow approach (M-mode) could read as hesitant and supportive. The operator essentially gives you an emotional filter you can apply on top of any movement.

---

## Assignment 2d : Head Tilt & Manual Override During Animation

**What we did:** Added a `control head tilt` block using `add_overlapping`, which mixes slider-driven manual control of the last three joints with the ongoing animation output. This allows real-time modulation of the robot's "head" posture while an animation plays.

[![Video 3 – Head tilt control](https://img.youtube.com/vi/HVNMVI_-8Ak/0.jpg)](https://youtu.be/HVNMVI_-8Ak)

[![Video 4 – Head tilt second take](https://img.youtube.com/vi/_m-Cnw9jexA/0.jpg)](https://youtu.be/_m-Cnw9jexA)

[![Video 5 – Longer version](https://img.youtube.com/vi/lwThhDVTHaE/0.jpg)](https://youtu.be/lwThhDVTHaE)

**Observation:** Mixing autonomous animation with live manual control opened up a qualitatively different mode of interaction. The robot could be "running" a sad animation while the operator tilted its head toward a specific point, making the motion feel directed and socially aware rather than just executing a loop. This hybrid - partly scripted, partly responsive, resonates strongly with our Wizard of Oz approach where a human puppeteer can steer the emotional quality of an ongoing motion in real time, without having to pre-program every nuance. For the MiRo-E wellbeing scenario, this suggests a puppeteering model where a researcher controls subtle orientation while pre-recorded behaviours handle the broader gesture.

---

## Assignment 3 : Physical Puppeteering, Recording & Anticipation

**What we did:** Disabled torques on the robot, physically moved the arm by hand to record a custom motion, then re-enabled torques and played it back. The `expressive_overlay` anticipation channel was then used: holding the MIDI square button while the animation plays causes the robot to pull back in the opposite direction before snapping to its target when released.

[![Video 6 – Recording & anticipation](https://img.youtube.com/vi/uqIwU4DsL0Y/0.jpg)](https://youtu.be/uqIwU4DsL0Y)

[![Video 7 – Recording take 2](https://img.youtube.com/vi/pHH-Jwtw3Ws/0.jpg)](https://youtu.be/pHH-Jwtw3Ws)

[![Video 8 – Recording take 3](https://img.youtube.com/vi/xPzdTOfE4nM/0.jpg)](https://youtu.be/xPzdTOfE4nM)

**Observation:** Physical puppeteering felt the most natural way to generate motion as it bypasses the abstraction of sliders entirely and produces motion that carries the puppeteer's own physical intuition. The anticipation effect was unexpectedly powerful because the pull-back before snapping to target gave the motion a sense of build-up and intention. A robot that "winds up" before doing something feels alive in a way that a robot that simply executes a command does not. For a social robot, this could be valuable like a subtle anticipatory lean before asking a question signals that something is about to happen, giving the user a moment to notice and prepare.

---

## Assignment 4 : Retargeting

**What we did:** Loaded `backaway_degrees.bclip` and used the `retarget_movement` operator to replay the animation adapted to whatever the robot's current joint configuration is at the moment of triggering, rather than replaying from the original recorded start pose.

[![Video 9 – Retargeting](https://img.youtube.com/vi/AUUrbKtXzrI/0.jpg)](https://youtu.be/AUUrbKtXzrI)

**Observation:** Retargeting solved one of the key practical problems with pre-recorded animation, the mismatch between the recorded start pose and the actual current pose. With retargeting, the robot could be in any configuration when triggered, and the dynamic character of the animation (its rhythm, the relative joint changes) would still come through cleanly. This is directly relevant for a deployment scenario where a MiRo-E robot in a real study room will not always be in the same pose when it decides to approach a student. Retargeting means the robot's expressive gestures remain consistent regardless of what it was doing before, which is essential for a believable interaction.

---

## Reflections

Across all four assignments, the clearest takeaway was that **expressiveness is not a property of a single operator, it emerges from the combination of motion content, physical character, timing, and live modulation**. The TouchDesigner node graph made this explicit: you could trace exactly which layer was contributing what, and swap them out. For our MiRo-E design, this suggests we should think in layers too - what is the base gesture, what emotional filter does it pass through, and what live adjustments does the puppeteer make in response to the student?

The anticipation effect and the H/M/L mode switching were the two features most likely to inform our experimental approach; both give us a direct lever for testing how motion character affects student perception of the robot's intent.

---

*All videos recorded during the Social Robot Design workshop, University of Twente, May 2026.*
