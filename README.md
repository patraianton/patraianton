# Anton Patrai

I have spent nine years in B2B SaaS growth: go-to-market, SEO, content, paid ads,
lifecycle marketing and product analytics. Over the past year I added AI agents
to those same channels, so a channel can grow without hiring more people for it.
The agents run on servers and work with the team in Slack; each job gets the
harness and the model that suit it, and each pipeline has its cost tracked. I
build these systems for other people to use and train the people who run them
day to day. I also build software with coding agents.

Claude Code (Anthropic) and Codex (OpenAI) are coding agents: programs that read
and write code on their own and run in a terminal. One running agent is a
session. A lane is one Codex session working in its own copy of the repository
on another machine. [herdr](https://herdr.dev) is the terminal manager that holds
the sessions on my Windows PC; each herdr window holds one or more of them. A
pull request is one proposed change to the code, checked before it is merged.
Each paid subscription allows only so much use per five hours and per week, so
the work is spread over several.

Today I run dozens of Claude Code sessions on the Windows PC and eight Codex
lanes: three on a Hetzner server, two on a Hostinger server and three on a Mac
mini. Each job gets the tool and the model that suit it. I track how much of each
subscription's limit every session uses, and I count Codex runs per pull request.
On 6 August 2026 herdr held 44 windows. All of this runs on seven Claude and two
Codex subscriptions, and I dictate instead of typing: 2,994 voice recordings in
the two weeks to 31 August 2026.

The repositories below are the tools I wrote for that work. Four of them solve
problems that appear only when one person runs many coding agents at once; the
fifth, local-dictation, turns my speech into text.

## What I build

| Repository | What it does | Stack, tests, status |
| --- | --- | --- |
| [multi-lane-development](https://github.com/patraianton/multi-lane-development) | A delivery board, one Node process, that ran sprints on eight Codex lanes across three machines until its own measurements replaced it with a shorter process. A Claude Code session wrote the GitHub tickets from the spec; `bin/watchtower.mjs` handed each ticket to a free lane, had an agent that did not write the code check every pull request against the spec, reviewed the code, merged it when the automated checks passed and walked the live site afterwards. I was asked once per sprint, on one page. | Node 22 or newer, no dependencies, 264 tests. Paused since 15 September 2026. |
| [sheepdog](https://github.com/patraianton/sheepdog) | A local kanban board for one person who runs dozens of Claude Code and Codex sessions in herdr. It reads every session's state every 3 seconds, counts a session as busy only when a process, a counter or a timer proves it, and shows for each card whether the next step is on you. A second Claude Code session, the dispatcher, reads the whole board as one page of text and writes its decisions back through a command-line tool. | Plain Node, no dependencies. In daily use since August 2026. |
| [teammate](https://github.com/patraianton/teammate) | A command-line tool that lets one Claude Code session hand a task to a second session in its own herdr tab and supervise it through a brief file, a status file of one-line updates and a close command that refuses to wipe uncommitted work. Each worker can get its own copy of the repository from a ready pool, so parallel workers never touch each other's files, and waiting on a worker costs the supervising session no AI tokens. | One Node file, no dependencies. |
| [local-dictation](https://github.com/patraianton/local-dictation) | Push-to-talk dictation that runs entirely on a Windows PC, so a spoken order reaches the coding agent as it was said, not reworded. faster-whisper recognizes Russian speech full of English product names; a model already loaded in LM Studio restores punctuation and terms under a lock that rolls back every other change it makes. Every measured setting in `config.toml` carries the measurement that chose it in a comment. | Python 3.11 or newer, faster-whisper and LM Studio; 28 test scripts, 24 of them on faked hardware. In daily use since August 2026. |
| [subtrack](https://github.com/patraianton/subtrack) | A local Windows dashboard for several paid Claude Code and Codex subscriptions. It shows how much of each five-hour and weekly limit is left, which local session used up a five-hour limit, and, for each idle session, what the separate idle-compaction task will do with it next (subtrack only writes the mode file that task obeys; compacting shrinks a session's chat history). | TypeScript on Node.js 24, over 300 tests. In use since June 2026. |

Three pieces are worth an engineer's first look. sheepdog puts a countdown on
every full card: how long Anthropic still keeps a stored copy of that session's
conversation (the prompt cache). Once the copy expires, the next message pays for
the whole conversation again, so cards you marked as today's focus or starred
turn red 10 minutes before the end. local-dictation compares the language
model's corrected text with the spoken words and keeps only punctuation, capital
letters, glossary terms and a verb turned into a command ("I will run it"
becomes "run it"); everything else rolls back. subtrack ranks the sessions that
used up a five-hour limit by a weighted token count (`src/burn/read.ts`): an
output token counts 5 and a token read back from the prompt cache counts 0.1, so
a session that writes a lot outranks one that mostly rereads its stored
conversation.

## How I work

1. A spec becomes one ticket before any code is written. A Claude Code session
   cuts the spec into one GitHub ticket that lists every requirement next to an
   empty "proved by" column, and starts a lane on it (multi-lane-development).
2. That one Codex lane builds the whole sprint in its own copy of the repository,
   proves every requirement itself, puts a screenshot of every screen next to its
   design mock-up and opens one pull request with the "proved by" column filled
   in. Workers started with teammate get the same kind of separate copy from a
   ready pool.
3. The reviewer is one standing thread of Amp, a third-party coding agent, woken
   by a GitHub Actions workflow. It answers with one verdict, GO or NO-GO, within
   30 minutes. The process allows one fix round; after a second NO-GO the Claude
   Code session decides what to do. The pull request merges when the automated
   checks pass, and I look at the screenshots and the live site for two minutes.
4. I watch the fleet on a board. sheepdog reads every session's state from herdr
   every 3 seconds and tells me which card waits on me; subtrack shows how much
   of each subscription's limit is left and which session used it up.
5. I measure the process and change it when the numbers say so.

## Contact

I am in Riga, Latvia. Write to me on
[LinkedIn](https://www.linkedin.com/in/anton-patrai).
