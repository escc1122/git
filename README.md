# git

git fetch --all

git reset --hard

git pull


git clean -f

git clean -f -d



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
