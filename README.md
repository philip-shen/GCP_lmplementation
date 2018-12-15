# GCP_lmplementation
Google Cloud Platform Hosting Implementation guide

## Implementation
Step 1.GCP Application. 
``` 
Reference 01:
※　注意
點開 管理、磁碟、網路、SSH 金鑰
選擇『網路』 → 外部IP → 新增『新的靜態 IP 位址』
※ 如果此步沒做，往後每次除開機IP將會變動

(https://lh5.googleusercontent.com/-x69xzePFVP0/TdesS4b6UsI/AAAAAAAABaU/iDGAZV8PP_8/s0/subnettingcfe8.png)

``` 

Step 2. Creat private and publiv key for SSH Connection.
``` 
Reference 03:

``` 

Step 3. Establish SSH session configuration on GCP consel
``` 
Reference 02:

首先，變更 Key comment。在 Key comment 日期的後面，輸入你申請 Google Cloud Platform 時「@gmail.com」前的名稱。如果申請的 gmail 為 ilovetechcoke@gmail.com 就在日期後面輸入「ilovetechcoke」。

下圖的例子為「techcoke」，完整輸入就是「rsa-key-20170120techcoke」。(* 這裡的日期，會和你操作時的日期不相同，以你當前建立密鑰對的時間為準。)

變更完 Key comment 之後，將 PuTTYgen 上方 OpenSSH authorized_keys 裡面的公鑰資料先做複製，最後再按下「Save private key」，將私鑰儲存到電腦中。
``` 

Step 4. Connecting Securely to Google Compute Engine Server with SFTP
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

Step 5. Python 3.6.6 to Ubuntu 16.04.1
``` 
Ubuntu 14.04 (Trusty), 16.04 (Xenial)

If you are using Ubuntu 14.04 or 16.04, you can use Felix Krull's deadsnakes PPA at https://launchpad.net/~deadsnakes/+archive/ubuntu/ppa:
``` 
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.6
``` 

``` 

Step 6. Install PIP On Debian/Ubuntu
``` 
Note: We will run all commands as the root user, if you are managing your system as a normal user, then use the sudo command to get root privileges or you can as well configure your system to run sudo command without entering a password, it’s possible. Try it out!

# apt install python-pip	#python 2
# apt install python3-pip	#python 3
``` 

Step 7. Install packages using pip and virtualenv
```
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

```

Step 8. Install modules under virtualenv
```
python -m  pip install -r ./requiremenets.txt

```

Step 8. TA-Lib modules under virtualenv
```
Steps:
    sudo apt-get install python3.6-dev

    wget https://github.com/mrjbq7/ta-lib/archive/TA_Lib-0.4.10.tar.gz
    tar -xvf TA_Lib-0.4.10.tar.gz
    cd ./ta-lib-TA_Lib-0.4.10/
    python setup.py install

```
## Environment Configuration
* Windows 10

## Reference 
* [【教學】Google Cloud Platform 申請試用，並建立免費專案！](https://izo.tw/gcp-apply/)
* [【教學】Google Compute Engine ( GCE ) 使用 PuTTY SSH 登入實例](https://www.techcoke.com/2017/01/google-compute-engine-putty-ssh-instances.html)
* [【教學】使用 PuTTYgen 產生 SSH 連線 RSA、DSA 公鑰與私鑰](https://www.techcoke.com/2017/01/puttygen-ssh-rsa-dsa-public-private-key-pair.html)
* [Connecting Securely to Google Compute Engine Server with SFTP](https://winscp.net/eng/docs/guide_google_compute_engine)
* [How do I install Python 3.6 using apt-get?](https://askubuntu.com/questions/865554/how-do-i-install-python-3-6-using-apt-get)
* [How To Install PIP to Manage Python Packages in Linux](https://www.tecmint.com/install-pip-in-linux/)
* [Installing packages using pip and virtualenv](https://packaging.python.org/guides/installing-using-pip-and-virtualenv/#creating-a-virtualenv)
* [Get error on pip install · Issue #285 · freqtrade/freqtrade · GitHub](https://github.com/freqtrade/freqtrade/issues/285)
* [Unable to install TA-Lib on Ubuntu](https://stackoverflow.com/questions/45406213/unable-to-install-ta-lib-on-ubuntu)
