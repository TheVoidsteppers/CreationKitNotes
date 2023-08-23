# Quest 相关

## 可调用函数

```c
Event OnStoryAddToPlayer(ObjectReference akOwner, ObjectReference akContainer, Location akLocation, Form akItemBase, int aiAcquireType)

# Parameters
# akOwner: 拥有该对象的 ObjectReference
# akContainer:包含对象的 ObjectReference
# akLocation: 事件发生的位置
# akItemBase: 添加到玩家库存中的物品的基础对象
# aiAcquireType: 执行的获取类型。将是以下之一!
#  0:  None 无
#  1:  Steal 偷窃
#  2: Buy 购买
#  3: Pick-pocket 扒窃
#  4: Pick up 拿起
#  5: Container 容器
#  6: Dead body 尸体

# Return Value
# None.

# Examples
# 玩家刚刚试图偷窃百万美元
Event OnStoryAddToPlayer(ObjectReference akOwner, ObjectReference akContainer, Location akLocation, Form akItemBase, int aiAcquireType)
	# Dead body
	if aiAcquireType == 6
		Debug.Trace(The player just looted a  + akItemBase + from a dead body")
	endIf
endEvent
```