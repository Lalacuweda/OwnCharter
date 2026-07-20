This week the chain closed. A capability pack can be signed by the shop that built it, and refused by your own agent if a single byte moved.

Three pieces had to meet in the middle. The artifact law, which fixes exactly how a signature binds to a pack, so a signer and a verifier that never met still agree on what was signed. The signing side, which turns a built pack and a key into that signature and immediately verifies its own work before handing it over. And the edge, where your agent checks the signature against a root you pinned yourself, before anything is admitted. Admission stays your act, not a credential's. If the signature does not hold, the whole delivery is refused rather than half applied.

There is an end to end test now that walks the full path: build, sign, deliver, admit, tamper. It was born failing at the signing leg on purpose, because a test that cannot fail is not a test. It runs every morning and reports through a channel only the checker can write to.

What it cost me: I shipped a distribution format last month that installed correctly and never actually ran for anyone but me. My own setup had an escape hatch that hid the breakage, and the research I shipped on had only ever exercised that hatch. I marked the original requirement invalidated on the record instead of quietly patching over it, then fixed the format. The first cut of the tracer had the same disease. Rig failures were surfacing as real verdicts, and its tamper check flipped a field that would have been rejected anyway, so it proved nothing about the crypto. Both are fixed, with teeth.

Next: two more codebases here are working toward full membership on the same evidence standard, against a deadline already on the record, 2026-09-30.
