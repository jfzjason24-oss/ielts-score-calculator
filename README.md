# IELTS 雅思总分计算器 | IELTS Overall Band Calculator

**非官方项目 / Unofficial project.** 一个无需安装、可直接在浏览器中使用的中英双语雅思总分计算器。界面采用 A「流体编辑风」，根据听力、阅读、写作和口语四项 Band Score 即时估算 Overall Band。

An install-free, bilingual IELTS overall band calculator in the Version A fluid editorial style. Enter the four component band scores to see the estimated overall band immediately.

## 在线使用 | Use Online

- [打开双语流体版计算器 / Open the bilingual fluid calculator](https://jfzjason24-oss.github.io/ielts-score-calculator/)

## 功能 | Features

- 中英文信息同屏呈现，无需切换语言；
- 听力、阅读、写作和口语均支持 `0–9`、间隔为 `0.5` 的 Band Score；
- 拖动滑杆或使用加减按钮后，原始平均分和换算总分即时更新；
- 提供重置示例成绩、换算说明和官方规则来源；
- 单页静态实现，不依赖框架、包管理器、第三方 CDN 或后端服务。

English and Chinese are presented together. All four component scores accept bands from `0` to `9` in `0.5` increments, with live average and overall-band results.

## 计算规则 | Scoring Rule

将听力、阅读、写作和口语四项 Band Score 相加后除以 4，再换算到最近的 `0.5` 分。平均分尾数为 `.25` 时进到下一个半分，尾数为 `.75` 时进到下一个整数。

The four component band scores are averaged and rounded to the nearest half band. An average ending in `.25` rounds up to the next half band; an average ending in `.75` rounds up to the next whole band.

例如 / Examples:

- `6.5 / 6.5 / 5.0 / 7.0` → 平均分 / average `6.25` → 总分 / overall `6.5`
- 平均分 / average `6.75` → 总分 / overall `7.0`
- 平均分 / average `6.125` → 总分 / overall `6.0`

规则参考 / Official rule reference: [IELTS Scoring in detail](https://ielts.org/take-a-test/your-results/ielts-scoring-in-detail)，最后核验日期 / last verified: 2026-08-15。

输入值应为已经获得或预计获得的四项 Band Score，而不是听力、阅读的答对题数。

Enter the awarded or expected component **band scores**, not the number of correct Listening or Reading answers.

## 项目结构 | Project Structure

```text
.
├── index.html          # 唯一主页：中英双语流体版计算器
├── fluid/index.html    # 旧 A 版地址的兼容跳转页
├── favicon.svg         # 站点图标
├── .nojekyll           # 让 GitHub Pages 原样发布静态文件
├── NOTICE.md           # 第三方名称与商标说明
└── LICENSE             # MIT License
```

`/fluid/` 仅为旧链接和收藏提供兼容跳转；当前唯一正式入口是仓库根页面。

## 本地运行 | Run Locally

可以直接打开根目录的 `index.html`，也可以在仓库根目录启动任意静态文件服务器。例如：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000/`。

Open the root `index.html` directly, or serve the repository with any static-file server and visit `http://localhost:8000/`.

## 无障碍 | Accessibility

- 四项成绩均有可识别的中英双语标签；
- 滑杆、加减按钮、重置按钮和链接均支持键盘操作；
- 提供清晰的焦点样式、跳转到计算器的链接和实时结果播报；
- 支持减少动态效果的系统偏好；
- 布局覆盖桌面端和窄至 `375 px` 的移动端视口。

Controls are keyboard accessible, visibly focused and labelled in both languages. Result updates are announced to assistive technology, reduced-motion preferences are respected, and the layout is responsive.

## 验证范围 | Verification

- 5 组计分及半分换算边界用例；
- 滑杆、加减按钮和重置操作；
- 表单标签、可访问名称、键盘焦点与实时结果；
- `375 px` 移动端横向溢出检查；
- 页面加载及浏览器控制台错误检查；
- 旧 `/fluid/` 地址到根页面的兼容跳转。

## 隐私 | Privacy

所有计算均在浏览器本地完成。项目没有登录、Cookie、统计分析或远程数据接口；输入的成绩不会上传、保存或发送给任何第三方。

All calculations run locally in your browser. There are no accounts, cookies, analytics or remote data APIs, and entered scores are neither stored nor transmitted.

## 免责声明 | Disclaimer

这是一个非官方学习工具，与 IELTS、British Council、IDP 或 Cambridge University Press & Assessment 无隶属、合作或认可关系。IELTS 名称及相关标识归其各自权利人所有。最终成绩以考试机构正式成绩单为准。详见 [NOTICE.md](./NOTICE.md)。

This unofficial study tool is not affiliated with, endorsed by or connected to IELTS, the British Council, IDP, or Cambridge University Press & Assessment. IELTS and related marks belong to their respective owners. Official test results always take precedence. See [NOTICE.md](./NOTICE.md).

本项目在开发、测试和发布过程中使用了 OpenAI Codex 辅助；最终代码由仓库所有者审核并发布。

## License

[MIT](./LICENSE)。MIT License 仅适用于本仓库中的原创代码和文档，不授予任何第三方名称、商标或标识的使用权。
