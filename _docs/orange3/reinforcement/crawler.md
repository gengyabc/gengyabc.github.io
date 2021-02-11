---
title: 爬行者(Crawler)
---

使用强化学习训练一个爬行者机器人




## 功能
[强化学习](https://en.wikipedia.org/wiki/Reinforcement_learning)是机器学习中的一个领域，强调如何基于环境而行动，以取得最大化的预期利益。在这个小部件中, 我们使用强化学习方法训练一个爬行者机器人


## 界面

![](/assets/images/reinforcement/crawler.png.webp)

* 点击运行即可开始, 显示爬行者游戏界面

![](/assets/images/reinforcement/crawler_stamped.png.webp)

1. 设置爬行者机器人的运行速度
2. 设置折扣系数. 折扣导致回报随着时间的流逝而指数降低.
3.  $\varepsilon$ 贪婪（$\varepsilon$-greedy）系数. 给爬行者想要找到更好的爬行方法的“贪婪性”做一个量化：$\varepsilon$。每次行动都有 $\varepsilon$ 的可能性随机行动，而 1-$\varepsilon$ 的可能性遵循现在的策略行动。这个方法就是 $\varepsilon$ 贪婪（$\varepsilon$-greedy）
4.  学习率. 当前学习成果和历史经验的相比有多重要, 学习率越大, 当前学习成果的权重越大.
5.  爬行者机器人的状态显示
       * `Step`: 计算迭代次数
       * `Positon`: 当前位置
       * `Velocity`: 爬行速度
       * `100-step Avg Velocity`: 100次迭代计算的平均爬行速度
       * 注: 如果比赛训练成果, 可以比较爬行者第一次到达最右侧时候的 `100-step Avg Velocity`