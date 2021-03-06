# Authentication Provider 身份提供者

将大量开源软件组合在一起必然会面临统一各个服务的用户体系的问题，我希望在一开始就解决掉这个问题。

需要强调的是，各种开源软件支持的第三方认证方式不尽相同，可能很难使用一种方式解决所有的问题，但是我依然希望尽可能使用更先进且更稳定的认证方式。OAuth2将会是最好的选择。

## 身份提供者

很多开源软件支持将软件本身作为身份提供者为其他软件提供身份认证服务，使用这种方式将不需要使用独立的身份认证提供者，而是选择使用构成Luffa的组件中的一个作为身份提供者。理所当然的，我们应该尽可能的选择支持的认证方式更多的组件，且这个组件应该尽可能是必须的。

另外一种方式是选择一个专门的身份提供者软件，那个我们就应该要求这个软件支持尽可能多的认证方式。或者选择大多数组件都支持的认证方式，比如LDAP。但这会导致我们必须坚持使用这种陈旧的认证方式。

## 各个组件支持的登录方式

1. Gitea: LDAP(via BindDN)、LDAP(simple auth)、SMTP、OAuth2、SPENEGO with SSPI
2. Jenkins: Jenkins拥有大量的插件，支持以各种方式登录

## 值得考虑的Authentication Provider

1. [JOIDS(Java OpenID Server)](https://code.google.com/archive/p/openid-server/)