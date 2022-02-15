# git 介紹
 * 2005 年時，開發 Linux kernel 的社群與開發 BitKeeper 的商業公司的合作關係結束，也就無法再免費使用該工具。 這就迫使了 Linux 社群（特別是 Linux 之父 Linus Torvalds）基於使用 BitKeeper 所學到的經驗，來開發自有的工具。
* 何謂版本控制？：


# 版本控制的邏輯

# Git的常用指令介紹
1. git init ：初始化git
2. git status ：git版本查詢
3. git add ：檔案加入版本控制 例：git add 123
4. git add .： 所有檔案加入版本控制
5. git rm --cached：把檔案移除版本控制 例：git re --cached 456
6. git commit：新建版本，會進入vim編輯器，可加入commit message，"q!"或"wq"跳回
7. git commit -m "版本敘述"：不進入vim直接給commit message 例：commit -m "1st"
8. git commit -am"版本敘述"：把所有檔案加入版本控制&建立版本(git add 和 git commit -m"" )的綜合功能。
9. git log ：查看版本的歷史紀錄。版本上方會寫commit+英數，就是它的版本號。
10. git log --online：查看簡單版本的歷史紀錄，版本號為最簡易的前七碼。
11. git checkout：git checkout +"完整"的版本號，改道版本號的版本。
12. git checkout master：把版本改到最新的版本。
13. .gitignore：不想被版本控制的檔案。先用touch建立.gitignore檔，再將不想被版本控制的檔案加入.gitignore檔（透過 vim .gitignore，再輸入不想被版本控制的檔名，按 :wq離開），即便之後一次用 git commit –am，.gitignore 檔也不被被版本控制。
14. git diff：在更改後的檔案再次加入版本控制前，可用git diff 看到版本更改的東西在哪
15. git branch -v：確認主幹&分支。
16. git branch :新增分支且命名 例：git branch 789。
17. git branch -d：刪除分支 例：git branch -d 1011。
18. git checkout ：移動到該分支 例：git checkout 789。
19. git merge ：把分支合併到目前所在的分支 例：git merge 1213。
20. git push：將本機已經commit 的版本上傳更新至github。例：git push origin(遠端主機) 1415。
21. git pull：把遠端的分支下載下來 例：git pull origin 1415。
22. git clone 網址：將遠端的repository 下載。
23. git commit --amend：更改已經commit的commit message。會進入編輯器中，直接更改後儲存後離開。
24. git reset HEAD^：(已經commit)回到commit前的狀態(還保留此次版本，只是尚未commit)
25. git reset HEAD^ --hard：(已經commit)回到上一版本的狀態(本次commit內容完全消失)
26. git reset 版本號：回到該版本號的狀態(放棄目前最新狀態)。
27. git checkout --：(未commit)回到上一版本(放棄此次修改的東西)。
28. git branch -m 新的branch名稱：修改branch的名稱 (要再想修改的branch上)。
29. git checkout 遠端brunch名稱：把遠端brunch載下來。
# .gitignore配置

# 分支的使用方法&介紹
1. 
# commit的介紹&使用
1. 
2. 
# push pull 實作

# GitFlow
