<div align="center">

# Bar Cohen

**Data Scientist and AI Engineer** · Weizmann Institute of Science

*I build AI systems end to end and keep them running in production at the Weizmann Institute of Science, and I teach researchers and staff to bring AI into their own work.*

![Python](https://img.shields.io/badge/-Python-2b2b2b?style=flat-square&logo=python&logoColor=3776AB)
![Java](https://img.shields.io/badge/-Java-2b2b2b?style=flat-square&logo=openjdk&logoColor=white)
![Android](https://img.shields.io/badge/-Android-2b2b2b?style=flat-square&logo=android&logoColor=3DDC84)
![Bash](https://img.shields.io/badge/-Bash-2b2b2b?style=flat-square&logo=gnu-bash&logoColor=4EAA25)
![Postgres](https://img.shields.io/badge/-Postgres-2b2b2b?style=flat-square&logo=postgresql&logoColor=4169E1)
![Supabase](https://img.shields.io/badge/-Supabase-2b2b2b?style=flat-square&logo=supabase&logoColor=3FCF8E)
![MCP](https://img.shields.io/badge/-MCP-2b2b2b?style=flat-square&logo=modelcontextprotocol&logoColor=white)
![Claude Code](https://img.shields.io/badge/-Claude_Code-2b2b2b?style=flat-square&logo=anthropic&logoColor=d4a27f)
![GitHub Pages](https://img.shields.io/badge/-GitHub_Pages-2b2b2b?style=flat-square&logo=githubpages&logoColor=white)

[![Website](https://img.shields.io/badge/brchn6.github.io-0F766E?style=flat-square&logo=google-chrome&logoColor=white)](https://brchn6.github.io)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0F766E?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/brchn)
[![CV](https://img.shields.io/badge/CV_(PDF)-0F766E?style=flat-square&logo=readthedocs&logoColor=white)](https://brchn6.github.io/BarCohenCV.pdf)

`Agent tools` · `MCP` · `CLI first` · `Android` · `Live dashboards`

</div>

<p align="center">
<a href="#tools">Tools</a> · <a href="#radio-playlist-dashboard">Radio Dashboard</a> · <a href="#lettucemeet-cli--mcp">LettuceMeet MCP</a> · <a href="#kol-hashfela-radio">Kol Hashfela Radio</a> · <a href="#how-i-build">How I build</a> · <a href="#teaching">Teaching</a>
</p>

---

## Tools

Tools I built because I needed them. Most of my day-to-day work lives in private repos; these are the ones I've made public.

| Tool | Lang | What it does | Try it |
|:-----|:----:|:-------------|:-------|
| [**Radio Playlist Dashboard**](https://github.com/brchn6/radio-playlist-dashboard) | ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white) | Recognizes and logs every song playing on 8 Israeli radio stations, live, for $0 a month | [Live site](https://brchn6.github.io/radio-playlist-dashboard/) |
| [**LettuceMeet CLI + MCP**](https://github.com/brchn6/LettuceMeet_CLI) | ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white) | Create meeting polls, read responses, and find the best time from the terminal, or let an AI agent do it | `uv sync` · [Setup](https://github.com/brchn6/LettuceMeet_CLI#quick-setup) |
| [**Kol Hashfela Radio**](https://github.com/brchn6/radio-kol-hashfela) | ![Java](https://img.shields.io/badge/-Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white) | One-button Android app for a local radio station: plays in the background and reconnects by itself when the network drops | [Download page](https://brchn6.github.io/radio-kol-hashfela/) |

---

## Radio Playlist Dashboard

8 radio stations, 8 Shazam proxies, one Postgres source of truth, and a dashboard on GitHub Pages that stays fresh within a minute. The collector runs on a machine at home and costs exactly $0 a month.

<p align="center">
  <a href="https://brchn6.github.io/radio-playlist-dashboard/"><img src="https://raw.githubusercontent.com/brchn6/radio-playlist-dashboard/main/docs/demo.png" alt="Radio Playlist Dashboard: live song log across 8 Israeli stations" width="800" /></a>
</p>

<p align="center">
  <a href="https://brchn6.github.io/radio-playlist-dashboard/"><strong>Live site</strong></a> · <a href="https://github.com/brchn6/radio-playlist-dashboard"><strong>Source</strong></a>
</p>

## LettuceMeet CLI + MCP

LettuceMeet has no public API, so I reverse-engineered its internal GraphQL API. Now an AI agent can schedule a meeting without opening a browser.

```
User / Agent -> CLI / MCP -> GraphQL -> lettucemeet.com
```

```bash
git clone https://github.com/brchn6/LettuceMeet_CLI.git && cd LettuceMeet_CLI
uv sync
uv run python main.py login "<token>"
uv run python main.py overlap <event-id>   # best meeting times
```

MCP tools: `create_poll`, `show_event`, `respond_to_poll`, `compute_overlap`, `delete_event`. Works with any MCP client, such as Claude Code, Codex, or Pi. 42 tests.

## Kol Hashfela Radio

An unofficial fan app for Radio Kol Hashfela 103.6FM, the local station in Rehovot. Open it and the station plays. It keeps playing in the background, pauses for calls and navigation prompts, and reconnects by itself when the network drops. Release APKs are signed with a private key kept outside the repo.

<p align="center">
  <a href="https://brchn6.github.io/radio-kol-hashfela/"><img src="https://raw.githubusercontent.com/brchn6/radio-kol-hashfela/main/site/app.png" alt="Kol Hashfela Radio app screen" width="220" /></a>
</p>

<p align="center">
  <a href="https://brchn6.github.io/radio-kol-hashfela/"><strong>Download page</strong></a> · <a href="https://github.com/brchn6/radio-kol-hashfela"><strong>Source</strong></a>
</p>

---

## Also on GitHub

| Project | What it does |
|:--------|:-------------|
| [**audio2md**](https://github.com/brchn6/audio2md) | Meeting recording in, structured English summary out: faster-whisper plus a local Qwen LLM. Hebrew and English. Needs a GPU cluster. |

---

## How I build

- **CLI first.** If a web app has no API, I build one, so scripts and agents can drive it.
- **Agent ready.** Where it makes sense, a tool ships with an MCP server or an agent skill, so AI agents can run it too.
- **One source of truth.** Every project gets one database that everything else reads from.
- **Free where possible.** The radio dashboard runs entirely on free tiers.

## Teaching

I teach *All the Things You Didn't Learn in Your Coding Course*, a course I founded as part of my role at the Weizmann Institute of Science, training researchers and staff to bring AI into their daily work.

## Connect

[brchn6.github.io](https://brchn6.github.io) · [LinkedIn](https://www.linkedin.com/in/brchn) · [CV (PDF)](https://brchn6.github.io/BarCohenCV.pdf)
