---
created: '2024-05-11'
cssclasses: ''
modified: '2025-07-10'
permalink: /🍀 花园导览/🧰 本库指南/Obsidian/Plugins/Advanced URI.md
publish: true
published: '2025-07-25T18:32:03.918+08:00'
tags:
- obsidian插件
title: Advanced URI
---
给每个笔记生成一个固定id，这样可以维持链接的稳定性，外部调用obsidian内部的时候，不至于当笔记移动的时候，调用或打开失败。

[[Sources/GithubStarsSync/quartz\|quartz]]目前最头痛的就是这个，如果要给每个笔记设置一个[[Cards/permanentlink]]，可以用这个插件生成唯一的uuid，但是会让frontmatter里面东西太多，不利于自己日常使用。以后看有没有更优雅地解决方案吧。其实[[🍀 花园导览/🧰 本库指南/Obsidian/obsidian相关笔记/obsidian publish 发布]]官方，也没有解决，如果挪动笔记位置，链接就失效。
