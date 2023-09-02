# 如何制作一个 NPC


![[npc.png]]


ID：在CK中的id名

name：名字

short name：小名（举个例子，持剑淑女朱迪斯就是name，朱迪斯就是short name）

Essential：像小孩一样无法被杀死
Protected：需要玩家补刀才能杀死
Essential和Protected只能二选一！！
Respawn：会在场景刷新时一起重生。默认为24天。一般用于敌人
Unique：独一无二的！如果你想你的他她它成为路人甲乙丙丁你可以不勾。。。
Summonable ： 是否可以通过法术召唤
Is Ghost：无敌，武器穿透他们没有任何效果（包括硬直），也不会触发攻击事件
Invulnerable：无敌，但武器会有攻击到他们的效果
Doesn't Bleed：被武器击中时，不会有溅血效果。
Simple Actor：该NPC没有任何表情，死亡或者受攻击也不会触发相应的事件
Doesn't affect Stealth Meter：当该NPC侦测到玩家时，不会影响你的隐匿状态，通常用于无害中立生物，狐狸 兔子 ，鹿等等

### Traits

Race：种族
height：高
weight：体重

### Stats

Level Mult：等级关联倍率
Pc LevelMult：是否和玩家等级关联
Calc Min：计算最小等级
Calc Max：计算最大等级

右边：是根据class结合等级计算出的，是固定死的，只能看无法修改，要改去游戏里控制台改
左边：三个属性分别是血，魔法，体力。每个属性有三个框，第一个是你自定的属性，第二个是固定死的，第三个就是第一加第二的最终结果

### Factions

CurrentFollowerFaction//当前跟随——必选：初值定为0
PotentialFollowerFaction//隐性跟随——必选：初值定为0
PlayerFaction
PotentialMarriageFaction//结婚
//这几个都是管家系的
TownWhiterunFaction
HousecarlWhiterunCrimeFaction
PlayerHousecarlFaction

### AI Data

Aggression：侵略性（建议设置为Aggressive）
Unaggressive：该NPC不会主动开始战斗
Aggressive：该NPC会主动攻击视野内的所有敌人
Very Aggressive 该NPC会主动攻击视野内的所有中立和敌对NPC 
Frenzied 该NPC会主动攻击视野内的所有人

Confidence：自信（建议设置为FoolHardy，）
Cowardly：懦夫 该NPC任何情况下都不会交战/逃跑
Cautious：谨慎 不会交战/逃跑除非该NPC强于对手
Average ：不敌时会逃跑
Brave：完全不敌时会逃跑
Foolhardy ：决不逃跑

Assistance：援助
Help Nobody 不帮助任何人
Help Allies：帮助盟友
Help Friends and Allies 帮助朋友和盟友

Morality：道德观（Any Crime）
Any Crime：该NPC愿意犯任何罪行
Violence Against Enemies：愿意对敌对NPC进行任何Crime
Property Crime Only ：只愿意进行财产Crime（盗窃，非法入侵）等，极少使用
No Crime：该NPC拒绝任何Crime

Combat Style：战斗风格



### AI Package


### Inventory

Default Outfit：默认套装有很多预设（穿了之后这就是默认外衣，每次被剥光后系统会自动刷出这套衣服给她）
Inventory：装备（初始身上的装备）

### SpellList

