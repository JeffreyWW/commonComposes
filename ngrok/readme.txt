目前设计是端口在服务器为82,ngrok镜像默认端口是80,所以这里设置先转为82,然后通过nginx映射
ngrok.yml端口指定本地服务端口即可
配置完成后,运行

ngrok -config=ngrok.yml start {服务}

服务为配置里的服务名,ngrok为文件夹内的脚本文件,不要直接cd进来运行,直接运行命令的话默认是找环境变量里的,除非设置过环境变量
本机目前编辑过.bash_profile文件,里面为
# customBinsPath
export PATH=/usr/local/customBin:$PATH

即,把文件夹中的ngrok放在这个文件夹即可直接运行ngrok命令

最后输入yml里DOMAIN的值,前面加上ngrok.yml的服务名作为前缀即可映射本地服务,当然,前提是nginx和ngrok在服务端都跑着才行
