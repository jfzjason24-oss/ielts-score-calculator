# IELTS 雅思成绩计算器

**非官方项目。** 一个无依赖、可直接在浏览器运行的雅思总分计算器。项目包含三种独立界面，计算逻辑一致，均支持响应式布局、键盘操作和输入错误提示。

## 在线使用

- [版本选择页](https://jfzjason24-oss.github.io/ielts-score-calculator/)
- [A · 流体编辑风](https://jfzjason24-oss.github.io/ielts-score-calculator/fluid/)
- [B · 公共服务风](https://jfzjason24-oss.github.io/ielts-score-calculator/service/)
- [C · 精密仪器风](https://jfzjason24-oss.github.io/ielts-score-calculator/instrument/)

## 计算规则

将听力、阅读、写作和口语四项 Band Score 相加后除以 4，再按照 IELTS 官方总分规则换算：

- 平均分尾数小于 `.25`：向下取整；
- 平均分尾数达到 `.25`：计为 `.5`；
- 平均分尾数达到 `.75`：进到下一个整数。

例如，四项成绩为 `6.5 / 6.5 / 5.0 / 7.0` 时，平均分是 `6.25`，最终总分为 `6.5`。

规则参考：[IELTS Scoring in detail](https://ielts.org/take-a-test/your-results/ielts-scoring-in-detail)，最后核验日期为 2026-08-15。

输入值应为已经获得或预计获得的四项 Band Score（`0–9`，整数或半分），而不是听力、阅读的答对题数。

## 项目结构

```text
.
├── index.html              # 三个版本的统一入口
├── fluid/index.html        # A · 流体编辑风
├── service/index.html      # B · 公共服务风
├── instrument/index.html   # C · 精密仪器风
├── .nojekyll               # 让 GitHub Pages 原样发布静态文件
└── LICENSE
```

三个计算器均为独立的单文件 HTML，不依赖框架、包管理器或第三方 CDN。

## 本地运行

可以直接双击任一 `index.html`，也可以在仓库根目录启动任意静态文件服务器。例如：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000/`。

## 已验证项目

- 5 组官方换算边界用例；
- 无效输入提示与修正恢复；
- 表单标签和键盘可操作性；
- 375 px 移动端无横向溢出；
- 浏览器控制台无错误；
- 所有计算均在本地完成，不收集或发送用户输入。

## 隐私

项目没有登录、Cookie、统计分析或远程数据接口。输入的成绩不会上传、保存或发送给任何第三方。

## 免责声明

这是一个非官方学习工具，与 IELTS、British Council、IDP 或 Cambridge University Press & Assessment 无隶属、合作或认可关系。IELTS 名称及相关标识归其各自权利人所有。最终成绩以考试机构正式成绩单为准。详见 [NOTICE.md](./NOTICE.md)。

本项目在开发、测试和发布过程中使用了 OpenAI Codex 辅助；最终代码由仓库所有者审核并发布。

## License

[MIT](./LICENSE)。MIT License 仅适用于本仓库中的原创代码和文档，不授予任何第三方名称、商标或标识的使用权。
