
# Debug 提供的方法

```c
# 消息弹窗
MessageBox(String asMessageBoxText)

# 左上角消息通知
Notification(String asNotificationText)

```

### SendAnimationEvent

直接将动画事件发送给对象

```c
SendAnimationEvent(ObjectReference arRef, String asEventName)

# Syntax
Function SendAnimationEvent(ObjectReference arRef, string asEventName) native global

# Parameters
# arRef: 发送的对象
# asEventName: 要发送的事件

# Return Value
# None.

# Examples
# 将跳舞事件发送给吟游诗人
Debug.SendAnimationEvent(BardRef, "Dance")

# notes
# 这会绕过对 ObjectReference 的检查，从而阻止向参与者发送事件，如果你使用它向 Actor 发送事件，你可能会永久地弄乱角色，因为内部角色数据可能不再匹配其动画状态
# SendAnimationEvent 使用的是 "Anim Events"，而不是 ID 。例如要让角色播放向左攻击的动画，应该使用的是 "AttackStartLeftHand" 而不是 "LeftHandAttack" （它的ID）
# 动画事件实际上会导致角色执行与之相关的动作，比如发送动画事件 "AttackStar" 将引导执行攻击，任何在它面前的东西都会受到伤害。此示例适用所有动画事件，例如发送 "DeathAnim" 将会杀死角色
```




























