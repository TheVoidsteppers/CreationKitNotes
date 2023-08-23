
# 脚本事件

### SendStoryEvent - Keyword

通过脚本命令 SendStoryEvent 创建事件

```c
# Syntax
Function SendStoryEyent(Location akLoc = None, ObjectReference akRef1 = None, ObjectReference akRef2 = None, int aiValue1 = 0, int aiValue2 = 0) native

# Parameters
# akLoc: 随事件一起发送的位置
# akRef1: 随事件发送的第一个 ObjectReference
# akRef2: 随事件发送的第二个 ObjectReference
# aiValue1: 随事件发送的第一个值
# aiValue2: 随事件发送的第二个值

# Return Value
# None.

# Examples
# 发送不若额外数据的事件
QuestEventProperty.SendStoryEvent()
# 仅发送具有单个值 QuestEventProperty 的事件
QuestEventProperty.SendStoryEvent(aivaluel = 5)

# note
# 如果将 aiValue1 或 aiValue2 发送为负值，则 OnStoryScript 事件接受时会当作 0
```

### Player Remove Item

每当玩家从库存中移除物品时就会触发事件

- ItemRef: 物品的 ObjectReference
- OwnerRef:  拥有该物品的角色
- Location: 事件触发的位置
- ObjectForm:   所取物品的基础对象
- RemoveType: 拿取类型
	- 0  REMOVE_TYPE_NONE  无
	- 1  REMOVE_TYPE_STOLEN 偷窃
	- 2  REMOVE_TYPE_CONSUMED 消耗
	- 3  REMOVE_TYPE_SCRIPT 脚本
	- 4  REMOVE_TYPE_DROPPED 丢弃
	- 5  REMOVE_TYPE_GIVEN 送礼
	- 6  REMOVE_TYPE_PUT_IN_CONTAINER 放入容器
	- 7  REMOVE_TYPE_COUNT


