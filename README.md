# html manual

1. 注释写上方，而不是写下方 \<!-- --\>
2. 代码缩进使用 2个空格，而不是4个空格
3. `<img />` `<input />` `<br />` 等都叫 void elements 空元素，因为不包含任何内容。(不包含任何内容的元素称为空元素。比如 <img> 元素)，而且没有结束标签，这些元素不需要通过内容来产生效果。也叫做自闭合元素，自闭合标签。https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web/HTML_basics#%E7%A9%BA%E5%85%83%E7%B4%A0 https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics#void_elements 
4. 空元素，虽然 `/` 可以省略，但为了可读性更好，建议可以加上，而且前面要有一个空格，例如`<br />`，但是很多编辑器，代码补齐出来的没有加反斜线，这个也不必要特地去加反斜线，随意就好 例如 vscode `<input type="text">` https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/br
