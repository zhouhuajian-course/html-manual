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
