# pod-dl Podcasts for Jellyfin

A standalone plugin for browsing and playing audio podcasts downloaded by pod-dl.
Requires **Jellyfin 12.2 / .NET 10**. It does not require Aurelia or Companion.
Video podcasts are planned for v2.

This repository hosts public release packages and Jellyfin's plugin catalog.
No release is published yet; the catalog will offer an installable version after
the first release succeeds.

## Install through Jellyfin

Add this URL under **Dashboard → Plugins → Repositories → Add**:

```text
https://raw.githubusercontent.com/drewtenn/pod-dl-jellyfin-dist/main/manifest.json
```

Once a release is available, install **pod-dl Podcasts** from the plugin catalog
and restart Jellyfin. In the plugin settings, set **Podcast output directory** to
the pod-dl archive path visible to Jellyfin. The archive must include a schema 1
`.pod-dl/catalog.json`; generate it with `pod-dl catalog --output-directory <root>`
if needed. Grant the intended users channel access, then open **pod-dl Podcasts**
in Jellyfin Web. Jellyfin needs read access to the catalog, audio and artwork.

## Manual installation

Download `pod-dl-jellyfin-<version>.zip` from Releases. MD5 and SHA-256 checksum
files accompany each package. Extract exactly `Jellyfin.Plugin.PodDl.dll` and
`meta.json` directly into a `PodDl_<version>` folder in Jellyfin's plugin directory.
Use the same ownership as the other plugins so Jellyfin can update `meta.json`.
Restart Jellyfin and configure the archive and channel access as above.

Installing or updating a release is your choice. Publishing a package does not
deploy it to your Jellyfin server.
