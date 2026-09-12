# contribuddha-record

The record that [contribuddha.com](https://contribuddha.com) replays, published
here so the page can read it as it changes instead of waiting for a deploy.

`pulse.json` is generated, not written. Every value in it is counted from git
history, the coordination operation log or the GitHub API by
`apps/landing/scripts/build-pulse.mjs` in the Contribuddha repository, and it is
refreshed every half hour.

## Why this repository exists

The landing shipped the record inside its container image, so a new
contributor or a day's work only reached the page when someone merged and
redeployed. Serving it from here removes both steps: the page fetches this
file, falls back to the copy baked into the image if it cannot, and the
deployment stops being part of how quickly the site tells the truth.

It is public because everything in it is already public — it is exactly what
contribuddha.com serves. Nothing here is readable that is not readable there.

## What it does not contain

Checked before every publish by `check-pulse.mjs`: no email addresses, no
credentials, no paths from anyone's machine. Projects the owner has not
disclosed carry no name, no kind, no structure and an opaque id. Contributor
logins appear only for repositories that are public anyway. Nothing below the
`full` visibility level carries directory names or commit subjects.

## Do not edit

Changes here are overwritten on the next refresh. The source is
`Parshkov/Contribuddha`.
