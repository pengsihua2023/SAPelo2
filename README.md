# SAPelo2
[OnDemand login](https://ondemand.gacrc.uga.edu/pun/sys/dashboard)  
[GPU Computing on Sapelo2](https://wiki.gacrc.uga.edu/wiki/GPU)  
[Running Jobs on Sapelo2](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2)  
[Sample job submission scripts](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#Sample_job_submission_scripts)  
[Environment Variables exported by batch jobs](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#Environment_Variables_exported_by_batch_jobs)  
[Discovering if a partition (queue) is busy](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#Discovering_if_a_partition_.28queue.29_is_busy)  
[How to run an interactive job with Graphical User Interface capabilities](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#How_to_run_an_interactive_job_with_Graphical_User_Interface_capabilities)  
[How to cancel (delete) a running or pending job](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#How_to_cancel_.28delete.29_a_running_or_pending_job)  
[How to check resource utilization of a running or finished job](https://wiki.gacrc.uga.edu/wiki/Running_Jobs_on_Sapelo2#How_to_check_resource_utilization_of_a_running_or_finished_job)  
[OnDemand](https://wiki.gacrc.uga.edu/wiki/OnDemand)  


## tips 
How to display GPU memory usage in real time on a Linux machine?  
Use nvidia-smi command: watch -n 1 nvidia-smi  

## 无密钥登录配置
如果你想设置无密码 SSH 登录以便在你的登录机（或任何其他计算机）与其他服务器之间自动进行 SSH 连接，你应该在你的登录机上运行 ssh-keygen -t rsa -b 2048。这将在你的登录机上生成一对 SSH 密钥（一个私钥和一个公钥），然后你可以将生成的公钥复制到需要无密码登录的每一个远程服务器的相应位置。这里是整个过程的具体步骤：  
### 步骤 1: 生成密钥对
在你的登录机的终端中运行：  
```
ssh-keygen -t rsa -b 2048
```
按照提示操作：  
当系统询问“Enter file in which to save the key”时，你可以按回车键使用默认位置（通常是 ~/.ssh/id_rsa）。  
系统接着会问你是否要设置密钥的密码（passphrase）。如果你的目标是无密码登录，这里应当留空，直接按回车键。  
### 步骤 2: 复制公钥到远程服务器
使用 ssh-copy-id 工具将公钥复制到每个远程服务器上。运行： 
```
ssh-copy-id -i ~/.ssh/id_rsa.pub sp96859@b1-2

```
这里，your_username 是你在远程服务器上的用户名，remote_host 是远程服务器的主机名或 IP 地址。这个命令会要求你输入一次远程服务器的密码。 

### 已经配置好ssh无密钥的登录机
ss-sub4  
