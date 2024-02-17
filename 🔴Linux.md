> Author: ChangleLIU

> 源课程链接：[https://www.bilibili.com/video/BV1n84y1i7td](https://www.bilibili.com/video/BV1n84y1i7td) 

# 基础命令
## ls
```shell
ls -a
ls -l -h //所有详细信息
```
## cd pwd
> Change Directory
> Print Work Directory

## 绝对路径和相对路径
```shell
cd /home/
cd Desktop
```

- . 当前目录
- .. 上一级
- ~ HOME目录
## mkdir
> Make Directory

- -p 创建多层级目录

## touch cat more
```shell
touch test.txt //创建文件
cat test.txt //查看文件内容
more test.txt //分页查看文件内容 b返回上一页 空格下一页 q退出
```

## cp mv
```shell
cp test1.txt test2.txt 
cp -r test1 test2 //复制文件夹

mv test1.txt Desktop/ //同样可移动文件夹
mv test1.txt test3.txt //文件重命名

rm -r test1.txt //删除文件夹
rm -f test1.txt //强制删除
rm -r *test* //模糊匹配
```

## which find
```shell
which cd //查找命令

find ./Desktop -name "*test*"//根据文件名查找文件
```
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708097877417-96b5b1bd-9465-4f2b-848e-02f6d83e05b1.png#averageHue=%23f7f7f7&clientId=ue962c70e-b95c-4&from=paste&height=321&id=u0ca1d5f9&originHeight=682&originWidth=1084&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=159980&status=done&style=none&taskId=u0e6376f3-6fcd-4762-9be5-a4ae44d62bd&title=&width=510.4285888671875)

## grep wc 管道符 |
```shell
grep [-n] keyWord Desktop/test.txt // 查找字符串/过滤文件行：-n 显示行号
```
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708098132975-7306a7b9-7a7c-4375-8a8f-47e78fe083d8.png#averageHue=%23f4f3f3&clientId=ue962c70e-b95c-4&from=paste&height=224&id=u1b3ee010&originHeight=464&originWidth=892&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=149400&status=done&style=none&taskId=u0a847cae-3f28-4f31-9bae-10670f8cf32&title=&width=429.71429443359375)
```shell
cat test.txt | grep keyWord
ls -l | grep test
```
## echo > >> tail
```shell
echo "hello Linux" //在命令行输出
echo `pwd` //输出命令结果
echo "hello" > test1.txt //覆盖写入
echo "hello" >> test1.txt //追加写入

tail -5 test1.t //查看文件尾部内容(5行)
tail -f test1.t //持续跟踪 ctrl+C 停止
```

## vi/vim

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708099151258-cbe43df1-3abf-4931-acb4-d5e81d56e8fd.png#averageHue=%23e9e8e7&clientId=ue962c70e-b95c-4&from=paste&height=285&id=u9fbcec4c&originHeight=499&originWidth=753&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=122252&status=done&style=none&taskId=ucf8b715b-ac30-4617-8436-fff3c597527&title=&width=430.2857142857143)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708099179182-446ac180-9d36-46a7-be4d-87ff265cdc8a.png#averageHue=%23f9f8f7&clientId=ue962c70e-b95c-4&from=paste&height=311&id=uf49f7fe8&originHeight=545&originWidth=1116&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=297884&status=done&style=none&taskId=ue73c62d7-a6d4-405b-b1f9-6851f4ee5a9&title=&width=637.7142857142857)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708099316378-cb0ae755-53b1-4c1a-a5dc-096d3181a6af.png#averageHue=%23f6f2ef&clientId=ue962c70e-b95c-4&from=paste&height=338&id=ud7e20524&originHeight=592&originWidth=1536&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=461496&status=done&style=none&taskId=u60136dc2-a025-4d46-9a28-1704a906a8a&title=&width=877.7142857142857)

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708099486580-238e4172-ca94-43df-93c7-68d58907c982.png#averageHue=%23f7f0ea&clientId=ue962c70e-b95c-4&from=paste&height=230&id=ud82493cd&originHeight=403&originWidth=753&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=163067&status=done&style=none&taskId=u45c1fd13-1e43-43da-beba-8050db13634&title=&width=430.2857142857143)
# Linux用户和权限
## su exit sudo
Switch User
exit / ctrl + d
```shell
su - root
```
## 用户组
```shell
su - root
groupadd itcast
groupdel itcast
useradd test2 -g itcast -d /home/test222 //-g: 指定组 -d: 指定HOME路径

userdel -r test2 //-r: 同时删除用户的HOME目录

id test2 //查看用户的组等信息


usermod -aG itcast2 test2 //将用户test2加入itcast组

getent passwd //查看当前系统有哪些用户
```
## 权限控制
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708102739979-edd2a252-6893-4ecb-94f1-43792578d4e5.png#averageHue=%23f4f0ee&clientId=ue962c70e-b95c-4&from=paste&height=386&id=u7fdd672c&originHeight=675&originWidth=1299&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=219165&status=done&style=none&taskId=u30a3d4ed-5522-4278-a3e3-414f99a928f&title=&width=742.2857142857143)
## 修改权限
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708103694863-ef9650c9-149f-406c-b75a-41aae3e05836.png#averageHue=%23f7f6f6&clientId=ue962c70e-b95c-4&from=paste&height=396&id=u589e0203&originHeight=693&originWidth=1412&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=279031&status=done&style=none&taskId=u727a8985-81e6-4fe8-8d08-6d29f518e2c&title=&width=806.8571428571429)
数字序号：r4, w2, x1
各种组合就是数值直接相加

## 修改所属用户和用户组
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708108715957-b2d3628f-5a94-4a09-b83d-daad85f72878.png#averageHue=%23f3f2f1&clientId=uf81496a3-66c9-4&from=paste&height=367&id=u4ce52ea3&originHeight=642&originWidth=1433&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=505891&status=done&style=none&taskId=u3433eaa4-862b-46ab-86bf-855bb97d6b3&title=&width=818.8571428571429)

# 实用操作
## 快捷键
ctrl + C : 强制停止
      + D : 退出或登出
history : 历史命令搜索
! + 命令前缀 : 自动执行history中上一次匹配前缀的命令
ctrl + r : 输入内容去匹配历史命令，回车键执行，左右键获得命令
      + a : 跳到命令开头
      + e : 结尾
      + 左键 : 向左跳一个单词
      + l : 清屏
## 软件安装
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708109433049-5414c865-b906-487a-b623-8d07c689eece.png#averageHue=%23f7f5f5&clientId=uf81496a3-66c9-4&from=paste&height=336&id=u1dc8709f&originHeight=588&originWidth=1210&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=220106&status=done&style=none&taskId=ua44a1710-3968-446f-9d52-0227c923f85&title=&width=691.4285714285714)

Ubuntu: aot
## 控制软件启动停止
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708109808277-be72b0a4-ae6c-40b2-aaaa-d17580c8f296.png#averageHue=%23f4f4f4&clientId=uf81496a3-66c9-4&from=paste&height=400&id=ude821800&originHeight=700&originWidth=1638&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=297157&status=done&style=none&taskId=u1faa52d0-f66c-4107-82be-2d0298261ec&title=&width=936)

## 软链接
```shell
ln -s loc1 lo2
```
## 日期和时区
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708110795358-f2a197d8-3fef-47a3-8dea-6d385773557b.png#averageHue=%23f7f7f7&clientId=uf81496a3-66c9-4&from=paste&height=416&id=u39baad51&originHeight=728&originWidth=1388&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=195990&status=done&style=none&taskId=u00ff8b4d-b1be-48d6-8e9e-18c91747cb2&title=&width=793.1428571428571)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708111308129-02d046c3-4640-4b43-a878-b445762a4920.png#averageHue=%23d9dbd4&clientId=uf81496a3-66c9-4&from=paste&height=129&id=u3e01093a&originHeight=153&originWidth=410&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=88614&status=done&style=none&taskId=u68d2a452-171c-46b0-bf5e-c6be558bd7d&title=&width=345.2857208251953)
## IP地址和主机名
ifconfig
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708111683972-d883b126-498b-4915-a8ee-e26339a16e25.png#averageHue=%23f4f4f4&clientId=uf81496a3-66c9-4&from=paste&height=295&id=u65137f5e&originHeight=516&originWidth=1179&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=231762&status=done&style=none&taskId=u0c2123f3-b450-4645-8098-e0c518361fc&title=&width=673.7142857142857)
## 网络请求和下载
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113276500-6f22be63-a338-48db-9766-b86473ef30dd.png#averageHue=%23eaeaea&clientId=uf81496a3-66c9-4&from=paste&height=155&id=u46d1a58c&originHeight=271&originWidth=937&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=124591&status=done&style=none&taskId=ueec721ab-8759-44a1-8ad5-92c33a93200&title=&width=535.4285714285714)

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113331225-07d31152-0aab-484a-8a8f-aa4de64fb19a.png#averageHue=%23efefef&clientId=uf81496a3-66c9-4&from=paste&height=143&id=ud70c7053&originHeight=251&originWidth=1126&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=105048&status=done&style=none&taskId=u06113f5a-76ba-4a99-91f0-47c58ca011b&title=&width=643.4285714285714)

![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113463573-35ca1274-8232-4f9d-8932-0a1167690e6b.png#averageHue=%23f1f1f1&clientId=uf81496a3-66c9-4&from=paste&height=162&id=uf3ef1809&originHeight=283&originWidth=1113&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=120503&status=done&style=none&taskId=u77a930b2-1ecf-412c-9036-a61236c7565&title=&width=636)

## 端口
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113827484-d8131d81-5d62-4190-849b-16e1d454e664.png#averageHue=%23bbbbba&clientId=uf81496a3-66c9-4&from=paste&height=234&id=uc30c989c&originHeight=410&originWidth=940&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=163210&status=done&style=none&taskId=u05690ef9-6e96-4042-bcc9-ed6acf19588&title=&width=537.1428571428571)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113841097-3b750c61-f849-421a-a59b-349269d58fab.png#averageHue=%23afaeac&clientId=uf81496a3-66c9-4&from=paste&height=225&id=ub2b3eeee&originHeight=393&originWidth=1335&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=243790&status=done&style=none&taskId=u6f471cb2-7599-4db7-adbe-cb3624f2457&title=&width=762.8571428571429)
## 进程
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708113990249-747549eb-2499-4404-a1b2-94e9a1b24b15.png#averageHue=%23f1f1f1&clientId=uf81496a3-66c9-4&from=paste&height=146&id=u6e84be33&originHeight=255&originWidth=910&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=75677&status=done&style=none&taskId=uf48b456a-ec1c-47ee-b0bf-76117e45fe8&title=&width=520)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708114096216-8eeae4f9-3dca-459f-a764-550d1598061c.png#averageHue=%23bbbab7&clientId=uf81496a3-66c9-4&from=paste&height=391&id=uaaa7a2b5&originHeight=684&originWidth=1562&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=532584&status=done&style=none&taskId=uaf1cd6b4-1ae7-4ebd-ab85-2842076967b&title=&width=892.5714285714286)
## 主机状态监控
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708160539388-0a857eeb-4d88-41f7-a0cd-c25cc16f4165.png#averageHue=%23cbcbc0&clientId=u63800989-fac4-4&from=paste&height=394&id=ua9d25c8c&originHeight=689&originWidth=1701&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=663269&status=done&style=none&taskId=u68f5e8b5-bc82-4375-8226-8d0dcfbdf61&title=&width=972)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708160659170-f5d463fc-44fb-4771-915c-db8ca94f0cfe.png#averageHue=%23f2f2f2&clientId=u63800989-fac4-4&from=paste&height=450&id=u0ebfbfd3&originHeight=787&originWidth=1354&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=448766&status=done&style=none&taskId=u2f1971b8-97c9-4b7b-a02b-43339088176&title=&width=773.7142857142857)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708160670956-c567faae-dfe8-427b-af03-2389cdbbc068.png#averageHue=%23f8f8f8&clientId=u63800989-fac4-4&from=paste&height=326&id=udf35fb18&originHeight=570&originWidth=1525&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=283635&status=done&style=none&taskId=u9abefad1-0047-49af-90d2-9651b1df9b5&title=&width=871.4285714285714)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708161735055-158b167d-cdaa-4d6a-ac4f-d8cedcb56263.png#averageHue=%23ddddd3&clientId=u63800989-fac4-4&from=paste&height=378&id=u3efea013&originHeight=661&originWidth=1236&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=359739&status=done&style=none&taskId=uace9fddc-7f7b-4791-9189-2070452d206&title=&width=706.2857142857143)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708161754253-f468a579-e9e7-4e20-9337-0167a69d54a1.png#averageHue=%23f2f2f2&clientId=u63800989-fac4-4&from=paste&height=168&id=u32b1604b&originHeight=294&originWidth=669&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=59291&status=done&style=none&taskId=uccd0a94b-97e0-4279-b324-10ab39d6b92&title=&width=382.2857142857143)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708161799512-dccd942a-5a03-4484-b078-860b1e9c83e0.png#averageHue=%23eeeeee&clientId=u63800989-fac4-4&from=paste&height=138&id=ua020ebeb&originHeight=241&originWidth=731&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=63375&status=done&style=none&taskId=u2a9d525e-0aa6-4969-b745-193167e2540&title=&width=417.7142857142857)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708161923982-720b1316-fabb-46ed-8e3a-ed17dc32ea5c.png#averageHue=%23f3f3f3&clientId=u63800989-fac4-4&from=paste&height=204&id=uaeb62e71&originHeight=357&originWidth=1334&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=132476&status=done&style=none&taskId=uc6d1f6f2-280c-453a-8fa9-ff1d0e06690&title=&width=762.2857142857143)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708161983091-2135aa88-6083-4c82-833c-f89ad10f9946.png#averageHue=%2379846a&clientId=u63800989-fac4-4&from=paste&height=294&id=u92a4c8ea&originHeight=515&originWidth=1518&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=696665&status=done&style=none&taskId=u34235bf7-5166-469f-8b40-fd5c97a57df&title=&width=867.4285714285714)
## 环境变量
env
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708162597315-0adaf393-695c-426a-a9a2-0c4cf79de8ad.png#averageHue=%23f2f2f2&clientId=u63800989-fac4-4&from=paste&height=341&id=u9d9695f8&originHeight=597&originWidth=1646&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=345039&status=done&style=none&taskId=ua0ff88e2-80b9-4c0c-bba6-2841bff4966&title=&width=940.5714285714286)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708162616933-171df84b-dafe-4af3-9961-52b757145429.png#averageHue=%23f3f2f2&clientId=u63800989-fac4-4&from=paste&height=403&id=ue7bf8b98&originHeight=706&originWidth=1483&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=455536&status=done&style=none&taskId=u290304cf-d8b9-4266-bba6-44986a7ce95&title=&width=847.4285714285714)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708162667946-f33c8a11-c9cc-44a3-914c-b2af684cf626.png#averageHue=%23f6f5f5&clientId=u63800989-fac4-4&from=paste&height=337&id=u3e9fb116&originHeight=590&originWidth=1281&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=232411&status=done&style=none&taskId=ub868a90f-e181-4234-9212-fbbb62fd6b1&title=&width=732)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163081517-d32fc735-1faa-4369-b7e0-fe97fc7a97b9.png#averageHue=%23f5f5f5&clientId=u63800989-fac4-4&from=paste&height=476&id=uf335469a&originHeight=833&originWidth=1548&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=277924&status=done&style=none&taskId=uec22e62f-046a-4d48-bae6-e814edcdc01&title=&width=884.5714285714286)
## 文件上传和下载
### FinalShell直接拖拽
### rz sz
上传速度较慢
## 压缩和解压
.tar .gzip .zip

- .tar: 简单封装
- .gz: 极大减少体积
### tar
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163488708-9d9b1ebb-f512-4e6e-9d19-1d2f1ba6cd1e.png#averageHue=%23f0f0f0&clientId=u63800989-fac4-4&from=paste&height=207&id=u117bbd52&originHeight=362&originWidth=940&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=142493&status=done&style=none&taskId=ua686da80-0d6e-4482-86bf-56be18558e7&title=&width=537.1428571428571)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163505090-5f7f37a6-3a79-444c-aabe-999c60b90141.png#averageHue=%23e7e7e7&clientId=u63800989-fac4-4&from=paste&height=27&id=u51ec64bf&originHeight=48&originWidth=480&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=13588&status=done&style=none&taskId=uc84158d0-a638-496d-872f-d33a052b226&title=&width=274.2857142857143)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163601944-541257e9-bbff-4a73-afd3-563f89bb4f5e.png#averageHue=%23f3f3f3&clientId=u63800989-fac4-4&from=paste&height=323&id=u96f6d00a&originHeight=565&originWidth=839&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=154450&status=done&style=none&taskId=u6037f7ce-5abd-46d3-b7fd-c439091ccb1&title=&width=479.42857142857144)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163768234-670c0e34-3a46-48a5-97c3-e379736bbdd6.png#averageHue=%23f0f0f0&clientId=u63800989-fac4-4&from=paste&height=267&id=u34cf162c&originHeight=467&originWidth=873&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=136906&status=done&style=none&taskId=u360261bd-1f1d-402b-98d0-728185f3d82&title=&width=498.85714285714283)
### zip
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163828383-975240dd-ff7f-49b6-9f93-0be82d501ff4.png#averageHue=%23f5f5f5&clientId=u63800989-fac4-4&from=paste&height=321&id=u1346bb91&originHeight=562&originWidth=1214&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=171709&status=done&style=none&taskId=ubffbc6ac-174a-437b-8ebe-749e1bb1e78&title=&width=693.7142857142857)
![image.png](https://cdn.nlark.com/yuque/0/2024/png/40712000/1708163913951-7389bc0e-3468-4ac2-ba26-160e473ac36d.png#averageHue=%23f6f6f6&clientId=u63800989-fac4-4&from=paste&height=356&id=ua41b6267&originHeight=623&originWidth=1308&originalType=binary&ratio=1.75&rotation=0&showTitle=false&size=183684&status=done&style=none&taskId=u8dc59969-9c4a-401e-ac49-cef78115ab3&title=&width=747.4285714285714)
