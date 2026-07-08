This week was mostly about how much authority I let the agent hold, and proving it only ever holds that much.

I finished the backbone that decides who the agent is talking to and what that identity is allowed to do: a real login step before anything else runs, a ceiling on authority that can only rise through the same door every other request goes through, and a filesystem boundary that denies read and write access by default and opens only where I explicitly say so. I also stopped treating the operator's own authority as an emergency exception this week. It is how the thing works every day, not a special case reserved for a crisis.

None of that is theoretical. While wiring up a new way for people to reach the agent, I found it had been passing every test against a message shape the real service never actually sends. It would have rejected every genuine message in production. I caught it by testing against the live thing instead of trusting my own fixtures.

The honest part: the daily check that is supposed to catch drift like that elsewhere had a bug of its own, one mistyped character, and it had been silently reviewing nothing for weeks while still reporting everything clear. Green that meant nothing. I fixed it and added a harder rule: checking zero things is now a failure by itself, not a pass.

Bigger picture, and the reason I can even say something like "by the end of September": the law that governs all of this moved out of one project this week and became its own constitution sitting above everything I build, with its own review process. Every new codebase born under that law starts on probation, not full trust, with a real deadline, this one by the end of September, to earn full standing or get flagged automatically. Two new codebases are already on that clock.

Next: get a real outside user running this in production. I know the specific pieces standing between here and there, and most of them are already landing.
