# README
1. 先用apt—get指令更新一下库文件以及jdk
`sudo apt-get update
 sudo apt-get install openjdk-7-jdk
 sudo apt-get install unzip`
2. 这里遇到很多问题，jdk7始终装不上，手动装oracle jdk，然后配置环境变量，配置环境变量需要修改bash文件,在此不做赘述
3. apt—get指令安装ant
`sudo apt-get install ant`
4. 下载编译systemC
`../cnofigure CXX=g++ --disable-async-updates
sudo make install`
5. 编译dol,这里要先修改下build_zip.xml文件里systemC的位置
`ant -f build_zip.xml all`
6. 跑下样例
`ant -f runexample.xml -Dnumber=1`

* 附一张成功截图 
![cmd markdown收费才能粘贴图片真尼玛坑啊](http://a1.qpic.cn/psb?/4e8c8ef6-8dff-4ace-a581-ed29b1252f80/jD4VYzSngNr52TuRerzIcPSM2JGdFZQXQjazRjj5vXg!/b/dAsBAAAAAAAA&bo=8QOAAgAAAAADB1I!&rf=viewer_4)
#### 写在最后
为了不换源，特意下了16.04，结果jdk7死活装不上，oracle jdk最后一步build失败，javac路径问题，网上只给了windows下的解决方案，于是重装，装在了电脑硬盘里，下了jdk8，结果还是最后一步编译失败，ubuntu反复装了不下五次的我最终决定拿ta配置好的ubuntu来跑。





