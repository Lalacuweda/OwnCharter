# The week I found a gap in my own armor

OwnCharter is only worth building if the agent can actually do things, and if the thing guarding it cannot be talked into standing down. This week I worked on both ends. One of them started as a hole I had not seen.

First, I gave the agent real hands. Until now it could say it was allowed to read a file, create one, or search your files, but those permissions pointed at nothing. Now they point at working capability, and they fail shut: it will not create a file in a folder you never set up, and it will not reach past the paths you granted. A permission now means a real, bounded action, not a promise.

Then the uncomfortable part. While testing, I found my gate guarded the rules but not its own code, and not the record of what it did. In plain terms, a worker-level agent could have rewritten the very thing meant to stop it, or quietly edited the log. That is the exact nightmare this project exists to prevent, and it was sitting in my own build. So I stopped and closed it. The agent can no longer touch the machinery that governs it, cannot run from inside its own install, and cannot forge its own history. One slip is no longer a total breach, because that door now has more than one lock.

I also made refusals honest. When the agent says no, that reads as a decision you can inspect, not a crash. Using your own authority to grant or step up is routine, not an emergency. And I can now sit at a command line and talk to it, every turn passing through the same gate.

Next I am working on how it proves who it is, and on more than one way to reach it. Still aiming for a first alpha late this summer.

