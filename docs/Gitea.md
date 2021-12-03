# Gitea

## 可集成组件

1. awesome-gitea
    [Awesome Gitea](https://gitea.com/gitea/awesome-gitea)

## 使用LDAP管理员用户

这里我们使用LDAP(via BindDN)进行配置，使用管理员账号登录，打开管理后台>认证源。
点击添加认证源，我们可以看到一个配置表单。
下面依次填写配置：
* 认证名称: 取一个便于识别的名字
* 安全协议: 选择Unencrypted
* 主机我们填写openldap
* 端口填写389，如果填写636会使用tls
* 绑定DN填写cn=readonly,dc=example,dc=com
* 绑定密码填写.env中配置的密码
* 用户搜索基准使用再openldap中配置的组 ou=members,dc=example,dc=com
* 用户过滤规则使用(&(objectClass=simpleSecurityObject)(uid=%s))
* 电子邮箱属性填写mail，然后保存