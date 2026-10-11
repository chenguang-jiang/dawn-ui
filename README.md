# jcg-ui

JCG 的个人 UI 设计 Skill：设计方向探索、多风格同屏对比、视觉层级与减法精修、基于实际画面的独立评审协议，适用于网站、App、后台与组件的界面设计和界面评审。

## 能做什么

- **方向探索**：先认品类、拆标杆，再用方向卡收敛出有辨识度的设计北极星。
- **风格对比页**：内置离线对比页模板与生成器，多个小样同屏并排、单张查看、桌面/手机视口切换、选择即复制。
- **视觉精修**：视觉层级、字体、色彩、空间、素材、配图与三处基本动效的判断方法。
- **独立评审**：无历史上下文、基于实际截图与录屏的评审协议，也支持按既有设计规范评审存量界面。

## 目录结构

```text
skills/jcg-ui/
├── SKILL.md              # 主流程：范围判断 → 方向 → 结构 → 取证 → 评审 → 交付
├── references/           # 按需加载的方法参考
├── assets/               # 风格对比页模板
├── scripts/              # 对比页生成器（Python 3.10+ 标准库）
└── tests/                # 生成器与模板的回归测试
```

## 安装

对支持安装 Skill 的 Agent 说：

```text
请帮我安装这个 Skill：https://github.com/chenguang-jiang/jcg-ui
```

或用命令安装：

```bash
npx skills add chenguang-jiang/jcg-ui
```

## 生成风格对比页

```bash
python3 skills/jcg-ui/scripts/build_explorer.py <任务目录>/manifest.json --output <任务目录>/style-explorer.html
```

manifest 格式见 [references/style-explorer.md](skills/jcg-ui/references/style-explorer.md)。

## 测试

改动 `scripts/` 或对比页模板后运行：

```bash
python3 -m unittest discover -s skills/jcg-ui/tests -v
```

## License

[MIT](skills/jcg-ui/LICENSE)
