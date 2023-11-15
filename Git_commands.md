git init 創建地方  
git add 檔名 or git add . 更新最新進度至地方  
git reset HEAD 檔案名稱.副檔名 取消add  
git add . 再輸入 git reset --hard 回復最後一次commit  
git commit -m "first commit" 每次新增完填寫描述  
git remote add origin https://github.com/CSCI-40500-77100-Spring-2021/project-3 連結線上  
git push -u origin master  第一次推上線MASTER   
git push 推上，遠程MASTER  
code . 開啟編輯  
git checkout -b yaoDev 開新branch至地方  
git push -u origin yaoDev 推上線branch  

新增pull request 在git上branch的地方有compare & pull request  
merge pull requst 用來合併branch到master  
pull request->new pull request->compare master & branch->create pull request  

git checkout master 換回master  
git checkout yaoDev 換回branch  
git pull origin master 從線上master拉東西  
git checkout (完整檔名) 可以回復成未modified狀態  

git log看commit紀錄  
git reset 版本當前的識別碼(前七碼)^ 回到上一個commit  
^ 的意思是回到 前一次
git reset 57989a6^^^^^^  =  57989a6~6  
git reset 版本識別碼(前7碼)  
git reset --soft HEAD~1 如果您想保留所做的更改但不在提交中，可以使用 --soft 選項。如果您想完全丟棄更改，則使用 --hard 選項
git reset --hard HEAD~1
git push origin HEAD --force 使用 git push 命令配合 --force 選項推送本地狀態到遠端，這將覆蓋遠端的歷史。


