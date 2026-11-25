# telegram-rpg-assets

Public pictures for the Telegram RPG murder-mystery Bot.

This repository is **public on purpose**. The Bot does not fetch these files —
**Telegram's own servers do**, when the Bot sends a picture by URL, so the files
must be readable without any credential. The Bot's own code and game data live
in a separate private repository.

## What belongs here

Role pictures, and nothing else. No tokens, no game data, no briefings, no
transcripts, no player information.

## How a picture is referenced

A scenario document names a role's picture by its raw URL:

```json
{ "id": "waiter", "title": "夥計", "briefing": "…",
  "image": "https://raw.githubusercontent.com/TraderBen2084/telegram-rpg-assets/main/roles/role_a.jpg" }
```

The host and this repository's path are pinned in the Bot's authoring contract,
so a scenario document cannot point the Bot at any other host. Only `.jpg`,
`.jpeg`, `.png` and `.webp` are accepted, and the URL may carry no query string
or fragment.

## Two rules when adding a file

1. **Filenames are public.** Anyone can list this repository, so a filename
   like `killer.jpg` or `murderer_chef.png` spoils the mystery before the game
   starts. Use neutral names: `role_a.jpg`, `role_b.png`.
2. **Keep it inside Telegram's limits.** A picture fetched by URL must be at
   most 10 MB, with width + height no more than 10000 and a side ratio no
   greater than 20.

Anything committed here is public permanently: deleting a file later does not
remove it from this repository's history.
