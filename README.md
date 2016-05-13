# autoGit
这是一个简单git推送的脚本


# Usage

     -m -message 提交信息
     -b -branch 当前分支 (默认为master分支)
     
     把脚本放到工程文件夹下
    $ python autoGit.py -m '提交信息' -b Test (假如当前是Test分支,如果是master分支，`-b Test`去掉即可)
    
    原理是:
    1 先commit当前分支，并直接进行push
    2 如果push失败，说明当前分支版本较低,那就pull最新内容
    3 如果pull失败，说明没有和远程仓库建立连接
    4 继续设置连接后，再次pull
    5 拉取成功后，直接push
    6 如果拉取后的没有冲突，push成功
    7 如果拉取后的分支有冲突，那么手动解决冲突后，手动执行push即可。
    
# 修改脚本的默认的分支
    
    在man()函数中
    
    if branch is None:
        branch = 'master'
    else:
        pass
        
 把`master`改成自己的就行了。
 
# 关于Git的其他常用功能

切换分支，合并分支，以及新建分支，删除分支，版本回退，打标签等功能就没写入脚本中

    1 因为我认为我们最常用的就是提交和推送
    2 Git本身的命令已经非常简洁了
    3 我认为重要的是保持使用的简单，功能越多，使用越复杂，这违背了我们的初衷。
 
   