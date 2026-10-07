# Anton Patrai

I have spent nine years in B2B SaaS growth: go-to-market, SEO, content, paid ads,
lifecycle marketing and product analytics. Over the past year I added AI agents
to those same channels, so a channel can scale on compute.

Today I run dozens of Claude Code sessions in [herdr](https://herdr.dev) on a
Windows PC and Codex lanes on a Mac mini and VPS servers, across several Claude
and Codex subscriptions. I built a few tools that make a fleet that size easier
to run, and a checker for the copy it writes.

## What I build

| Repository | What it does | Stack |
| --- | --- | --- |
| [anti-slop-content](https://github.com/patraianton/anti-slop-content) | Rules, a checker and an eight-step review line for marketing copy written by AI agents. Nine rules cover what agents get wrong: product claims, prices, compliance promises, setup times, competitors and unsourced numbers. Each rule is a data file with its source of truth, regex cues and test cases; an agent from a second model family tries to refute the facts, and a release ships only if its hash matches the last reviewed text. Everything about your company lives in one `project/` folder. | Python, standard library only |
| [herdr-sidebar](https://github.com/patraianton/herdr-sidebar) | herdr plugin for a Spaces sidebar of twenty-plus workspaces full of AI agents: titled categories with drag and drop, four kinds of colour stars with a hotkey to cycle through each kind, jump hotkeys to a project or a single tab, and git worktrees detached into a category of their own without stopping their agents. Agents on 24/7 duty check in with `herdr-duty`; one that stops waking up, hangs on a question or loses its pane turns red and can ping Telegram. | Node.js, no dependencies |
| [subtrack](https://github.com/patraianton/subtrack) | Local dashboard for a fleet of Claude Code and Codex windows on several Claude, Codex and Grok subscriptions. Shows what is left of every five-hour and weekly limit and which sessions burned it, ranked by a cost-weighted token count; Codex sessions on other machines are read over ssh. Lists every Claude window in herdr, longest idle first: one click opens it or moves it to another subscription, and a mode per window decides whether its prompt cache is kept warm or the window gets compacted. | TypeScript, Node.js |
| [teammate](https://github.com/patraianton/teammate) | CLI that lets one Claude Code session hire another as a worker in its own herdr tab: a written brief, a status log the worker appends to, and a close command that refuses to discard uncommitted work. Each worker can get its own git worktree from a ready pool, so parallel workers never touch each other's files; waiting on a worker costs the supervisor no tokens. | Node.js, no dependencies |
| [sheepdog](https://github.com/patraianton/sheepdog) | Live kanban board and dispatcher for dozens of Claude Code and Codex sessions in herdr. Every session is a card filed by hand into Focus, Ongoing or Tools; the board raises one verdict, whether the next step is on you, and counts a session as busy only when a process, a counter or a timer proves it. Each card carries a one-line recap and a prompt-cache countdown; a dispatcher session reads the whole board as text and writes decisions back. | Node.js, no dependencies |
| [local-dictation](https://github.com/patraianton/local-dictation) | Push-to-talk dictation that runs entirely on a Windows PC: faster-whisper on the GPU transcribes speech full of product names, and a local LM Studio model restores punctuation and terms. Every other change the model makes is diffed against the spoken words and rolled back, and every setting in `config.toml` carries the measurement that chose it. | Python, faster-whisper, LM Studio |
| [multi-lane-development](https://github.com/patraianton/multi-lane-development) | Delivery board that ran sprints on a fleet of parallel Codex agents. It handed each ticket to a free lane, had a separate agent check every pull request against the spec, reviewed the code, merged on green CI and walked the live site afterwards; I was asked once per sprint. | Node.js, no dependencies |

## Contact

I am in Riga, Latvia. Write to me on
[LinkedIn](https://www.linkedin.com/in/anton-patrai).
