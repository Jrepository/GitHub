# GitHub
GitHub相关操作

<img width="512" alt="image" src="https://user-images.githubusercontent.com/38684698/155286118-179c55ca-88ee-43e1-9147-33b5847411f4.png">

在github页面创建项目后,根据提示信息将本地项目上传的github上，且分支为master

echo "# algorithm" >> README.md

git init

git add README.md

git commit -m "提交备注信息"

git branch -M master

git remote add origin git@github_private:Jrepository/XXX.git

git push -u origin master

## 本地项目推送到github

>step1:　git init
>
>step2:　git add XXX
>
>step3:　git commit -m提交信息
>
>step4:　本地项目关联github：git remote add origin git@github_private:Jrepository/XXX.git
>
>step5:　本地项目推送到github：git push -u origin master
>
>其他：本地项目取消与github的关联：git remote remove origin

## 撤销push文件

>step1:　git log --pretty=oneline　　 查看当前提交的日志
>
>step2:　git reset --soft XXX 　　XXX是commitID(ab1cd23....) 回退当前工作空间的上一个版本,并且保留代码更改
>
>step3:　git log --pretty=oneline 　　再次查看当前提交的日志,确认是否成功撤销,当然,你也可以不看,基本上都会成功,保险一下,看看呗
>
>step5:　git push origin 分支 --force 　　强制提交当前版本号，以达到撤销版本号的目的.必须添加参数force进行强制提交，否则会提交失败,报错原因：本地项目版本号低于远端仓库版本号。(master 代表分支名称,默认是 master，或者也可以直接用git push --force)

## 撤销中间某次提交信息

>step1:　git log --pretty=oneline 　　查看当前提交的日志
>
>step2:　git revert XXX 　　XXX是commitID(ab1cd23....)需要撤销
>
>step3:　git push 　　推送到远程

## 回滚reset与revert的区别

>1. git revert是用一次新的commit来回滚之前的commit，git reset是直接删除指定的commit。 
>
>2. 在回滚这一操作上看，效果差不多。但是在日后继续merge以前的老版本时有区别。因为git revert是用一次逆向的commit“中和”之前的提交，因此日后合并老的branch时，导致这部分改变不会再次出现，但是git >reset是之间把某些commit在某个branch上删除，因而和老的branch再次merge时，这些被回滚的commit应该还会被引入。 
>
>3. git reset 是把HEAD向后移动了一下，而git revert是HEAD继续前进，只是新的commit的内容和要revert的内容正好相反，能够抵消要被revert的内容。
