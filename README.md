# git-demo-0106

### Them toan bo su thay doi cua cac file vao stage change

```
git add .
```

### Xem trang thai hien tai cua cac file va buoc thuc hien tiep theo

```
git status
```

### Dong goi de chuan bi push (commited)

```
git commit -m "Message..."
```

### Xem thong tin commit

```
git log
```

```
git log --oneline
```

### Xem thong tin chi tiet thay doi commit

```
git show <commit_id>
```

```
gitk
```

### So sanh su thay doi code truoc va sau commit

```
git diff <commit_id>
```

### Xem cac nhanh hien hanh

```
git branch
```

### Tao nhanh va chuyen sang nhanh do

```
git checkout -b <branch_name>
```

### Chuyen nhanh

```
git checkout <branch_name>
```

### Xoa nhanh
```
 git branch -D <branch_name>
```

### Dong bo code tu remote repo ve local repo

```
git pull
```

```
git pull origin master
```

### Sao chep code tu remote repo ve local repo

```
git fetch <branch_name>
```

```
git pull origin <branch_name>
```

### Dua trang thai cua file tu Staged change => Change

```
git reset <file_name>
```

```
git reset
```

### Backup commit ve commit cu (old version)
#### Note: Han che xai, nen tao commit moi de fix commit loi

```
git revert <commit_id>
```
### Quy trinh lam viec trong thuc te
1. pull code moi nhat ve tu base (master/develop)
2. checkout sang nhanh moi va lam task cua minh
3. git add, commit, push origin <current_branch>
4. Tao Pull Request (PR), Chon nguoi review neu can, chon nhanh gop (master/develop)
5. Tu review lai code, Duoc phe duyet thi merge
6. Neu co loi xay ra can fix thi
   1. Ve VSCode xu ly loi
   2. git add, commit --amend, push origin <current_branch> -f
7. Quay lai buoc 5
8. Can tao PR khac de fix PR truoc (it gap)

### Resolve Conflict:
- Method 1: Use Rebase
+ Checkout ve master + pull code moi nhat ve
$ git co master
$ git pull
+ Checkout sang nhanh bi conflict + su dung rebase
$ git br
$ git co <conflict_branch>
$ git br
$ git rebase master
+ Vao Visual Code fix conflict su dung hint
$ git add .
$ git rebase --continue
$ git log --oneline
+ Push len github
$ git push origin <conflict_branch> -f

- Method 2: Using merge
+ Checkout ve master + pull code moi nhat ve
$ git co master
$ git pull
+ Checkout sang nhanh bi conflict + su dung rebase
$ git br
$ git co <conflict_branch>
$ git br
$ git merge master
+ Vao Visual Code fix conflict su dung hint
$ git add .
$ git ci -m "resolve conflict."
+ Push len github
$ git push origin <conflict_branch> -f
