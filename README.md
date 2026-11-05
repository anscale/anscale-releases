# Anscale releases

Public downloads of Anscale apps (the Anscale desktop, ClipTab, Mousetab).
This repository holds no source code: only GitHub Releases with
`anscale-package/1` archives, so the Anscale store can download them
without signing in.

The primary download location is https://dl.anscale.app, a Cloudflare R2
bucket behind Cloudflare's CDN. Releases here hold the same files as a
backup. Versions published before 2026-11-05 are still signed with their
GitHub address and download from here.

Install apps with the Anscale desktop or `anscale install <app>`, not from
here. The store does not trust this repository or the R2 bucket: it
installs an archive only when its size and SHA-256 match a release
statement signed by the app's developer and published in the catalog at
https://anscale.app.

## Layout

- One release per app version, tagged `<app>-v<version>`, e.g.
  `cliptab-v0.2.9`, `anscale-v0.1.0`, `mousetab-v0.18.0`. The R2 bucket
  uses the tag as a directory: `<app>-v<version>/<file>`.
- Assets are the archives for each target, e.g.
  `cliptab-0.2.9-linux-x86_64.anscale.tar.gz`.
- The download base for a release, as the release scripts expect it in
  `ANSCALE_DOWNLOAD_BASE`, is `https://dl.anscale.app/<app>-v<version>`.
  Upload to R2 first (see anscale-web `docs/release-runbook.md`), then
  attach the same files to the release here.

Assets are never replaced once published: a signed statement fixes each
archive's SHA-256, and the CDN caches each file for a year. A bad version
is withdrawn with a signed yank, not by deleting its files.

---

# Anscale 安装包

Anscale 应用（Anscale 桌面端、ClipTab、Mousetab）的公开下载位置。这里没有源代码，只有 GitHub Releases 里的 `anscale-package/1` 安装包，供应用商店匿名下载。

主下载位置是 https://dl.anscale.app（Cloudflare R2 存储桶，经 Cloudflare CDN 分发），这里的 Release 放同样的文件作备份。2026-11-05 之前发布的版本签名里是 GitHub 地址，仍从这里下载。

请用 Anscale 桌面端或 `anscale install <app>` 安装。商店不信任本仓库，也不信任 R2 存储桶：只有大小和 SHA-256 与开发者签名、发布在 https://anscale.app 目录里的声明一致时才会安装。

每个应用版本一个 Release，标签为 `<app>-v<version>`；R2 里用同名目录 `<app>-v<version>/<文件名>`。对应的 `ANSCALE_DOWNLOAD_BASE` 是 `https://dl.anscale.app/<app>-v<version>`：先上传到 R2（见 anscale-web 的 `docs/release-runbook.md`），再把同样的文件附到这里的 Release。已发布的文件不替换（CDN 缓存一年）；有问题的版本用签名的撤回声明处理，不删除文件。
