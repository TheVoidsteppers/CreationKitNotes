
# 动画相关

## 播放动画

```c
Bool PlayAnimation(String asAnimation)
# - 在此对象上播放指定的动画，并立即返回。
Bool PlayAnimationAndWait(String asAnimation, String asEventName)
# - 在此对象上播放指定的动画并在返回之前等待指定的事件。 (latent 隐性的)
Bool PlayGamebryoAnimation(String asAnimation, Bool abStartOver, Float afEaselnTime)
# - 播放基于旧版 nif 文件的动画
Bool PlayImpactEfect(ImpactDataset akImpactEfect, Strinc asNodeName, Float afPickDirX, Float afPickDirY, Float afPickDirZ, Float afPicklength, Bool abApplyNodeRotation, Bool abUseNodeLocalRotation)
# - 起到冲击效果
Bool PlaySyncedAnimationAndWaitSS(String asAnimation1, String asEvent1, ObjectReference akObj2, String asAnimation2, String asEvent2)
# - 同时播放两个动画，并等待两个动画的事件。
Bool PlaySyncedAnimationSS(String asAnimation1, ObjectReference akObj2, String asAnimation2)
# - Plays two animations simultaneously.
PlayTerrainEffect(String asEffectModelName, String asAttachBoneName)
# - Plays a terrain effect.

```

## 动画名称

