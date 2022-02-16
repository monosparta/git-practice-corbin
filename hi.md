# git 介紹
 * 2005 年時，開發 Linux kernel 的社群與開發 BitKeeper 的商業公司的合作關係結束，也就無法再免費使用該工具。 這就迫使了 Linux 社群（特別是 Linux 之父 Linus Torvalds）基於使用 BitKeeper 所學到的經驗，來開發自有的工具。
* 何謂版本控制？：版本控制就是將所有檔案的歷史紀錄的版本都保存下來，以便之後檢查時查看。
# 版本控制的邏輯
1. 集中式：有個伺服器來集中管理所有版本的檔案，讓用戶端去連線至伺服器取出檔案來使用。
>![集中式](https://git-scm.com/book/en/v2/images/centralized.png)
2. 分散式：用戶端並不只取出最新的檔案快照；還把整個倉儲做個鏡像。 假設有任何一個協同合作的伺服器故障，事後都可以用任何一個用戶端的鏡像來還原。 因為每個地方都有完整的資料備份。另外，分散式可以和各種遠端倉儲做互動，因此可以和很多部群組的人去進行專案協同合作。
> ![分散式](https://git-scm.com/book/en/v2/images/distributed.png)
3. 分散式和集中式的比較：
> 1. 比較後的優點：
> * 無網路連線時，也可以存取其電腦中的軟體存庫。
> * 不須和中央達成通訊便能上傳資料，速度快。
> * 資料不用單一主機進行備份，避免單點失效之風險。
> * 自由開放的原始碼中，若有管理上的衝突或設計不同，可以輕易的從專案中分出新的分支。
> 2. 比較後的缺點：
 > * 剛開始儲存較慢，需將所有分支及版本歷史下載下來。
 > * 每一個使用者都需要備份所有的資料、分支及版本歷史，需要額外儲存空間。
 > * 各軟體儲存庫內容不一定同步。

# Git的常用指令介紹
> 1. git init ：初始化git
> 2. git status ：git版本查詢
> 3. git add ：檔案加入版本控制 例：git add 123
> 4. git add .： 所有檔案加入版本控制
> 5. git rm --cached：把檔案移除版本控制 例：git rm --cached 456
> 6. git commit：新建版本，會進入vim編輯器，可加入commit message，"q!"或"wq"跳回
> 7. git commit -m "版本敘述"：不進入vim直接給commit message 例：commit -m "1st"
> 8. git commit -am"版本敘述"：把所有檔案加入版本控制&建立版本(git add 和 git commit -m"" )的綜合功能。
> 9. git log ：查看版本的歷史紀錄。版本上方會寫commit+英數，就是它的版本號。
> 10. git log --online：查看簡單版本的歷史紀錄，版本號為最簡易的前七碼。
> 11. git checkout：git checkout +"完整"的版本號，改道版本號的版本。
> 12. git checkout master：把版本改到最新的版本。
> 13. .gitignore：不想被版本控制的檔案。先用touch建立.gitignore檔，再將不想被版本控制的檔案加入.gitignore檔（透過 vim .gitignore，再輸入不想被版本控制的檔名，按 :wq離開），即便之後一次用 git commit –am，.gitignore 檔也不被被版本控制。
> 14. git diff：在更改後的檔案再次加入版本控制前，可用git diff 看到版本更改的東西在哪
> 15. git branch -v：確認主幹&分支。
> 16. git branch :新增分支且命名 例：git branch 789。
> 17. git branch -d：刪除分支 例：git branch -d 1011。
> 18. git checkout ：移動到該分支 例：git checkout 789。
> 19. git merge ：把分支合併到目前所在的分支 例：git merge 1213。
> 20. git push：將本機已經commit 的版本上傳更新至github。例：git push origin(遠端主機) 1415。
> 21. git pull：把遠端的分支下載下來 例：git pull origin 1415。
> 22. git clone 網址：將遠端的repository 下載。
> 23. git commit --amend：更改已經commit的commit message。會進入編輯器中，直接更改後儲存後離開。
> 24. git reset HEAD^：(已經commit)回到commit前的狀態(還保留此次版本，只是尚未commit)
> 25. git reset HEAD^ --hard：(已經commit)回到上一版本的狀態(本次commit內容完全消失)
> 26. git reset 版本號：回到該版本號的狀態(放棄目前最新狀態)。
> 27. git checkout --：(未commit)回到上一版本(放棄此次修改的東西)。
> 28. git branch -m 新的branch名稱：修改branch的名稱 (要再想修改的branch上)。
> 29. git checkout 遠端brunch名稱：把遠端brunch載下來。
# .gitignore配置

# 分支的使用方法&介紹
* 介紹：分支是為了將修改記錄的整體流程分開儲存，讓分開的分支不受其他分支的影響，所以在同一個數據庫裡可以同時進行多個不同的修改。分開的分支還是可以和其他分支合併的。
 * 使用方法：

> 1. 建立分支：
```
git branch imbranch
```
![1](/nwe.png)

> 2. 顯示分支列表：(有*號的就是現在的分支)
```
git branch
```
![2](/look.png)

> 3. 切換分支：
```
git checkout imbranch
```
![3](/seitch.png)
```
git checkout -b 新分支名稱

*直接建立新分支且同時切換過去
```
![4](/newnew.png)

> 4. 合併分支：
```
git merge 分支名稱
```
![5](/merge.png)

> 5. 刪除分支：
```
git branch -d 分支名稱
```
![6](/delete.png)

# commit的介紹&使用
> 1. 介紹：開發者要將修改檔案後的專案內容，增加為一個新的專案版本，這個動作就稱為提交(commit)
> 2.指令：
```
git commit
*須進入編輯器寫版本訊息
```

```
git commit -m "版本訊息"
*無須進入編輯器直接寫版本訊息
```
![7](/commit.png)

# push pull 實作
> 1. push 123

> 2. pull 

![9](/pull.png)

# GitFlow
