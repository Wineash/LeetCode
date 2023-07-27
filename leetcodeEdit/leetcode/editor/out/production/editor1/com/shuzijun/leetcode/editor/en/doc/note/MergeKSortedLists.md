### 最初想法（暴力）  时间：n方  空间：1
1. 判断输入的临界条件：链表数组为空。
2. 声明结果res链表和最小节点
3. 在循环中遍历数组，每次遍历初始化两个flag用于记录是否为第一次for循环（以便给空的最小节点赋值）和所有队列已经为空。
4. 遍历数组每个队列的首个元素，并获取最大的节点位置。
5. 第二次遍历，将这个节点位置赋给结果res链表，且节点前进。

易错点：java的链表数组中，用for each声明的节点前进，并不会使lists中的list前进。要用for i和数组下标来进行节点前进才可以。

### 更有的解决方法 优先级队列（堆排序） 时间：O(Nlogk) 空间：n
1. 声明一个最小堆，堆元素为listNode
2. 将k个链表头节点放入堆中（不是k个链表的所有元素，因为链表本身升序，所以头节点最小即为全部节点最小）
3. 只要堆不为空，就依次执行：最小节点出堆，赋给res，将最小节点的下一个节点（不为空）入堆。
4. k个链表全部为空则结束