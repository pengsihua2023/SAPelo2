## commands
使用 scontrol show node 命令结合 grep 过滤 GPU 相关信息：  
```
scontrol show node <node_name> | grep Gres
>>Gres=gpu:A100:4(S:0-1),lscratch:3570
```
 
