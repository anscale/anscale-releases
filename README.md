# Anscale releases

Public downloads of Anscale apps (the Anscale desktop, ClipTab, Mousetab).
This repository holds no source code: only GitHub Releases with
`anscale-package/1` archives, so the Anscale store can download them
without signing in.

Install apps with the Anscale desktop or `anscale install <app>`, not from
here. The store does not trust this repository: it installs an archive
only when its size and SHA-256 match a release statement signed by the
app's developer and published in the catalog at https://anscale.app.

## Layout

- One release per app version, tagged `<app>-v<version>`, e.g.
  `cliptab-v0.2.9`, `anscale-v0.1.0`, `mousetab-v0.18.0`.
- Assets are the archives for each target, e.g.
  `cliptab-0.2.9-linux-x86_64.anscale.tar.gz`.
- The download base for a release, as the release scripts expect it in
  `ANSCALE_DOWNLOAD_BASE`, is
  `https://github.com/tsui66/anscale-releases/releases/download/<app>-v<version>`.

Assets are never replaced once published: a signed statement fixes each
archive's SHA-256. A bad version is withdrawn with a signed yank, not by
deleting its release here.

---

# Anscale 安装包

Anscale 应用（Anscale 桌面端、ClipTab、Mousetab）的公开下载位置。这里没有源代码，只有 GitHub Releases 里的 `anscale-package/1` 安装包，供应用商店匿名下载。

请用 Anscale 桌面端或 `anscale install <app>` 安装。商店不信任本仓库：只有大小和 SHA-256 与开发者签名、发布在 https://anscale.app 目录里的声明一致时才会安装。

每个应用版本一个 Release，标签为 `<app>-v<version>`；对应的 `ANSCALE_DOWNLOAD_BASE` 是 `https://github.com/tsui66/anscale-releases/releases/download/<app>-v<version>`。已发布的附件不替换；有问题的版本用签名的撤回声明处理，不删除这里的 Release。
