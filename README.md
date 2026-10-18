# dawn-ui

Dawn UI 设计 Skill，适用于网站、App、后台、组件设计和 UI/UX 评审。支持从设计方向、实际页面制作到视觉与操作验收。

当前版本 **1.1.1**。合并 [oil-oil/oil-ui](https://github.com/oil-oil/oil-ui) **v0.23.6** 的开源改进，并独立补充体验设计、工作区、组件和特效实践。保留 MIT 署名；不包含 Oil UI Pro 非公开内容，也不宣称与付费版等同。

## 能做什么

- **探索方向**：按品类和产品内容建立风格，多候选需要时做离线对比页，支持桌面/手机和中英文外壳。
- **制作与取证**：视觉层级、素材、动效、滚动叙事、截图还原；内置截图、录屏、图像对比和素材检索工具。
- **体验设计**：表单、异步状态、失败恢复、持久化验证、权限表达、键盘焦点和窄屏重排。
- **存量项目**：分别处理视觉改版、流程修复和增加功能，从现有变量与共享组件修改。
- **工作区与组件**：按任务选择表格、队列、编辑器、看板或画布，支持组件精修、原位展开和微型抽屉。
- **视觉特效**：按需采用 SVG 流光、点阵、Canvas、渐变和着色器，提供性能预算、静态回退与减少动态效果路径。
- **评审闭环**：用实际画面与任务结果评审；需要深度打磨时有限轮次迭代，记录依据，不以追分代替可用性。

上游的更新检查、原地覆盖安装、购买提示及宣传物料未纳入。独立补充的具体范围和限制见 [能力说明](skills/dawn-ui/references/capabilities.md)。

## 安装与使用

```bash
npx skills add chenguang-jiang/dawn-ui
```

也可让 Agent 安装本仓库。然后描述需求，例如：

```text
用 dawn-ui 优化这个后台，保留品牌，重点改任务层级和失败状态，直接完成并验证。
用 dawn-ui 比较三个不同的首屏方向，做成同屏对比页供我挑选。
用 dawn-ui 评审现有页面，只给有实际证据的问题，先不要修改文件。
用 dawn-ui 精修这个卡片的原位展开，兼顾键盘、手机和减少动态效果。
```

主流程见 [SKILL.md](skills/dawn-ui/SKILL.md)，参考按需加载，不依赖其他 Skill 或指定模型。小改动直接完成；已经给定方向时不强制探索多个方案。

## 可选工具

```bash
python3 skills/dawn-ui/scripts/build_explorer.py <任务目录>/manifest.json --output <任务目录>/style-explorer.html
node skills/dawn-ui/scripts/shoot.mjs <页面或HTML文件> --size desktop --out <任务目录>/shots
node skills/dawn-ui/scripts/curate-media.mjs search "wood" --kind texture --limit 6
```

对比页生成器只需 Python 3.10+ 标准库。截图与素材工具需 Node.js 22+；截图另需本机 Chrome/Chromium/Edge，录屏编码需 ffmpeg。工具不足时使用宿主能力，并明确未验证项。素材联网检索仅在需要时运行，按条目保留许可与署名，不自动购买服务。

详见 [工具](skills/dawn-ui/references/tools.md) 和 [对比页输入格式](skills/dawn-ui/references/style-explorer.md)。产物写任务目录，不写安装目录。

## 维护与验证

对照上游公开版本手动合并，不整目录覆盖 dawn-ui。当前基线 commit：`3a9574dcb23d769b8a2a9a95eb1006544cb307ad`。更新时保留本地命名、无推广/无自动更新策略与独立参考，并验证链接、脚本和模板。

```bash
python3 -m unittest discover -s skills/dawn-ui/tests -v
```

浏览器测试需要本机浏览器，素材回归测试使用本地 HTTP fixtures；未安装依赖时相应测试会跳过。自动化验证能确认工具契约，不能证明每次生成设计的质量。

## License

[MIT](skills/dawn-ui/LICENSE)。上游 Oil UI、独立修改和所带第三方素材的来源见 [第三方声明](skills/dawn-ui/THIRD_PARTY_NOTICES.md)。
