在Ubuntu安装gcc-9，g++-9时，

sudo apt install gcc-9 g++-9
发现无法定位软件包，随即搜索得知需添加ppa源，

sudo add-apt-repository ppa:ubuntu-toolchain-r/test -y
但是添加源时无反应，便手动添加，在https://launchpad.net/~ubuntu-toolchain-r/+archive/ubuntu/test?field.series_filter=trusty网址中找到ppa源，添加。

sudo gedit /etc/apt/sources.list


将ppa源复制到sources.list文件中，保存退出。

deb http://ppa.launchpad.net/ubuntu-toolchain-r/test/ubuntu bionic main 
deb-src http://ppa.launchpad.net/ubuntu-toolchain-r/test/ubuntu bionic main 
添加ppa证书，ID复制网页中

 

sudo apt-key adv --keyserver keyserver.ubuntu.com --recv ID
 证书添加完毕后，执行更新。

sudo apt-get update && sudo apt-get upgrade
更新完成后即可安装gcc-9，g++-9。
