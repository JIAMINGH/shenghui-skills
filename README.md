# 嵊晖出海 · AI 外贸技能库

**V1.0.0 · 学员基础版（发布前审阅稿）**

面向制造工厂 B2B 出海的技能库，现收录三个可独立使用的 Skill。

| Skill | 用途 |
|---|---|
| [嵊晖出海](skills/shenghui-export/SKILL.md) | 出海策略、社媒获客、独立站承接、AI 外贸聊单。包含 15 个专题和 6 个模板，基础工作流无需配置额外 API。 |
| [B2B Facebook Ads Manager](skills/b2b-facebook-ads-manager/SKILL.md) | Meta 广告账户报表、受众研究、诊断和广告操作，也支持 B2B 广告、主页及视频素材制作。 |
| [工厂出海品牌视觉设计](skills/global-brand-visual-designer/SKILL.md) | 从官网、真实产品图和参考图提炼品牌风格，设计 Facebook 主页封面、LinkedIn 与 YouTube 横幅和独立站 Banner。 |

## 安装（Codex）

**本地试用。** 将要用的完整 Skill 目录从本仓库的 `skills/` 复制到业务项目的 `.agents/skills/`。保留原目录名。打开该项目，用下方示例里的 `$技能名称` 调用。若客户端未刷新列表，重启 Codex 后再试。

**从 GitHub 安装。** 计划发布仓库为 `JIAMINGH/shenghui-skills`。文件提交到 GitHub 的 `main` 分支后，可在支持 Skill Installer 的 Codex 聊天中输入对应的一条：

```text
$skill-installer install https://github.com/JIAMINGH/shenghui-skills/tree/main/skills/shenghui-export
$skill-installer install https://github.com/JIAMINGH/shenghui-skills/tree/main/skills/b2b-facebook-ads-manager
$skill-installer install https://github.com/JIAMINGH/shenghui-skills/tree/main/skills/global-brand-visual-designer
```

安装后按提示刷新并确认技能可用。也可按上述方式本地试用。[Codex 技能文档](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)

## 开始使用

```text
$shenghui-export 帮我初始化工厂档案，并根据我的实际产品制定外贸获客方案。
$b2b-facebook-ads-manager 帮我为包装工厂做一份面向海外进口商的线索广告草稿和即时表单问题。
$global-brand-visual-designer 用我的产品实拍和官方 Logo 设计一张 Facebook 主页封面。
```

也可直接提问：我是建材工厂，怎样筛选拉美市场？帮我写面向墨西哥批发商的西语工厂视频；帮我诊断 Facebook 询盘为什么全是零售客户；根据这段 WhatsApp 对话给我推荐下一步跟进。

广告工具读取实际账户时需要配置 `FB_ACCESS_TOKEN` 并安装其 Python 依赖。新建、更改或启用广告前按工具流程确认具体操作。剪辑脚本另外需要 `ffmpeg` 和 `ffprobe`。[广告工具说明](skills/b2b-facebook-ads-manager/README.md)

原工具把 AI 生图和主页资料完善交给 `$jojocode-imagegen` 和 `$fb-page-profile-builder`。使用这两个功能时，按原工具说明设置对应技能。广告输出保存在 `fb_output/` 时，该目录会被 Git 忽略。

品牌视觉 Skill 可以单独提炼图库风格，也可以在当前环境有图像工具时制作封面。公司名称、产品和 Logo 以企业的真实素材为准。

## 仓库结构

- `skills/shenghui-export/SKILL.md`：入口、任务路由、执行规范。
- `skills/shenghui-export/references/`：15 个专题 SOP。
- `skills/shenghui-export/assets/`：6 个可复用模板。
- `skills/b2b-facebook-ads-manager/`：原版广告工具，保留参考资料、脚本、依赖清单与许可。
- `skills/global-brand-visual-designer/`：品牌视觉与主页封面工作流，附风格提炼、平台尺寸、提示词和验收资料。
- `tests/scenarios.md`：人工验收题库。
- [资料收录进度](SOURCE-MAP.md)记录各专题的来源与待核对项。
- `plugin.json`：插件清单草稿。独立 Skill 可按上面的方式使用。
- `CHANGELOG.md`：版本记录。
- `LICENSE-PENDING.md`：待发布者确定授权，不是开源许可证。

## 更新与隐私

已安装的本地 Skill 不保证自动同步 GitHub 更新。发布新版本后，按客户端安装流程备份并更新，不覆盖私人业务档案。学员应把工厂档案保存在自己的私人工作项目，不要提交至公开仓库。

本版本已收录部分课程方法和项目实践，完整历史对话和课件仍待逐项核对。市场、法规及平台规则以任务中的实际核验为准。嵊晖出海 Skill 的 Codex 本地识别及首轮四项模拟任务已通过。[验收记录](tests/scenarios.md#验收记录)

B2B Facebook Ads Manager 由老秦外贸运营手记发布，沿用其原始 MIT 许可。[工具许可](skills/b2b-facebook-ads-manager/LICENSE)

发布前需确认公开范围和授权，发布后的 GitHub 安装需用实际仓库地址验证。
