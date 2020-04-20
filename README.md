# Udisk-DOS
# 用U盘DOS修改主板硬件MAC地址

## 步骤
### 一、DOS系统构建

1. 调整电脑bios到Legacy Only  
2. 使用UltraISO烧录MSDOS7.10.iso到U盘

### 二、复制mac149d工具包到U盘

### 三、重启电脑并设置bios引导首选项为U盘，进入DOS系统

### 四、烧写更新网卡MAC

#### 方法一
1. 进入MAC文件夹  
2. 输入命令 mac c 001122334455 (即是你需要写入的的mac地址)，然后等系统出现sucess画面如下  
![方法一如图](https://github.com/shen/SwiftNotes/blob/master/image/1.png)  
如果此方法失效，请看方法二  

#### 方法二
1. 进入MAC文件夹下，主板网卡对应型号文件夹，比如intel i211 千兆网卡就进入Int211  
2. 运行eeupdate.exe，查看网卡的nic 的id号，我的intel网卡nic id=1  
3. 备份网卡硬件设置，输入 eeupdate /all /dump 将网卡的硬件配置存成.eep文件。（此方法适用于intel的82574、82573、I210等。）  
4. 执行 eeupdate /nic=1 /mac=001122334455 命令， 将网卡的MAC修改为00-11-22-33-44-55(即是你需要写入的的mac地址)。  
![方法二如图](https://github.com/shen/SwiftNotes/blob/master/image/1.png)  
