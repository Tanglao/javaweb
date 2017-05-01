如何解决多机session问题





session sticky，固定单机保存，由负载均衡根据会话标识路由到固定服务器，存在单机故障问题

session复制，增加网络开销，占用内存

session集中存储，服务器读写session要额外网络访问

cookie传递session，有存储长度问题，网络传递数据量增加，安全问题

