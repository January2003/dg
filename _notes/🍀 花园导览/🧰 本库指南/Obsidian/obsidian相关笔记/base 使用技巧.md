---
created: '2025-06-27'
cssclasses: ''
modified: '2025-07-28'
permalink: /🍀 花园导览/🧰 本库指南/Obsidian/obsidian相关笔记/base 使用技巧.md
publish: true
title: base 使用技巧
---
##

目前的bug：

如果在设置里排除了某个文件夹，则base过滤的时候，也会排除。。这不知道是不是符合预期。毕竟这些被排除的文件夹，通过cmd o命令又是能搜索到的。

## 使用formula

from [[Spaces/3-Resource/人/Moy]]

![b1eadc6ce11c1c9ed2367df4949ef880.png](https://pub-pic.oldwinter.top/2025/06/423370140ae432c8b1b8e2f0fb08f1cc.png)

【距死线】（天数）

number((date(deadline)-today()).days)

deadline 是 DDL 属性，先用日期相减算出“相对日期”

用 .days 转换成天数，然后用 number() 转成数字类型

【死线状态】

if(formula["距死线"].isEmpty(),"❔ 无", if(formula["距死线"]>= 15, "🟠 长期", if(formula["距死线"] < 1 && formula["距死线"] >= 0, "🚨 今天截止", (if(formula["距死线"]< 0, "🔴 逾期 ",if(formula["距死线"]<= 5, "🟡 只剩 ", "🟢 尚有 "))) + (date(deadline)-today()))))

这个比较复杂……但可以拆解出来，主要是用 if(条件, 真值结果, 否则显示) 这个三元判断做了一大堆日期条件分支，然后显示不同的结果

【进度条】

if(formula.prog_percent * 10 > 0, "▰▰▰▰▰▰▰▰▰▰".slice( 0, (formula.prog_percent * 10).floor()), "").toString() + if((formula.prog_percent * 10).floor() < 10, "▱▱▱▱▱▱▱▱▱▱".slice( 0, 10 - (formula.prog_percent * 10).floor()), "").toString()

也类似，先计算出 progress 属性的百分比，然后用这个比值去截取两个代表“完成”和“未完成”的字符串
