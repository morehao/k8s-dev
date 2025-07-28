# my-nginx-app
Sample Nginx Deployment & Service

## 部署步骤
### 部署应用
`kubectl apply -f my-nginx-app`
### 验证部署

``` yaml

# 查看 Kubernetes 资源
kubectl get pods
kubectl get svc
```


### 访问应用

测试连接：

``` bash
curl http://192.168.194.179:9000/
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```

### 删除应用

`kubectl delete -f my-nginx-app`