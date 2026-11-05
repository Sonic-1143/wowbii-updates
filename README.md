# WOWBII Primary Quiz Challenge — Update Feed

This repository hosts public update packages and the JSON release feed for the WOWBII Primary Quiz Challenge server.

## Enable GitHub Pages

1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **GitHub Actions** as the source.
3. Push files into `release_site/` to trigger deployment.
4. After the first successful deployment, the site will be available at:

   https://sonic-1143.github.io/wowbii-updates/

The updater feed URL is:

`https://sonic-1143.github.io/wowbii-updates/update_feed.json`

## Publish a release

Use the `publish_release.py` script included in the WOWBII HTTPS Release Feed Edition project ZIP. It validates the update package and its manifest, then generates the package file and `update_feed.json` under `release_site/`.

Example:

```bash
python publish_release.py wowbii-update.zip --version 1.0.1 --base-url https://sonic-1143.github.io/wowbii-updates --notes "Bug fixes and improvements"
```

Commit and push the generated `release_site/` directory. GitHub Actions will deploy it.

## Security

- Publish only update ZIPs, release notes, feed JSON and static site files.
- Never commit student records, databases, passwords, teacher PINs, private keys, or server configuration.
- Protect the GitHub account with multifactor authentication.
- The updater verifies HTTPS and SHA-256 package hashes. The feed hash is an integrity check, not an independent publisher signature.
- Test each update on a separate installation before publishing it to the school server.

## Current status

The Pages workflow and landing page are being configured. No update package or live update manifest is published until a validated release is generated and deployed.
