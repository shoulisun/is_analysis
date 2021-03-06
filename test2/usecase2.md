
![](./usecase2_flow.png '')
#用例规约2
###2.1 解除预订
|   项目   |    内容    |
|:-------:|:------------- | 
|用例编号：|2.1|
|用例名称：| 解除预订 |
|角色： | 借书者，图书管理员|  
|用例说明： |读者刷卡，系统检索并显示出该读者预订图书信息 |
|前置条件： |用户进行过图书预订 |
|基本事件流: |  1.图书管理员选择“取消预订登记”，提交“取消预订登记”请求； 2.系统显示“取消预订登记”窗口； 3.借书者输入预订登记信息 4.系统列表显示出该读者预订图书信息  5.借书者选择取消预订 6.若用户之前进行过预订，则取消成功。若用户之前没有进行过预订，则转入6.1.1 |
|其他事件流: |无 |
|异常事件流:|   6.1.1用户没有进行预订但想取消预订   6.1.1提示用户取消失败  |
|后置条件：| 用户解除预订成功|
###2.2 预订图书
|   项目   |    内容    |
|:-------:|:------------- | 
|用例编号：|2.2
|用例名称：| 预订图书   |
|角色： |借书者、图书管理员  |
|用例说明：| 借书者已经注册成图书馆系统用户 |
|前置条件：| 借书者已经打开图书馆系统的页面，并登录，进入图书预定界面 |
|基本事件流： | 1. 借书者、图书管理员打开学院图书馆系统的页面 2. 借书者、图书管理员进入图书预定页面   3. 借书者、输入要预定的书名/编者/版本... 4. 借书者、点击确定查找    5. 借书者、在结果中选择需要预定的图书进行预定   6. 双击选择要预定的图书，确认提交预定 | 
|其它事件流： |第五步系统若无能订购的图书则返回“没有剩余图书预定”|  
|异常事件流：| 第五步，系统搜索时出现系统故障，例如网络故障，数据库服务器故障， 系统弹出系统异常页面，并提示“系统异常，请联系管理员” |
|后置条件： | 页面将返回到学院图书馆系统主页面|
###2.3 交付罚金
|   项目   |    内容    |
|:-------:|:------------- | 
|用例编号：|2.3|
|用例名称：| 交付罚金 | 
|角色：| 借书者、图书管理员 |
|用例说明：| 借书者向图书管理员及交付罚金 |
|前置条件：| 图书管理员登录系统  |
|基本事件流：|  1. 管理员进入学院图书馆系统；     2. 管理员打开借还书页面；    3. 管理员扫描图书读入图书信息；    4. 管理员扫描食堂卡读入读者信息；    5. 管理员点击还书按钮，在弹出的确认窗口点击确认按钮；   6. 系统检测读者信息图书信息，确认是否可以进行还书操作；   7. 系统进行超期罚款操作；    8. 系统进行还书操作，更改数据库；   9. 提示还书成功。|  
|其它事件流：| 第三步，系统读入图书信息错误时，提示图书信息错误；   第三步，系统读入图书信息后检测到图书未被借阅时，显示该图书不能进行还书操作；   第六步，系统检测到读者卡内金额不足以进行罚款扣费时，提示卡内余额不足；  |
|异常事件流：| 第八步，超期罚款操作时出现系统故障，例如网络故障，数据库服务器故障，系统弹出系统异常页面，提示扣费失败    第八步，还书操作时出现系统故障，例如网络故障，数据库服务器故障，系统弹出系统异常页面，提示还书失败 | 
|后置条件：| 系统更新图书信息|