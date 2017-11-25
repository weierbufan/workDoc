## git config配置文件
设置 git status的颜色。
```
git config --global color.status auto

```
一.Git已经在你的系统中了，你会做一些事情来客户化你的Git环境。你只需要做这些设置一次；即使你升级了，他们也会绑定到你的环境中。
你也可以在任何时刻通过运行命令来重新更改这些设置。

Git有一个工具被称为git config，它允许你获得和设置配置变量；这些变量可以控制Git的外观和操作的各个方面。这些变量可以被存储在三个不同的位置：  
* /etc/gitconfig 文件：
包含了适用于系统所有用户和所有库的值。如果你传递参数选项’--system’ 给 git config，它将明确的读和写这个文件。  
* ~/.gitconfig 文件 ：
具体到你的用户。你可以通过传递--global 选项使Git 读或写这个特定的文件。
* 位于git目录的config文件 (也就是 .git/config) ：
无论你当前在用的库是什么，特定指向该单一的库。每个级别重写前一个级别的值。因此，在.git/config中的值覆盖了在/etc/gitconfig中的同一个值。

在Windows系统中，Git在$HOME目录中查找.gitconfig文件（对大多数人来说，位于C:\Documents and Settings\$USER下）。
它也会查找/etc/gitconfig，尽管它是相对于Msys 根目录的。这可能是你在Windows中运行安装程序时决定安装Git的任何地方。

二.你的标识(Your Identity) 

* 当你安装Git后首先要做的事情是设置你的用户名称和e-mail地址。这是非常重要的，因为每次Git提交都会使用该信息。它被永远的嵌入到了你的提交中：
```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com 

```
重申一遍，你只需要做一次这个设置。如果你传递了 --global 选项，因为Git将总是会使用该信息来处理你在系统中所做的一切操作。
如果你希望在一个特定的项目中使用不同的名称或e-mail地址，你可以在该项目中运行该命令而不要--global选项。 
* 你的编辑器(Your Editor)
现在，你的标识已经设置，你可以配置你的缺省文本编辑器，Git在需要你输入一些消息时会使用该文本编辑器。缺省情况下，Git使用你的系统的缺省编辑器，
这通常可能是vi 或者 vim。如果你想使用一个不同的文本编辑器，例如Emacs，你可以做如下操作： 
```
$ git config --global core.editor emacs 

```
* 你的比较工具(Your Diff Tool)另外一个你可能需要配置的有用的选项是缺省的比较工具它用来解决合并时的冲突。例如，你想使用vimdiff: 
```
$ git config --global merge.tool vimdiff 
```
Git可以接受kdiff3, tkdiff, meld, xxdiff, emerge, vimdiff, gvimdiff, ecmerge, 和 opendiff作为有效的合并工具。
你也可以设置一个客户化的工具；查看第7章获得更多关于此的信息。 
* 检查你的设置(Checking Your Settings)
如果你想检查你的设置，你可以使用 ```git config --list``` 命令来列出Git可以在该处找到的所有的设置: 
```
$ git config --list 

　　user.name=weifansym 

　　user.email=31312312@gmail.com 

　　color.status=auto 

　　color.branch=auto 

　　color.interactive=auto

　　color.diff=auto

　　... 

```
你可能会看到一个关键字出现多次，这是因为Git从不同的文件中(例如：/etc/gitconfig以及~/.gitconfig)读取相同的关键字。
在这种情况下，对每个唯一的关键字，Git使用最后的那个值。 
你也可以查看Git认为的一个特定的关键字目前的值，使用如下命令 git config {key}: 
```
$ git config user.name 

weifansym
```
* 获取帮助(Getting help)
如果当你在使用Git时需要帮助，有三种方法可以获得任何git命令的手册页(manpage)帮助信息: 
```
$ git help <verb> 
$ git <verb> --help 
$ man git-<verb> 

```
例如，你可以运行如下命令获取对config命令的手册页帮助: 
```
$ git help config 
```
* 总结(Summary)
你应该对Git是什么以及Git与你可能使用的其它CVCS之间的不同有了一个基本的了解。你也应当在你的系统中有了一个具有你个人标识的可以工作的Git版本。
是时候来学习一些Git的基本知识了。


