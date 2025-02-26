
### docker跑deepseek模型
```shell
docker exec -it ollama ollama run deepseek-r1:14b
```

### 加速ollama下载速度
```shell
while true; do
    ollama run mistral-small:24b &
    CMD_PID=$!
    echo $CMD_PID
    sleep 60
    kill -9 $CMD_PID
    wait $CMD_PID 2>/dev/null
done
```
### RagFlow安装教程
