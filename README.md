## 程序说明

本系统3.0版基于奥蓝学生管理信息系统打卡模块，使用OpenCV对验证码进行处理后，再利用EasyOCR对验证码进行识别，经过测试，识别准确率良好，可满足实际使用需求。

目前3.0版尚处在开发阶段，目前仅具有基础的自动打卡功能和错误重试功能，2.0版本具有的发信提醒功能和批量打卡功能将在后续版本完善。

如需基于信息门户和E河海打卡接口的自动打卡系统请前往2.x分支

## 使用方法
1.首先请将本项目Fork到自己用户下

2.在Settings > Secrets中添加名称为USERNAME和PASSWORD的secrets，分别填写奥蓝系统用户名和密码

3.进入Actions > health_report中，点击Run workflow，测试是否能正常使用

4.接下来的每天上午8点半，系统会自动进行打卡任务。

## 运行环境

python 3.8

## 更新日志
**[2022/04/04] 3.0.3**

1.修复Github Action定期运行失败的bug

2.修复Github Action中读取时间为UTC时间的Bug

2.修改模型存储目录

**[2022/04/04] 3.0.2**

1.添加GitHub Action适配

2.修改模型存储目录

**[2022/04/03] 3.0.1**

1.修复带字母的密码无法登录的问题

2.修复无法识别已填报情况的问题

**[2022/04/02] 3.0**

1.接辅导员通知，学校将于清明后开始测试奥蓝系统打卡模块，拟于4月11日正式启用奥蓝系统打卡模块。故该版本新增对奥蓝学生管理信息系统打卡模块的支持，取消对原有信息门户和E河海打卡接口的支持。

2.暂时取消发信提醒功能和批量打卡功能。

3.优化代码可读性。

**[2021/09/07] 2.0(重大更新)**

1.代码重构，减少代码冗余

2.新增研究生自动打卡功能（理论可用，未严格测试）[感谢某位研究生学长的支持]

3.新增发信功能

4.支持同时为多个同学打卡

5.规范日志记录格式和错误检测

**[2021/09/07] 1.3**

由于新接口dailyreport.hhu.edu.cn不支持弱密码，故新增弱密码检测，若密码为纯数字，默认使用老接口进行打卡。

修复老接口form.hhu.edu.cn在部分环境下出现Cookie丢失的Bug。

将Crypto包修改为cryptography，便于安装。

将时区固定为GMT +8，避免部分环境下因日期获取错误导致的打卡失败。

**[2021/09/06] 1.2**

由于form.hhu.edu.cn外网访问不稳定，故新增dailyreport.hhu.edu.cn打卡接口。

目前逻辑如下：

优先使用dailyreport.hhu.edu.cn打卡，若dailyreport.hhu.edu.cn需要验证码登录，则使用form.hhu.edu.cn打卡

**[2021/09/03] 1.1**

修正了因学校打卡系统修改打卡字段而导致程序崩溃的Bug

**[2021/08/25] 1.0**

第一版上线，较以往版本修改登录接口，新增解析打卡内容功能
