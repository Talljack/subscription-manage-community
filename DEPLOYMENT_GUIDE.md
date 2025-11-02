# 公开社区仓库文件使用说明

## 📁 文件清单

所有文件已生成在 `/community-repo-files/` 目录下：

```
community-repo-files/
├── README.md                          # 主页介绍
├── CODE_OF_CONDUCT.md                 # 行为准则
├── CONTRIBUTING.md                    # 贡献指南
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── subscription_review.md     # 订阅评价模板
│   │   ├── bug_report.md              # Bug 报告模板
│   │   ├── feature_request.md         # 功能建议模板
│   │   └── config.yml                 # Issue 模板配置
│   ├── DISCUSSION_TEMPLATE/
│   │   └── subscription_share.yml     # 讨论模板
│   └── workflows/
│       └── greetings.yml              # 自动欢迎新成员
└── docs/
    ├── getting-started.md             # 快速开始指南
    └── faq.md                         # 常见问题
```

## 🚀 部署步骤

### 1. 在 GitHub 创建新仓库

1. 访问 https://github.com/new
2. 填写信息：
   - **仓库名**: `subscription-manage-community`
   - **描述**: `WhereMyMoney 订阅管理社区 - 分享订阅服务体验、价格对比和管理技巧`
   - **可见性**: ✅ Public
   - **初始化**:
     - ✅ Add a README file
     - ✅ Choose a license: CC BY-SA 4.0
3. 点击 "Create repository"

### 2. 克隆仓库到本地

```bash
git clone https://github.com/YOUR_USERNAME/subscription-manage-community.git
cd subscription-manage-community
```

### 3. 复制所有文件

将 `community-repo-files/` 下的所有文件复制到仓库根目录：

```bash
# 在 subscription-manage 项目目录下执行
cp -r community-repo-files/* ../subscription-manage-community/
```

或者手动复制每个文件。

### 4. 修改文件中的占位符

在所有文件中，将以下内容替换为实际值：

- `yourusername` → 你的 GitHub 用户名
- `subscription-manage-community` → 你的仓库名（如果不同）

**需要替换的文件**：
- README.md
- CONTRIBUTING.md
- .github/ISSUE_TEMPLATE/config.yml
- docs/getting-started.md
- docs/faq.md
- .github/workflows/greetings.yml

**快速替换命令**（在仓库目录下）：

```bash
# macOS/Linux
find . -type f -name "*.md" -o -name "*.yml" | xargs sed -i '' 's/yourusername/YOUR_USERNAME/g'

# 或者使用你喜欢的文本编辑器全局查找替换
```

### 5. 提交到 GitHub

```bash
git add .
git commit -m "feat: 初始化社区仓库"
git push origin main
```

### 6. 启用 GitHub Discussions

1. 进入仓库 → Settings
2. 滚动到 "Features" 部分
3. 勾选 ✅ **Discussions**
4. 点击 "Set up discussions"

### 7. 配置 Discussion 分类

进入 Discussions → Categories → Manage categories

创建以下分类：

| 表情 | 名称 | 说明 | 格式 |
|------|------|------|------|
| 📣 | 公告 / Announcements | 官方公告和重要通知 | Announcement |
| 💬 | General | 一般讨论和闲聊 | Discussion |
| ⭐ | 订阅推荐 / Recommendations | 分享值得订阅的服务 | Discussion |
| 💰 | 价格讨论 / Price Discussions | 价格对比和优惠信息 | Discussion |
| 💡 | 使用技巧 / Tips & Tricks | 订阅管理技巧和省钱攻略 | Discussion |
| ❓ | 求助问答 / Q&A | 提问和解答 | Q&A |
| 🎁 | 优惠分享 / Deals & Promos | 分享优惠码和促销活动 | Discussion |

### 8. 发布第一个欢迎帖

在 Discussions 发布欢迎帖，例如：

```markdown
# 🎉 欢迎来到 WhereMyMoney 社区！

大家好！

这里是 WhereMyMoney 的官方社区，欢迎大家分享：
- 📝 订阅服务使用体验
- 💰 价格对比和优惠信息
- 💡 订阅管理技巧
- 🤝 互帮互助解决问题

让我们一起聪明管理订阅，省钱又高效！

---

Hello everyone!

This is the official WhereMyMoney community. Feel free to share:
- 📝 Subscription service experiences
- 💰 Price comparisons and deals
- 💡 Management tips
- 🤝 Help each other

Let's manage subscriptions smartly together!
```

## 📋 验证清单

部署完成后，确认以下内容：

- [ ] README 显示正常，链接可点击
- [ ] Issue 模板在创建 Issue 时可选择
- [ ] Discussions 已启用且分类设置完成
- [ ] GitHub Actions 工作流可以运行
- [ ] 所有文档链接正确
- [ ] 占位符已全部替换

## 🔗 集成到主应用

现在可以在反馈页面添加社区链接了！

**修改 `/app/feedback/page.tsx`**：

在 "其他联系方式" 部分添加：

```typescript
<a
  href="https://github.com/YOUR_USERNAME/subscription-manage-community/discussions"
  target="_blank"
  rel="noopener noreferrer"
  className="flex items-center gap-3 p-3 bg-gray-50 dark:bg-gray-800 rounded-lg hover:bg-gray-100 dark:hover:bg-gray-700 transition-colors"
>
  <GitBranch className="h-5 w-5 text-gray-700 dark:text-gray-300" />
  <div>
    <p className="text-sm font-medium">GitHub 社区</p>
    <p className="text-xs text-gray-500">加入讨论</p>
  </div>
</a>
```

## 🎯 下一步

1. **发起初始话题** - 创建 3-5 个有价值的讨论话题
2. **邀请用户** - 在应用中引导用户访问社区
3. **定期维护** - 及时回复问题，删除垃圾内容
4. **收集反馈** - 根据用户反馈优化社区结构

## 💡 运营建议

### 每周任务

- 📝 发起 2-3 个新话题
- 💬 回复用户问题
- 🔖 标记精华内容为 Pinned
- 🗑️ 清理垃圾内容

### 每月任务

- 📊 发布月度社区报告
- 🏆 表彰活跃贡献者
- 📢 分享热门话题总结
- 💡 收集功能建议

## 📞 需要帮助？

如有问题：
- 📧 发邮件: support@wheremymoney.pro
- 💬 在社区提问
- 📖 查看 GitHub Discussions 文档: https://docs.github.com/discussions

---

**祝你的社区越来越好！🎉**
