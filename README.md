## 自如新房源实时提醒

> 利用自如网页版查询房源，解析HTML并分析房源，找到新上架房源并推送至钉钉群。

#### 第一步：通过自如网页版本过滤条件并获取URL链接

![](images/964E6B93-FF17-42B1-8531-F77D79DDAF44.png)

#### 第二步：运行GO程序

> 需自行编译（参考Golang交叉编译）。使用命令可参考：ziroom --help，查看提示信息。


```shell script
┌─[uzdz@uzdz] - [~/work/golang/ziroom] - [Tue Jul 06, 14:19]
└─[$] <git:(master*)> go run main.go --help                                                                                                                                                                                              
usage: main [<flags>] [<url>]

Flags:
      --help              Show context-sensitive help (also try --help-long and --help-man).
  -d, --ding=DING         钉钉消息通知接口地址
  -k, --dingKey="自如"      钉钉消息通知接口地址
  -p, --taskInterval=300  任务周期间隔时长（最少5分钟），单位：秒
  -t, --TestForNotice=0   [测试] 每次调度推送t个房源通知

Args:
  [<url>]  自如网页版请求链接
```

将从自如拿到的请求URL带入到参数末尾即可，以下进行举例：

* linux_ziroom --ding='https://oapi.dingtalk.com/robot/send?access_token=xxx' --dingKey=xxx 'https://www.ziroom.com/z/z2-s100011-u13-r0/?p=x14&cp=0TO4500&isOpen=1'

## License

This project is licensed under the [Apache v2.0 License](https://github.com/apache/skywalking-cli/blob/master/LICENSE).

## 免责声明

此软件程序用于替代人工耗时的检索房源过程，请勿修改代码中的网站保护策略。知法懂法，请参考[破坏计算机信息系统罪](https://www.66law.cn/zuiming/276.aspx)。