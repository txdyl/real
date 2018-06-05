---
layout: post
title:  "debian8安装shadowsocks-libev"
date:   2018-06-03 12:36
author: "starry"
categories: Clutter
permalink: 2018/04/06/11/
---
<pre><code class="language-css">apt update
apt install shadowsocks-libev</code></pre>
如果不能安装就<br>
<pre><code class="language-css">sh -c 'printf "deb http://deb.debian.org/debian jessie-backports main\n" &gt; /etc/apt/sources.list.d/jessie-backports.list'
sh -c 'printf "deb http://deb.debian.org/debian jessie-backports-sloppy main" &gt;&gt; /etc/apt/sources.list.d/jessie-backports.list'
apt update
apt -t jessie-backports-sloppy install shadowsocks-libev
</code></pre>
然后编辑配置文件
<pre><code class="language-css">vim /etc/shadowsocks-libev/config.json</code></pre>
配置如下，端口为8838
<pre><code class="language-css">{
"server":"0.0.0.0",
"server_port":8388,
"local_port":1080,
"password":"yourpassword",
"timeout":400,
"method":"aes-256-cfb"
}</code></pre>
然后重启shadowsocks-libev
<pre><code class="language-css">systemctl restart shadowsocks-libev</code></pre>
