# 数据结构
创建一个长度为 kk 的数组充当循环队列，使用两个变量 he 和 ta 来充当队列头和队列尾（起始均为 00），整个过程 he 始终指向队列头部，ta 始终指向队列尾部的下一位置（待插入元素位置）。

两变量始终自增，通过与 kk 取模来确定实际位置。

分析各类操作的基本逻辑：

isEmpty 操作：当 he 和 ta 相等，队列存入元素和取出元素的次数相同，此时队列为空；
isFull 操作：ta - he 即队列元素个数，当元素个数为 kk 个时，队列已满；
enQueue 操作：若队列已满，返回 -1−1，否则在 nums[ta % k] 位置存入目标值，并将 ta 指针后移；
deQueue 操作：若队列为空，返回 -1−1，否则将 he 指针后移，含义为弹出队列头部元素；
Front 操作：若队列为空，返回 -1−1，否则返回 nums[he % k] 队头元素；
Rear 操作：若队列为空，返回 -1−1，否则返回 nums[(ta - 1) % k] 队尾元素；