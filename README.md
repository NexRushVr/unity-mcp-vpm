# unity-mcp-vpm

Unofficial **VPM repository mirror** of [CoplayDev/unity-mcp](https://github.com/CoplayDev/unity-mcp), auto-synced daily so you can install it via [VCC](https://vcc.docs.vrchat.com/) or [ALCOM](https://github.com/anatawa12/AvatarOptimizer).

---

## Add to VCC / ALCOM


```
https://NexRushVr.github.io/unity-mcp-vpm/index.json
```

Or use the VCC deep-link:

```
vcc://vpm/addRepo?url=https://NexRushVr.github.io/unity-mcp-vpm/index.json
```

```
https://NexRushVr.github.io/unity-mcp-vpm/index.json
```

The workflow runs daily at 08:00 UTC and will automatically pick up new upstream versions.

---

## How it works

1. **Sync job**: Sparse-checks out only the `MCPForUnity/` subfolder from the upstream repo, reads the version from `package.json`, and if that version hasn't been released yet creates a new GitHub Release with a properly structured `.zip`.
2. **Publish job**: Fetches all releases from this repo, downloads each zip, reads the `package.json` inside, computes a SHA256, and assembles a VPM-compatible `index.json` — then deploys it to GitHub Pages.
3. **Deploy job**: Publishes the `Website/` folder (index.json + landing page) via GitHub Pages.

---

## Notes

- This is a personal mirror, not affiliated with CoplayDev.
- Packages are unmodified — the zip is built directly from the upstream source.
<!-- - To force a re-sync, manually trigger the workflow from the Actions tab. -->
