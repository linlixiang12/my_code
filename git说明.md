    Initialized empty Git repository in C:/Users/Administrator/Desktop/myproject/.git/
    git init 初始化git仓库;
    git config --global user.name "名字";配置用户名字
    git config --global user.email "xxxxxx@.com";配置用户邮箱;
    git add ./readme.html; //把代码放到房间;
    git commit -m "我们完成了第一个功能" 提交 并说明;
    git status; 查看当前代码有没有放在上传队列中的状态
    git commit --all -m "一次性上传不用放到仓库门口"
    git add ./;把所有修改过的代码放入等待队列;
    git log ;查看历史提交日志;
    git reset --hard Head~1;回退代码提交时的状态
    git reset --hard 版本号;
    git refog ;查看之前的操作记录;

    当功能开发一半又想保存备份;又不能影响之前功能的完整性;如下

    git branch div;创建分支;后面的div是分支名字;
    git branch;查看分支
    git checkout dev;选则创建的分支;
    git merge div;当前的用户代码和选择的用户名合并;
    完成了div中功能的提交;
    git pull https://github.com/linlixiang12/my_code.git master;下载
    git clone https://github.com/linlixiang12/my_code.git master;克隆
    git push https://github.com/linlixiang12/my_code.git master ;上传
    git remote add [自定义名字] [地址];

