###  cmdb 服务需求
服务stack 包括  cmdb-service-webapp、cmdb-webapp 两个服务

同时服务依赖其它stack 先启动，包括 userinfochange/sequence ，  LDAP/ldap-service

启动顺序  ： 依次是sequence、ldap-service、cmdb-service-webapp、cmdb-webapp


####  LDAP 服务

原有RANcher 环境stack 名称使用大写字母LDAP ， k8s stack 名称不支持。

####   完成镜像修改并启动验证，该项目有CI 的流程，当前直接改了镜像，git还没有改。
#### 问题汇总

1.  为了区分开k8s的代码 及rancher 内流水线的代码。需要搭建新的git仓库吗？
2.  有些项目可能不能按照单个stack 迁移， 而需要一并将所有关连的stack 一起迁移才行。这加大了迁移的复杂度及风险。 跨stack调用的设计特别多。
cmdb-webapp
