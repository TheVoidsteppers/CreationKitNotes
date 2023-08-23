
# 如何制作一个爆炸效果

![[explosion.png]]

- ID: 唯一标识符
- Name: 名称
- Force: 爆炸的推力
- Damage: 伤害: 站在爆炸半径内可能受到的伤害量
- Radius: 半径，这是爆炸影响区域的半径; 该半径内的任何刚体都会被推动，并且其内的任何 reference 都可能被损坏。
- IS Radius: IS 半径, 能看到的贴图效果的区域的半径
- Vertical Offset Mult: 垂直偏移倍数， 爆炸从其放置的原点垂直偏移的单位数值
- Chain: 连锁，用于连锁闪电，如果选中，则您可以从下拉列表中选择要在弹跳”时生成的射弹，它必须与最初引发爆炸的射弹类型（光束、导弹等)相匹配
- Alwavs Uses World Orientation: 爆炸是否与地面对齐
- lgnore LOS check: 忽略LOS 检查，设置爆炸以忽略对目标的现场检查。如果选中，爆炸将忽略固体覆盖物，例如墙壁和静态物体
- Push Explosion Source Ref 0nly: 仅推动爆炸源参考， 选择此选项可使爆炸力仅影响对象本身。用于销毁数据。
- lgnore lmagespace Swap: 忽略图像空间交换: 覆盖近距离爆炸优化
- No Controller Vibration: 无控制器振动，爆炸不会导致控制器振动
- Art File: 特效文件
- Light: 灯光， 爆炸使用的灯光的编辑器 ID。目前不支持
- Enchantment: 结界，应用于爆炸的魔法咒语。
- Sound 1: 爆炸时播放的音效。
- Sound 2: 爆炸时播放的第二个音效
- Is Mod: 爆炸发生时播放的图像空间修改器。
- Impact Data Set: 设置爆炸向外辐射时对不同材料的效果
- Sound Level: 噪音等级
- Placed Obiect: 放置物体，将物体放置在爆炸位置
- Spawn Projectile: 生成射弹，与 Chain 复选框一起使用，它必须与最初产生爆炸的射弹类型 (光束、导弹等) 相匹配。
- Knock Down living Actors: 击倒未死亡的角色，如果选中，爆炸会击角色，但不一定会杀死他们。如果不选中，未死亡的角色将保持站立状态。
- 