本目录下的文件： 修改配置文件的脚本

修改配置文件.py 主程序文件
功能：
主要用来作为功能菜单选择及相关模块的选择、处理功能，包括：
        1 查看 backend 的配置信息
        2 添加配置信息
        3 删除配置信息

设计思路：
查看功能： 打开配置文件,一行一行的进行读取,当发现有 backend开头行时,再判断后面的 域名是否等于要查找的名称,如果是则做一个标记,判断标记
           为True时开始写到变量中,直到找到下一个backend时将标志位置False
增加：打开配置文件读取的同时打开一个临时文件写入,同查找功能一样一行一行读取的同时写入临时文件,同时判断当找到指定backend的记录后，置标志位,到下一个backend记录时
            将新增加的记录写入文件，再将剩下的配置信息写入到文件中。最后进行重命名操作替换到以前的配置文件
删除： 同添加类似,一行一行读取。当找到与要删除的配置一样时,就把那一行跳过不写入文件，如果找不到要删除的配置信息则提示"不存在你要删除的内容"，如果backend下所有的记录都已经被删除，那么将当前 backend test.oldboy.org 也删除掉

涉及到的主要知识点：文件操作，函数的调用，字符串转换成字典，文件的改名，列表字典的操作,异常处理，循环，if ...else

