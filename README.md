# nginx.conf
Configuring NGINX for maximum throughput under high Traffic



sysctl.conf

/etc/sysctl.conf

    net.core.somaxconn = 65536
    net.ipv4.tcp_max_tw_buckets = 1440000
    net.ipv4.ip_local_port_range = 1024 65000
    net.ipv4.tcp_fin_timeout = 15
    net.ipv4.tcp_window_scaling = 1
    net.ipv4.tcp_max_syn_backlog = 3240000
    
 
limits.conf

/etc/security/limits.conf

* soft nofile 4096

* hard nofile 4096
