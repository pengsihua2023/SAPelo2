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

## 与Tensorflow兼容的cuda，cudnn版本
[深度学习TensorFlow—GPU，CUDA、cuDNN](https://blog.csdn.net/shine_Lee_/article/details/128753290)  
Tensorflow_GPU-2.5.0兼容的 CUDA 11.2, CuDNN 8.1  
Sapelo2： module load cuDNN/8.1.0.77-CUDA-11.2.1  
## Sapelo2中cuda与cudnn版本
```
  CUDA:
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      CUDA (formerly Compute Unified Device Architecture) is a parallel computing platform and programming model created by NVIDIA and implemented by the graphics processing units (GPUs) that they produce. CUDA gives developers
      access to the virtual instruction set and memory of the parallel computational elements in CUDA GPUs.

     Versions:
        CUDA/10.0.130
        CUDA/10.1.243
        CUDA/11.1.1-GCC-10.2.0
        CUDA/11.2.1-GCC-8.3.0
        CUDA/11.2.1
        CUDA/11.3.1
        CUDA/11.4.1
        CUDA/11.7.0
        CUDA/12.0.0

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  For detailed information about a specific "CUDA" package (including how to load the modules) use the module's full name.
  Note that names that have a trailing (E) are extensions provided by other modules.
  For example:

     $ module spider CUDA/12.0.0

```
## CuDNN
```
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  cuDNN:
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      The NVIDIA CUDA Deep Neural Network library (cuDNN) is a GPU-accelerated library of primitives for deep neural networks.

     Versions:
        cuDNN/7.6.2.24-CUDA-10.1.243
        cuDNN/7.6.4.38-CUDA-10.0.130
        cuDNN/8.0.4.30-CUDA-11.1.1
        cuDNN/8.1.0.77-CUDA-11.2.1
        cuDNN/8.2.1.32-CUDA-11.3.1
        cuDNN/8.2.2.26-CUDA-11.4.1
        cuDNN/8.4.1.50-CUDA-11.7.0
        cuDNN/8.8.0.121-CUDA-12.0.0
        cuDNN/8.9.2.26-CUDA-12.1.1

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  For detailed information about a specific "cuDNN" package (including how to load the modules) use the module's full name.
  Note that names that have a trailing (E) are extensions provided by other modules.
  For example:

     $ module spider cuDNN/8.9.2.26-CUDA-12.1.1
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


```

## GenSLM
```
  GenSLM: GenSLM/0.0.4a1-foss-2022a-CUDA-11.7.0
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      GenSLMs: Genome-scale language models reveal SARS-CoV-2 evolutionary dynamics 


    This module can be loaded directly: module load GenSLM/0.0.4a1-foss-2022a-CUDA-11.7.0

    Help:
      Description
      ===========
      GenSLMs: Genome-scale language models reveal SARS-CoV-2 evolutionary dynamics
      
      
      More information
      ================
       - Homepage: https://github.com/ramanathanlab/genslm

```
## ESM-2
```
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ESM-2: ESM-2/2.0.0-foss-2022a-CUDA-11.7.0
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      ESM-2 outperforms all tested single-sequence protein language models across a range of structure prediction tasks. ESMFold harnesses the ESM-2 language model to generate accurate structure predictions end to end directly
      from the sequence of a protein.


    This module can be loaded directly: module load ESM-2/2.0.0-foss-2022a-CUDA-11.7.0

    Help:
      Description
      ===========
      ESM-2 outperforms all tested single-sequence protein language models
       across a range of structure prediction tasks. ESMFold harnesses the ESM-2 language model to generate
       accurate structure predictions end to end directly from the sequence of a protein.
      
      
      More information
      ================
       - Homepage: https://github.com/facebookresearch/esm
      
      
      Included extensions
      ===================
      antlr4-python3-runtime-4.9.3, fair-esm-2.0.0, omegaconf-2.2.3
      

```
## Alphafold
```
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  AlphaFold:
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      AlphaFold can predict protein structures with atomic accuracy even where no similar structure is known. This package of AlphaFold contains patches for ColabFold.

     Versions:
        AlphaFold/2.3.1-foss-2022a-CUDA-11.7.0
        AlphaFold/2.3.4-foss-2022a-CUDA-11.7.0-ColabFold

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  For detailed information about a specific "AlphaFold" package (including how to load the modules) use the module's full name.
  Note that names that have a trailing (E) are extensions provided by other modules.
  For example:

     $ module spider AlphaFold/2.3.4-foss-2022a-CUDA-11.7.0-ColabFold
--------------------------------------------------------------------------------------------------------------------------------------------

```
## Pymol
```
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  PyMOL: PyMOL/2.5.0-foss-2022a
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      PyMOL is a Python-enhanced molecular graphics tool. It excels at 3D visualization of proteins, small molecules, density, surfaces, and trajectories. It also includes molecular editing, ray tracing, and movies. Open Source
      PyMOL is free to everyone! 


    This module can be loaded directly: module load PyMOL/2.5.0-foss-2022a

    Help:
      Description
      ===========
      PyMOL is a Python-enhanced molecular graphics tool. It excels at 3D             
      visualization of proteins, small molecules, density, surfaces, and trajectories.
      It also includes molecular editing, ray tracing, and movies. Open Source PyMOL  
      is free to everyone!
      
      
      More information
      ================
       - Homepage: https://github.com/schrodinger/pymol-open-source
      
      
      Included extensions
      ===================
      Pmw-2.0.1, PyMOL-2.5.0

```
## schrodinger
```
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  schrodinger:
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Description:
      chemical simulation software for use in pharmaceutical, biotechnology, and materials research.

     Versions:
        schrodinger/2022-3
        schrodinger/2023-3

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  For detailed information about a specific "schrodinger" package (including how to load the modules) use the module's full name.
  Note that names that have a trailing (E) are extensions provided by other modules.
  For example:

     $ module spider schrodinger/2023-3
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


```
