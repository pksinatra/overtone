# Development Policy

## Environments

`beta/` is the active development and testing area.

`tools/` is production. Treat it as release output, not a workspace for experiments.

## Production Approval

Before anything is deployed to `tools/`, it must be:

- tested in `beta/`
- approved by PK
- approved by external tester
- reviewed by Codex

PK is the communication link between external tester and Codex.

## Server-Side Authority

Keep valuable logic on the server:

- Pro/VIP membership
- payment status
- API access rules
- complete paid datasets
- export and download generation
- saved projects, songs, presets, and user data
- authorization rules

Frontend code may render keyboards, guitars, wheels, synth UI, charts, and interactions, but it should not contain the full protected logic or paid datasets.

## API Access Control

APIs must decide what the user receives:

- full data
- limited data
- upgrade required
- not authorized

Never trust frontend-only flags such as `window.CL_IS_PRO` for real access. They may be used for UI hints, but the server must check actual access.

## Modular Apps

Split apps into modules:

- free modules can be loaded for all users
- Pro/VIP modules should be fetched only after authentication and access checks
- paid datasets should come through controlled server endpoints

## Generated Content

Downloads, presets, exported chord charts, and similar generated content may include discrete attribution where appropriate:

- `Powered by ChordLink`
- `www.chordlink.net`
- `ChordLink by Overtone Works AS`

## Minification And Obfuscation

Do not introduce minification or obfuscation into the development process yet.

Production minification/obfuscation is postponed until the strategy has been discussed and approved.
