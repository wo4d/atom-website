# Atom website — community data setup

The Home Page is ready to display real Atom server statistics and featured communities. It reads `data/communities.json`. The starter file intentionally contains no invented server count or names.

## Data format

```json
{
  "guildCount": 123,
  "featuredServers": [
    {
      "name": "Community name",
      "icon": "https://cdn.example.com/server-icon.png",
      "memberCount": 250,
      "inviteUrl": "https://discord.gg/example"
    }
  ]
}
```

- `guildCount` must be the real number of guilds the Atom bot is currently in.
- `featuredServers` should contain only communities whose owners/admins have agreed to be publicly listed. This is an opt-in showcase, not a dump of every private guild name.
- `icon`, `memberCount`, and `inviteUrl` are optional. Use only public HTTPS URLs.

## To make it live

The current website is a static front end and the real Atom bot source was not supplied in this build. For automatic updates, the bot process must publish the live guild count and owner-approved featured-server data to a public JSON endpoint (or update this JSON file through your deployment workflow). Keep the Discord bot token and any write/API secret on the bot server only; never place them in website JavaScript.

Send the Atom bot ZIP/source and say where it is hosted (for example, a VPS, Pterodactyl panel, or another host) to integrate a real automatic feed into its existing runtime.
