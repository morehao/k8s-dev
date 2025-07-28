# elasticsearch + kibana
Sample Elasticsearch and Kibana

## 部署步骤
### 部署应用
`kubectl apply -f elasticsearch-kibana`
### 验证部署

``` yaml
# 查看部署状态
helm list

# 查看 Kubernetes 资源
kubectl get pods
kubectl get svc
```


### 访问应用

测试连接：

``` bash
# `curl http://<CLUSTER-IP>:<CLUSTER-PORT>/_cluster/health`
curl http://192.168.194.207:9200/_cluster/health
{"cluster_name":"docker-cluster","status":"green","timed_out":false,"number_of_nodes":1,"number_of_data_nodes":1,"active_primary_shards":29,"active_shards":29,"relocating_shards":0,"initializing_shards":0,"unassigned_shards":0,"unassigned_primary_shards":0,"delayed_unassigned_shards":0,"number_of_pending_tasks":0,"number_of_in_flight_fetch":0,"task_max_waiting_in_queue_millis":0,"active_shards_percent_as_number":100.0}%
```

或

``` bash 
# `curl http://<LOCAL-IP>:<NODE-PORT>/_cluster/health`
curl http://localhost:31964/_cluster/health
{"cluster_name":"docker-cluster","status":"green","timed_out":false,"number_of_nodes":1,"number_of_data_nodes":1,"active_primary_shards":29,"active_shards":29,"relocating_shards":0,"initializing_shards":0,"unassigned_shards":0,"unassigned_primary_shards":0,"delayed_unassigned_shards":0,"number_of_pending_tasks":0,"number_of_in_flight_fetch":0,"task_max_waiting_in_queue_millis":0,"active_shards_percent_as_number":100.0}%
```

### 删除应用

`kubectl delete -f elasticsearch-kibana`