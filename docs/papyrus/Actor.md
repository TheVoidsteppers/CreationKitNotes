
# 角色相关

## 可调用函数


### ApplyHavokImpulse

```c
ApplyHavokImpulse(Float afX, Float afY, Float afZ, Float afMagnitude)
```

- 向该对象施加 Havok 冲力。可移动物品，非NPC

### SetScale

```c
SetScale(Float afScale)
```

- 设置对象的缩放比例

### SplineTranslateTo

```c
SplineTranslateTo(Float afX, Float afY, Float afZ, Float afAngleX, Float afAngleY, Float afAngleZ, Float afSplineCurve, Float afSpeed)
```

- 使对象平移到样条曲线指定的位置/方向。

### SplineTranslateToRef

```c
SplineTranslateToRef(ObiectReference arTarget, Float afTangentMagnitude, Float afSpeed, Float afMaxRotationSpeed)
```

- 使对象以给定速度移动到样条曲线上指定的位置/方向

### SplineTranslateToRefNode

```c
SplineTranslateToRefNode(ObiectReference arTarget, String arNodeName, Float afTangentMagnitude, Float afSpeed, Float afMaxRotationSpeed)
```

- 使对象以给定速度转换为样条曲线上指定的的位置/方向

### StopTranslation

```c
StopTranslation()
```

- 停止对象的任何移动

### TetherToHorse

```c
TetherToHorse(ObjectReference akHorse)
```

- 将一辆囚犯拴在指定的马车上

### TranslateTo

```c
TranslateTo(Float afX, Float afY, Float afZ, Float afAngleX, Float afAngleY, Float afAngleZ, Float afSpeed, Float afMaxRotationSpeed)
```

- 使对象移动到指定的位置/方向.

### TranslateToRef

```c
TranslateToRef(ObjectReference arTarget, Float afSpeed, Float afMaxRotationSpeed)
```

- 使对象以给定速度移动到指定位置/方向

### WaitForAnimationEvent

```c
Bool WaitForAnimationEvent(String asEventName)
```

- 等待动画发送指定的事件。

### OpenInventory

```c
# 打开该角色的仓库，就好像你正在扒窃他们一样
OpenInventory(Bool abForceOpen)
```

### SetUnacious

```c
# 将角色设置为无意识 。。。似乎无效
SetUnacious(Bool ablsUnacious)
SetUnconscious(Bool ablsUnconscious)

 # Syntax
 Function SetUnconscious(bool abUnconscious = true) native
 
 # Parameters
 # abUnconscious: 是否设置或清除无意识状态
 
 # Return Value
 # None.
 
 # Examples
 # Stony 失去知觉
 Stony.SetUnconscious()
```

### UnequipAll

```c
# 取消装备该角色的所有物品
```

### UnequipItem

```c
# 取消装备该角色的一件物品
UnequipItem(Form akItem, Bool abPreventEquip, Bool abSilent)
```

### UnequipItemSlot

```c
# 强制取消该角色给定插槽上的所有护甲
UnequipItemSlot(Int aiSlot)
```

### UnequipShout

```c
# 取消该角色装备的指定吼声
UnequipShout(Shout akShout)
```

### UnequipSpell

```c
# 取消装备该角色的指定来源的指定法术.
UnequipSpell(Spell akSpell, Int aiSource)
```

### SheatheWeapon

```c
# 角色的武器收起
```

### DrawWeapon

```c
# 强迫角色拔出武器
```
### EnableAI

```c
# 启用或禁用该角色的AI
```

### Int GetGoldAmount

```c
# 获取该角色身上拥有的金币数量.
```

### Resurrect()

```c
# 复活.
```
### SendAssaultAlarm()

```c
# 发送攻击警报
```

### SendTrespassAlarm(Actor akCriminal)

```c
# 发送入侵警报.
```
### SetActorValue(String asValueName, Float afValue)


```c
# 更改角色属性值.
```
### SetAlert(Bool abAlerted)

```c
# 将参与者标记/清除当前已收到警报.
```

### StartSneaking()

```c
# 强迫改角色进入潜行状态.
```

### StopCombat()

```c
# 停止战斗.
```

### StopCombatAlarm()

```c
# 停止该角色的所有的战斗和警报.
```









