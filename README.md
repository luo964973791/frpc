### 一、上传frpc到/usr/local/bin目录下,frpc官网https://www.natfrp.com

```javascript

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
ExecStart=/usr/local/bin/frpc -f 20o5w1fpztg3vmaj:5055971
[Install]
WantedBy=multi-user.target
```
### 三、设置开机自启

```javascript
systemctl enable frpc
systemctl start frpc
systemctl status frpc
```
