# Container workflows

`docker-build-push.yml` builds with Buildx, GitHub Actions cache, platform selection,
and caller-supplied tags. Pass registry credentials only when a registry requires them.
Enable `scan` to fail after pushing an image with critical or high findings.

`docker-scan.yml` scans an existing image, uploads SARIF to code scanning, and preserves
the SARIF report as an artifact. Set `fail-on-vulnerability: false` for report-only use.
