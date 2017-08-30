**所需命令：**

**姓名邮箱设置：**
<br>`git config –-global user.name / email xxx` 
<br>`git config –-global color.ui auto`
<br>查看使用 `cat ~/.gitconfig`

**创建ssh** 
<br>创建文件夹 `mkdir .ssh`    //如果有建议清楚重新配置
<br>进入文件夹 `cd ~/.ssh`
<br>开启ssh-agent：`eval $(ssh-ageny -s)`
<br>创建 `ssh-keygen -t rsa -C “email” `
<br>复制 `clip < ~/id_rsa.pub`
<br>粘贴到git web上//成功有邮件提醒
<br>查看是否成功创建： `ssh -T（克隆用加端口） git@（ssh.）github.com`

>**报错记录：**

>**测试ssh后可能出现的情况**

>1，**Warning: Permanently added '' (RSA) to the list of known hosts.**
<br>&emsp; &emsp; &emsp; &emsp; &emsp; **Permission denied (publickey).**
>>**原因：**防火墙可能拒绝ssh连接：克隆使用过ssh的端口
<br>&emsp; &emsp; 或是ssh-agent未开启：`eval $(ssh-ageny -s)`

>2，could not open a connection to your authentication agent
>>**原因：** ssh-agent未开启：`eval $(ssh-ageny -s)`

>3，大小写敏感  //不管是什么提醒都要先检查
