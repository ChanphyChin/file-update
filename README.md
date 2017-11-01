### 烂笔头
```javascript
单个文件上传文件处理
注：key为键，value为值，url为接口地址，file为文件

1. form表单
    <form id="sslForm" action="url" enctype='multipart/form-data' method="post">
      <input type="text" name="key" value="value">
      <input type="file" name="key" value="value">
      <input type="submit">
    </form>
2. 普通ajax请求
  <input type="file" onchange="filechange">
  function filechange (event){
    let file = new FormData();
    file.append(key,event.target.files[0]);
    $.ajax({
      url:url(拼上你的其他参数),
      type:'post',
      data:file
      ......
    })
  }

  多个文件上传文件处理
  注：key为键，value为值，url为接口地址，file为文件


  1. form表单
    <form id="sslForm" action="url" enctype='multipart/form-data' method="post">
      <input type="file" name="key" value="value">
      <input type="file" name="key2" value="value2">
      <input type="submit">
    </form>
2. 普通ajax请求
  <input type="file"  onchange="filechange">
  <input type="file"  onchange="filechange">
  function filechange (event){
    let files = new FormData();
    files.append(key,file);
    files.append(key2,file2);
    $.ajax({
      url:url(拼上你的其他参数),
      type:'post',
      data:file
      ......
    })
  }
