<p align="center">
  <img alt="Contributor License" src="brand/logo-1024-transparent.png" width="120">
</p>

<h1 align="center">docs</h1>

<p align="center">
  Brand assets, design concepts and documentation sources for
  <a href="https://github.com/contributor-license">contributor-license</a>.
</p>

---

## Contents

| Path | What |
| --- | --- |
| [`brand/`](brand) | Logo source and generated PNGs for the organization avatar, GitHub App and social previews |

## Brand assets

[`brand/cla-logo.svg`](brand/cla-logo.svg) is the source of truth. Every PNG is
generated from it — [`brand/README.md`](brand/README.md) has the exact commands.
Regenerate rather than editing a PNG by hand.

| Asset | Size | Use |
| --- | --- | --- |
| `org-avatar-500.png` | 500×500 | Organisation avatar |
| `app-logo-512.png` | 512×512 | GitHub App logo |
| `app-logo-200.png` | 200×200 | GitHub App logo, if 512 is rejected |
| `logo-1024.png` | 1024×1024 | Master raster |
| `logo-1024-transparent.png` | 1024×1024 | Transparent, for your own background |
| `social-preview-460.png` | 460×460 | Repository social preview |

Colours: navy `#101e41`, teal `#209a8f`.

The navy is close to unreadable on a dark background. The white-backed variants
are the safe default anywhere you cannot control the surface. Where you can —
a README, for instance — serve a `prefers-color-scheme` pair instead, as
[the organisation profile](https://github.com/contributor-license/.github/blob/main/profile/README.md)
does.

## Where the projects live

| Repository | |
| --- | --- |
| [cla-action](https://github.com/contributor-license/cla-action) | The GitHub Action. Released, `v1` |
| [.github](https://github.com/contributor-license/.github) | Organisation profile and shared community files |
| `app` | Hosted service. Private, in development |
| `infra` | Terraform and Cloudflare configuration. Private |

## Licence

[Apache-2.0](LICENSE) for the contents of this repository.

The logo is a project mark. Use it to refer to `contributor-license`; do not use
it to imply that a project of yours is endorsed by or affiliated with it.
