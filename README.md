# Overtone

Main repository for Overtone Works development.

Production target:

- `https://www.overtone.no/tools`

Test target:

- `https://www.overtone.no/beta`

## Repository Layout

- `beta/` - test and staging area for tools before production approval.
- `tools/` - production-ready tools only. Do not edit directly during development.
- `members/` - membership-related shared code, docs, or future integration work.
- `docs/` - project map, release policy, and development rules.

## Production Rule

Nothing is deployed to `tools/` until it has been tested in `beta/` and explicitly approved by:

- PK
- External tester
- Codex review

## Development Rule

Keep valuable logic on the server. Frontend code should focus on presentation and interaction. Access, payment status, Pro/VIP features, exports, saved projects, presets, and full paid datasets must be controlled by server-side code and APIs.
