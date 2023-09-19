# css 文本换行/超出省略

##

[链接](https://juejin.cn/post/6966042926853914654)
来个 css 大佬吧，grid 布局里，文字里有中文可以换行，只有数字不能换行，大佬们怎么处理？

.container {
display: grid;
grid-template-columns: repeat(3, 1fr);
word-break: break-all; /_ 这将允许单词在任何字符处断开 _/
}
