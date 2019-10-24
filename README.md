# linux_std
linux_std



ftp_address=192.144.205.210
user=root
password=@

#本地变更的文件夹
local_path="C:/Users/kylin/Desktop/sh/java1"
#服务器上的jar地址路径
romote_path="/log/zhongxin/"
cd $local_path

for dir in $(ls .)
do
echo $dir
done   

sftp ${user}@${ftp_address} << EOF

set xfer:clobber on

cd ${romote_path}

lcd ${local_path}


get "zhongxin0608-6.log"

bye

EOF


