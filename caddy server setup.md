# Setup Caddy on EC2

## Step1 Install
```
https://caddyserver.com/docs/install
```
Edit the proxy
```
sudo nano /etc/caddy/Caddyfile
```
```
:80 {
    reverse_proxy localhost:3000
} 
```
Remember port 80 defaults to http while 

Restart Caddy 
```
sudo systemctl restart caddy
```

systemctl status caddy