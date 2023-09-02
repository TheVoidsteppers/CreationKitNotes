# 如何制作一个附魔

![[enchantment.png]]


ID: 唯一ID

Name: 附魔名称

Type: 附魔类型，标准附魔(武器、盔甲)，还是法杖附魔

Casting: 护甲必须是  Constant Effect ，武器和法杖可以是  Concentration 或 Fire and Forget

Delivery: 传递方式，盔甲只能是 self ，武器只能是 Contact， 法杖只能是 Aimed

Base Enchantment: 分解后学到的附魔，如果是None，则默认此附魔

Worn Restriction: 关键词限制，当附魔时，只有有此关键词的物品才可以附魔

Extend Duration on Recast: 勾选时，如果重新附魔，会重置持续事件，未勾选则在重新附魔时添加新效果

Effect List: 附魔效果列表

Auto Calculate： 是否自动计算价格和费用成本





