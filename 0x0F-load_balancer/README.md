Installing HAProxy and configuring HAProxy
$ sudo apt-get install -y haproxy=1.6.\*

$ sudo vi /etc/haproxy/haproxy.cfg
# Add the below code to the file opened using vi editor
frontend wadza.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 167154-web-01 52.91.152.79
        server 167154-web-02 100.25.33.42
~
~
:wq(to save and exit)
--------------- or ----------------------- 
$ echo '
frontend wadza.tech
        bind 0:80
	mode http
        default_backend web_servers

backend web_servers
        balance roundrobin
        server 167154-web-01 52.91.152.79
        server 167154-web-02 100.25.33.42
' >> /etc/haproxy/haproxy.cfg

$ service haproxy restart

# git clone this repo on your terminal and run the file
# install_haproxy_safely or 1-install_load_balancer to 
# configure yours on a fly.
