# nginx.conf
Configuring NGINX for EC2/GCE in production



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

* soft nofile 4096

* hard nofile 4096
