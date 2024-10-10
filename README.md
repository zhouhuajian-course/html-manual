# html manual

1. 注释写上方，而不是写下方 \<!-- --\>
2. 代码缩进使用 2个空格，而不是4个空格
3. `<img />` `<input />` `<br />` 等都叫 void elements 空元素，因为不包含任何内容。(不包含任何内容的元素称为空元素。比如 <img> 元素)，而且没有结束标签，这些元素不需要通过内容来产生效果。也叫做自闭合元素，自闭合标签。https://developer.mozilla.org/zh-CN/docs/Learn/Getting_started_with_the_web/HTML_basics#%E7%A9%BA%E5%85%83%E7%B4%A0 https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/HTML_basics#void_elements 
4. 空元素，虽然 `/` 可以省略，但为了可读性更好，建议可以加上，而且前面要有一个空格，例如`<br />`，但是很多编辑器，代码补齐出来的没有加反斜线，这个也不必要特地去加反斜线，随意就好 例如 vscode `<input type="text">` https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/br
5. 要文件上传，form 需要 `method="post" enctype="multipart/form-data"`
6. `<input type="radio">` `<input type="checkbox">` 右边的文本，不需要加空格，例如`<input type="radio" />男`；
7. `<input />` `<img />` 等空元素，`/`统一规范，前面要加个空格
8. `<input type="checkbox">` GET 请求 `languages=Java&languages=C++` POST 请求 `languages=Java&languages=C++` 相同的name多个value
9. `input` `select` `textarea` 尽量都要设置 `name`
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>个人资料</title>
</head>
<body>
  <form action="/profile" method="post" enctype="multipart/form-data">
    <div>姓名：<input type="text" name="name" /></div>
    <div>性别：<input type="radio" name="gender" value="男" />男
               <input type="radio" name="gender" value="女" />女
    </div>
    <div>语言：<input type="checkbox" name="languages" value="汉语" />汉语
               <input type="checkbox" name="languages" value="英语" />英语
    </div>
    <div>生日：<input type="date" name="birthday" /></div>
    <div>颜色：<input type="color" name="color" /></div>
    <div>范围：<input type="range" name="range" min="0" value="0" max="100" /></div>
    <div>头像：<input type="file" name="avatar" /></div>
    <div>学校：<select name="school">
                 <option value="">请选择</option>
                 <option value="小学">小学</option>
                 <option value="初中">初中</option>
                 <option value="高中">高中</option>
               </select>
    </div>
    <div>简介：<textarea name="intro"></textarea></div>
    <div>照片：<input type="file" name="photos" multiple /></div>
    <div><button type="submit">保存</button></div>
  </form>
</body>
</html>
```
10. 表单控件 `form control` 能加 `label` 的尽量加上，好处很多，例如 `<input type="radio">` `<input type="checkbox">` 点 label 就能选，如果没有 label，则只能点击 `<input>` 才能选，体验比较差，更多好处，`https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/label`
```text
将一个 <label> 和一个 <input> 元素相关联主要有这些优点：

  标签文本不仅与其相应的文本输入元素在视觉上相关联，程序中也是如此。这意味着，当用户聚焦到这个表单输入元素时，屏幕阅读器可以读出标签，让使用辅助技术的用户更容易理解应输入什么数据。
  你可以点击关联的标签来聚焦或者激活这个输入元素，就像直接点击输入元素一样。这扩大了元素的可点击区域，让包括使用触屏设备在内的用户更容易激活这个元素。

其他使用事项：

  关联标签的表单控件称为这个标签的已关联标签的控件。一个 input 可以与多个标签相关联。
  点击或者轻触（tap）与表单控件相关联的 <label> 也可以触发关联控件的 click 事件。
```
11. `<input type="date">`，它的 value `值	按照 YYYY-MM-DD 格式化过的代表日期的字符串，或者为空字符串`，`有一点需要注意的是，在格式方面显示的日期与实际的 value 不一样——显示的日期格式取决于用户浏览器的区域设定，而经解析的 value 的格式始终为 yyyy-mm-dd。`，`可以通过 JavaScript 代码获取和设置 HTMLInputElement 的 value 和 valueAsNumber 属性`，`valueAsNumber` 是 `JavaScript` 的时间戳，例如 `1496275200000` (ms)，不能设置其他格式的值，不然会变成 空字符串；默认值是 空字符串。
```text
<input type="date"> 默认 value 为空字符串 默认格式 需要是 yyyy-MM-dd 设置 yyyy/MM/dd无法设置成功，value会变空字符串
> $("input[type=\"date\"]").value
  ''
> $("input[type=\"date\"]").value = "2024-10-01"
  '2024-10-01'
> $("input[type=\"date\"]").value = "2024/10/01"
  VM1908:1 The specified value "2024/10/01" does not conform to the required format, "yyyy-MM-dd".
  '2024/10/01'
> $("input[type=\"date\"]").value
  ''
```
12. `<textarea></textarea>` 文本域的 `rows="5"`，表示高度为 5 行文本的高度；
13. `<canvas></canvas>` 画布 是行内元素，`width="300" height="300"` 可以设置 画布宽高，不同 `<img />`，画布需要闭合标签；
