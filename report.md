##Report


####实现基本的驾驶智能体

*问题: 在你的报告中，说明观察到的智能体的行为。它最终到达目标位置了吗？有什么其他值得注意的地方吗？*

Answer: 由于智能体的行为是随机的，运气好的话，它是可以到达目标位置的，但是到达目标位置时一般都超过了deadline。如果deadline = -100时智能体还没有到达目标位置的话，就会尝试失败。

####Inform the Driving Agent

*QUESTION: What states have you identified that are appropriate for modeling the smartcab and environment? Why do you believe each of these states to be appropriate for this problem?*

Answer: 

1. next_waypoint（下一路径点的位置）
2. light（信号灯的状态）

next_waypoint是根据目标位置得到的，用于指示前进方向。

light是为了不违反交通规则，不发生撞车事故。

至于input中的 三个路口车的方向，经过测试，如果添加，Q表格将会变得比较大，训练100次也不能保证reward为正，因此只使用了next_waypoint和light。

*OPTIONAL: How many states in total exist for the smartcab in this environment? Does this number seem reasonable given that the goal of Q-Learning is to learn and make informed decisions about each state? Why or why not?*

Answer: 在这个环境中一共有6个状态，对于Q学习来说是合理的。

####Implement a Q-Learning Driving Agent

*QUESTION: What changes do you notice in the agent's behavior when compared to the basic driving agent when random actions were always taken? Why is this behavior occurring?*

Answer:

####Improve the Q-Learning Driving Agent

*QUESTION: Report the different values for the parameters tuned in your basic implementation of Q-Learning. For which set of parameters does the agent perform best? How well does the final driving agent perform?*

Answer:

*QUESTION: Does your agent get close to finding an optimal policy, i.e. reach the destination in the minimum possible time, and not incur any penalties? How would you describe an optimal policy for this problem?*

Answer: 在程序中的智能体依据优化，已经可以以最短路径到达目的地，并且能够保证在到达母队时得分为正，但是不能