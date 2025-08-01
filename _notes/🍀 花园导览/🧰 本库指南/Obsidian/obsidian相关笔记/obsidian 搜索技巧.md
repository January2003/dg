---
date created: 2022-08-08
date modified: 2023-03-14
publish: true
title: obsidian 搜索技巧
---
[搜索 - Obsidian 中文帮助 - Obsidian Publish](https://publish.obsidian.md/help-zh/%E6%8F%92%E4%BB%B6/%E6%90%9C%E7%B4%A2)

[[🍀 花园导览/🧰 本库指南/Obsidian/obsidian相关笔记/Obsidian 搜索系统搭建]]

## 搜索语法

### 基础语法

在设计检索式时，不要忘了 `说明搜索含义` 能够显示搜索的具体含义，这能在你测试检索式时帮上大忙。

- 使用空格分隔关键词。每个关键词都是被独立查找的。比如，检索式 `foo bar` 将搜索同时包含 `foo` 和 `bar` 的笔记。
- 使用双引号来搜索短语。短语中的空格将不再有分隔关键词的作用，因此你可以搜索那些带有空格的语句。比如，`"foo bar"` 将搜索包含 `foo bar` 这一短语的笔记。
- 可以使用逻辑运算符。`OR` 表示或者关系，即文档应该包含以下关键词之一；`-` 表示非关系，即文档不要包含以下关键词；空格表示与关系，即文档应该同时包含以下关键词。比如，`foo OR bar` 会返回包含 `foo` 或包含 `bar` 的笔记。`foo -bar` 将会返回包含 `foo` 但不包含 `bar` 的笔记。
- 可以使用括号来设置逻辑运算顺序。比如 `(a OR b) (c OR d)`。这对于那些复杂的检索式非常有用，可以确保检索式的计算顺序是符合设计的。
- 可以使用正则表达式。正则表达式需要使用 `/` 包括起来，比如 `/[a-z]{3}/`。Obsidian 接受 JavaScript 风格的正则表达式，你可以在[这里](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)对其进行学习。

### 搜索符

Obsidian 还提供了一些特殊的搜索符。一些搜索符允许你进行嵌套查询，比如 `file:("to be" OR -"2B")`。

- `file:` 将使搜索对象变为文件名。比如，`file:"202007"` 则会搜索名称包含 `202007` 的文件。如果你使用 Zettelkasten 方法并使用时间戳来命名的话，这个搜索符能让你通过搜索文件名来找到某个时间段内记录的笔记。
- `path:` 将使搜索对象变为文件的绝对路径（基于库的根目录）。你也可以将它理解为搜索特定文件夹中的文件。比如 `path:"日记/2020-07"` 将返回路径中包含 `日记/2020-07` 的文件（`日记` 文件夹下子文件夹 `2020-07` 中的文件）。
- `content:` 将使搜索对象变为文件中的内容。比如 `content:"happy cat"`。
- `match-case:` 和 `ignore-case:` 将改变检索式的大小写敏感状态，即 `match-case:` 将使检索式大小写敏感，`ignore-case:` 将使检索式大小写不敏感。
- `tag:` 将检索对象变为标签，返回包含特定标签的文件。比如，`tag:#work` 将返回包含 [\#work](https://publish.obsidian.md/#work) 标签的笔记。使用标签搜索符搜索标签比直接在内容中检索 `#标签` 字符串要精确得多，因为标签搜索符会忽略代码块以及小标题中出现的、形似标签但不是标签的字符串。
- `line:(…)` 将使搜索对象从整个文档的内容变为行的内容。比如，当我们使用最普通的搜索搜索 `foo bar` 时，会返回那些第一行中有 `foo`，最后一行有 `bar` 的笔记。但是，如果使用 `line:(foo bar)`，则会返回只在同一行中同时包含 `foo` 和 `bar` 的笔记。
- `block:(…)` 将使搜索对象从整个文档的内容变为块的内容。正如[块链接与块引用](https://publish.obsidian.md/help-zh/%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/%E5%9D%97%E9%93%BE%E6%8E%A5%E4%B8%8E%E5%9D%97%E5%BC%95%E7%94%A8)中所说的，块是被两个空行包围的元素。由于涉及块的操作需要进一步解析每个文件，因此这种搜索可能会比其他搜索慢。
- `section:(…)` 将使搜索对象从整个文档的内容变为章节的内容。所谓章节指的是两个小标题间的文本（包括开头的小标题）。
- `task:(…)` 将使搜索对象变为[任务列表](https://publish.obsidian.md/help-zh/%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/%E6%A0%BC%E5%BC%8F%E5%8C%96%E4%BD%A0%E7%9A%84%E7%AC%94%E8%AE%B0#%E4%BB%BB%E5%8A%A1%E5%88%97%E8%A1%A8)。你可以使用`task:""` 来在所有任务中检索相应任务。
- `task-todo:(…)` 将使搜索对象变为[任务列表](https://publish.obsidian.md/help-zh/%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/%E6%A0%BC%E5%BC%8F%E5%8C%96%E4%BD%A0%E7%9A%84%E7%AC%94%E8%AE%B0#%E4%BB%BB%E5%8A%A1%E5%88%97%E8%A1%A8)中的待办任务。使用 `task-todo:""` 来在未完成的任务中检索相应任务。
- `task-done:(…)` 将使搜索对象变为[任务列表](https://publish.obsidian.md/help-zh/%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97/%E6%A0%BC%E5%BC%8F%E5%8C%96%E4%BD%A0%E7%9A%84%E7%AC%94%E8%AE%B0#%E4%BB%BB%E5%8A%A1%E5%88%97%E8%A1%A8)中的已完成任务。使用 `task-done:""` 来在已完成的任务中检索相应任务。