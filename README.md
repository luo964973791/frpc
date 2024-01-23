### 一、上传frpc到/usr/local/bin目录下,frpc官网https://www.natfrp.com

```javascript
git clone https://github.com/luo964973791/frpc.git && cd frpc && chmod a+x frpc
mv frpc /usr/local/bin
```
### 二、设置server

```javascript
cat /lib/systemd/system/frpc.service 
[Unit]
Description=SakuraFrp Service
After=network.target
[Service]
Type=idle
User=root
Restart=on-failure
RestartSec=60s
ExecStart=/usr/local/bin/frpc -f 20xxxx:xxxxx
[Install]
WantedBy=multi-user.target
```
### 三、设置开机自启

```javascript
systemctl enable frpc
systemctl start frpc
systemctl status frpc
```
