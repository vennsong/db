mongobackup手册及mongobackup下载地址

http://dl.nosqldb.org/mongobackup

http://dl.nosqldb.org/mongobackup_user_guide_zh_CN.pdf

简介

mongobackup 是用于复制集的增量备份与恢复工具，恢复时，需要结合全量备份与恢复使用。

增量备份

普通备份

mongobackup -u ccj-p'123'--port27020 -h10.0.4.91--backup 
 

流模式备份

mongobackup -u ccj-p'123'--port27020–h10.0.4.91--backup--stream 
 

都可以指定备份初始时间点

mongobackup -u ccj-p'123'--port27020 -h10.0.4.91--backup-s1385367056,1 
 

增量恢复

必须指定起止时间点，配合全备，可以恢复到任意时间点（结束时间点），开始时间点可以理解为全备的时间点。

mongobackup -u ccj-p'123'--port27020-h10.0.4.91--recovery  -s1385367098,27350 -t 1385367132,35490 ./backup/
