# bt_crack
Bt Pro for free


方法1

安装bt5.9

    yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh

复制代码


升级到专业版

    wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro

复制代码


开心

    >/www/server/panel/data/userInfo.json
    /etc/init.d/bt restart

复制代码



反正就这样就可以装付费插件了，到期时间显示当天




还有一种方法(方法2)，先正常安装5.9.2专业版，然后用5.9.0的common.py替换5.9.2的，再按照网上流传的修改方法(164行修改为[data = {'status' : True,'msg' : {'endtime' : 32503651199 }};])

安装bt5.9

    yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh

复制代码


升级到专业版

    wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro

复制代码


替换common.py

    cd /www/server && cp -r panel panel-bak
    wget http://download.bt.cn/install/update/LinuxPanel-5.9.0_pro.zip
    unzip -o LinuxPanel-5.9.0_pro.zip panel/class/common.py
    rm -f LinuxPanel-5.9.0_pro.zip

复制代码


开心

    sed -i "s/data = panelAuth.panelAuth().get_order_status(None);/data = {'status' : True,'msg' : {'endtime' : 32503651199 }};/" /www/server/panel/class/common.py
    >/www/server/panel/data/userInfo.json
    /etc/init.d/bt restart

复制代码


这样的话，就是显示2099年到期了


————————————————

不管你用不用的上，建议把这几个老版本下载保存一份

脚本

    http://download.bt.cn/install/install.sh
    http://download.bt.cn/install/update_pro.sh

复制代码


面板文件

    http://download.bt.cn/install/update/LinuxPanel-5.9.0.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.1.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.2.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.0_pro.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.1_pro.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.2_pro.zip

复制代码


主要是安装脚本和5.9.0和5.9.2这三个

    http://download.bt.cn/install/install.sh
    http://download.bt.cn/install/update/LinuxPanel-5.9.0_pro.zip
    http://download.bt.cn/install/update/LinuxPanel-5.9.2_pro.zip

复制代码


——————————————————————————————

一键脚本


    #确保有wget和unzip
    yum install -y wget unzip

    apt install -y wget unzip

复制代码


方法1

    #以下代码一起复制粘贴回车
    yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh && \
    wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro && \
    >/www/server/panel/data/userInfo.json && \
    /etc/init.d/bt restart && /etc/init.d/bt default

复制代码


方法2

    #以下代码一起复制粘贴回车
    wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh && \
    wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro && \
    cd /www/server && cp -r panel panel-bak && \
    wget http://download.bt.cn/install/update/LinuxPanel-5.9.0_pro.zip && \
    unzip -o LinuxPanel-5.9.0_pro.zip panel/class/common.py && rm -f LinuxPanel-5.9.0_pro.zip && \
    sed -i "s/data = panelAuth.panelAuth().get_order_status(None);/data = {'status' : True,'msg' : {'endtime' : 32503651199 }};/" /www/server/panel/class/common.py && \
    >/www/server/panel/data/userInfo.json && \
    /etc/init.d/bt restart && /etc/init.d/bt default

复制代码

Reference: https://www.hostloc.com/thread-747391-1-1.html
