---
name: simple-software
description: Design or simplify software around the concepts a user must hold in their head. Delete concepts before restructuring flows, restructure flows before polishing screens, and account for where removed complexity goes. Use when deciding what features, settings, or form fields to cut, reviewing an app or flow for complexity, weighing walk-up versus expert-user needs, or when the user asks to simplify software.
---

# Simple Software

Simplicity in software is not a property of screens. It is a property of what the user has to hold in their head — and most of it is decided before anyone draws a pixel.

The evidence for this is unusually clean, because governments publish their redesigns. In 2013, the UK's Carer's Allowance claim ran to nearly 350 questions, and 61% of the people who started it finished. The team that fixed it did not redesign the form. They challenged the way policy had been interpreted and deleted 170 of the questions — 49% of the total. Completion rose to 83%, time-to-complete fell by a third, and ineligible claims dropped 41%. On another service, Register to Vote, the team went further: they got the law changed to remove a requirement, because including it would have forced every mainstream user to wade past a concept that applied to almost no one.

Meanwhile, the same team's guidance for screen-level polish — label alignment, error styling — improves things by percentage points, not tens of points. The leverage hierarchy is consistent everywhere the numbers are published: **delete the concept, then restructure the flow, then fix the screen, then polish the widget.** Each level down, the payoff shrinks by an order of magnitude.

## **The concept inventory**

So the first tool is not a wireframe. It is a list. Jeff Johnson and Austin Henderson, who spent careers on this, prescribe writing down the conceptual model before any UI sketching: the objects the user will believe exist, the operations they can perform, the relationships between them. Then one rule: **if it isn't in the conceptual model, the application should not expose it.**

You can watch this rule win markets. In 2008, SugarSync was the best file-syncing product money could buy — Walt Mossberg called it "by far the best solution I have tested." Its model had six or seven concepts: sync-folder selection per machine, full-replication versus online-only choices, a Magic Briefcase that was always replicated, a separate Web Archive that never updated, a manager application to tend it all. Dropbox shipped with three: a folder, it syncs itself, there's a website. In a 2011 head-to-head review, SugarSync won five of eight feature categories — and the reviewer concluded that non-technical users "would be leery of picking up SugarSync" anyway. Feature count lost to concept count. It usually does.

Every input, setting, and option deserves the same interrogation. Caroline Jarrett's question protocol, the tool behind the Carer's Allowance cut, demands that each form field name the person inside the organization who uses the answer, and for what. "Might be useful" fails. So does the most seductive escape hatch in product development — "we can make it optional" — because an option is not a smaller commitment. An option is one more concept, permanently.

## **Where the complexity goes**

Complexity, as Larry Tesler observed, is conserved. You cannot delete it; you can only move it. The craft is in the accounting — every removal should name who pays.

The original iPhone keyboard is the canonical entry in the ledger. The design team's prototypes were full of user-facing cleverness: multi-letter keys, gesture vocabularies, chorded layouts. What shipped was the most boring possible surface — a plain QWERTY keyboard — backed by invisible machinery: an autocorrect dictionary and touch targets that silently resized themselves based on what you were likely to type next. One new invisible concept absorbed a zoo of visible ones. Even the suggestion bar was cut when watching people type revealed that mid-word suggestions were themselves a concept users had to track.

That is the pattern's noble form: complexity absorbed by software. There are others. Dropbox absorbed sync-direction semantics by constraint (one folder, always bidirectional) and replaced SyncToy's preview-before-sync with version history — recovery instead of prevention, a safety net instead of a decision. The iPod absorbed "transfer" into FireWire and auto-sync; hardware speed is what made syncing *everything* a sane default. And there is a counterfeit form: box.net "simplified" sync by simply not doing it, then spent years rebuilding it as a paid feature. Complexity deferred is not complexity absorbed. The ledger always balances; the only question is whether you balanced it on purpose.

## **Two kinds of simple**

Everything above serves a definition, and the definition forks. Simple for whom, at what frequency?

For the walk-up user — the person renewing a license once, on their phone, mid-crisis — simple means *minimal concepts required right now*. One question per page. One primary button. Answers, not information: when Canada rebuilt its weather pages around the questions people actually had ("will it rain?", "is that storm warning for me?"), task success went from 33% to 72%, and success on the worst task — acting on a thunderstorm alert — went from 6% to 63%. Part of that fix was pure concreteness: alerts had been rendered as plain text, and things you can click must look like things you can click. Eyetracking studies of flat design put a number on ignoring this: weak signifiers cost 22% more looking time for the same tasks. The "cleaner" interface was slower.

For the trained daily user, simple means something nearly opposite: *minimal cost per action at full fluency*. Density is not clutter — the honest measure is value divided by the time and space the interface occupies, and by that measure a packed Bloomberg screen can be simpler than a serene dashboard that makes you click four times. For these users, stable layout is a contract; Bloomberg's own designers note that "even something as simple as a font change or the relocation of a button can be disruptive" to someone whose hands know where everything is. Hiding is a per-use tax. The command palette is this regime's unifying abstraction — one keyboard-summoned surface that absorbs scattered menus, searches, and shortcut lists.

Confuse the regimes and users will tell you, loudly and in workflow terms. Snapchat's 2018 "simpler" redesign broke the chronological structure fluent users navigated by habit: a 1.2-million-signature petition, the first daily-active-user decline in the company's history, a rollback. Windows 8 removed the Start menu; an entire third-party industry sprang up to restore it, and then Microsoft did too. Final Cut Pro X deleted the concepts professional editing pipelines ran on; Apple issued refunds and spent two years restoring them. The backlash pattern is the diagnostic: when trained users articulate a loss in terms of *tasks they can no longer do quickly*, what shipped wasn't simplification. It was removal wearing simplicity's clothes.

## **The discipline**

The uncomfortable finding, testing this craft against documented redesigns, is that the instinct to *help* is the main enemy. The structure you add in good faith — the filter, the confirmation dialog, the "I'm not sure" option — is disproportionately what user testing later removes. The UK teams whose redesigns I studied deleted an escape-hatch option and made the criteria explicit; removed confirmation questions because they disrupted the workflow; removed filters because they confused the people they were meant to help. In each case the fix for a confusing path was not another aid alongside it, but a primary path that needed no aid.

Which yields the working discipline, and it is the same one writing teaches. Ask what the user is here to do, and at what frequency. Inventory the concepts and make each one earn its place. Look for the one concept that deletes several. Name who pays for every removal. Then ship less than feels safe, watch real people, and restore only what actually broke.

Dieter Rams compressed all of it decades ago: less, but better — *because it concentrates on the essential aspects, and the products are not burdened with non-essentials.* The "because" is the craft. Less is not the goal. Less is what's left when everything remaining is load-bearing.

