---
date created: 2022-08-24
date modified: 2023-03-14
publish: true
title: 本库obsidian如何批量重命名文件
---
以将`+ MOC`等格式的文件批量重命名成`∑ MOC`为例。分2步：

- 批量重命名文件
- 批量重命名内部链接

## 批量重命名文件

[[Cards/vscode 文件批量重命名]]

## 批量重命名内部链接

- vscode中的正则搜索和替换
	- 搜索表达式 `\[\[\+ (.*?)\]\]`
	- 替换表达式 `[[∑ $1]]`  
![](https://img2.oldwinter.top/202208241649678.png)