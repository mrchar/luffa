# Jenkins

对于CICD这方面我还不是特别熟悉，所以我选择了知名度最高的Jenkins实现流水线，因为它应该有更多的资料可以参考，并且大多数开源软件都愿意集成它。

## 容器镜像

jenkins 官方文档推荐使用jenkinsci/blueocean镜像部署jenkins，在对jenkins还不是很熟悉的情况下，我接受了官方的推荐，但是我觉的，如果需要客制化部署的话，还是有必要使用官方仓库的jenkins/jenkins镜像进行尝试。

## 使用LDAP管理用户