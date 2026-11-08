# gap 年假换算器

gap 多久，等于多少年假？

填入开始 gap 的日期（结束日期选填，默认算到今天），按 **gap 天数 ÷ 每年年假天数** 折算，算出你相当于从哪一年开始上班、一天不休地攒年假，才攒得出这段 gap。

- 显示入职年份对应的朝代与年号（明清元精确到年号，宋到皇帝，唐到主要年号）
- 列出入职年份前后的中外历史小故事，配有历史图片（来自 Wikimedia Commons，见 `credits.html`）
- 展示你的“工龄”横跨了哪些朝代
- 年假标准可选 5 / 10 / 15 / 20 天
- 一键复制分享文案，或生成一张分享图（可保存，支持系统分享；图上带网站二维码，微信里长按即可识别打开）
- 日期按浏览器的语言和地区格式显示

灵感来自网上流传的那张“gap 多久 = 多少年假”对照表。

## 本地运行

纯静态页面，无需构建：

```bash
npx serve .
```

直接用浏览器打开 `index.html` 也能用，但 `file://` 下生成的分享图里不会带历史配图（浏览器限制），建议起个本地服务器。

文件说明：

- `index.html`：页面和全部逻辑
- `events-img.js`：历史事件 → 配图文件、作者、许可的对照表
- `img/ev/`：配图（480×360 WebP，已裁切压缩）
- `credits.html`：图片来源与许可列表
- `vendor/qrcode.js`：生成二维码用的 [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) 1.4.4（MIT），只在点“生成分享图”时加载

分享图里的二维码指向 `index.html` 里 `<link rel="canonical">` 的地址，换域名时记得一起改。

## 部署到 Cloudflare Pages

在 Cloudflare Dashboard → Workers & Pages → Create → Pages → Connect to Git，选择本仓库：

- Framework preset：None
- Build command：留空
- Build output directory：`/`

或者用 Wrangler 直接上传：

```bash
npx wrangler pages deploy . --project-name gap-calculator
```

## 说明

- “一辈子年假”按 35 年工龄 × 每年 15 天 = 525 天估算。
- 公元前 841 年（共和元年）以前的年代均为约数。
- 历史配图均为公有领域、CC0 或知识共享许可（CC BY / CC BY-SA），作者和许可逐张列在 `credits.html`。少数事件没有合适的自由版权图片，页面上用朝代印章样式的占位图代替。

## License

MIT
