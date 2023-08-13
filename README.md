# halo

1. 把文件`application/src/main/resources/application.yaml`中的工作目录（work-dir）改为`/home/runner/${REPL_SLUG}/.halo2`
2. 修改`gradle.properties`中的`version`为当前 tag 的版本号，如：`version=2.8.0`

```
git clone https://github.com/halo-dev/halo.git
cd halo
git checkout v2.8.0  #使用git tag --column可以查看所有标签
make -C console build  #构建 Console
./gradlew clean build -x check  #构建 Fat Jar
```
构建完成之后，在 halo 项目下产生的 `application/build/libs/application-2.8.0.jar` 即为构建完成的文件。

# memos

```
git clone https://github.com/usememos/memos.git 
cd memos
git checkout v0.14.4 #使用git tag --column可以查看所有标签
cd web #进入前端目录，可以自行替换logo.png等
yarn && yarn build #编译前端文件，会在当前目录(web/)下生成dist文件夹
cd ..
rm -rf server/dist/ && mv web/dist/ server/ #将编译好的前端静态资源放入后端目录等会一块编译
go build -o memos main.go #编译二进制文件命名为memos并放入根目录
```
