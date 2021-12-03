# Jenkins

对于CICD这方面我还不是特别熟悉，所以我选择了知名度最高的Jenkins实现流水线，因为它应该有更多的资料可以参考，并且大多数开源软件都愿意集成它。

## 容器镜像

jenkins 官方文档推荐使用jenkinsci/blueocean镜像部署jenkins，在对jenkins还不是很熟悉的情况下，我接受了官方的推荐，但是我觉的，如果需要客制化部署的话，还是有必要使用官方仓库的jenkins/jenkins镜像进行尝试。

## 使用LDAP管理用户

搭建统一账户最直接的办法就是使用ldap管理用户，因为大多数开源组件都支持ldap协议，所以ldap也是兼容性最强的一种方式。
首先我们需要启动openldap服务，可以使用docker compose启动ldap:
```bash
cd compose
docker-compose up openldap -d
```
openldap的root用户密码在.env文件中进行配置。
然后我们就可以启动Jenkins了，等待openldap和jenkins启动完毕后便可以进行配置。
打开Jenkins的 管理Jenkins(Dashboard) > 配置全局安全(Configure Global Security)界面，在安全域中选择LDAP，随后点击高级服务器设置(Advanced Server Configuration)。
我们可以看到一个看起来挺复杂的表单。

让我们一项一项的看一下具体如何配置：
* Server 是openldap的地址，我这里直接使用docker内部的网络，填写openldap；
* root DN 是搜索的根节点；
* User search base 搜索用户的基节点，我们将在openldap中添加People组，所以这里填写ou=People；
* User search filter 是对用户名进行格式化，默认的表达式为`uid={0}`也就是将用户名写到uid字段；
* Manager DN 是openldap的管理员地址，jenkins将会使用这个账号跟openldap进行通讯，我们这里使用cn=admin,dc=example,dc=com；
* Manager Password就是我们在.env中配置的root密码；
* Display Name LDAP attribute 是显示在jenkins中的用户名，我们这里取cn

然后点击Test LDAP setting进行测试：

首先我们要在openldap中创建用户，可以使用 phpldapadmin 进行操作。添加一个叫做People的ou，然后再ou下面创建一个cn叫username密码为password的联系人。

回到测试页面，我们就可以使用username和password测试了，查看Jenkins的提示，如果登录成功了，我们就可以使用ldap登录了。