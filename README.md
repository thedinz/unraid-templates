# unraid-templates

Unraid Community Applications templates for apps maintained by `thedinz`.

The `main` and `dev` branches are kept aligned for template publishing. App
release tracks are selected by each container image tag, not by switching this
template repository.

## Templates

- `templates/deduplarr.xml` - Deduplarr
- `templates/kam.xml` - Kometa Asset Manager
- `templates/spotifybu.xml` - SpotifyBU, a Spotify metadata backup and
  Navidrome-ready library helper with optional Navidrome or Plex playlist sync.
  The template uses the stable `ghcr.io/thedinz/spotifybu:latest` image and
  includes Unraid-friendly `PUID`, `PGID`, reverse-proxy URL, Navidrome API, and
  ownership-repair settings.
- `templates/naviclean.xml` - NaviClean
