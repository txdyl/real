---
layout: post
title:  "debian8安装shadowsocks-libev"
date:   2018-06-03 12:36
author: "starry"
categories: Clutter
permalink: 2018/04/06/11/
---
<code>apt update
apt install shadowsocks-libev</code>
如果不能安装就<br>
<code>sh -c 'printf "deb http://deb.debian.org/debian jessie-backports main\n" &gt; /etc/apt/sources.list.d/jessie-backports.list'
sh -c 'printf "deb http://deb.debian.org/debian jessie-backports-sloppy main" &gt;&gt; /etc/apt/sources.list.d/jessie-backports.list'
apt update
apt -t jessie-backports-sloppy install shadowsocks-libev
</code>
然后编辑配置文件
<code>vim /etc/shadowsocks-libev/config.json</code>
配置如下，端口为8838
<code>{
"server":"0.0.0.0",
"server_port":8388,
"local_port":1080,
"password":"yourpassword",
"timeout":400,
"method":"aes-256-cfb"
}</code>
然后重启shadowsocks-libev
<code>systemctl restart shadowsocks-libev</code>
