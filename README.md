# slam
実行手順  
ros-docker-guiディレクトリで  

- `vim Makefile`

cpu_ros_noeticの見出しの部分を編集

nerdctlの部分とかimage名を自身の環境に置き換え

- `make cpu_ros_noetic`

ここ時間かかる

- `nerdctl push your_account/ros-noetic:cpu`

orbslam3_dockerディレクトリで  

- `vim Dockerfile`

一行目を書き換え  

- `nerdctl build -t your_account/orbslam3:latest`

僕はここでメモリが足りなくなってフリーズした，こっから先は未知　　

- `nerdctl push your_account/orbslam3:latest`

slam.yamlのimageを書き換えて　　

- `kubectl apply -f slam.yaml`

これがうまくいくと熱い  

あとは参考サイトに従ってコンテナの中に入ったりする　　 


# 参考
[slam](https://github.com/jahaniam/orbslam3_docker)  

[ros入りubuntu](https://github.com/turlucode/ros-docker-gui)
