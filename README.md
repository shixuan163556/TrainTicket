# TrainTicket
在12306.com购买火车票

### 运行环境：
python3.7, splinter, configparser, pycharm

### 使用方法:
1.在config.ini中设置12306用户名、密码，乘车人信息 
```
## 登陆账号和密码
[login]
### username：12306登录用户名，必选参数
username=
### password：12306登录密码，必选参数
password=

## users：乘客姓名，必选参数，中文姓名，支持多个乘客，用英文逗号隔开，例如：张三,李四
### 乘客姓名需要提前加入到登录的12306账号的联系人中，为了程序自动选择乘客姓名
[userInfo]
users =
```
2.[点击下载chromedriver](http://npm.taobao.org/mirrors/chromedriver/)  
3.在config.ini中配置chromedriver信息
```
## 路径信息
[pathInfo]
### driver_name: 浏览器名称，必选参数
driver_name = chrome
### executable_path: 浏览器驱动路径，必选参数
executable_path =

```
4.在config.ini中配置车次类型、发车时间短、坐席
```
## 车次类型：
[trainInfo]
### train_types：车次类型，可选参数，默认全部车次，支持多个值，用英文逗号隔开，特别需求的在此指定值，不指定请删除等号后的值，默认是车次不勾选，有效值如下：
#### T->特快
#### G->高铁
#### D->动车
#### Z->直达
#### K->快车
train_types =D,G

### start_time：发车时间，可选参数，不指定请删除等号后的值，默认值“00:00--24:00”
### 时间格式 12:00--18:00，有效值如下：
##### 00:00--24:00->00:00--24:00
##### 00:00--06:00->00:00--06:00
##### 06:00--12:00->06:00--12:00
##### 12:00--18:00->12:00--18:00
##### 18:00--24:00->18:00--24:00
start_time = 00:00--24:00

[confirmInfo]
## 席别
### seat_type：席别，可选参数，不指定请删除等号后的值，默认按照12306预定到的车次的席别，有效值如下：
#### 硬座
#### 硬卧
#### 软卧
#### 一等软座
#### 二等软座
#### 商务座
#### 一等座
#### 二等座
#### 混编硬座
#### 特等座
seat_type = 二等座

## 是否允许分配无座
## noseat_allow: 默认为1, 表示允许; 0则不允许
noseat_allow = 0
```

5.运行TicketInf.py
