### Cast

从指定的 object reference 施放该法术，也可以选择向目标 object reference 施放该法术。

```c
# Syntax
Function Cast(ObjectReference akSource, ObjectReference akTarget = None) native

# Parameters
# akSource: 从中施放咒语的ObjectReference ，来源必须能够施放此法术测试似乎表明任何东西都会起作用，无论他们是否拥有该法术)
# akTarget: 一个可选的对象参考，用于瞄准咒语。如果没有传递任何内容并且法术需要方向，它将瞄准默认方向。

# Return Value
# None.

# Examples
# myActivator 已对玩家释放法术
mySpell.cast(myActivator, playerRef)

# notes
# 法术会立即释放，不会有施法动作
# 任意角色都能调用此功能，也适用于物体，包括岩石
# 
```

