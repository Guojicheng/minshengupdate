### ingress 问题
   原因总结：
   设置route 侦听58080 端口导致冲突。引发ingress 问题。
   避免措施：
   规范wisecloud所有可用的侦听端口范围。
### 得到所有k8s 指定namespaces 下的服务ip 及port 信息
 for i in ` kubectl  -n ns-team-4-env-1 get svc  | sed 1d |awk '{print $1}'` ; do kubectl  -n ns-team-4-env-1 get svc $i --output=go-template --template='{{.metadata.name}}{{"\t"}}{{range .spec.ports}}{{"container port:\t"}}{{.port}}{{"\t"}}{{"target port:\t"}}{{.targetPort}}{{"\n"}}{{end}}' ; done

### 日志问题

*  在node1 node3 上资源占用较多的计算节点服务器，日志显示明显较慢。有时没有显示，提示获取不了日志。
* 
