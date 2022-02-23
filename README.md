# GitHub
GitHub相关操作

<img width="512" alt="image" src="https://user-images.githubusercontent.com/38684698/155286118-179c55ca-88ee-43e1-9147-33b5847411f4.png">

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
