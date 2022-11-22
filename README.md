


# 小米运动自动刷步数For Email

最后一次运行

## Github Actions 部署指南

### 一、Fork 此仓库

### 二、设置账号密码
> 添加名为  **USER**、**PWD**、**OPEN_GET_WEATHER**、**AREA**、**SCKEY**的变量: Settings-->Secrets-->New secret  

| Secrets |  格式  |
| -------- | ----- |
| USER |   小米运动登录账号,仅支持小米运动账号邮箱账号，不支持手机号（请注意，账号不是 [小米账号]，而是 [小米运动] 的账号。）|
| PWD |   小米运动登录密码,仅支持小米运动账号对应的密码|
|SCKEY|Server酱sckey，如无填写NO（Server酱：https://sct.ftqq.com/）|
| OPEN_GET_WEATHER|   开启根据地区天气情况降低步数**False**关闭,**True**开启|
| AREA |   设置获取天气的地区（上面开启后必填）如：**北京**，当**OPEN_GET_WEATHER**为**False**时填写**NO**|
| PAT （在登入状态下步骤3链接即可一键获取）|此处**PAT**需要申请，值为github token，需要repo和workflow权限,此项必填，避免git push的权限错误。<br><br><br>1、在 https://github.com 登录你的帐号，登录以后点击右上角你的头像的Settings<br><br>2、 点击 Developer settings 下的 Personal access tokens，如果您老人家觉得上面两个步骤很麻烦，那么您就直接进入这个链接(前提是你要先登陆你的帐号)：https://github.com/settings/tokens<br><br><br>3、点击 https://github.com/settings/tokens/new 这个超链接，就是创建你的token。<br><br>4、在Token description中随便填一个描述名称，下面的复选框是你这个token需要的权限，全部勾上就可以了。<br><br>5、生成的这个就是你的token了，可以直接复制使用。|<br>


### 三、自定义启动时间多账户(用不上请忽略)

>多账户请用 **#** 分割 然后保存到变量 **USER** 和 **PWD**
>
>#### 例如

>*12345@qq.com#54321@qq.com* 变量 **USER**

>**abc123qwe#abcqwe2** 变量 **PWD**

### 四、自定义启动时间

编辑 **.github/workflows/run.yml**
修改其中**cron**语句的判断时间为UTC时间，即**北京时间-8**，如北京时间8点为UTC时间0点，需要运行的时间-8就是UTC时间

### 五、自定义随机步数范围

在main.py 87~88行处修改计算方法

## 六、感谢名单<br><br>https://github.com/huangshihai/mimotion<br>https://github.com/xunichanghuan/mimotion<br>https://gitee.com/daenmax/zepp-millet-brush-steps/blob/master/sport.php



### 七、注意事项

**1. 每天运行六次，整由run.yml中的cron控制，分钟为随机值**

**2. 多账户的数量和密码请一定要对上 不然无法使用!!!**

**3. 启动时间得是UTC时间!**

**4. 如果支付宝没有更新步数,到小米运动->设置->账号->注销账号->清空数据,然后重新登录,重新绑定第三方**

**5. 小米运动不会更新步数，只有关联的会同步！！！！！**

**6. 请注意，账号不是 [小米账号]，而是 [小米运动] 的账号。**

**7. 本人业余，东拼西凑机缘巧合做成的，反馈问题本人不会处理**


