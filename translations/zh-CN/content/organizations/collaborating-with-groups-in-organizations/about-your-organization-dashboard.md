---
title: 关于组织仪表板
intro: 作为组织成员，您可以全天访问组织仪表板，以了解近期活动的最新信息，跟踪您参与的议题和拉取请求，或者关注组织。
redirect_from:
  - /articles/about-your-organization-dashboard
  - /github/setting-up-and-managing-organizations-and-teams/about-your-organization-dashboard
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - Organizations
  - Teams
shortTitle: 组织仪表板
---

## 访问组织仪表板

{% data reusables.dashboard.access-org-dashboard %}

## 查找近期活动

在消息馈送的“Recent activity（最近活动）”部分，您可以快速找到并跟进组织中最近更新的议题和拉取请求。

{% data reusables.dashboard.recent-activity-qualifying-events %}

## 查找组织中的仓库

在仪表板的左侧栏中，可以访问您参与的组织顶部仓库。

![组织中您参与最多的仓库列表](/assets/images/help/dashboard/repositories-from-organization-dashboard.png)

## 了解组织中活动的最新信息

在消息馈送的“All activity（所有活动）”部分，您可以查看来自组织中其他团队和仓库的更新。

“All activity（所有活动）”部分显示组织中所有最近的活动，包括您未订阅的仓库中以及您未关注的人员的活动。 For more information, see "[About notifications](/github/managing-subscriptions-and-notifications-on-github/about-notifications)" and "[Following people](/articles/following-people)."

例如，当组织中有人执行以下操作时，组织消息馈送会显示更新：
 - 创建新分支。
 - 评论议题或拉取请求。
 - 提交拉取请求审查评论。
 - 对仓库复刻。
 - 创建 wiki 页面。
 - 推送提交。{% ifversion fpt or ghes or ghec %}
 - 创建公共仓库。{% endif %}

## 更多信息

- "[关于个人仪表板](/articles/about-your-personal-dashboard)"
