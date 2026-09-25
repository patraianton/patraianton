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
and Codex subscriptions. I built a few tools that make a fleet that size easier
to run.

## What I build

| Repository | What it does | Stack, tests, status |
| --- | --- | --- |
| [subtrack](https://github.com/patraianton/subtrack) | Local dashboard for a fleet of Claude Code and Codex windows on several Claude, Codex and Grok subscriptions. Shows what is left of every five-hour and weekly limit and which sessions burned it. Lists every Claude window in herdr, longest idle first, with what it is doing and which account it runs on; one click opens the window or moves it to another subscription, and a care mode per window decides whether its prompt cache is kept warm or the window gets compacted. | TypeScript on Node.js 24, 300+ tests. In use since June 2026. |
| [teammate](https://github.com/patraianton/teammate) | CLI that lets one Claude Code session hand a task to another in its own herdr tab and supervise it: a brief file, a status file and a close command that refuses to wipe uncommitted work. Each worker can get its own copy of the repository from a ready pool; waiting on a worker costs the supervisor no tokens. | One Node file, no dependencies. |
| [sheepdog](https://github.com/patraianton/sheepdog) | Keeps you focused on the few sessions that matter when dozens run at once. Every herdr session is a card, filed by hand into Focus, Ongoing or Tools; the board raises one verdict, whether the next step is on you, and shows those cards first. A session counts as busy only when a process, a counter or a timer proves it; every card carries a one-line recap and a prompt-cache countdown. A dispatcher session reads the whole board as text and writes decisions back. | Plain Node, no dependencies. In daily use since August 2026. |
| [local-dictation](https://github.com/patraianton/local-dictation) | Push-to-talk dictation that runs entirely on a Windows PC. faster-whisper transcribes Russian speech full of English product names; a local LM Studio model restores punctuation and terms, and any other change it makes is rolled back. Every setting in `config.toml` carries the measurement that chose it. | Python 3.11+, faster-whisper, LM Studio; 28 test scripts, 24 on faked hardware. In daily use since August 2026. |
| [multi-lane-development](https://github.com/patraianton/multi-lane-development) | Delivery board that ran sprints on a fleet of Codex lanes. `bin/watchtower.mjs` handed each ticket to a free lane, had a separate agent check every pull request against the spec, reviewed the code, merged on green CI and walked the live site afterwards. I was asked once per sprint. Its own measurements replaced it with a shorter process. | Node 22+, no dependencies, 264 tests. Paused since 15 September 2026. |

## Contact

I am in Riga, Latvia. Write to me on
[LinkedIn](https://www.linkedin.com/in/anton-patrai).
