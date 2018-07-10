代码如下
'''
Call Plugin.Web.Bind("WQM.exe") //绑定浏览器
Call Plugin.Web.Go("http://39.108.125.141/register/?from=/") //访问注册网址
i = 0 //统计注册量
n=1 //注册变量
name = "testtest"
email="@163.com"
Sub shuru

Call Plugin.Web.HtmlInput(name+Cstr(i), "id:id_username")//获取用户名输入框，填入数据
Call Plugin.Web.HtmlInput(Cstr(i)+email, "id:id_email")//获取邮箱输入框，填入数据
Call Plugin.Web.HtmlInput(name+Cstr(i), "id:id_password")//获取密码输入框，填入数据
Call Plugin.Web.HtmlInput(name + Cstr(i), "id:id_password_again")//获取用户名输入框，填入数据
Call Plugin.Web.HtmlClick("tag:INPUT&value:注册") //获取注册按钮，点击
Call Plugin.Web.HtmlClick("tag:A&txt:退出") //获取退出按钮，点击
Call Plugin.Web.Go("http://39.108.125.141/register/?from=/") //再进入注册页面，进入循环
TracePrint "第" + Cstr(i-1) + "次注册"  //显示注册次数
i = i + 1
n = n + 1
End Sub


do
call shuru
Loop
'''
可以加入一个MySQL注入语句字典，暴力破解后台字典试一次，这只是一个开始。
