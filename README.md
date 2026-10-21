# 3d-car

纯静态页面合集，通过 GitHub Pages 部署。

| 页面 | 在线地址 | 说明 |
|---|---|---|
| 陀螺仪 & 加速器 Demo | https://tkobe129-create.github.io/3d-car/ | 实时显示手机加速器 / 方向角数据 |
| 广州小蛮腰 · 全息光效 | https://tkobe129-create.github.io/3d-car/canton-tower/ | 倾斜手机驱动的广州塔全息卡片（WebGL） |

两个页面都会调用手机的陀螺仪 / 加速器：iOS 13+ 会在点击按钮后弹出系统权限请求，Android 直接可用；传感器 API 只能在 HTTPS 下工作，GitHub Pages 已强制 HTTPS。

## 陀螺仪 & 加速器 Demo 使用方法

1. 用手机浏览器（建议 Safari / Chrome）打开上面的链接（必须是 HTTPS，GitHub Pages 默认即为 HTTPS）。
2. 点击「🔓 开启陀螺仪 & 加速器权限」按钮。
   - iOS 13+ 会弹出系统权限请求，点击「允许」。
   - Android 及其他设备会直接开始监听。
3. 页面实时显示：
   - 加速器（含重力）X / Y / Z
   - 陀螺仪方向角 Alpha / Beta / Gamma

> 若 iOS 上误点了「不允许」，需要彻底关闭 Safari（从后台划掉）后重新打开页面再试。

## 部署

- `main` 分支每次 push 都会触发 [`.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml)，
  使用 `actions/upload-pages-artifact` + `actions/deploy-pages` 把仓库根目录发布到 GitHub Pages。
- 也可以在 Actions 页面手动触发（`workflow_dispatch`）。
- 修改页面只需编辑 `index.html` 并推送到 `main`。
