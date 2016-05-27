Deprecated
=====================
Instead, you should look at a well maintained project like [dnsmasq-china-list
](https://github.com/felixonmars/dnsmasq-china-list).

解决使用国外 DNS 造成国内网站访问慢的问题，使得国内国外网站分别智能解析的配置文件。

# 作用是什么？
这些配置文件用于在本地搭建 DNS 缓存服务器，采用白名单的方式使常见国内的域名使用 114.114.114.114 进行解析，其它所有域名使用 8.8.4.4 与 8.8.8.8 进行解析防止 DNS 污染与投毒。

# 为什么要这样做？
使用 8.8.4.4 与 8.8.8.8 解析，防止解析国外网站时遭到的 DNS 污染与投毒，导致解析到完全虚构的 IP。  
使用 114.114.114.114 解析，防止解析国内网站时由于无法判断来源胡乱分配 CDN，导致访问缓慢。

# 如何使用？
Windows 下安装 [Bind](http://www.isc.org/downloads/bind/)，使用 `named.conf` 配置文件。这是一个图文并茂，可以参考，但因为版本原因有些许问题的[教程](http://drupalmotion.com/article/dev-environment-install-and-configure-bind-dns-server-windows-7)。

Mac 与 Linux 下使用包管理（brew 或 apt-get 等）安装 dnsmasq，使用 `dnsmasq.conf` 配置文件。这是一个可以参考的[教程](https://wzyboy.im/post/874.html)。
