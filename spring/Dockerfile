# 注:DockerFile只针对构建镜像,IDE运行docker,需要勾选run build image
# 另外,本DocikerFile上下文是基于target,需要在configuration里设置爱context folder为target目录
# 否则则需要手动添加jar包到docker目录下(或者写脚本copy)
FROM java:8
# 镜像端口,只是镜像的,容器相关内容,例如映射端口, 名字等需要自己制定
EXPOSE 8080
ENV TARGET_JAR="test-0.0.1-SNAPSHOT.jar"
ADD ./${TARGET_JAR} /${TARGET_JAR}
RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
  && echo 'Asia/Shanghai' >/etc/timezone
CMD java -Xrs -Xmx200m -jar ${TARGET_JAR}

