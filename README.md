# Anton Patrai

I have spent nine years in B2B SaaS growth: go-to-market, SEO, content, paid ads,
lifecycle marketing and product analytics. Over the past year I added AI agents
to those same channels, so a channel can scale on compute.

Today I run dozens of Claude Code sessions in [herdr](https://herdr.dev) on a
Windows PC and Codex lanes on a Mac mini and VPS servers, across several Claude
and Codex subscriptions. I built a few tools that make a fleet that size easier
to run, and a checker for the copy it writes.

## What I build

| Repository | What it does | Stack, tests, status |
| --- | --- | --- |
| [anti-slop-content](https://github.com/patraianton/anti-slop-content) | Rules, a checker and an eight-step line for marketing copy that an agent writes and a person signs. Nine rules cover the sentences agents get wrong in launch copy: product claims, prices, compliance promises, setup times, unsourced numbers and more. Each rule carries its source of truth, regex cues and fixtures; everything about the company lives in one `project/` folder. On the launch it was built for, the first run found 189 problems in a version that earlier review rounds had passed; the released version had none. | Python standard library only, 243 self-test fixtures, a fictional example company checked in CI. Published October 2026. |
| [herdr-sidebar](https://github.com/patraianton/herdr-sidebar) | herdr plugin that keeps a Spaces sidebar of twenty-plus workspaces in order: titled categories, four kinds of colour stars with `Alt+1`…`Alt+4` to cycle through each kind, jump hotkeys to a project or one of its tabs, and git worktrees detached into a category of their own without stopping their agents. Agents that work around the clock check in with `herdr-duty`; one that stops waking up, waits on a question or loses its pane turns red in the sidebar and can ping Telegram. | Node.js 20+, no dependencies, 178 unit tests and an end-to-end run in throwaway herdr sessions. Published October 2026. |
| [subtrack](https://github.com/patraianton/subtrack) | Local dashboard for a fleet of Claude Code and Codex windows on several Claude, Codex and Grok subscriptions. Shows what is left of every five-hour and weekly limit and which sessions burned it. Lists every Claude window in herdr, longest idle first, with what it is doing and which account it runs on; one click opens the window or moves it to another subscription, and a care mode per window decides whether its prompt cache is kept warm or the window gets compacted. | TypeScript on Node.js 24, 300+ tests. In use since June 2026. |
| [teammate](https://github.com/patraianton/teammate) | CLI that lets one Claude Code session hand a task to another in its own herdr tab and supervise it: a brief file, a status file and a close command that refuses to wipe uncommitted work. Each worker can get its own copy of the repository from a ready pool; waiting on a worker costs the supervisor no tokens. | One Node file, no dependencies. |
| [sheepdog](https://github.com/patraianton/sheepdog) | Keeps you focused on the few sessions that matter when dozens run at once. Every herdr session is a card, filed by hand into Focus, Ongoing or Tools; the board raises one verdict, whether the next step is on you, and shows those cards first. A session counts as busy only when a process, a counter or a timer proves it; every card carries a one-line recap and a prompt-cache countdown. A dispatcher session reads the whole board as text and writes decisions back. | Plain Node, no dependencies. In daily use since August 2026. |
| [local-dictation](https://github.com/patraianton/local-dictation) | Push-to-talk dictation that runs entirely on a Windows PC. faster-whisper transcribes Russian speech full of English product names; a local LM Studio model restores punctuation and terms, and any other change it makes is rolled back. Every setting in `config.toml` carries the measurement that chose it. | Python 3.11+, faster-whisper, LM Studio; 28 test scripts, 24 on faked hardware. In daily use since August 2026. |
| [multi-lane-development](https://github.com/patraianton/multi-lane-development) | Delivery board that ran sprints on a fleet of Codex lanes. `bin/watchtower.mjs` handed each ticket to a free lane, had a separate agent check every pull request against the spec, reviewed the code, merged on green CI and walked the live site afterwards. I was asked once per sprint. Its own measurements replaced it with a shorter process. | Node 22+, no dependencies, 264 tests. Paused since 15 September 2026. |

## Contact

I am in Riga, Latvia. Write to me on
[LinkedIn](https://www.linkedin.com/in/anton-patrai).
