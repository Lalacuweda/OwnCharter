This week I started building OwnCharter in the open. The real work was not adding features. It was making the agent's rules provable against a live, running system, not just true in a test file.

So I stood up a real environment where the agent runs against a real model, and I began producing live proof that the governance actually holds there, not just in theory. To iterate on it without fear, I built a way to capture a clean image of that whole environment and roll it back between runs. Every proof cycle now starts from the same known good baseline, and a wrecked run costs me one reset.

What I was proving it refuses is the part I care about. I removed the agent's ability to run arbitrary shell commands. That closed a real hole I found while auditing my own agent: it could rewrite its own governance rules by routing the change through a command my file guard did not cover. Every action it can take is now a named, typed capability. On top of that, each role runs under a hard ceiling: a set autonomy level, only the write paths it is granted, and a spending limit it cannot exceed. If it keeps failing, a breaker trips and it stops instead of thrashing.

The honest part: most of this week went into the proof apparatus, not the features. Showing that the system refuses the wrong thing is harder, and slower, than making it do the right thing. I wrote some of these checks more than once before I trusted them.

Next I want to keep widening what it safely refuses, and make this governed core something I can sit in front of and talk to.
