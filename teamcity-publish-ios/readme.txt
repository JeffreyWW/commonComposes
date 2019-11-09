说明:
1.关于gitlab时区问题:
gitlab在提交新代码后,teamcity服务端拉代码会报cookie错误,具体原因为时区有误,环境变量设置为TZ=CST-8可以解决显示问题
但实际时间并不对,在报错的log日志中,有cookie失效时间,最后可以看到和当前时间不一致
解决办法:
进去teamcity内部,命令行执行apt-get install -y tzdata即可,可能会提示你升级,apt-get update即可,然后根据说明选择
Asia/Shanghai即可,直接设置环境变量会因为缺少tzdata无法设置

2.关于解析,看到配置会发现,解析里有jr开头的命令,它实际上是命令,直接agent执行brew install jr安装即可

3.关于命令行下载, curl -o为保存
