# Home Lab Config

Config inspired by [htpcBeginner](https://github.com/htpcBeginner/docker-traefik),
Homelab is running on [Ubuntu Linux](https://ubuntu.com/),
hosting [Docker](https://www.docker.com/) + [Portainer](https://www.portainer.io/) on an internal [Tailscale](https://tailscale.com) VPN
with application stacks that auto-sync to the docker-compose files in this repo.

TODO: Set up proper backups of application data/config. I don't trust docker volumes.

The stacks are:
- Homelab - general docker management, watchtower, frontends, reverse proxy
- Adblock - DNS Filtering for adblocking
- CI - I have a Rails app I use as a testbed for multiple CI/monitoring services, and some of those require self-hosted runners
- Media - Plex server, and friends
- Misc others for scoped applications

---

TODO/Notes:

- See https://github.com/htpcBeginner/docker-traefik for some config ideas (and a linked huuuuge tutorial)
  - Specifically, Traefik for wildcard DNS from inside Tailscale would be easier than managing ports
  - Would also be nice to map a few things publicly like `foundry.example.com`
- See above + https://apps.heimdall.site/applications/enhanced for potentially more app ideas
  - [Glances](https://glances.readthedocs.io/en/latest/) for "remote" monitoring on the docker host OS
  - Monicahq.com maybe? I've thought about it on and off for years
  - Ombi or https://overseerr.dev/
  - https://github.com/HaveAGitGat/Tdarr with a worker on the mac would be nice
  - _possibly_ Heimdall as a universal frontend, with Organizr for the media center subtools? Would be useful to have links to foundry, komga, plex, ombi etc at toplevel for easier navigation, and leave organizr to manage swapping detailed media tools like sonarr/radarr/etc.

See also https://github.com/meienberger/runtipi for a curated app list
