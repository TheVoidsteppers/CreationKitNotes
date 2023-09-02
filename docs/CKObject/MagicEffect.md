
# 如何制作一个法术效果

![[magicEffect.png]]

```shell
# ID: 唯一id

# Name: 该效果在“魔法菜单”的“活动效果”窗口中显示的名称(如果它有持续时间并影响玩家)

# Effect Archetype: 效果的一般类型，参照下表

# Casting Type: 施法类型:指定施法者如何触发效果。
#               - Concentration Effects 持续施法
#               - Fire and Forget 按住松开触发
#               - Constant Effects 恒定效果就像一种 ability，并且始终处于活动状态。这仅适用于护甲或能力
#               - 法术或附魔的所有效果必须具有相同的施法类型

# Delivery: 指定效果如何传递到目标
#               - Self:  效果应用于施法者。
#               - Contact: 通过接触(击中事件) 对目标施加效果。这仅适用于武器
#               - Aimed: 效果附加到发射物上，然后射向十字准星。如果它与有效目标接触，就会应用该效果。
#               - Target Actor: 效果立即应用于十字准线中的角色。没有发射物发射。请注意，第三人称视角下的目标是偏离的，因此很难远距离使用.
#               - Target Location: Effects is applied to the object/landscape under the crosshairs. No projectile is fired
#               - 法术或结界的所有效果必须具有相同的传递类型。

# Macic skil:  与效果相关的技能。该技能可以修改效果的力量、持续时间或成本，并会从中累积派系技能经验

# Minimum Skil level: 最低技能等级:仅用于 NPC，这是使用此效果所需的最低技等级。该值还控制法术在用户界面中显示的级别。如，值为 25 将在魔法界面中将使用此效果的法术显示为学徒。

# Assoc. Item 1: 关联项目 1: 此效果原型所需的第一个关联项目 (如果有)

# Assoc. Item 2: 关联项目 2: 此效果原型所需的第二个关联项目 (如果有)

# 2nd AV Weight: 第二个 Assoc 强度的幅度乘数。项自应与第一个 Assoc 进行比较。物品。与双值乘数原型一起使用

# Resist Value:  抗性值，适用于此效果的抗性类型。

# Perk to Apply: 要应用的辅助能力， 当且仅当目标是玩家时，指定的辅助能力会在效果激活时添加到目标.

# Base Cost: 基本消耗，效果的基本魔法或充能成本，用作公式输入，该公式根据技能、perk和任何其他适用因素计算最终成本。修改基本成本可能不会对自动计算法术的成本产生相应的变化

# Skil Usage Mult: 双手释放倍率，对于法术，施放此效果将给予玩家的技能使用乘数(其会促进效果的魔法技能，如上所述)

# Taper Duration: 效果持续的时间。
# Taper Weight: 锥度持续时间开始时的效果有多强。例如，值为 0.5 将使持续时间到期时效果减半
# Taper Curve:  控制锥度持续时间内效果幅度减小的速度。 (负值会导致影响幅度增加。) 注意，如果锥度曲线小于 -1，则该法术几乎总是致命的，因为总伤害无法收敛到有限值。

# Flags 标记
#               - Hostile: 敌对:此效果被视为攻击。加上才会产生敌对影响
#               - Detrimenta: 有害:此效果作为负值(伤害)应用于指定的 角色属性（Assoc Item 设置的） 请注意，并非所有有害的效果都需要勾选此项。上帝模式可防止“有害”效果对玩家起作用。
#               - Recover: 恢复:当此效果结束时，会使属性回复到之前的状态。如果选中， value Modifer 和 Peak Value Modifier 将会一开始修改角色的属性，然后在效果过期后回复到初始值；如果不勾选，角色属性将每秒修改一次，不会在效果结束时重置。注意，对于魔力和生命，其工作方式如下:如果选中，最大值和当前值都会改变(buff/debuff)。如果未选中，只会影响当前值(治疗/伤害)。
#               - FX Persist: 如果选中，则目标上的视觉效果在效果的整个持续时间内持续存在。否则，它只播放一次。
#               - Snap to Navmesh: 如果选中，瞄准或目标位置目标点将捕捉到导航网格上最近的点。用于召唤生物，以确保它们从有效位置开始.
#               - No Recast: 魔法效果一旦作用于目标，就无法再次对同一目标施放，直到效果消失或被驱散
#               - No Hit Effect: 击中到目标时，没有视觉效果
#               - No Death Dispel: 如果选中，即使目标死亡，效果仍然持续
#               - No Duration: 此效果是瞬时的。对于具有此效果的对象，“持续时间”字段不可用
#               - No Hit Event: 此效果是隐秘的;目标在被击中时不会记录击中事件。
#               - No Magnitude: 此效果不使用 Magnitude  字段。
#               - No Area: 此效果不使用 Area 字段。
#               - Painless: 如果选中并且该法术是敌对的，则该效果的目标不会痛苦地哭泣。如果目标是玩家，则防止击中模糊和哎哟声音
#               - Gory Visuals: 血腥视觉效果，未使用。
#               - Hide in Ul: 如果选中，效果不会在界面的魔法效果部分中向玩家显示，该效果的描述也不会显示在法术的串联法术效果描述中

# Keywords 与咒语相关的关键字列表。这些关键字不会直接应用于目标，但可以通过脚本检查或以其他方式使用。
#               - 复选框是“要么全有，要么全无”。如果目标上的任何其他法术效果的关键字与此列表中的关键字之一相匹配，它将被驱散。

# Counter Effects: 反作用，不曾用过。现在可以通过上述关键字系统取消法术.

# Target Conditions 目标条件: 
#               - 如果这些条件的值为True，则效果将应用于目标。经常与关键字一起使用，以从列表中排除特定类型的角色的效果。可以将条件放置在 magic effect 本身上，也可以放置在 spell。magic effect 会在应用效果时检查，并确定角色是否会受到该效果，而 spell 条件则决定了法术何时处于生效状态。在大多数情况下，瞬时法术只会在施法瞬间检查一次。然而，持续性法术相反:瞬时法术的条件只在当施法者开始施法时检查，如果，每秒施法一次，每秒会检查一次效果条件。这意味着，例如，如果你试图制作一个非集中效果，如果它已经存在则不会卡住，你可以将效果的条件写道条件窗口里。而持续性法术就会被取消，因为会发现自己

# Visual Effects: 视觉效果
#               - Menu Display Object: 菜单显示对象: 魔法菜单中法术的视觉效果
#               - Casting Art: 准备施法时手上的特效
#               - Casting Light:  正在施法时手上的特效
#               - Hit Effect Art: 命中特效
#               - Hit shader: 命中到目标时，目标身上的特效
#               - Enchant Art: 仅对附魔有效，附加到物品上的特效
#               - Enchant Shader: 仅对附魔有效，附加到物品上的 shader 着色器？
#               - Proiectile: 发射物
#               - Impact Data Set: 当命中目标时，产生的冲击特效
#               - Explosion: 当命中目标时，产生的爆炸特效
#               - Image Space Mod: 法术触发时所产生成的图像空间

# Dual Casting 双手施法

# Spellmaking
#               - Power Affects Magnitude/Duration: 力量影响幅度/持续时间，决定了在双手施法时法术效果的强度和持续时间是否会缩放，或者在制作药水或附魔时，是否会根据玩家的炼金术和附魔等级还有perk进行计算
#               - Area: 区域：如果法术效果有关联区域，需要在此处指示。面积的测量单位是英尺，而不是单位。
#               - Casting Time: 施法时间: 施法之前需要按住施法按的秒数。通常为0.5秒。对于施法时间较长且使用两只手的法术，建议使用关键字 RituaSpellEffect:此关键字会将施法动回画改为更合适的动画

# Script Effect Al Data 脚本效果AI数据
#               - Score: 分数: 决定 AI 使用此效果的几率。值越大越经常使用.
#               - Delay Time: 延迟时间: AI 再次使用此效果之前必须经过的时间

# Equip Ability 装备能力，当装备此效果时，施放到玩家身上的法术。不可链接 - 通过装备的能力不会添加到其已经分配的能力槽中

# Sounds 声音
#               - Draw/Sheathe: 当玩家装备或收起时发出的声音
#               - Charge: 充能，对于 Fire and Forget 的法术，第一次按下时发出的声音
#               - Ready: 就绪，对于 Fire and Forget 法术，当法术充能完毕时发出的声音
#               - Release: 释放，对于 Fire and Forget 法术，当玩家释放时发出的声音
#               - Cast Loop (Conc.): 循环施法（连续），对于 Concentration 法术，当按下鼠标时会持续释放此声音
#               - On Hit: 击中时，当击中目标时发出的声音
#               - Casting Sound Level: 施法噪声等级

# Magic Item Description 效果的描述。
#               - 在魔法菜单的活动效果列表中，当此效果影响玩家时
#               - 在任何使用该效果的Spell、Enchantment、Potion、Scroll 或 Shout 的描述中，除非该物品有自己的描述(覆盖任何继承的描述)
#               - 该文本支持占用符
#               - <mag>: 法术强度
#               - <dur>: 持续时间
#               - <area>: 区域
#               - <TEXT]>： 加粗并放大 <> 中的文本

# Papyrus Scripts 脚本，应用于 MagicEffect 或由 MagicEffect 应用的任何 Papyrus 脚本。这些通常扩展 ActiveMagicEffect Script

# 注意
#               - No Magnitude, No Area 还有 No Duration 实际上不影响法术效果的执行，只是在 spell、scroll、potion、shout、或 Enchantment 时，这些对应的参数不能选
#               - Area 必须大于 0 才会有爆炸效果
```

### Effect Archetype

> 效果原型本质上是基于代码的效果，可以由  MagicEffect 触发。除了 MagicEffect 上的  Papyrus Scripts 可能产生任何脚本化效果之外，还会出现这些效果

| 原型 | 关联项目 | 描述 | 
| --- | --- | --- |
| Absorb 吸收 | 1、吸取的角色的属性值，通常是生命值、魔法值、或耐力值 | 对目标属性造成最多 `<mag>` 点伤害，并根据造成的伤害恢复施法者对应的属性。如果没勾选 detrimental，则会消耗施法者来补充目标 |
| Accum Magnitude 结界术 | | 授予目标最多 `<mag>` 值，但从0开始随时间的推移增加 |
| Banish 驱逐 | | 将最高`<mag>` 等级的召唤的生物驱逐 |
| Bound Weapon 召唤武器 | 要创造的武器 | 创建指定的武器，并在持续时间结束或者收鞘时驱散 |
| Calm 平静术 | | 将 `<Mag>` 级别的目标攻击性降到最低 |
| Cloak 斗篷术 | 1、代表斗篷伤害的法术，必须是 Concentration/Aimed 或 Concentration/Target | 当该法术激活时，会对区域内的所有目标释放法术效果。 注意：斗篷效果的伤害不是由 `<mag>` （由其1: 法术决定），而是斗篷攻击目标的半径 |
| Command Summoned 获取召唤生物控制权 | | 控制最高等级为`<MAG>`的召唤角色 |
| Concussion 昏迷 | | 未使用过 |
| Cure Addiction 治愈成瘾 | | 未使用过 |
| Cure Disease 治愈疾病 | | 消除目标所有疾病效果 |
| Cure Paralysis 治愈麻痹 | | 消除目标麻痹状态 |
| Cure Posion 去除药水负面效果-解毒 | | 消除目标所有中毒效果 |
| Demoralize 恐惧术 | | 使 `<MAG>` 级别的敌人溃逃。在战斗开始前没有效果 |
| Detect Life 侦察生命 | | 对范围内的所有有效目标应用视觉效果。fire-and-forget 瞬时效果；concentration effect 是持续效果 |
| Disarm 缴械 | | 缴械最高`<MAG>`等级的目标 |
| Disguise 伪装 | ??? |  ???未使用过 |
| Dispel 抵消 | | 在一段时间内移除目标的魔法效果。`<MAG>` 似乎未使用。未使用过  |
| Dual Value Modifier 提供两个Assoc Item |  |  修改两个角色属性值。第一个值由 `<MAG>` 修改，第二个值由 `<MAG>` ` x AV Weight修改 |
| Enhance weapon 强化武器 | | 任何装备的(近战)武器都会受到指定的附魔，直到收鞘或效果消失为止。用于元素之怒 |
| Etherealize 虚化 | | 使目标虚化，防止他们造成伤害或受到伤害。 |
| Frenzy  愤怒术 |  |  影响最大`<MAG>`级别目标 |
| Grab Actor 抓取角色 | | 可以拾起并扔出选中的NPC。由吸血鬼之握使用，不会影响龙，猛犸，龙祭司，骷髅法师，骷髅射手，诺德怒灵和骷髅，保持目标的距离基于施法者的 GrabActorOffset actor 值。 |
| Guide 洞察术 | | 创建从施法者到最近的任务目标的一系列危险物体。用于洞察术。步道并没有延伸很远，需要不断刷新才能使用。 |
| Invisibilty 隐形 | |  使目标变得隐形。当隐形被打破时，该效果会自动消除。请注意，隐形并不意味着听不见，任何不静音的魔法效果实际上都会持续发出噪音，直到有安静施法的 perk 为止。 |
| Light 创建一个光源 | 1: 要创建的灯光对象. | 创建指定的灯光对象。请注意，必须选择 Hit Effect Art ，并且光将从特定节点发出? |
| Lock 上锁 | | 上锁目标。注意:实际上不可能瞄准对象，这使得这个原型或多或少毫无用处。唯一可以针对对象的效果是脚本 |
| Open 开锁 | | 解锁目标。注意:实际上不可能瞄准对象，这使得这个原型或多或少毫无用处。唯一可以针对对象的效果是脚本 |
| Paralysis 麻痹 | | 使目标麻痹，应该添加 ImmuneParalysis keyword，并设置 Recover 时才有效，这还会将 Actor 值的 Paralyze 设置为 1 以防止移动 |
| Peak Value Modifier 提供两个Assoc Item | 1、要修改的值 2、keyword No Recast  | 如果同时存在两个具有相同关键字的 PVM，`<mag>` 较低的 PVM 会自动被驱散吗? |
| Rally 勇气术 | | 影响最高 `<MAG>` 级别角色 |
| Reanimate 复活尸体 | | 如果目标死亡，则将其复活，并将其置于施法者的控制之下 |
| Script 脚本 | | 除指定的任何 Papyrus 脚本外没有任何效果 |
| Slow Time 时缓术 | | 使除玩家之外的所有人的时间减慢指定的量(乘数，1 为正常时间) |
| Soul Trap 灵魂陷阱 | | 如果目标在该效果生效时间内死亡，则会填充施法者携带的灵魂石 |
| Spawn Hazard 创建一个 Hazard 对象 | 1: 产生的炮台 | 在目标处创建指定的炮台，炮台由施法者拥有(意味着它只会击中敌人)，并且法术会随着生成法术的强度而变化。如果您希望炮台击中盟友，则需要一个脚本来 PlaceAtMe 炮台，该对象不保留所有权(但也不允许缩放)。请注意，constant effect 每次激活时只会产生一种炮台 |
| Spawn Scripted Ref 生成脚本参考 | 1:未使用 | 用于投掷语音。您无法直接选择参考，但“投掷语音”包含一个爆炸，其中放置了一个能说出某些内容的激活器对象 |
| Stagger 蹒跚 | | 使目标蹒跚。值介于 0 和 1 之间。时间影响效果的CD。不应该勾选 detrimental  |
| Summon Creature 召唤生物 | 1.要召唤的生物 | 召唤指定的生物，将其置于施法者的控制之下。死亡后，该生物会自动消失并且不会留下尸体。 |
| Telekinesis 念动力 | | 将念动力应用于目标物体，允许施法者在一定距离外操纵它，这还将 Actor 值 Telekinesis 设置为 1，以便您可以在远处查看项目统计信息。 |
| Turn Undead 驱逐亡灵 | | 导致目标逃离施法者，类似于恐惧术。在战斗开始前没有效果。要求目标具有 ActorTypeUndead 关键字才能发挥作用；即使效果的条件允许，没有该关键字的目标也不会受到影响 |
| Value and Parts 提供一个Assoc Item | 1 ??? |  ??? |
| Value Modifier 提供一个Assoc Item | 1.要修改的值 | 通过 `<MAG>` 修改 Actor 值 |
| Vampire Lord  | | |
| Werewolf 转为狼人 | |  改变目标种族为狼人 |
| Werewolf Feed 狼人饲料 | | 标记狼人啃食过??? |

```c
# the Effect ltem Form 包括
# Casting Type 和 Delivery 由父对象的设置决定。这些限制了你可以选择的魔法效果类型,
# Effect: 效果: 效果物品的魔法效果。
# Magnitude: 幅度: 生效时，法术强度
# Area: 面积，生效时，效果的半径，英寸为单位
# Duration: 持续时间: 生效时，效果的持续时间。持续时间永远不会应用于  Constant Effects
#    - 根据这些值和Magic Effect的属性，将自动计算本节中的其他值
# Conditions: 条件:只有满足这些条件，该效果才会发挥作用。请注意，过多的条件可能会导致性能问题,
```

### 注意

```c
# 通常在游戏的每一秒都会检查条件，但是， concentraton 法术只会在第一次施法时检查
#   另外，考虑两个斗篷效果都触发相同的 concentration 法术的情况。如果角色不间断地切换斗篷，则  concentration 法术只会检查其条件一次（在第一个斗篷开始时）。所以，你不能通过在两个相同的斗篷之间交替使用相同的 concentration 法术来强制(或伪造)重新检查状态。
#   然而，似乎 concentration 的法术效果每秒钟都会被单独重新应用，至少当 concentration 法术由斗篷效果触发时是这样。在这种情况下，条件有效地向后工作:魔法效果条件每秒运行一次，而法术条件在施法开始时运行
#       请注意，虽然效果每秒钟都被重新应用，但它们的 shaders （着色器）不是。仍然需要勾选 FX Persist。
# 在所有条件检查完之前，不会生效。如果魔法效果的条件返回false。该效果将不会被停用，直到来自相同的法术的其他效果已被检查。
# 考虑一个法术，它的第一个魔法效果通过“应用perk”的方式对目标施加一个perk，它的第二个魔法效果测试该perk。当检查条件时，如果第一个魔法效果的条件失败，它将排队等待停用，然后继续检查下一个魔法效果，直到所有的法术效果检查完，才会停用之前失败的法术
```



