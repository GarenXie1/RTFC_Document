---
typora-root-url: ..\
---





## 创建 github remote 仓库



- https://github.com/new

![image-20221117235507920](/pic/image-20221117235507920.png)



- 创建 仓库

![image-20221117235521913](/pic/image-20221117235521913.png)



- git@github.com:GarenXie1/RTFC_Document.git



### GitHub给队友开放仓库读写权限

- `Settings` | `Collaborators` | `Add people`

  ![image-20221118000818571](/pic/image-20221118000818571.png)



- 邀请队友

![image-20221118001752734](/pic/image-20221118001752734.png)

- 等待队友验证通过

  ![image-20221118001952729](/pic/image-20221118001952729.png)

- 队友操作

  ![image-20221118002147206](/pic/image-20221118002147206.png)

  ![image-20221118002206489](/pic/image-20221118002206489.png)

- 成功邀请队友一同管理remote 仓库

  ![image-20221118002433500](/pic/image-20221118002433500.png)









## 甲修改提交到 remote仓库

- 先从 remote 仓库拉取到本地

  ~~~shell
  Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local
  $ git clone git@github.com:GarenXie1/RTFC_Document.git
  Cloning into 'RTFC_Document'...
  warning: You appear to have cloned an empty repository.
  ~~~

  ![image-20221117235939609](/pic/image-20221117235939609.png)



- 修改并提交到 remote 仓库

  ~~~shell
  Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
  $ git commit -am "1. Commit First.txt"
  [main (root-commit) 1eb4138] 1. Commit First.txt
   1 file changed, 1 insertion(+)
   create mode 100644 First.txt
  
  Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
  $ git push origin
  Enumerating objects: 3, done.
  Counting objects: 100% (3/3), done.
  Writing objects: 100% (3/3), 224 bytes | 224.00 KiB/s, done.
  Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
  To github.com:GarenXie1/RTFC_Document.git
   * [new branch]      main -> main
  ~~~

  ![image-20221118000157472](/pic/image-20221118000157472.png)



- 查看 remote 仓库的 提交信息

  ![image-20221118000406178](/pic/image-20221118000406178.png)







## 乙拉取合并_并提交到 remote 仓库

- 拉取

  ~~~shell
  git fetch origin
  git pull origin
  ~~~

  

- 合并

  ~~~shell
  # 使用到的命令
  git merge
  git rebase
  ~~~

  

- 修改并提交

~~~shell
Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
$ git commit -am "1. Nortek Garen change it."
[main 18b1996] 1. Nortek Garen change it.
 1 file changed, 2 insertions(+), 1 deletion(-)

Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
$ git push origin
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:GarenXie1/RTFC_Document.git
   1eb4138..18b1996  main -> main

Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
~~~



- 本地查看 不同的提交者

~~~shell
$ git log
commit 18b1996b78829d1c7dc8faa038b0efa02088aac0 (HEAD -> main, origin/main)
Author: NortekGaren <longhui.xie@nortekcontrol.com>
Date:   Fri Nov 18 00:28:53 2022 +0800

    1. Nortek Garen change it.

commit 1eb4138e786ddf454d137416d4c2ebcb5fa33d1c
Author: Garen <1192645898@qq.com>
Date:   Fri Nov 18 00:01:05 2022 +0800

    1. Commit First.txt

Garen@DESKTOP-TELH2GL MINGW64 /k/RTFC_Docunment_local/RTFC_Document (main)
~~~

![image-20221118003127127](/pic/image-20221118003127127.png)



## remote 仓库查看不同作者的commit

- 远程git 查看

  ![image-20221118003101938](/pic/image-20221118003101938.png)





## 可能的问题

- 甲乙丙可能无法提交到 远程git , 这就可能需要配置 SSH key. 来提交到远程 git 中.







