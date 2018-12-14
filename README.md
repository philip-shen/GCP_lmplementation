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

## Environment Configuration
* Windows 10

## Reference 
*[【教學】Google Cloud Platform 申請試用，並建立免費專案！](https://izo.tw/gcp-apply/)
*[[教學] Google Compute Engine ( GCE ) 使用 PuTTY SSH 登入實例](https://www.techcoke.com/2017/01/google-compute-engine-putty-ssh-instances.html)
*[[教學] 使用 PuTTYgen 產生 SSH 連線 RSA、DSA 公鑰與私鑰](https://www.techcoke.com/2017/01/puttygen-ssh-rsa-dsa-public-private-key-pair.html)