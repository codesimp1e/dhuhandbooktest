# DHUHandbookTest
东华大学新生入学教育学生手册、网络安全、垃圾分类考试脚本

## 环境搭建
1. Python 3.X
2. Edge浏览器和与其版本号对应的<a href="https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver">webdriver驱动</a>并且将msedgedriver.exe文件放置在脚本同级的edgedriver_win64文件夹下
（chrome及firefox浏览器同理但要修改脚本）
3. <a href="https://jupyter.org/install">JupyterNotebook</a>以及<a href="https://jupyter.readthedocs.io/en/latest/running.html#running">如何使用</a>
4. 使用pip安装selenium和bs4
``` powershell
pip install selenium bs4
```

## 使用
1. 除了readme外的两个文件都需要下载并放在同一文件夹下
2. 运行脚本前请修改你的用户名和密码
``` python
wd.find_element_by_xpath('/html/body/main/section[1]/div/div[1]/input').send_keys('输入用户名') #输入用户名
wd.find_element_by_xpath('/html/body/main/section[1]/div/div[2]/input').send_keys('输入密码') #输入密码
```
3. 需要进行哪项考试就留下哪项其余两项注释掉
``` python
# wd.get('https://yb.dhu.edu.cn/sccloudV2/NewStudent1/User/HandBook/handBookTestDetail?customer_id=5&module_tag=HANDBOOK') #学生手册
# wd.get('https://yb.dhu.edu.cn/sccloudV2/NewStudent1/User/HandBook/handBookTestDetail?customer_id=5&module_tag=NETWORK_SECURITY') #网络安全
wd.get('https://yb.dhu.edu.cn/sccloudV2/NewStudent1/User/HandBook/handBookTestDetail?customer_id=5&module_tag=GARBAGE_CG') #垃圾分类
```
另外相应的修改quiz_id
``` python
form_data = {
  "quiz_question_id":test_content.get('data-id'),
  "question_type_fixed" : test_content.get('data-question-type-fixed'),
  "user_quiz_answer_id": '237042', #随便填
  "quiz_id" : '490',#489学生手册 #491网络安全 #490垃圾分类
  "answer" : 'A',
}
```
