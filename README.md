# nginx.conf
Configuring NGINX for EC2/GCE (4 Core CPU) in production based on experience for stability and performance



sysctl.conf

/etc/sysctl.conf
    
    # the maximum number of "backlogged sockets"
    net.core.somaxconn = 65536
    # maximal number of timewait sockets held by system simultaneously
    net.ipv4.tcp_max_tw_buckets = 1440000
    # use the full range of ports.
    net.ipv4.ip_local_port_range = 1024 65000
    # decrease the time default value for tcp_fin_timeout connection
    net.ipv4.tcp_fin_timeout = 15
    # improve network performance
    net.ipv4.tcp_window_scaling = 1
    # increase the number of outstanding syn requests allowed
    net.ipv4.tcp_max_syn_backlog = 3240000
    
 
limits.conf

/etc/security/limits.conf
~~~
* soft     nproc          65535
* hard     nproc          65535
* soft     nofile         65535
* hard     nofile         65535
root soft     nproc          65535
root hard     nproc          65535
root soft     nofile         65535
root hard     nofile         65535
~~~


