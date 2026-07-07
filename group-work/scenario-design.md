# Scenario Design Tool - CardsAgainstRobots

---

## Overview

This chapter documents the design and application of *CardsAgainstRobots*, a card-based improvisation toolkit. It is developed to explore and evaluate appropriate MiRo-E robot behaviours for promoting student wellbeing in university study environments. The tool was the group's primary design contribution and is directly connected to the [case description](case-description.md).

---

## Tool Structure and Conceptualisation

The central design problem, as established in the case description, was that no single interaction model could account for the range of student states and contexts that DonE might encounter. Rather than resolving this early through assumption, the group chose to make the space of possibilities explorable — using an improvisation-based approach to surface what appropriate behaviour might look like before committing to a design direction.

The resulting toolkit consists of three card types:

- **Human Action cards** (blue) : student emotional and behavioural states, including daydreaming, determined but stuck, frustrated and stuck, distracted by phone, listening to loud music, and productive but off-task.
- **Robot Action cards** (pink) : discrete MiRo-E behaviours or verbal prompts, such as "Do you need a small break?", "What are you up to?", "Done with homework?", and "Looking curious."
- **Wildcard cards** (yellow) : contextual modifiers that shift the scenario, such as "Human doesn't like the robot" or "Quick blinking."

The toolkit also includes a printed instruction manual, a structured evaluation form, and a QR code linking to a printable PDF of additional evaluation forms so as to ensure the tool can be used repeatedly without physical constraint.

![The CardsAgainstRobots toolkit: three card piles (human action, robot action, wildcard), instruction manual, and evaluation forms laid out on a table](../assets/srd_cards.jpeg)
*Figure 1: The full CardsAgainstRobots toolkit - card piles, instruction manual, and evaluation forms. The three card types are colour-coded to distinguish student states, robot actions, and wildcards.*

---

## HRI Knowledge Embedded in the Tool

The toolkit operationalises two key methodological frameworks from HRI research.

The first is **LEADOR** (Winkle et al., 2021), a participatory design methodology for end-to-end co-design of autonomous social robot behaviour. LEADOR advocates for an in-situ teaching phase where domain experts live-programme or enact robot behaviour while embedded in the actual interaction context. CardsAgainstRobots draws directly on this principle so rather than designing behaviour at a desk, the tool places participants in an improvised enactment of the scenario with the actual MiRo-E robot present and puppeteered in real time.

The second is **HRI CUES** (Cuadra et al., 2024), an observer-perspective interaction rating scale designed for conversational HRI. The evaluation form embedded in the toolkit adopts HRI CUES's external observer approach, rating each enacted scenario across eight criteria: effective, motivational, clear, kind, natural, empathic, predictable, and trustworthy - each scored on a 1-5 scale. Crucially, observers are instructed to rate what they *saw*, not what they imagined could have happened, and to wait until after the scenario ends before rating. This mirrors the behavioural observation logic in HRI CUES.

The tool embeds the assumption that appropriate robot behaviour in a wellbeing context is not only a design question but a perceptual and social one. And that it therefore requires an observer's judgement, not just a designer's intention.

---

## Two Game Modes

The toolkit supports two distinct game modes, each addressing a different design question.

**Game 1: Random Scenario Card Improvisation** uses blind card draws to generate unexpected scenario combinations. One participant leaves the room, a robot action card is drawn and enacted with MiRo-E using the controller, then a human action card is drawn and the absent participant returns to enact the student role. The group improvises from this starting point until the scenario reaches a natural end. Wildcards can be introduced at any stage to shift the context. This mode foregrounds exploration as it is not about finding the right answer but about encountering situations the design team had not anticipated.

**Game 2: Mix and Match** is more deliberative. One human action card is drawn and five robot action cards are laid open. Participants discuss how the student would react to each robot action, rank the five cards from best to worst fit, and then work backwards to find the minimum combination of cards that produces the best outcome. A wildcard can then be introduced to test whether the ranking holds. This mode foregrounds evaluation as it makes the reasoning behind design choices explicit and discussable.

Both modes share the same evaluation form, allowing observations across games to be compared.

---

## Tool in Action

The session was conducted with six participants using the actual MiRo-E robot, puppeteered via a game controller. The robot was connected to a laptop by cable, which limited its range of movement - a constraint that became relevant during evaluation.

![Game 1 in progress: a participant enacts the student role while another controls MiRo-E with the game controller; observers hold evaluation forms](../assets/srd_game_1_(1).jpeg)
*Figure 2: Game 1 - Random Scenario Card Improvisation in progress. One participant puppeteers MiRo-E while another enacts the student state drawn from the human action pile. Observers rate the interaction using the evaluation form.*

![Game 2 in progress: participants discuss and rank five robot action cards laid out on the table alongside the human action card](../assets/srd_game_2_(1).jpeg)
*Figure 3: Game 2 - Mix and Match. Participants rank five robot action cards against a single human action card, discussing the reasoning behind each ranking before agreeing on the best outcome.*

![A participant puppeteering the robot actions, with MiRo-E](../assets/srd_puppeteering.jpeg)
*Figure 4: The puppeteering setup - MiRo-E is controlled via a game controller, with the laptop connection visible. The cable constraint meant the robot's movement range was limited to the immediate area around the table.*

### Game 1 : Observed Scenario

Cards drawn: Human Action - *"Overwhelmed by work"*; Robot Action - *"Do you need a small break?"*

The participant enacting the student role put their head in their hands and appeared stressed. MiRo-E was slowly driven toward the student, the head raised and turned, and the ears adjusted. The student initially watched with apparent curiosity and eventually reached out to pet the robot. Observers noted the interaction felt considerate but that the ending was abrupt as MiRo-E moved away before any clear positive thoughts were established. Ratings on the *effective* and *empathic* criteria were moderate; *natural* received lower scores.

The observation that mattered most here was not which card pairing worked best, but what it revealed about the robot; when MiRo-E retreats without a clear closing gesture, the student is left uncertain. This is a design insight that would not have been reachable through desk-based scenario planning alone.

### Game 2 : Observed Scenario

Cards drawn: Human Action - *"Switching tasks often"*; Robot Action cards - *"Put the phone down"*, *"What are you up to?"*, *"Done with homework?"*, *"Looking curious"*, and *"2 min Breathing exercises guide"*.

After discussion, participants ranked *"Done with homework?"* as the best fit as it felt least intrusive and most conversational. Especially for a student who was already moving between tasks. The wildcard introduced was *"Human doesn't like the robot"*, which shifted the ranking. The discussion itself, not just the outcome, was where the design value emerged as participants made criteria for appropriate robot behaviour that they had not stated before drawing the cards.

---
![A participant completing the evaluation form after an enacted scenario](../assets/srd_poster_eval_(1).jpeg)
*Figure 5: The evaluation form being filled.*
## Evaluation and Reflection

**Design outcome quality:** The tool produced design insights that the group could not have reached through assumption alone. The Game 1 scenario revealed a gap in MiRo-E's closing behaviour; Game 2 surfaced the tension between warmth and directness depending on a student's prior opinions toward the robot. Both are actionable observations that inform the behaviour design direction documented in the [behaviour section](behaviour.md).

**Tool quality:** The two-mode structure is well-suited to different phases of design. Game 1 for early exploration, Game 2 for comparative evaluation. The evaluation form, grounded in HRI CUES, gave observers a shared vocabulary for what they were judging, which reduced the risk of purely subjective responses.

There are, however, genuine limitations. The cable-tethered MiRo-E constrained the spatial dynamics of the enactment - approach distance, which is central to the wellbeing use case, could not be explored fully. Additionally, some wildcard combinations produced no meaningful shift in the scenario, requiring a redraw; this suggests the wildcard set needs pruning or better contextual framing. Finally, the tool is better suited to exploration than to final validation - the Wizard of Oz puppeteering means that what is being evaluated is partly a function of how skilled the puppeteer is. not only of what the robot's behaviour design specifies.

The card structure and evaluation protocol are adaptable to other robot platforms and deployment contexts. A team designing a robot for a different public space could rebuild the card set for their own student states and robot actions without changing the underlying methodology.

**References:**
- Winkle, K., et al. (2021). LEADOR: A Method for End-to-End Participatory Design of Autonomous Social Robots. *arXiv:2105.01910.*
- Cuadra, A., et al. (2024). HRI CUES: Human-Robot Interaction Conversational User Enjoyment Scale. *arXiv:2405.01354.*
