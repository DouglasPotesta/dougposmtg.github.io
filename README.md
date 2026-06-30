# Breaking Mutliplayer Block Restrictions with False Orders

False Orders is not a good card. It’s a one-mana instant from alpha that removes a creature from combat and maybe redirects it to block something else. Nobody’s winning tournaments with it. Nobody’s building around it.

What it is, is old enough to predate a lot of the infrastructure the rules have built up around multiplayer combat. Strangely the original text of the card is less confusing, than it's oracle text which has one line of text that creates a genuinely weird question in Commander:

*“You may have it block an attacking creature of your choice.”*

Say Alice is attacking Bob with a 5/5 and attacking Carol with a 3/3. Bob blocks the 5/5 with a 1/1. You cast False Orders targeting Bob’s 1/1. When the spell resolves, can you have that 1/1 block the 3/3 aimed at Carol instead of getting it out of the way of the 5/5?

The answer feels like it has to be no. Bob’s creatures block for Bob. That’s the whole premise of multiplayer combat. But when you actually go looking for the rule that says so in this specific situation, things get complicated.

TLDR; Blocking restrictions are only for declaring blocks, which includes the checks for which defending player's creatures are allowed to block which attacking creatures. "May have it block" is understood to get around blocking restrictions such as "can't be blocked." Since multiplayer block restrictions are similarly only checked when declaring blocks, it means that this effect also circumvents that specific restriction. This is what allows "False Orders" to target one defending player's creature to block a creature attacking a different defending player.

-----

The multiplayer blocking rules are pretty clear on the baseline. Rule 802.4a: a defending player can block only with creatures they control, and those creatures can only block creatures attacking that player, a planeswalker they control, or a battle they protect. Rule 802.2a pins down that “a defending player” means one specific player, not the whole table. When a spell or ability references both an attacking creature and a defending player, the defending player is whoever that attacking creature is aimed at.

So the 3/3 is attacking Carol. Carol is the defending player for that creature. Bob’s 1/1 can’t be declared as a blocker for it. Seems settled.

The wrinkle is that False Orders isn’t declaring a blocker.

Declaring blockers is a specific turn-based action under rule 509.1. The defending player picks their untapped creatures, assigns each one to an attacking creature aimed at them, and the game checks everything for legality. That whole process happens at the beginning of the declare blockers step, and it’s already over by the time anyone can cast False Orders.

What False Orders does is remove a creature from combat (see rule 506.4) and then the spell may cause that creature to block an attacking creature. That’s not the same mechanical event as declaring a blocker, and the rules actually acknowledge this distinction exists. Rule 509.3a says “whenever [a creature] blocks” triggers can fire when a creature becomes a blocker through an effect, not just when it’s declared. Rule 509.3f refers to “the point an effect causes it to block” as its own distinct moment. The rules know there’s a category of “effect causes a creature to block” that’s separate from the declaration process.

-----

## The targeting split

There’s another piece to this: False Orders only targets one thing. “Target creature defending player controls” is the target chosen when you cast the spell per rules 115.1a and 601.2c. The attacking creature isn’t a target. The card says “an attacking creature of your choice,” with no use of the word “target.” Rule 115.10a is pretty direct about this: unless the text uses the word “target,” the thing being affected isn’t a target.

What that means practically is that the attacking creature gets chosen on resolution, not on cast. Rule 608.2d covers this; choices that weren’t made while casting get made when the effect resolves, and they just have to be legal in that moment. All rules that restrict how a creature blocks and is allowed to be blocked are only with respect to declaring a blocker, which is distinct from an effect that directly has it block.

So at cast time, you lock in Bob’s creature. At resolution, you pick an attacking creature. The question of whether those two choices can come from different combat lanes is exactly what the rest of this argument is about.

-----

The strongest case against using False Orders cross-lane comes from how the rules define “defending player.” Rule 508.5 says that when a spell or ability references both an attacking creature and a defending player, the defending player is whoever that attacking creature is attacking. Rules 508.5a and 802.2a reinforce this in the multiplayer context.

The argument goes: if you pick the 3/3 as your attacking creature on resolution, Carol is the relevant defending player for that creature. False Orders targets “a creature defending player controls.” But the creature you targeted is Bob’s — and Bob isn’t Carol. The phrase “defending player” in False Orders and the attacking creature you chose are pointing at different players, so the choice would be illegal.

The problem with it is that 508.5, 508.5a, and 802.2a are definitional rules that tell you how to identify “the defending player” in a given context. The context of an attacking creature is only used to help informs the definition of "the defending player." Since the defending player is already defined, there is nothing restricting which attacking creatures are valid choices. Take for example a spell that says "Each defending player chooses an attacking creature. Destroy all creatures not chosen this way." The players would be able to choose creatures not attacking them. 

-----

## Camouflage

It helps to look at Camouflage, the other ancient blocking manipulation card that creates chaos in multiplayer.

Its Oracle text tells each defending player to divide their creatures into piles based on attacking creatures “for whom that player is the defending player.” That specific phrase, “for whom that player is the defending player,” explicitly partitions everything by combat lane. Bob’s piles are built from creatures attacking Bob. Carol’s piles are built from creatures attacking Carol.

False Orders doesn’t say anything like that. It doesn’t say “an attacking creature attacking that player” or “for whom that player is the defending player.” It just says “an attacking creature of your choice.”

Old Oracle text isn’t always a reliable guide to original intent. But if you’re looking for evidence that the rules know how to restrict a weird blocking effect to the appropriate combat lane, Camouflage shows exactly what that looks like. False Orders doesn’t have it.

-----

## The rule that almost closes it

Rule 506.3d is the closest thing to a direct answer: if an effect would put a creature onto the battlefield blocking a creature that isn’t attacking the entering creature’s controller, a planeswalker they control, or a battle they protect, the creature enters the battlefield but is never considered a blocking creature.

That rule cares about cross-lane blocking. Unfortunately, it covers creatures entering the battlefield as blockers, not creatures that are already on the battlefield being caused to block by an effect. False Orders doesn’t put anything onto the battlefield, the 1/1 is already there. It removes the creature from combat under 506.4 and then may cause it to block. The event that 506.3d governs isn’t the event False Orders creates.

So you end up with the rules having explicit cross-lane restrictions for two situations declaring blockers (509.1, 802.4a) and entering the battlefield blocking (506.3d) but nothing explicitly written for the third situation, which is an existing creature being caused to block by a resolving effect. Rules 509.3a through 509.3f acknowledge this third category exists. They just don’t say it’s subject to the same lane restrictions as the other two.

That gap is where False Orders lives.

-----

## A note on judge rulings

This interaction was checked against judges in the official askjudges chat and the Commander Staple discord. I even checked with Jess Dunks the rules architect at the time of writing this, who admits that on its face yes the loophole may be allowing this to happen. The general response was that the rules may technically allow it, but judges reserve the right to rule on RAI over RAW.  This means you could be ruled against even if the strict reading is on your side. There are also no official rulings on this interaction on the Gatherer page as of this writing, so it’s worth checking there periodically in case that changes.

-----

## At the table

At Competitive REL, call a judge.

At a Commander table, mention it before you start a game. Something like: “this card has an interaction in multiplayer where it exploits a loophole that lets a creature controlled by one defending player block an attack aimed at a different player. is that something we’re okay with?”

It’s the kind of thing that feels fake when it happens and feels like rules lawyering when you try to explain it. Walking someone through 802.4a, 509.1, 506.3d, 508.5, 509.3, 115.10, and 608.2d to justify why a one-mana Alpha instant redirected a block across the table is going to be a bad time without an explicit ruling regardless of whether you’re right.

-----

Most cards do what they say. Some cards do what they meant. A few cards do whatever the Comprehensive Rules forgot to explicitly forbid.

False Orders appears to be one of the latter.

-----

## On whether any of this should be updated

Alpha was designed for a game that looked pretty different from what Magic is now. The rules framework was explicitly built around 1v1, and a lot of the cards reflect that. Lifetap, for instance, now reads “any opponent” in its Oracle text, where the original said “target opponent.” A small update that expands it to work beyond 1v1. False Orders got similar treatment with its oracle text, but it functionally changed dramatically.

Part of why this situation is so strange is what False Orders is even trying to do. The original intent seems pretty clearly to have been “interrupt the blocking declaration and redirect a creature to block something else.” The problem is that declaring blockers is not something you can simply have a player redo via spell. Getting that effect to work at all requires very careful oracle text, and even more careful rules text. The current version of the oracle text and rules text does not do that.

The oracle text also creates at least one unintended break from its original intent with another Alpha card: Two-Headed Giant of Foriys, which may block two creatures. Current False Orders only puts the creature blocking a single attacking creature, where it would have intentionally allowed it to block two creatures (like if you wanted to force it to gang block so that it died).

What makes this more interesting is the timeline. False Orders has been played using its oracle text for longer than it was ever played with its original text, at this point 22 years. Anyone picking the card up today is almost certainly playing it by the oracle text, not relying on the Alpha wording. The oracle text, whatever its quirks, is what players have been working with, and the weird cross-player blocking loophole is part of how the card actually functions in the current rules.

If the text ever does get updated, the right call seems like it should go in the direction of legitimizing what’s already happening rather than restricting it. The loophole is fun. It’s strange in a way that’s consistent with the card’s whole personality. An explicit ruling added to the card to confirming that yes, False Orders can in fact redirect a creature to block an attack aimed at a different player, would be a welcome acknowledgment.

-----
