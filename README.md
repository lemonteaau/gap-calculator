# gap 年假换算器

gap 多久，等于多少年假？

填入开始 gap 的日期（结束日期选填，默认算到今天），按 **gap 天数 ÷ 每年年假天数** 折算，算出你相当于从哪一年开始上班、一天不休地攒年假，才攒得出这段 gap。

- 显示入职年份对应的朝代与年号（明清元精确到年号，宋到皇帝，唐到主要年号）
- 列出入职年份前后的中外历史小故事
- 展示你的“工龄”横跨了哪些朝代
- 年假标准可选 5 / 10 / 15 / 20 天
- 一键复制分享文案

灵感来自网上流传的那张“gap 多久 = 多少年假”对照表。

## 本地运行

纯静态单文件，无需构建：

```bash
npx serve .
# 或者直接用浏览器打开 index.html
```

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

## License

MIT
