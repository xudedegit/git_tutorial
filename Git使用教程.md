#  为什么要使用Git？
Git是一款非常实用并且先进的分布式版本控制系统，在我们日常处理文件时，经常会经历反复修改的过程，最后文件夹中会躺着类似如下的情况：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211140345618.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
一般我们都是通过文件名的不同进行版本管理，当文件数量更多的时候，这种方式的弊端就会暴露出来，以至于最后自己都不记得哪份才是最新版本。
或者在编写代码时会遇到Bug，需要回头找错误，但是却不知道是在哪个环节添加的代码出了问题，很难排查出Bug是由于哪几行代码导致的，影响开发效率。这时就需要一个可以管理版本的软件，Git优于其他版本管理系统的原因之一，就是因为Git跟踪并管理的是修改，而不是文件，这里的修改指的是每次的添加或删除，然后通过时间线的方式进行管理，这样就可以根据需求很自如地回退到某个时间点的文件。
#  安装Git
下面的链接是git的官方网站，根据自己使用的系统进行下载：
**[https://git-scm.com/downloads](https://git-scm.com/downloads)**
安装好Git后，在桌面鼠标右键会有Git Bash的图标，点击后会弹出一个terminal,在命令行窗口中还需要进行如下设置：
```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```
你的机器作为分布式版本控制系统的一部分，需要对你的机器进行命名。
#  创建一个版本库
## 首先打开命令行窗口
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211152108783.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
## 输入命令创建版本库
```
$git init
```
该命令是为了在一个目录下创建版本库。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211152331499.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
这时就会创建好一个文件夹，并在文件夹中创建了一个版本库，如果显示隐藏文件的话会看到一个.git的文件，注意一定不要修改这个文件。这个隐藏文件就是我们的版本库。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211152626884.jpg#pic_center)
## 创建一个C文件，添加并提交到版本库中
创建了一个文件之后，但是没做其他操作，文件上会显示一个小感叹号
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211161219270.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
输入以下命令后，文件就会被添加并提交到版本库中。修改之后可以添加一次就提交一次，也可以添加多次之后统一提交，因为commit可以提交很多文件。-m后的部分就是对你所修改内容的一个说明。
```
$git add <文件名>
$git commit -m "******"
```
可以看到当文件被添加并提交到版本库后，文件上的小图标就会变成一个绿色的对号
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201211161554327.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
这个warning是由于windows中换行符为回车，在linux下换行符是换行造成，但不影响正常工作，具体可查阅资料。
注意：在编写代码或文本时，不建议使用windows自带的编辑器，推荐使用**Notepad++**，且将编码设置为**UTF-8 without BOM**。

#  时光穿梭
##  版本回退
先添加并提交几个不同的版本的test.c文件。
（1）第一次添加并提交到版本库
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214210418726.jpg#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214210554995.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
（2）第二次添加并提交到版本库
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214211217505.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214211412563.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
（3）第三次添加并提交到版本库
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214211749426.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214211708435.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
查看当前提交的全部版本
```
$git log
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214212857754.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
也可以输入以下命令换一种形式展示全部版本。
```
$git log --pretty=oneline
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201214213426458.jpg#pic_center)
因为在每次提交之后，git都会将操作串成一条时间线进行管理，所以现在我们也可以回退到某个时间，这里我们将会使用上图中红线标出的id（版本号）作为我们回退时的目的地。下面将展示版本回退的过程。
输入如下命令可以显示当前版本：
```
$git reset --hard HEAD
```
输入如下命令可以回退到上一个版本：
```
$git reset --hard HEAD^
```
以此类推想要回到上上一个版本的命令就是：
```
$git reset --hard HEAD^^
```
如果版本过多的话，^太多会数不清，假如想要回退到50版本，则可以表示：
```
$git reset --hard HEAD~50
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020121509400536.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
回退到上一个版本后，查看一下test.c文件中的信息，确实是回到了"add test 2"的状态。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215094631991.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
再试一下回到第一个版本。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215095124214.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
此时查看一下当前的全部版本。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215095604349.jpg#pic_center)
可以看到只剩下第一次添加的版本了。
## 后悔药
如果你的代码回退到了最初的版本，但是第二天你突然后悔了，还是想要从过去的版本回到新的版本，这时可以通过ID（版本号），也就是我们的目的地，回到我们想要的版本。这里有一个问题，就是当我们已经回退到最初的版本后，新添加的版本的id不就看不到了吗？如果你的命令窗口没有关闭，可以往上翻找到你新版本的ID，当然，如果找不到也没关系，可以使用如下命令：
```
$git reflog
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215100931170.jpg#pic_center)
这样就会显示出来你所添加的所有版本的ID了，假如我现在想要回到"add test 3"的版本，那么1589b.....就是这个版本的ID。
```
$git reset --hard 1589b
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215101228379.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
可以看到此时，后添加的版本又回来了，查看一下test.c文件中的内容，也是如我所愿。Git的回退速度是很快的，Git内部相当于有一个HEAD指针，指向当前版本，当你输入指令回退到不同版本时，HEAD指针就进行移动，顺便工作区的文件也会更新，也就是我们test.c中的内容。

## 工作区和暂存区
Git和其他版本控制系统的区别在于Git有一个叫暂存区的概念。

当我们在某个目录下输入命令`$git init`时就会在该目录下创建了一个版本库，此时的这个目录也就是我们的工作区。上文也提到.git这个隐藏文件是我们的版本库，内部的文件不要修改，因为版本库中包含着最重要的暂存区（stage/index），还有Git为我们自动创建的第一个分支master，以及指向master的指针HEAD。

我们想要将代码存放到版本库要分为两个步骤，分别是`$git add <flie>`和`$git commit -m "***"`，其中git add的过程就是将我们工作区的文件添加到版本库的暂存区(stage)中，然后`$git commit -m "***"`的过程是将版本库暂存区中的文件提交到版本库中的分支中，当前我们只有master一个分支，那么`$git commit -m "***"`后，文件就会提交到master分支中，HEAD指针指向最新提交的版本。

所以这里就可以理解了之前提到的添加和提交两个步骤，可以添加一次就提交一次，也可以多次添加后一次性提交。若添加一次就提交一次，也就是将我们本地工作区的文件添加到版本库的暂存区，紧接着就提交到master分支上进行管理；若多次添加再提交，也就是将我们在本地工作区多次的修改添加到版本库的暂存区，然后一次性的都提交到master分支进行管理。两种方式都是可行的，要根据自己的需求。接下来实际操作一下：

对test.c文件进行修改，又写入了一个打印函数。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215110247147.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
当我们`$git add <file>`将文件添加到版本库的暂存区后，还没有`$git commit -m "***"`提交，我们通过如下命令查看一下当前的状态：
```
$git status
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215110812220.jpg#pic_center)
Git提醒我们此时有一个被更改的文件test.c还没有被提交。我们将添加到版本库暂存区的文件提交到master分支上再查看一下状态。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215111244120.jpg#pic_center)
此时的工作区就变得干净了。
## 撤销修改
**（1）如果在工作区中做了一些修改但是觉得不满意想要撤销如何操作。**
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215112559715.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
在对test.c文件进行修改，但是并没有添加、提交，查看一下目前的状态。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215124341508.jpg#pic_center)
如果此时你对此时所作的修改不满意，可以使用如下命令撤销修改（注：此时的修改并没有添加并提交！！！）：
```
$git checkout -- <file>
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215124824587.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
这可以看到test.c文件又回到了修改前的版本，此时与暂存区内的版本时相同的。

**（2）下面进行实际操作一下，如果修改后的文件添加到暂存区后应该如何撤销修改（注：此时已经将文件添加到暂存区，但是并没有提交！！！），输入如下命令：**

```
$git reset HEAD <file>
```
输入这条命令后就代表将我们添加到暂存区的修改撤销，重新放回到工作区。工作区的修改如何撤销，就是参照上面所提到的内容，使用如下命令即可：
```
$git checkout -- <file>
```
实际操作如下，先是对test.c文件进行修改。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215130633785.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
查看目前状态。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020121513080079.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
Git提示我们文件已被修改，如果需要添加的话就使用`$git add <file>`的命令，如果需要撤销则使用`$git checkout -- <file>`的命令可以撤销工作区的修改，我们现在将该版本添加到暂存区。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215131101954.jpg#pic_center)
添加到暂存区后，Git提示我们该文件还没有被提交到分支master，如果想要撤销可以使用`$git reset HEAD <file>`的命令撤销暂存区的修改，重新放回工作区，现在我们尝试一下。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215131324975.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
此时我们可以看到在使用`$git reset HEAD <file>`命令之后的状态，Git提示我们暂存区没有需要提交的修改，这与刚才没有将修改添加到暂存区时的状态是一样的，也就是回到了工作区刚被修改的状态。如果需要添加到暂存区并提交到分支master，则必须先`$git add <file>`；如果想要撤销工作区的修改，再次`$git checkout -- <file>`即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215131737834.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
此时的状态是在分支master上没有修改被提交，而且工作区也是干净的，再次查看一下test.c文件，确实回退到了修改之前！

**（3）如果你的修改文件添加到了暂存区，并且也提交到分支master，此时需要撤销的话就要使用之前提到的版本回退。**

**小结**：
（1）如果文件只是在工作区作了修改，想要撤销修改的话使用命令`$git checkout -- <file>`。
（2）如果文件在工作区作了修改之后，并添加到暂存区后，此时想要撤销修改，使用命令`$git reset HEAD <file>`撤销到工作区，想要继续撤销工作区的修改，再次使用命令`$git checkout -- <file>`。
（3）如果文件在工作区作了修改，并且添加到暂存区后又提交到分支master，此时想要撤销的话，就要使用版本回退。
##  删除文件
删除文件也是一个修改，在工作区新建一个文件并添加到暂存区，如果此时将工作区的文件删除掉之后，Git会提示此时暂存区和工作区是不一样的。
（1）如果确实希望删除掉该文件，使暂存区与工作区保持一致，则输入如下命令：
```
$git rm <file>
$git commit -m "***"
```
创建一个新的文件并添加到暂存区，然后删除掉工作区的该文件。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215135742759.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
查看当前状态。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215135851776.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
使用命令`$git rm <file>`删除文件，并使用命令`$git commit -m "***"`提交。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215140303390.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
这样文件就成功的从暂存区删除掉了，与工作区保持一致。
注：命令`$git diff`是显示工作区和暂存区目前的区别。
**（2）如果是误删了工作区的文件，想要恢复该如何操作。**
因为工作区的文件已经添加到了暂存区，但是现在工作区的文件被误删掉，此时工作区和暂存区中的内容不一致了，如果想要恢复的话只需要将暂存区中的内容替换到工作区即可，使用的命令和上文提到的**将工作区的修改撤销**是一样的，所以这里可以得出命令`$git checkout -- <file>`的原理就是将暂存区的内容替换到工作区。实际操作如下：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215143938114.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201215144042396.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2FzZGFzZGFzZDY2Ng==,size_16,color_FFFFFF,t_70#pic_center)
可以看到使用命令$git checkout -- <file>后确实将暂存区的内容替换到工作区了。
