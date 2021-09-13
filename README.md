# git

git fetch --all

git reset --hard

git pull


git clean -f

git clean -f -d

# tag
git tag big_cats 51d54ff
git push origin big_cats



# sourcetree
https://community.atlassian.com/t5/Sourcetree-questions/Git-Credential-Manager-for-Windows-Popups/qaq-p/579905

git config --global credential.helper manager

git config --global credential.useHttpPath true




# 如何緊急上 Patch 並且發佈下一個版本，底下是最簡單的操作步驟。
參考 https://blog.wu-boy.com/2017/12/github-flow-vs-git-flow/

    # 抓取遠端所有 tag
    $ git fetch -t origin

    # 從上一版本建立 branch (0.2.4 代表上一個版本)
    $ git checkout -b patch-1 origin/0.2.4

    # 把修正個 commit 抓到 patch-1 branch
    $ git cherry-pick commit_id

    # 打上新的 Tag 觸發 Deploy 流程
    $ git tag 0.2.5
    $ git push origin 0.2.5

    # 將 patch 也同步到 master 分支
    $ git checkout master
    $ git cherry-pick commit_id
    $ git push origin master


# 備份分支 並刪除遠端分支
    # 當前分支更名
    git branch --move back_name
    # 推上去新的分支
    git push origin -u back_name
    # 刪除遠端分支
    git push origin --delete name




# 幾種版控的流程 備忘 Git flow & GitHub flow & GitLab Flow

    all

    https://medium.com/@lf2lf2111/%E4%B8%89%E7%A8%AE%E7%89%88%E6%8E%A7%E6%B5%81%E7%A8%8B-29c82f5d4469

    https://blog.wu-boy.com/2017/12/github-flow-vs-git-flow/

    https://www.jianshu.com/p/0080df2c2d8c

    https://cloud.tencent.com/developer/article/1646937

    1.Git flow

    https://blog.hellojcc.tw/the-flaw-of-git-flow/

    2.GitHub flow

    https://guides.github.com/introduction/flow/

    3.GitLab Flow

    https://zhuanlan.zhihu.com/p/65781620
