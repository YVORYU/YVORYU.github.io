# Linux命令大全

这是一个全面的Linux命令参考手册，旨在帮助开发者和系统管理员更好地理解和使用Linux命令。

## 目录

1. [文件管理命令](#文件管理命令)
2. [文档编辑命令](#文档编辑命令)
3. [系统管理命令](#系统管理命令)
4. [磁盘管理命令](#磁盘管理命令)
5. [网络通讯命令](#网络通讯命令)
6. [系统安全命令](#系统安全命令)
7. [备份压缩命令](#备份压缩命令)
8. [进程管理命令](#进程管理命令)
9. [文本处理命令](#文本处理命令)
10. [软件包管理命令](#软件包管理命令)
11. [系统监控命令](#系统监控命令)

## 文件管理命令

### ls - 显示目录内容
- 格式：`ls [选项] [目录名]`
- 常用选项：
  - `-l`: 以长格式显示文件和目录信息
  - `-a`: 显示所有文件，包括隐藏文件
  - `-h`: 以人类可读的方式显示文件大小
- 示例：
  ```bash
  ls -l /home
  ls -la
  ls -lh
  ```

### cd - 切换目录
- 格式：`cd [目录名]`
- 常用用法：
  - `cd /`: 切换到根目录
  - `cd ~`: 切换到用户主目录
  - `cd ..`: 切换到上级目录

### pwd - 显示当前工作目录
- 格式：`pwd`
- 示例：
  ```bash
  pwd
  ```

### mkdir - 创建目录
- 格式：`mkdir [选项] 目录名`
- 常用选项：
  - `-p`: 创建多级目录
- 示例：
  ```bash
  mkdir test
  mkdir -p test/test1/test2
  ```

## 文档编辑命令

### vim - 文本编辑器
- 格式：`vim [文件名]`
- 常用模式：
  - 命令模式：按`Esc`进入
  - 插入模式：按`i`进入
  - 底行模式：按`:`进入
- 常用命令：
  - `:w`: 保存
  - `:q`: 退出
  - `:wq`: 保存并退出

### cat - 查看文件内容
- 格式：`cat [选项] 文件名`
- 常用选项：
  - `-n`: 显示行号
- 示例：
  ```bash
  cat /etc/passwd
  cat -n file.txt
  ```

## 系统管理命令

### ps - 显示进程状态
- 格式：`ps [选项]`
- 常用选项：
  - `-ef`: 显示所有进程
  - `-aux`: 显示详细信息
- 示例：
  ```bash
  ps -ef
  ps aux
  ```

### top - 动态显示进程信息
- 格式：`top`
- 常用操作：
  - `q`: 退出
  - `P`: 按CPU使用率排序
  - `M`: 按内存使用率排序

## 磁盘管理命令

### df - 显示磁盘空间使用情况
- 格式：`df [选项]`
- 常用选项：
  - `-h`: 以人类可读的方式显示
- 示例：
  ```bash
  df -h
  ```

### du - 显示目录或文件大小
- 格式：`du [选项] [目录或文件名]`
- 常用选项：
  - `-h`: 以人类可读的方式显示
  - `-s`: 仅显示总计
- 示例：
  ```bash
  du -sh /home
  ```

## 网络通讯命令

### ping - 测试网络连接
- 格式：`ping [选项] 目标主机`
- 常用选项：
  - `-c`: 指定发送次数
- 示例：
  ```bash
  ping -c 4 www.google.com
  ```

### ifconfig - 配置网络接口
- 格式：`ifconfig [接口名]`
- 示例：
  ```bash
  ifconfig
  ifconfig eth0
  ```

## 系统安全命令

### chmod - 修改文件权限
- 格式：`chmod [选项] 模式 文件名`
- 常用选项：
  - `-R`: 递归修改
- 示例：
  ```bash
  chmod 755 file.txt
  chmod -R 644 directory
  ```

### chown - 修改文件所有者
- 格式：`chown [选项] 用户:组 文件名`
- 常用选项：
  - `-R`: 递归修改
- 示例：
  ```bash
  chown user:group file.txt
  ```

## 备份压缩命令

### tar - 打包压缩文件
- 格式：`tar [选项] 文件名`
- 常用选项：
  - `-c`: 创建新的归档文件
  - `-x`: 解压文件
  - `-z`: 使用gzip压缩
  - `-f`: 指定归档文件名
- 示例：
  ```bash
  tar -czf archive.tar.gz directory/
  tar -xzf archive.tar.gz
  ```

### gzip - 压缩文件
- 格式：`gzip [选项] 文件名`
- 常用选项：
  - `-d`: 解压缩
- 示例：
  ```bash
  gzip file.txt
  gzip -d file.txt.gz
  ```

## 进程管理命令

### kill - 终止进程
- 格式：`kill [选项] 进程ID`
- 常用选项：
  - `-9`: 强制终止
- 示例：
  ```bash
  kill 1234
  kill -9 1234
  ```

### nohup - 后台运行命令
- 格式：`nohup 命令 &`
- 示例：
  ```bash
  nohup ./script.sh &
  ```

## 文本处理命令

### grep - 文本搜索
- 格式：`grep [选项] 模式 文件名`
- 常用选项：
  - `-i`: 忽略大小写
  - `-r`: 递归搜索目录
  - `-n`: 显示行号
- 示例：
  ```bash
  grep -i "error" /var/log/syslog
  grep -rn "function" /src/
  ```

### sed - 流编辑器
- 格式：`sed [选项] '命令' 文件名`
- 常用命令：
  - `s/旧/新/g`: 替换文本
  - `d`: 删除行
  - `p`: 打印行
- 示例：
  ```bash
  sed 's/hello/world/g' file.txt
  sed -i '1d' file.txt
  ```

### awk - 文本处理工具
- 格式：`awk [选项] '模式{动作}' 文件名`
- 常用用法：
  - `$0`: 整行
  - `$1,$2`: 第1,2列
  - `NR`: 行号
- 示例：
  ```bash
  awk '{print $1}' file.txt
  awk 'NR>1{print $1,$3}' data.csv
  ```

## 软件包管理命令

### apt - Debian/Ubuntu包管理器
- 格式：`apt [选项] 子命令`
- 常用子命令：
  - `update`: 更新软件包列表
  - `install`: 安装软件包
  - `remove`: 移除软件包
- 示例：
  ```bash
  apt update
  apt install nginx
  apt remove mysql-server
  ```

### yum - Red Hat/CentOS包管理器
- 格式：`yum [选项] 子命令`
- 常用子命令：
  - `install`: 安装软件包
  - `update`: 更新软件包
  - `remove`: 移除软件包
- 示例：
  ```bash
  yum install httpd
  yum update
  yum remove php
  ```

## Web服务器管理案例

### Nginx性能调优
- 场景：网站响应缓慢，需要分析Nginx访问日志并优化配置
- 解决方案：
  ```bash
  # 分析访问最频繁的IP地址
  awk '{print $1}' /var/log/nginx/access.log | sort | uniq -c | sort -nr | head -n 10

  # 查看响应时间最长的请求
  awk '$NF > 3{print $7}' /var/log/nginx/access.log | sort | uniq -c | sort -nr

  # 检查Nginx配置并优化worker进程
  nginx -t
  vim /etc/nginx/nginx.conf
  systemctl reload nginx
  ```

### Apache日志分析
- 场景：分析网站访问特征和异常请求
- 解决方案：
  ```bash
  # 统计HTTP状态码分布
  cat /var/log/apache2/access.log | cut -d '"' -f3 | cut -d ' ' -f2 | sort | uniq -c | sort -rn

  # 查找可疑的SQL注入尝试
  grep -i "union\\|select\\|insert" /var/log/apache2/access.log

  # 分析高频访问的URL
  awk '{print $7}' /var/log/apache2/access.log | sort | uniq -c | sort -nr | head -n 10
  ```

## 系统运维案例

### 服务器性能问题排查
- 场景：服务器负载高，响应慢
- 解决方案：
  ```bash
  # 查看系统负载和CPU使用率
  top -c
  mpstat 1 5

  # 分析内存使用情况
  free -h
  vmstat 1 5

  # 检查磁盘IO状态
  iostat -xz 1
  iotop -o

  # 查看网络连接状态
  netstat -nat | awk '{print $6}' | sort | uniq -c | sort -n
  ```

### 日志监控和告警
- 场景：监控系统关键日志并设置告警
- 解决方案：
  ```bash
  # 实时监控系统日志
  tail -f /var/log/syslog | grep -i "error\\|failed\\|warning" --color

  # 统计错误日志数量
  grep -i "error" /var/log/syslog | awk '{print $1,$2,$3}' | sort | uniq -c

  # 设置日志告警（使用mail命令）
  tail -f /var/log/syslog | grep -i "error" | while read line; do
    echo "$line" | mail -s "System Error Alert" admin@example.com
  done
  ```

## 安全排查案例

### 可疑进程检测
- 场景：服务器可能被入侵，需要排查可疑进程
- 解决方案：
  ```bash
  # 查看CPU占用异常的进程
  ps aux | sort -nr -k 3 | head -10

  # 检查隐藏进程
  ps -ef | awk '$3==1{print}'

  # 查看进程建立的网络连接
  lsof -i -n -P | grep "ESTABLISHED"

  # 检查定时任务
  crontab -l
  ls -la /etc/cron.*
  ```

### 系统安全审计
- 场景：定期进行系统安全检查
- 解决方案：
  ```bash
  # 检查登录失败记录
  grep "Failed password" /var/log/auth.log

  # 查看最近登录用户
  last | head -n 20

  # 检查系统用户变更
  cat /etc/passwd | grep -v nologin | grep -v false

  # 检查特权用户
  grep -v -E "^#" /etc/sudoers
  ```

## 系统监控命令

### free - 显示内存使用情况
- 格式：`free [选项]`
- 常用选项：
  - `-h`: 以人类可读方式显示
  - `-s`: 持续显示
- 示例：
  ```bash
  free -h
  free -s 5
  ```

### vmstat - 系统资源统计
- 格式：`vmstat [选项] [延时 [次数]]`
- 显示信息：
  - CPU使用率
  - 内存使用
  - 交换分区使用
  - IO状态
- 示例：
  ```bash
  vmstat 1 5
  vmstat -S M
  ```

### iostat - IO统计信息
- 格式：`iostat [选项] [延时 [次数]]`
- 常用选项：
  - `-x`: 显示扩展统计信息
  - `-k`: 以KB为单位显示
- 示例：
  ```bash
  iostat -x 1 5
  iostat -k
  ```

## 用户管理命令

### useradd - 创建新用户
- 格式：`useradd [选项] 用户名`
- 常用选项：
  - `-m`: 创建用户主目录
  - `-s`: 指定登录shell
  - `-g`: 指定用户组
- 实际案例：
  ```bash
  # 创建开发用户并设置shell
  useradd -m -s /bin/bash developer
  # 创建web服务用户并加入www组
  useradd -m -g www-data webuser
  ```

### passwd - 修改用户密码
- 格式：`passwd [选项] [用户名]`
- 常用选项：
  - `-l`: 锁定用户账号
  - `-u`: 解锁用户账号
- 实际案例：
  ```bash
  # 修改当前用户密码
  passwd
  # 修改指定用户密码
  sudo passwd webuser
  # 锁定用户账号
  sudo passwd -l suspicious_user
  ```

## 系统服务管理命令

### systemctl - 控制系统服务
- 格式：`systemctl [选项] 动作 服务名`
- 常用动作：
  - `start`: 启动服务
  - `stop`: 停止服务
  - `restart`: 重启服务
  - `status`: 查看服务状态
  - `enable`: 设置开机启动
- 实际案例：
  ```bash
  # 启动并设置Nginx开机自启
  sudo systemctl start nginx
  sudo systemctl enable nginx
  
  # 重启MySQL服务并查看状态
  sudo systemctl restart mysql
  sudo systemctl status mysql
  ```

## 高级文本处理命令

### sort - 文本排序
- 格式：`sort [选项] 文件名`
- 常用选项：
  - `-n`: 按数字排序
  - `-r`: 逆序排序
  - `-k`: 按指定列排序
- 实际案例：
  ```bash
  # 对日志按访问量排序
  cat access.log | cut -d' ' -f1 | sort | uniq -c | sort -nr
  
  # 对CSV文件按第三列数字排序
  sort -t',' -k3,3n data.csv
  ```

### uniq - 去除重复行
- 格式：`uniq [选项] [输入文件] [输出文件]`
- 常用选项：
  - `-c`: 显示重复次数
  - `-d`: 仅显示重复行
- 实际案例：
  ```bash
  # 统计TOP 10 IP访问
  cat access.log | awk '{print $1}' | sort | uniq -c | sort -nr | head -n 10
  
  # 查找重复的文件名
  ls -l | awk '{print $9}' | sort | uniq -d
  ```

## 网络工具命令

### curl - 数据传输工具
- 格式：`curl [选项] URL`
- 常用选项：
  - `-X`: 指定请求方法
  - `-H`: 设置请求头
  - `-d`: 发送POST数据
- 实际案例：
  ```bash
  # 测试REST API
  curl -X POST -H "Content-Type: application/json" \
       -d '{"name":"test"}' \
       https://api.example.com/users
  
  # 下载文件并显示进度
  curl -O -L -# https://example.com/file.zip
  ```

### netstat - 网络连接状态
- 格式：`netstat [选项]`
- 常用选项：
  - `-tunlp`: 显示所有监听端口
  - `-an`: 显示所有连接
- 实际案例：
  ```bash
  # 查看Web服务器端口
  netstat -tunlp | grep :80
  
  # 检查系统所有TCP连接
  netstat -ant | awk '{print $6}' | sort | uniq -c
  ```

## 贡献

欢迎提交问题和改进建议！如果你发现了错误或者有新的命令要添加，请提交 Issue 或 Pull Request。

## 许可证

本项目采用 MIT 许可证，详情请见 [LICENSE](LICENSE) 文件。