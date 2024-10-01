# Appcast Workflow

> Reusable workflow to generate [Sparkle `appcast.xml`](https://sparkle-project.org/documentation/) for my apps

Fork and use this for your own apps if you'd like. I'm happy to accept improvements, but I won't be accepting additional configuration. This workflow is tailored to my needs.

## Setup

- Create a new repo.
- Enable GitHub Pages in the repo settings, then go to “Environments”, and in “Deployment branches and tags”, select “No restriction”.
- Export the [EdDSA private key](https://sparkle-project.org/documentation/#eddsa-ed25519-signatures) from Sparkle (`./generate_keys -x private-key-file`) and add it as a repo secret called `SPARKLE_PRIVATE_KEY`.
- Add [this workflow file](https://github.com/sindresorhus/quickgpt-meta/blob/main/.github/workflows/appcast.yaml) to the repo.
- Add the GitHub Pages URL to your app's Info.plist with the key `SUFeedURL`. For example, `https://sindresorhus.com/quickgpt-meta/appcast.xml`.

## Publish update

- Create a new release on the repo and add the zipped app bundle as a binary to the release.
	- To mark an update as [criticial](https://sparkle-project.org/documentation/publishing/#critical-updates), include `<!-- CRITICAL_UPDATE -->` in the release notes.
