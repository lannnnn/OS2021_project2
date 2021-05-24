安装RealEvo-IDE,点击File->新建SylixOS base工程,设置参考文件2_RealEvoIDE使用手册第7-20页,IP可以照抄，开启simulator的虚拟机,将网络IP地址设置为相同地址
2.1,2.2 参考文件4_SylixOS应用开发手册13.6.2代码,在/libsylixos/SylixOS/system/device/input/下有键盘输入信号的定义文件
问题：1.在哪里捕捉执行？  /libsylixos/SylixOS/shell/ttinyShell/ttinyShellReadline.c/__tshellCharTab row 771
    查询已输入的指令是  
    					1.完整的func 展示args（可利用help的内容）
                        2.不完整的func 匹配（可利用help的内容）
      2. 关键字和参数的联想，可以调用/libsylixos/SylixOS/shell/ttinyShell/ttinyShellSysCmd.c/的函数
      3. 内置管道定义在/libsylixos/SylixOS/system/device/pipe/下，但是在代码中使用的函数，命令行的管道没有实现，需要在shellReadline捕捉的地方加上|的捕捉
2.3 实现find, grep, awk, sed指令
    找到Base工程下的/libsylixos/SylixOS/shell/ttinyShell目录,参考文件7_SylixOS shell用户手册第2页添加部分加入新的shell指令

