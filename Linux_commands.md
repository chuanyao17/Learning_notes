MobaXterm
vi +檔案名 可以用vim開啟
VIM
	- 直接打i可以編輯
	- :w 檔名.副檔名 可以存檔
sftp
	-put/get 上下載檔案
	或是直接用拖拉的

Ubuntu (linux指令)

pwd:查看當前路徑
sudo: 使用root權限
sh: 使用shell檔(xxx.sh)
~/: home directory
./: 執行執行檔 (./xxxx.exe)
rm: 移除檔案,  rm xxxx -rf(遞迴強制)
vi, vim:都是編輯器
CC: c語言
CXX: C++
export 讓外部也看的到
gf: 可以確認路徑， ctrl+o 可以退出
find: find ~/ -name "xxx.xx"

export CC=/usr/bin/mpicc
export CXX=/usr/bin/mpic++
cmake -DCMAKE_CXX_COMPILER=/usr/bin/mpic++ ../


