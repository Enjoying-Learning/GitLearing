## 我们可以使用 Git 以及 GitHub 做哪些事情？

>要想回答git/github/任何工具可以做哪些事情，一个有系统性的思路是先看它有哪些feature，然后从这些feature极其组合出发看看有那些可能的应用。

  - 使用github作为静态博客的托管，比如jekyll、hexo等
  - 使用git来管理自己的工作文档（使用纯文本文件markdown，word之流的不适用）
  - 使用github来向开源程序的作者提问题（比email更方便一些，且能得到更多的人的帮助）
  - 使用git做网站维护（每次先将网站的服务器上的程序程序下载到本地，修改过commit到git后再覆盖到网站的服务器上）
  - 使用git做程序代码收集器，使用分支和标签的功能来管理同一套的程序各种主题、插件等内容

### 调参数神器

对于文本文件，git可以高效地保存历史，方便回滚到以前的状态。如果每个参数设定都搞一个commit，在commit message里面写上定量的效果如何，就方
便回滚到最好的参数。

### 分支管理=>写文档神器

写文档一般都有好几个版本在进行。一个比较成型但不少新想法还没加进去的给老板看的版本，不成熟的新想法版本1，不成熟的新想法版本2等等。如何在不同版本间自如切换就要用到git branch和git rebase了。用git相比于拷贝粘贴的好处体现在——有些更改是会影响到所有版本的。这时候用git的分支管理直接rebase就可以把一段更改同时应用到所有版本里。同时新想法也会逐渐并到给老板看的稳定版本里，用git也十分方便。

### git hook=>自动化神器

git 有个比较高阶一点的功能是 [git hook](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)。大概的说就是每次执行git push的时候，客户的git会向一个远程服务器比如github发起push请求，内容是我做了这些更改有这些commits等等。服务器在接受完数据以后可以直接挂断，也可以执行一个用户指定的小程序。比如你可以（用某种方法，方法是什么下面讲）告诉服务器这个“制定的小程序”就是ls，那么服务器在你的git push执行完以后就会执行一下ls，然后把执行的结果（当前repo下面的文件列表）发给你。你的git收到以后会把这个打印在屏幕上。

具体怎么指定这个“特定的小程序”，不同的平台不一样。
如果是github可以看一下[webhook](https://help.github.com/articles/about-webhooks/)

- 结合github的web hook可以实现代码更新邮件提醒等功能 
[Automatic Email Notification on Github Pushes](https://grapeot.me/automatic-email-notification-on-github-pushes.html)。
- 代码的自动连续部署和测试[Self-Updating Node.js Web App](https://grapeot.me/self-updating-nodejs-web-app.html)

作者：grapeot
链接：https://www.zhihu.com/question/23835324/answer/25813506
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
