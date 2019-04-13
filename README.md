# GCP_lmplementation
Google Cloud Platform Hosting Implementation guide

# Table of Contents  
[Implementation](#implementation)  
[Step 1.GCP Application.](#step-1gcp-application)  
[Step 2. Creat private and publiv key for SSH Connection.](#step-2-creat-private-and-publiv-key-for-ssh-connection)  
[Step 3. Establish SSH session configuration on GCP consel](#step-3-establish-ssh-session-configuration-on-gcp-consel)  
[Step 4. Connecting Securely to Google Compute Engine Server with SFTP](#step-4-connecting-securely-to-google-compute-engine-server-with-sftp)  
[Step 5. Python 3.6.6 to Ubuntu 16.04.1](#step-5-python-366-to-ubuntu-16041)  
[Step 6. Install PIP On Debian/Ubuntu](#step-6-install-pip-on-debianubuntu)  
[Step 7. Install packages using pip and virtualenv](#step-7-install-packages-using-pip-and-virtualenv)  
[Step 8. Install modules under virtualenv](#step-8-install-modules-under-virtualenv)  
[Step 9. TA-Lib modules under virtualenv](#step-9-ta-lib-modules-under-virtualenv)  
[Step 10. Setup GUI Desktop](#step-10-setup-gui-desktop)  

[Troubleshooting](#troubleshooting)  
[Environment Configuration](#environment-configuration)  
[Reference](#reference)  

# Implementation

## Step 1.GCP Application. 
* [【教學】Google Cloud Platform 申請試用，並建立免費專案！](https://izo.tw/gcp-apply/)
``` 
※　注意
點開 管理、磁碟、網路、SSH 金鑰
選擇『網路』 → 外部IP → 新增『新的靜態 IP 位址』
※ 如果此步沒做，往後每次除開機IP將會變動
``` 
![alt tag](https://lh5.googleusercontent.com/-x69xzePFVP0/TdesS4b6UsI/AAAAAAAABaU/iDGAZV8PP_8/s0/subnettingcfe8.png)

## Step 2. Creat private and publiv key for SSH Connection.

* [【教學】使用 PuTTYgen 產生 SSH 連線 RSA、DSA 公鑰與私鑰](https://www.techcoke.com/2017/01/puttygen-ssh-rsa-dsa-public-private-key-pair.html)


## Step 3. Establish SSH session configuration on GCP consel

* [【教學】Google Compute Engine ( GCE ) 使用 PuTTY SSH 登入實例](https://www.techcoke.com/2017/01/google-compute-engine-putty-ssh-instances.html)


首先，變更 Key comment。在 Key comment 日期的後面，輸入你申請 Google Cloud Platform 時「@gmail.com」前的名稱。如果申請的 gmail 為 ilovetechcoke@gmail.com 就在日期後面輸入「ilovetechcoke」。

下圖的例子為「techcoke」，完整輸入就是「rsa-key-20170120techcoke」。(* 這裡的日期，會和你操作時的日期不相同，以你當前建立密鑰對的時間為準。)

變更完 Key comment 之後，將 PuTTYgen 上方 OpenSSH authorized_keys 裡面的公鑰資料先做複製，最後再按下「Save private key」，將私鑰儲存到電腦中。


## Step 4. Connecting Securely to Google Compute Engine Server with SFTP
``` 
 Set up SSH keys for your Google Compute account:

    Load your private key to PuTTYgen;
    Enter your GCE username1 to Key comment box.
    Copy a contents of Public key for pasting to OpenSSH authorized_keys file to the clipboard (note that the contents includes your username);
    Go to Metadata page of your project on Google Cloud Platform;
    Go to SSH Keys tab and click Edit;
    Click Add item button and paste contents of the clipboard to Enter entire key data box (note how the username is automatically recognized).
    On the bottom of the page, click Save and wait for the key to be saved.
``` 

## Step 5. Python 3.6.6 to Ubuntu 16.04.1
 
Ubuntu 14.04 (Trusty), 16.04 (Xenial)

If you are using Ubuntu 14.04 or 16.04, 
you can use Felix Krull's deadsnakes PPA at https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa:

``` 
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.6
``` 
 

## Step 6. Install PIP On Debian/Ubuntu

Note: We will run all commands as the root user, if you are managing your system as a normal user, then use the sudo command to get root privileges or you can as well configure your system to run sudo command without entering a password, it’s possible. Try it out!

``` 
# apt install python-pip	#python 2
# apt install python3-pip	#python 3
``` 

## Step 7. Install packages using pip and virtualenv

Installing virtualenv

On macOS and Linux:
```
python3 -m pip install --user virtualenv
```

Creating a virtualenv

On macOS and Linux:
```
python3 -m virtualenv env
```

Activating a virtualenv

On macOS and Linux:
```
source env/bin/activate
```
You can confirm you’re in the virtualenv by checking the location of your Python interpreter, it should point to the env directory.

On macOS and Linux:
```
which python
.../env/bin/python
```

Leaving the virtualenv

```
deactivate
```

## Step 8. Install modules under virtualenv
```
python -m  pip install -r ./requiremenets.txt

```

## Step 9. TA-Lib modules under virtualenv
```
Steps:
    sudo apt-get install python3.6-dev

    wget https://github.com/mrjbq7/ta-lib/archive/TA_Lib-0.4.10.tar.gz
    tar -xvf TA_Lib-0.4.10.tar.gz
    cd ./ta-lib-TA_Lib-0.4.10/
    python setup.py install

```

## Step 10. Setup GUI Desktop

Install the desktop
```
sudo apt-get install ubuntu-desktop
```

Install VNC server
https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04

```
sudo apt-get install xinit
```

and then run
```
startx
```

# Troubleshooting
phpMyAdmin turn blank page after login:
![alt tag](https://i.imgur.com/JgJiKyL.jpg)

Solution: Change another browser, casue $cfg['Servers'][$i]['auth_type'] = 'cookie' at /etc/phpmyadmin/config.inc.php
![alt tag](https://i.imgur.com/VdXMfaa.jpg)




# Environment Configuration
* via Putty on Windows 10

# Reference 
* [【教學】Google Cloud Platform 申請試用，並建立免費專案！](https://izo.tw/gcp-apply/)
* [【教學】Google Compute Engine ( GCE ) 使用 PuTTY SSH 登入實例](https://www.techcoke.com/2017/01/google-compute-engine-putty-ssh-instances.html)
* [【教學】使用 PuTTYgen 產生 SSH 連線 RSA、DSA 公鑰與私鑰](https://www.techcoke.com/2017/01/puttygen-ssh-rsa-dsa-public-private-key-pair.html)
* [鳥哥的 Linux 私房菜 第十一章、遠端連線伺服器SSH / XDMCP / VNC / RDP](http://linux.vbird.org/linux_server/0310telnetssh.php) 
* [Connecting Securely to Google Compute Engine Server with SFTP](https://winscp.net/eng/docs/guide_google_compute_engine)
* [How do I install Python 3.6 using apt-get?](https://askubuntu.com/questions/865554/how-do-i-install-python-3-6-using-apt-get)
* [How To Install PIP to Manage Python Packages in Linux](https://www.tecmint.com/install-pip-in-linux/)
* [Installing packages using pip and virtualenv](https://packaging.python.org/guides/installing-using-pip-and-virtualenv/#creating-a-virtualenv)
* [How to open a browser on a Google Compute Engine VM](https://stackoverflow.com/questions/46207046/how-to-open-a-browser-on-a-google-compute-engine-vm)
* [How to Install and Configure VNC on Ubuntu 16.04 ](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-vnc-on-ubuntu-16-04)
* [What is the simplest way to have remote GUI access to Ubuntu 16.04 “server” from Ubuntu 16.04 “desktop”?](https://askubuntu.com/questions/886313/what-is-the-simplest-way-to-have-remote-gui-access-to-ubuntu-16-04-server-from) 
* [Your desktop on Google Cloud Platform VNC on Google Compute Engine instances](https://medium.com/google-cloud/linux-gui-on-the-google-cloud-platform-800719ab27c5)
* [VNCViewer fonts Font directory '/usr/share/fonts/X11/75dpi/' not found - ignoring Font directory '/usr/share/fonts/X11/100dpi/' not found - ignoring](https://raspberrypi.stackexchange.com/questions/10452/vncviewer-fonts)
* [Get error on pip install · Issue #285 · freqtrade/freqtrade · GitHub](https://github.com/freqtrade/freqtrade/issues/285)
* [Unable to install TA-Lib on Ubuntu](https://stackoverflow.com/questions/45406213/unable-to-install-ta-lib-on-ubuntu)
* [[Ubuntu] 安裝LAMP PHP7 , Apache2 , MaraiDB 版本：16.04](http://holmes.logdown.com/posts/734144-linux-ubuntu-install-ubuntu-1604-lamp-php7-apache2-maraidb)
* [Ubuntu 16.04 在 Apache2.4 用 mod_php 跑 PHP7.0 ](https://shazi.info/ubuntu-16-04-%E5%9C%A8-apache2-4-%E7%94%A8-mod_php-%E8%B7%91-php7-0/)
* [Ubuntu Apache 2.4 正確使用conf、mods、sites等設定檔。](http://mickey-tang.blogspot.com/2018/04/ubuntu-apache-24-confmodssites.html)
* [Ubuntu Apache 2.4 啟動SSL ](http://mickey-tang.blogspot.com/2015/08/ubuntu-apache-24-ssl.html)
* [Let’s encrypt on Apache 使用 https 加密連線，讓你的 Apache 網站更安全](https://ccnrz.wordpress.com/2017/05/19/lets-encrypt-on-apache/)
* [Ubuntu Apache 上用自簽憑證啟用 https 服務](https://ccnrz.wordpress.com/2017/05/04/%E5%9C%A8-ubuntu-apache-%E4%B8%8A%E5%95%9F%E7%94%A8-https-%E8%87%AA%E7%B0%BD%E6%86%91%E8%AD%89/)
* [How To Create a SSL Certificate on Apache for Ubuntu 14.04 ](https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-apache-for-ubuntu-14-04)

* [ubuntu 基礎架站](http://www.alvinchen.club/2018/04/12/ubuntu-%E5%9F%BA%E7%A4%8E%E6%9E%B6%E7%AB%99/)
* [讓你的 apache支援ssl](http://www.alvinchen.club/2018/04/13/%e8%ae%93%e4%bd%a0%e7%9a%84apache%e6%94%af%e6%8f%b4ssl/)
* [ubuntu 進階架站分享](http://www.alvinchen.club/2018/04/13/ubuntu-%e6%9e%b6%e7%ab%99%e9%80%b2%e9%9a%8e%e5%88%86%e4%ba%ab/)
* [How To Set Up Apache Virtual Hosts on Ubuntu 14.04 LTS ](https://www.digitalocean.com/community/tutorials/how-to-set-up-apache-virtual-hosts-on-ubuntu-14-04-lts)
* [How To Set Up mod_rewrite for Apache on Ubuntu 14.04 ](https://www.digitalocean.com/community/tutorials/how-to-set-up-mod_rewrite-for-apache-on-ubuntu-14-04)
* [安裝 LAMP Server + phpMyAdmin 在 Linux 系統上輕鬆架設網站](https://magiclen.org/lamp/)

* [Nginx+Apache+PHP ](http://blog.kenyang.net/2012/09/18/nginxapachephp)
* [Ubuntu16.04+Apache虛擬主機配置詳解](https://hk.saowen.com/a/7b1f0ea4b830876fbf2be10ba9e298b95171c0b0e5d680c539d96c60e42576e3)
* []()

* [Ubuntu 教學](https://www.arthurtoday.com/p/ubuntu-tutorial.html)
* [Change password on root user and user account](https://askubuntu.com/questions/423942/change-password-on-root-user-and-user-account)
* [Cannot enter phpmyadmin as root (MySQL 5.7)](https://askubuntu.com/questions/763336/cannot-enter-phpmyadmin-as-root-mysql-5-7)
* [Ubuntu 16.04.1 Server(PHP 7.06)安裝 phpmyadmin 後登入的問題 已將 /etc/phpmyadmin/config.inc.php 其中的 $cfg['Servers'][$i]['auth_type'] = 'cookie'; 修改為 $cfg['Servers'][$i]['auth_type'] = 'http';](https://ithelp.ithome.com.tw/questions/10184428)
