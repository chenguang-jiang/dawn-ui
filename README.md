# jcg-ui

JCG 的个人 UI 设计 Skill：设计方向探索、多风格同屏对比、视觉层级与减法精修、基于实际画面的独立评审协议，适用于网站、App、后台与组件的界面设计和界面评审。

基于 [oil-oil/oil-ui](https://github.com/oil-oil/oil-ui) v0.12.0（MIT）本地化而来，方法论文本未改动，主要差异：

- 改名 `jcg-ui`，移除上游的 oil-ui-pro / draw-ui / oil-motion 推广和首次使用提示。
- 移除加载时自更新机制（上游实现会读取上游版本列表并用 npx 原地覆盖整个目录），改为对照上游手工维护，frontmatter 的 `upstream` 字段记录基线版本。
- 风格对比页模板去品牌：移除 Oil UI 标志与外部链接，浏览器存储键前缀改为 `jcg-ui:`。
- 移除 GitHub 宣传物料；保留 LICENSE（MIT，版权归上游作者）与测试。

## 安装

对支持安装 Skill 的 Agent 说：

```text
请帮我安装这个 Skill：https://github.com/chenguang-jiang/jcg-ui
```

或用命令安装：

```bash
npx skills add chenguang-jiang/jcg-ui
```

## 升级

上游出新版本时，不要整目录覆盖更新，先 diff `SKILL.md` 和 `references/` 的方法论文本增量，手工合并到本仓库，再更新 `skills/jcg-ui/SKILL.md` 里的 `upstream` 字段。

## 测试

改动 `scripts/` 或对比页模板后运行：

```bash
python3 -m unittest discover -s skills/jcg-ui/tests -v
```

## License

[MIT](LICENSE)
