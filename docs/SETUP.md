# GitHub 主页更新说明

目标仓库：[Dong7777/Dong7777](https://github.com/Dong7777/Dong7777)。本目录包含主页源码、贡献动画配置和维护说明；主页文件提交到 `main` 分支后，即会展示在个人主页。

## 1. 更新主页

打开 [README 编辑页面](https://github.com/Dong7777/Dong7777/edit/main/README.md)，用本目录 `README.md` 的全部内容替换原文，点击 **Commit changes**，提交到 `main` 分支。

打开 [个人主页](https://github.com/Dong7777) 查看更新。现有 Profile 仓库已经创建，不需要重新建仓库，也不需要开启 GitHub Pages。

打字动画、技能图标、统计卡片和贡献活动图使用公开图片服务；它们不需要额外密钥，但可用性取决于对应服务和网络。原贡献折线图服务检查时返回错误，已替换为通过检查的 GitHub Profile Summary Cards。

## 2. 添加贡献动画配置

1. 打开 [创建动画配置文件](https://github.com/Dong7777/Dong7777/new/main?filename=.github%2Fworkflows%2Fsnake.yml)。
2. 确认文件名是 `.github/workflows/snake.yml`。
3. 将本目录 `.github/workflows/snake.yml` 的全部内容填入编辑框。也可以使用 `docs/snake-workflow.txt`，两份内容一致，文本版本便于直接查看。
4. 点击 **Commit changes**，提交到 `main` 分支。

请单独创建上述路径的文件。只上传 `README.md` 不会配置动画；普通文件选择窗口也可能隐藏以点开头的 `.github` 文件夹。

## 3. 确认首次运行

1. 打开 [仓库 Actions](https://github.com/Dong7777/Dong7777/actions)。如果提示启用工作流，先启用。
2. 选择 **Update contribution snake**。首次提交配置会自动触发运行。
3. 如果尚未运行，点击 **Run workflow**，选择 `main`，再次点击 **Run workflow**。
4. 等待任务显示绿色成功标记，再返回个人主页，展开 **Contribution Animation**。

工作流会创建 `output` 分支，并在其中生成：

```text
github-contribution-grid-snake.svg
github-contribution-grid-snake-dark.svg
```

之后每天北京时间约 **09:17** 自动刷新。GitHub 的定时任务可能延迟；公开仓库长时间无活动时，定时工作流也可能被暂停，届时在 Actions 中重新启用。

这个配置使用 GitHub 自动提供的 `GITHUB_TOKEN`，不需要创建个人访问令牌，也不需要手动创建 `output` 分支。

## 4. 常见问题

**提示 `403`、`Permission denied` 或无权推送：**

检查仓库 **Settings → Actions → General**。允许所用 Actions 运行，并确认组织或仓库策略没有禁止工作流写入。配置中已经对生成任务声明 `contents: write`；如果有分支规则阻止写入 `output`，也需要调整对应规则。保存后重新运行失败任务。

**动画图片还没有出现：**

先确认最近一次任务成功，并检查 `output` 分支是否包含上述两个 SVG 文件。GitHub 图片可能有缓存，稍后刷新。不要把图片地址里的 `output` 改成 `main`。

**统计卡片或打字动画偶尔加载失败：**

这些图片来自第三方服务，稍后刷新。静态介绍、技能名称和项目文字仍然可读；不要将个人访问令牌添加到任何图片 URL。

## 5. 后续维护

- `README.md` 中已加入中文注释，可据此修改介绍、颜色、研究方向和项目。
- 未提供真实邮箱或学术链接，因此主页不展示示例邮箱、空链接或 “Coming Soon” 徽章。
- 四个工程与教学方向作为工作方向展示，不声称已经发布对应项目。仓库公开后，再使用注释中的模板添加真实项目链接。
- 当前精选项目保留已有的 `im6A` 仓库；可逐步补充 README、演示图片、复现步骤和论文引用。
- 语言统计反映公开仓库的代码构成，不代表完整技能水平。

参考：[GitHub Profile README](https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme)、[贡献动画项目](https://github.com/Platane/snk)、[GitHub Stats Extended](https://github.com/stats-organization/github-stats-extended)、[GitHub Profile Summary Cards](https://github.com/vn7n24fzkq/github-profile-summary-cards)。
