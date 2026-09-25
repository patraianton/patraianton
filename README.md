# Anton Patrai

I have spent nine years in B2B SaaS growth: go-to-market, SEO, content, paid ads,
lifecycle marketing and product analytics. Over the past year I added AI agents
to those same channels, so a channel can grow without hiring more people for it.
The agents run on servers and work with the team in Slack; each job gets the
harness and the model that suit it, and each pipeline has its cost tracked. I
build these systems for other people to use and train the people who run them
day to day. I also build software with coding agents.

Today I run dozens of Claude Code sessions in [herdr](https://herdr.dev) on a
Windows PC and Codex lanes on a Mac mini and VPS servers, across several Claude
and Codex subscriptions. I track how much of each limit every session uses, and I
dictate instead of typing.

## What I build

| Repository | What it does | Stack, tests, status |
| --- | --- | --- |
| [multi-lane-development](https://github.com/patraianton/multi-lane-development) | Delivery board that ran sprints on a fleet of Codex lanes. `bin/watchtower.mjs` handed each ticket to a free lane, had a separate agent check every pull request against the spec, reviewed the code, merged on green CI and walked the live site afterwards. I was asked once per sprint. Its own measurements replaced it with a shorter process. | Node 22+, no dependencies, 264 tests. Paused since 15 September 2026. |
| [sheepdog](https://github.com/patraianton/sheepdog) | Local kanban board for dozens of Claude Code and Codex sessions in herdr. Reads every session's state every 3 seconds, counts a session as busy only when a process, a counter or a timer proves it, and marks the cards waiting on you. A dispatcher session reads the whole board as text and writes decisions back through a CLI. | Plain Node, no dependencies. In daily use since August 2026. |
| [teammate](https://github.com/patraianton/teammate) | CLI that lets one Claude Code session hand a task to another in its own herdr tab and supervise it: a brief file, a status file and a close command that refuses to wipe uncommitted work. Each worker can get its own copy of the repository from a ready pool; waiting on a worker costs the supervisor no tokens. | One Node file, no dependencies. |
| [local-dictation](https://github.com/patraianton/local-dictation) | Push-to-talk dictation that runs entirely on a Windows PC. faster-whisper transcribes Russian speech full of English product names; a local LM Studio model restores punctuation and terms, and any other change it makes is rolled back. Every setting in `config.toml` carries the measurement that chose it. | Python 3.11+, faster-whisper, LM Studio; 28 test scripts, 24 on faked hardware. In daily use since August 2026. |
| [subtrack](https://github.com/patraianton/subtrack) | Local Windows dashboard for several Claude Code and Codex subscriptions: what is left of each five-hour and weekly limit, which session burned through a five-hour limit, and what the idle-compaction task will do with each idle session next. | TypeScript on Node.js 24, 300+ tests. In use since June 2026. |

## Contact

I am in Riga, Latvia. Write to me on
[LinkedIn](https://www.linkedin.com/in/anton-patrai).
