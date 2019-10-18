### 上传文件到服务器的技巧

本地有时候要上传二进制文件到服务器 比如.class 文件或者图片，有的服务器不允许直接上传文件，可以使用`base64`命令来绕过。

1. 在本地先转换`.class`文件为base64，再保存为result.txt

   ```
   base64 < Test.class > result.txt
   ```

2. 到服务器上，新建并编辑`result.txt`，复制本地的内容，粘贴再保存

   ```
   touch result.txt
   
   vim result.txt
   ```

3. 把服务器上的 `result.txt`还原为`.class`

   ```
   base64 -d < result.txt > Test.class
   ```

4. 用md5命令计算哈希值，校验是否一致