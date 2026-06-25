# 换汇计算器 PWA 部署说明

## 文件结构

- `index.html`：主页面
- `manifest.webmanifest`：PWA 安装配置
- `service-worker.js`：离线缓存与本地运行支持
- `icons/`：手机桌面图标

## 最简单部署方式：Cloudflare Pages

1. 登录 Cloudflare。
2. 进入 Workers & Pages / Pages。
3. 创建项目。
4. 选择 Upload assets / Direct Upload。
5. 上传本目录内的全部文件，或上传 ZIP 后解压再部署。
6. 部署完成后，会得到一个 `https://xxx.pages.dev` 链接。
7. 用手机浏览器打开该链接。
8. 安卓 Chrome：菜单 → 添加到主屏幕 / 安装应用。
9. iPhone Safari：分享 → 添加到主屏幕。

## 注意

- 不建议继续用 `file://` 本地文件方式做 PWA，因为 Service Worker 和安装能力通常需要 HTTPS 或 localhost。
- 实时离岸汇率仍依赖网络接口；离线时计算器主体功能可继续使用，汇率可以手动输入。
- 若修改了页面后手机没有更新，可在浏览器里刷新，或改 `service-worker.js` 里的 `CACHE_NAME` 版本号。


## 更新说明
- 新增“扣汇差后等值换汇金额 / 扣价差后等值兑换金额”内部结果行。
- 客户版复制结果继续隐藏基准汇率、离岸参考价、额外汇差、杂费、扣汇差后等值金额、市场参考金额和汇差成本。
