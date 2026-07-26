# What is RubyDung?

RubyDung is a ground-up modernization and reimagining of Minecraft, built by forking the game at version 1.5.2 and rebuilding almost everything underneath it — the engine, the toolchain, the language, and eventually the modding layer — while keeping the parts of the game that actually made it great.

It is not a Minecraft server plugin, a mod, or a client tweak. It's a fork in the truest sense: a separate codebase descended from Minecraft 1.5.2, heading somewhere else entirely.

## The short version

Minecraft changed direction after update 1.13. Whether that direction was good or bad is a matter of taste, but RubyDung starts from the position that it wasn't — that the game had accumulated seventeen years of community knowledge, tooling, and genuinely excellent third-party work (performance mods, rendering overhauls, modding frameworks) that the official game never adopted, and that a good starting point plus that accumulated knowledge could produce something better than either the original or its current form.

So RubyDung asks a simple question: *if you were designing this game today, knowing everything the community has learned since, how would you build it?*

The answer isn't "recreate modern Minecraft" and it isn't "keep 1.5.2 forever." It's: take 1.5.2 as a foundation — chosen deliberately, not out of nostalgia — strip out seventeen years of legacy baggage by rebuilding the engine layer by layer, and bring back only the features the community actually wanted, built the way they should have been built the first time.

## Why 1.5.2, specifically

1.5.2 isn't the destination and was never meant to stay the destination. It was chosen as a *starting point* for a few concrete reasons:

- It already has most of the features people associate with "classic" Minecraft, without the years of accumulated complexity that came after.
- The client and integrated/dedicated server code are separated more cleanly in this era than in many later versions, which matters a great deal when you're about to rebuild the engine from the inside out.
- It predates a lot of the architectural decisions RubyDung explicitly wants to avoid repeating.

Nothing about the final project is meant to resemble 1.5.2 by the time it's done. Every phase of the roadmap below exists specifically to erode that starting point and replace it with something built properly.

## The name

Before Minecraft, Notch worked on a game called RubyDung, and some of its ideas and assets became the seed Minecraft grew from. RubyDung, the project, is doing the same thing one level up: taking a known, working foundation and using it as raw material for something that eventually stops being that foundation at all. The name is a joke, but it's also a fairly literal description of what's happening here.

## The philosophy: Minecraft isn't Minecraft anymore

Something changed in Minecraft's identity, and it's easiest to see by looking at what the game used to be built out of. Up through around 1.13, Minecraft was blocky, minimal, a little clanky, built on programmer-art textures, scored almost entirely by C418's sparse ambient music, and voiced by sound effects that were often literally just Creative Commons recordings of someone's dog barking. None of that was a limitation the game was waiting to outgrow — it *was* the art style, and it worked precisely because it stayed out of the way. A sandbox game where the player's own builds are the most interesting thing on screen needs its mobs, sounds, and textures to be simple enough not to compete with that. Even the ravager, added as late as 1.14, is still blocky and clanky in exactly the right way.

Since roughly 1.16, that's changed. The strider was arguably the first real sign of it: smooth, fully animated, alive in a way nothing before it had been — recognizable as good work, but work that belongs to a different kind of game. The 1.14 texture overhaul moved away from programmer art toward smoother, more vibrant textures. The Nether's warped and crimson forests read as strikingly modern next to everything around them. The soundtrack and sound design shifted to newer composers and more cinematic production. And the new mobs and mechanics arriving since — the warden, the allay, the creaking, the mace, deep dark dungeons — bring articulated animation rigs, elaborate encounter design, and a tone that's reaching for *exploration and survival horror* rather than *sandbox*. None of this is bad work. Put in a different game, most of it would be great. It's specifically the mismatch that's the problem: it would fit comfortably in a modern action-adventure title, and it doesn't fit in a game about placing blocks.

That drift has a name in other corners of the internet — "enshittification" — and whether or not it's the product of deliberate strategy or just the ordinary gravity of a huge company optimizing a huge live-service property, the practical effect on the game itself is the same either way: Minecraft has been quietly becoming a different game, wearing the original's name, for years. RubyDung's asset-replacement plans later in the roadmap aren't only about staying clear of Mojang's intellectual property — they're a deliberate aesthetic stance. RubyDung intends to keep feeling like a sandbox game, on purpose, rather than drifting toward whatever the current live-service incentives happen to favor.

## The roadmap: is it still the same game?

RubyDung is being rebuilt in deliberate phases, each one intentionally sequenced so that only one hard problem is being solved at a time — never rewriting the toolchain and the renderer and the language simultaneously. The project starts with mechanical, low-risk groundwork and only gets more ambitious once that ground is solid: modernizing the build tooling, untangling a flat and disorganized file structure into something a real engineer would recognize, giving fifteen years of decompiled `var1`/`var2`/`var3` placeholder variables real names, porting the rendering backend to a current graphics API generation, moving the whole codebase to a current, actively-maintained language runtime, adopting a cleaner and more sensible world/block ID system than the original ever had, modernizing the OpenGL rendering path for real performance gains, selectively bringing back only the community's favorite ideas from later Minecraft versions and from mods, and gradually introducing Kotlin as the primary language across the codebase — not because Java is bad as a platform (the JVM itself is one of the best pieces of engineering in computing), but because Kotlin is a considerably more pleasant, safer, and more modern language to actually build something in, especially once heavier multithreading enters the picture.

Somewhere past the halfway point of that list, a fair question starts to apply: is this still the same codebase it started as? The honest answer is that it's a ship of Theseus, on purpose. Every plank gets replaced eventually — the language, the renderer, the file layout, and eventually the assets themselves, since RubyDung intends to replace textures and art with original work that captures the same spirit without being a copy of anything Mojang currently sells. By the time the project is "done," in whatever sense a project like this is ever done, very little of the original 1.5.2 source will remain untouched. That's not a side effect. That's the actual goal.

The furthest-out ambition, sitting past all of the above, is a modding API built into the engine itself from the start — one that draws on the best ideas from Forge, Fabric, Quilt, LiteLoader, and everything the modding community has learned about what makes a good modding layer, rather than bolting a mod loader onto an engine that was never designed to be modded. The internals are meant to stay *recognizable* to anyone who's modded real Minecraft before, even where they're not compatible with it — familiar shapes, different foundations underneath.

None of this is about compatibility with vanilla Minecraft. It was never the goal to stay compatible, and it isn't the goal now. It's about using a good foundation, and everything the last seventeen years taught the community, to build the game as it could have been — and as it used to be, before it started turning into something else.

## On the legal side of things

Anyone building something like this owes it to themselves — and to anyone thinking about getting involved — to be honest about the legal terrain, rather than hand-wave it.

The short version: this is very unlikely to be a legal problem, though "very unlikely" is not the same as "impossible," and nothing here is legal advice.

A few concrete points inform that read:

- **The Minecraft EULA does not prohibit reverse engineering or decompilation.** It restricts redistributing exact copies of the game's source code — it does not restrict building your own, substantially different implementation informed by having studied the original.
- **Mojang has a long, consistent track record of tolerating this exact category of project.** Cuberite and Minosoft, among others, are vanilla-inspired server and client reimplementations that have existed publicly for years without any enforcement action. More recently, the source code for Minecraft: Legacy Console Edition leaked, and multiple community forks have been actively modernizing and porting it to modern platforms in the open, entirely unbothered.
- **Mojang has been officially distributing deobfuscation mappings for the current game for a long time**, and in recent versions those mappings are essentially unobfuscated — the decompiled source is close to 1:1 readable. That's not the posture of a company trying to prevent this kind of work; if anything, it's closer to "go ahead."
- **A large share of Minecraft's classic sound effects were never Mojang's original work to begin with.** Minecraft's own official sound attribution page credits dozens of individual effects — dog barks, cow moos, glass breaking, footsteps, thunder, water splashes, gunfire, and much more — to named contributors on Freesound.org, released under Creative Commons licenses like CC0 (public domain) and CC BY. Mojang is, in fact, recognized as the first major video game studio to legally use more than one Freesound sample. This doesn't mean the sounds are RubyDung's to freely reuse verbatim — attribution and license terms still apply to whoever uses them — but it does mean the common assumption that "every byte of Minecraft's audio is proprietary Microsoft property" is simply false, and demonstrably so, straight from Mojang's own credits page.
- **The game's famous "End Poem" isn't owned by Microsoft at all.** Writer Julian Gough wrote it in 2011 and, by his own account, never signed the contract handing its rights over to Mojang, and later declined a second contract sent to him just before the Microsoft acquisition. In 2022 he confirmed publicly that Microsoft never held the rights and formally released the poem into the public domain under a CC0 dedication — meaning Minecraft's actual ending narrative is free for anyone to use, quote, or build on, by the choice of the one person who's always owned it.
- **A large portion of Minecraft's original soundtrack is owned by its composer, not Mojang or Microsoft.** C418 (Daniel Rosenfeld) retained the copyright to the tracks he wrote for the game's early years — Mojang and Microsoft hold usage rights within Minecraft itself, but the compositions remain his intellectual property. Later composers like Lena Raine did sign their rights over to Microsoft, so this doesn't apply to all of the game's music, but it's one more piece of the picture showing that "Minecraft" isn't a single, monolithic block of Microsoft-owned material the way it's often assumed to be.
- The name "RubyDung" itself isn't trademarked by Microsoft or Mojang, and — being a joke reference to one of Notch's pre-Minecraft projects rather than anything resembling the Minecraft name or branding — isn't the kind of name Microsoft could meaningfully claim a trademark over even if they wanted to.
- On top of all of that, RubyDung intends to replace the game's textures and art assets with original work over time, which further separates the project from anything Mojang currently sells.

None of this amounts to a legal guarantee, and nobody involved in this project is a lawyer. But the pattern is clear and consistent: Mojang's actual, demonstrated posture toward fan reimplementations, decompilation-based projects, and even full leaked-source-code derivatives has been to leave them alone, as long as nobody is redistributing Mojang's own exact source or selling something that competes directly with the official game. RubyDung fits comfortably inside the space that history has already shown Mojang tolerates.

## Where this ends up

RubyDung isn't trying to replace Minecraft, compete with it, or pull its playerbase away. It's a labor of love aimed at building the game a chunk of the community has wanted for a long time — one shaped by everything that's been learned since 1.5.2, unconstrained by corporate incentives or backward-compatibility obligations, and free to just be good. If it ends up small — a handful of people playing something they genuinely enjoy — that's success. Anything bigger than that is a bonus.
