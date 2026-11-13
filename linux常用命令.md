# Linux 常用命令整理

> 第 2 次实验：Linux 常用命令
> 整理人：杨钊（26计算机3班，2662120070）

## 一、目录与文件操作

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `pwd` | 显示当前所在目录 | `pwd` |
| `ls` | 列出目录内容 | `ls -l` 详细列表，`ls -a` 显示隐藏文件 |
| `cd` | 切换目录 | `cd /home` 进入目录，`cd ..` 返回上一级 |
| `mkdir` | 创建目录 | `mkdir test`，`mkdir -p a/b/c` 递归创建 |
| `rmdir` | 删除空目录 | `rmdir test` |
| `touch` | 创建空文件 / 更新时间戳 | `touch hello.txt` |
| `cp` | 复制文件或目录 | `cp a.txt b.txt`，`cp -r dir1 dir2` |
| `mv` | 移动或重命名 | `mv a.txt b.txt`，`mv a.txt /tmp/` |
| `rm` | 删除文件或目录 | `rm a.txt`，`rm -rf dir`（谨慎使用） |
| `ln` | 创建链接 | `ln -s /data/a.txt link.txt` 软链接 |

## 二、查看文件内容

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `cat` | 一次性显示全部内容 | `cat hello.txt` |
| `more` | 分页查看，只能向下翻 | `more hello.txt` |
| `less` | 分页查看，可上下翻（推荐） | `less hello.txt`，按 `q` 退出 |
| `head` | 查看文件开头 | `head -n 10 hello.txt` |
| `tail` | 查看文件结尾 | `tail -n 20 hello.txt`，`tail -f log` 实时跟踪 |
| `wc` | 统计行数/词数/字节数 | `wc -l hello.txt` |
| `file` | 查看文件类型 | `file hello.txt` |

## 三、查找与搜索

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `find` | 按条件查找文件 | `find / -name "*.txt"`，`find . -type f` |
| `grep` | 在文件内容中搜索字符串 | `grep "root" /etc/passwd`，`grep -rn "abc" .` |
| `which` | 查看命令所在路径 | `which python3` |
| `whereis` | 查找程序的二进制/手册位置 | `whereis ls` |

## 四、权限与用户

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `chmod` | 修改文件权限 | `chmod 755 run.sh`，`chmod +x run.sh` |
| `chown` | 修改文件属主 | `chown user:group a.txt` |
| `whoami` | 显示当前用户 | `whoami` |
| `id` | 显示用户与组信息 | `id` |
| `su` / `sudo` | 切换用户 / 提权执行 | `sudo apt update` |

## 五、压缩与解压

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `tar` | 打包 / 解包 | `tar -czf a.tar.gz dir/`，`tar -xzf a.tar.gz` |
| `zip` / `unzip` | zip 压缩 / 解压 | `zip -r a.zip dir/`，`unzip a.zip` |
| `gzip` / `gunzip` | gz 压缩 / 解压 | `gzip a.txt`，`gunzip a.txt.gz` |

## 六、进程与系统信息

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `ps` | 查看进程 | `ps -ef`，`ps aux` |
| `top` | 动态查看系统资源 | `top`，按 `q` 退出 |
| `kill` | 结束进程 | `kill -9 1234` |
| `df` | 查看磁盘空间 | `df -h` |
| `du` | 查看目录占用 | `du -sh /data` |
| `free` | 查看内存 | `free -h` |
| `uname` | 查看系统信息 | `uname -a` |
| `date` | 查看/设置时间 | `date` |

## 七、重定向与管道

| 符号 | 作用 | 示例 |
| --- | --- | --- |
| `>` | 输出重定向（覆盖） | `ls > list.txt` |
| `>>` | 输出重定向（追加） | `echo hi >> list.txt` |
| `<` | 输入重定向 | `wc -l < list.txt` |
| `\|` | 管道，把前一个命令的输出交给后一个 | `ps -ef \| grep python` |

## 八、网络相关

| 命令 | 作用 | 常用示例 |
| --- | --- | --- |
| `ping` | 测试网络连通性 | `ping -c 4 www.baidu.com` |
| `ip` / `ifconfig` | 查看网卡与 IP | `ip addr` |
| `netstat` / `ss` | 查看端口与连接 | `ss -tlnp` |
| `curl` / `wget` | 下载或请求网页 | `curl -O http://example.com/a.txt` |

## 九、学习小结

1. 文件操作类命令（`ls`、`cd`、`cp`、`mv`、`rm`）是日常使用频率最高的，要熟练到不用查手册。
2. `man 命令` 可以查看完整手册，`命令 --help` 查看简短帮助。
3. 使用 `rm -rf`、`chmod 777` 等命令前一定要确认路径，避免误操作。
4. 管道和重定向能把简单命令组合成强大的处理流程，是 Linux 的精髓之一。
