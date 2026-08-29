# Security notes

This repository is a private English localization and hardening derivative of
[zLanqing/codex-claude-academic-skills](https://github.com/zLanqing/codex-claude-academic-skills).
It is a **skill pack** for AI coding agents (Cursor, Claude Code, Codex), not a
network service. Agents that load these skills can run local scripts, unpack
Office files, launch browsers, and call literature APIs.

## Hardening in this fork

| Area | Change |
|------|--------|
| Google Scholar | Free-proxy / `FreeProxies` MITM path removed from `search_google_scholar.py`. Prefer PubMed, OpenAlex, or Crossref. |
| LibreOffice shim | `xlsx/.../soffice.py` LD_PRELOAD C shim is **off** unless `ALLOW_SOFFICE_LD_PRELOAD=1`. Prefer skipping validation when `soffice` is missing. |
| Office unpack | Zip Slip checks in all `unpack.py` copies before `extractall`. |
| Windows PowerShell | `.ps1` COM helpers remain for Windows + PowerPoint only; they are inert on macOS. |

## Safe usage rules

1. **Do not auto-install packages.** Do not run `pip`, `brew`, `uv`, or `sudo apt` unless the user explicitly asks for that install in the current task.
2. **Do not dump or commit secrets.** Never print or commit API keys, tokens, or `.env` contents. Keys such as `NCBI_API_KEY`, `S2_API_KEY`, `CORE_API_KEY`, and `OPENALEX_API_KEY` must stay in the environment.
3. **Confirm before outbound literature calls** that would send titles, abstracts, manuscript text, or unpublished data to third-party APIs (PubMed, PMC, arXiv, OpenAlex, Crossref, Semantic Scholar, CORE, Unpaywall, Google Scholar).
4. **Treat untrusted PDFs/DOCX/PPTX as untrusted input.** Unpack and parse only files the user provided; do not open random downloads.
5. **Do not overwrite originals.** Write versioned copies of Office files, data, and figures.
6. **Playwright / Chromium** (`html2pptx.js`) launches a browser for HTML→PPTX. Use only when generating slides from HTML.
7. **Academic figure prompts** (`academic-figure-prompt`) write English image-generation prompts only. Do not call image APIs from the skill. Do not run [LigphiDonk/academic-figure-generator](https://github.com/LigphiDonk/academic-figure-generator) or send prompts to `api.keepgo.icu` / `tpkcur.xyz`. The user pastes the prompt into an official tool they already use (Gemini, ChatGPT Images, Midjourney). Do not install third-party skills with `npx skills add`.
8. **Unpublished manuscripts still leave the machine** when pasted into Cursor or an official image tool (the model provider sees the text). Ask before reading confidential files.

## What was assessed (summary)

Sampled Python, JavaScript, and PowerShell showed no reverse shells, no committed secrets, and no GitHub Actions. Residual risk is intentional agent capability (local file IO, optional network literature lookup, optional Office tooling), not hidden malware.
