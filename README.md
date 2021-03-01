# Health
对系统温度、风扇转速、硬盘SMART信息进行检测的bash脚本，可以生成比较直观的简报。  
**依赖 lm_sensors 和 smartmontools 软件包，请先自行安装和配置这两个软件包。**  

可以通过dingtalkrobot脚本将检测结果发送到钉钉，结合cron可以做到每天定时发送检测报告。  
比如设置PushTime="12:00"，然后在 crontab 中添加如下行.

          */5 * * * * /脚本存放路径/health cron

则脚本每5分钟运行一次，中午12:00后的第一次运行才会发送检测报告，其余时间如果检测到温度过高、风扇停转、SMART故障才会发送报告。  
脚本开头的参数可以根据个人需要自行修改。 

正常状态命令行显示内容：  
![正常命令行显示](https://github.com/hzgjq/Health/blob/main/screenshot/%E6%AD%A3%E5%B8%B8%E5%91%BD%E4%BB%A4%E8%A1%8C%E6%98%BE%E7%A4%BA.jpg?raw=true)  
检测到异常命令行显示内容：  
![异常命令行显示](https://github.com/hzgjq/Health/blob/main/screenshot/%E5%BC%82%E5%B8%B8%E5%91%BD%E4%BB%A4%E8%A1%8C%E6%98%BE%E7%A4%BA.jpg?raw=true)  
正常状态钉钉推送内容：  
![正常钉钉消息](https://github.com/hzgjq/Health/blob/main/screenshot/%E6%AD%A3%E5%B8%B8%E9%92%89%E9%92%89%E6%B6%88%E6%81%AF.jpg?raw=true)  
检测到异常钉钉推送内容：  
![异常钉钉消息](https://github.com/hzgjq/Health/blob/main/screenshot/%E5%BC%82%E5%B8%B8%E9%92%89%E9%92%89%E6%B6%88%E6%81%AF.jpg?raw=true)  
