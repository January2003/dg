---
date created: 2022-07-26
date modified: 2023-03-14
publish: true
title: 使用简悦对web文章进行渐进式总结
---
## 整体效果

- 剪藏和批注可以实时同步到obsidian中。
- 在obsidian中点击批注，可以直接找到原文位置，从而不丢失上下文。
- 在obsidian中，可以对全文剪藏或批注进行块引用。

## 注意事项

简悦配置真tm麻烦，而且还一堆不生效的小bug。尤其不能使用同步助手去同步配置数据，会出现插件配置不生效的问题。

![](https://img2.oldwinter.top/Pasted%20image%2020220726195428.png)

此外有些文章如果含有|等特殊字符，会导致remotely save同步出问题，要手动处理。

## 常用快捷键：

- aa进阅读模式
- dd直接丢到稍后读
- sr进入控制模式，而后`,`打开快捷键列表，`an`进入标注模式
- 简悦的稍后读，可以存成edge的应用，然后用[[Spaces/3-Resource/软件梳理/macos软件/Raycast]]快速调用打开。

稍后读的文件是html文件，剪藏至ob的均是md文件。

## 需安装的简悦插件

- 导入到 Obsidian
- 自动化辅助增强
- Markdown 模板辅助增强

## 使用步骤

- 剪藏和批注。看到需要剪藏or批注的好文章，按aa进入阅读模式
	- 若只想剪藏，则dd加入稍后读，并会同步剪藏全文至obsidian
		- 如果只用`ob`命令，则只会剪藏至obsidian，没有加入稍后读
	- 若想精读，则直接标注即可，会自动将标注后的全部内容同步至obsidian
- 总结和引用。要引用的时候，直接用双链语法即可。
	- 总结的想法写在最前面##我的理解下面，可以方便直接进行标题引用。
	- 原文内容如果要用标题引用需要动模板，懒得搞了，直接用块引用好了，实践一段时间再看是否需要调整。