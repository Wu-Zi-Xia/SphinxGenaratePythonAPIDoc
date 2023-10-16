# SphinxGenaratePythonAPIDoc
bat脚本采用Sphinx流程化生成Python的帮助文档

# 使用说明
1.需要在使用的机器上安装python

2.使用python安装sphinx
pip install sphinx(如果需要无网络连接安装，请搜索教程去下载对应的安装包进行本地安装)

3.使用python安装sphinx_rtd_theme
pip install sphinx_rtd_theme(如果需要无网络连接安装，请搜索教程去下载对应的安装包进行本地安装)

4.修改sphinx_rtd_theme的一些配置以达到自定义需求（可选）
  --1.生成的html不需要footer：
    找到python的安装目录（where python）
	在python的lib目录下找到sphinx_rtd_theme目录，比如：C:\Users\Administrator\AppData\Local\Programs\Python\Python39\Lib\site-packages\sphinx_rtd_theme
	在此目录下将footer.html文件中的内容全部删除，保留为空文件。
  --2.让一些html元素为块级元素，使得排版美观：
    在python的lib目录下找到sphinx_rtd_theme目录，在目录下找到static/css
	找到theme.css文件,在文件中搜索.property的css样式，
	将此css样式的display:inline-block属性直接直接删除
    
5.运行生成API文档的脚本：
  运行脚本有四个参数：GenerateAPIDoc.bat 产品名称 产品版本 源代码目录 sphinx工程目录，API文档生成在doc/build/html目录下；
  以上参数中涉及路径的都必须是绝对路径
  比如：GenerateAPIDoc.bat "ProjectName" "0.1" "D:\Project\src" "D:\SphinxDemo"
  
  --1.cmd命令行生成：
  在脚本所在的目录键入cmd然后执行命令。

  --2.在另一个脚本调用生成：
  在另一个脚本调用此脚本生成（保证调用脚本与GenerateAPIDoc.bat与ReplaceText.bat在同一个目录下）
  


  注意：如果修改了sphinx的配置文件（conf.py），需要将整个sphinx工程目录（D:\SphinxDemo）删除掉再重新生成
