
# 使用ansible-playbook推送安装nginx
> 本文主要介绍了如何将ansible-playbook投入生产中，下面我们以推送安装nginx举例

#### 1. 思路：
- 现在主机上编译，配置好nginx，
- 然后将安装程序目录打包
- 最后用ansible分发下去

#### 2. 流程图如下：
![image](https://s1.ax1x.com/2018/10/11/itW3sf.png)


#### 3. 执行配置过程
##### 3.1 编译安装nginx详见： [编译安装Nginx](http://note.youdao.com/noteshare?id=b73effc8df9b50ad2b63f8f0ed2ba676&sub=0D01183B5BCA44C593B382FB2AE2FE3D)

##### 3.2 创建ansible roles目录结构

> 说明：
> - roles下有两个角色，common为一些准备操作，install为安装nginx的操作
> - 每个角色下面又有6个目录，
>   - handlers 下面是当发生改变时，要执行的操作，通常用在配置文件发生改变，重启服务等
>   - flies 为安装时用到的一些文件
>   - meta 为说明信息，说明角色依赖等信息
>   - tasks 里面为核心配置文件
>   - templates 通常存一些配置文件，启动脚本等模板文件
>   - vars 下为定义的变量
 
##### 3.3 将安装好的nginx程序包打包，并放到 `$/install/files/` 下面，启动脚本 放入`$/install/templates`中，


##### 3.4 在common目录下定义安装nginx的依赖包任务

##### 3.5 定义变量

##### 3.6 定义拷贝操作
  
##### 3.7 创建安装总线

##### 3.8 创建执行总线 

##### 3.9 创建入口配置文件
