
# ObjectReference 相关

## 可调用函数


### SendStealAlarm

```c
 SendStealAlarm(Actor akThief)
 # Syntax
 Function SendStealAlarm(Actor akThief)
 
 # Parameters
 # akThief: 将表演“盗窃”的角色
 
 # Return Value
 # None.
 
 # Examples
 # 玩家刚刚试图偷窃百万美元
 MillionDollars.SendStealAlarm(Game.GetPlayer())
```

- 发送盗窃警报，如同该 reference 刚刚被这个角色偷窃了
- 是否这个对象的行为就像试图偷走

### PushActorAway

```c
PushActorAway(Actor akActorToPush, Int aiKnockbackDamage)

# Syntax
Function PushActorAway(Actor akActorToPush, float afKnockbackForce) native

# Parameters
# akActorToPush: 要推开的角色
# afKnockbackForce: 施加到目标角色的力的大小

# Return Value
# None.

# Examples
ExplosionMarker.PushActorAway(Bill, 10.0)

# notes
# 使用 XMarkerHeading 对象来控制 actor 被推动的确切方向.
# Force 参数可以为负，以将角色拉向你的的 ObjectReference
# 推动是通过爆炸施加的，因此受到 fMagicExplosion 游戏设置的影响
```

- 用指定大小的力量将指定角色推离该对象

### PlayAnimation 

开始在对象上播放指定的动画并立即返回。(在内部，它将指定的事件发送到对象的动画图)如果成功，则返回 true.

```c
# Syntax
bool Function playAnimation(string asAnimation) native

# Parameters
# asAnimation: 要播放的动画

# Return Value
# 如果动画成功开始播放则为 true。

# Examples
# 在开关播放切换动画
Switch.PlayAnimation("flip")

# notes
无法对角色使用。对于角色，请使用 SendAnimationEvent，这会绕过对 ObjectReference 的检查,从而阻止向参与者发送事件，如果你使用它向角色发送事件，可能会导致角色卡动画，你可以使用 PlayIdle(IdleStop_Loose)取消卡住
```

### PlayAnimationAndWait 

在对象上播放指定动画，并在指定事件发送时返回，如果成功，返回 true

```c
# Syntax
bool Function PlayAnimationAndWait(string asAnimation, string asEventname) native

# Parameters
# asAnimation: 要播放的动画
# asEventname 要等待的事件的名称，如果事件名不存在，则函数永远不会返回

# Return Value
# 如果动画成功播放则为 true。

# Examples
if Switch.PlayAnimationAndWait("flip", "done")
	Debug.Trace("Flip animation finished playing")
else
	Debug.Trace("Flip animation failed to play or unloaded while playing .")
endIf
```



























