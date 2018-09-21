# FAQ 




- <a href="#1">`1. ssh/git相关`</a>
- <a href="#2">`2. HW相关`</a>
- <a href="#3">`3. Lab相关`</a>
- <a href="#4">`4. 其他系统/平台/环境等相关`</a>
- <a href="#5">`5. 课程资源`</a>
- <a href="#6">`6. 目录结构`</a>

 <a id="1"/>
 
## 1. ssh/git相关

1.1 服务器是否外网ip可以访问?
> 可以, 不限于校园网ip

1.2 把私钥弄丢了怎么办?
> 重新生成,发给助教

1.3.1 生成了公私钥之后,怎么ssh到服务器上的git?
> 可以配置~/.ssh/config文件,配置方式如:

``` text
Host pc
HostName 202.38.79.111
    User git
    Port 13022
    IdentityFile path/to/your/id_rsa
```

>或者

``` bash
eval $(ssh-agent -s)
ssh-add path/to/your/id_rsa
```

1.3.2 如果提示权限太open怎么办?
> 这个error指的是私钥的权限太open,不够安全, 可以用`ll`查看,用`chmod` 修改,一般`chmod 600`是推荐的权限.

1.3.3 如果要求填入下面这样的密码怎么办?

``` bash
git@202.38.79.111's password:
``` 

> 这个提示是让你填写我们服务器上的git用户的密码.说明你的公私钥的登录方式发生了错误,一般情况下是你的私钥没有配置正确.(极少数情况下是老师的公钥没配置正确).配置方式参照前两个问题.


1.3.4 对于助教反馈的`reply.md`,没有通过`git branch -r` 看到鸭?
> 记得先git pull.
> 对于git的用法,务必参考你们git库下面的REAMDME-git!!!!!!!

<a id="2"/>

## 2. HW相关  

2.1 作业的程序有语言要求吗?

> 默认要求是C,但也可以在向老师/助教提供充分的说明(比如如何快速的编译,运行)的条件下,提交其他语言的程序.

2.2 第二个作业有程序的复杂度要求吗?
> 如果没有明确的要求,就没有要去.

2.3 词法分析那题的输入输出格式具体有什么要求
> 对于作业hw(而非实验lab),我们没有用自动化的测试工具进行测试.输入输出格式没有具体要求,向大家开放.大家可以自行设计.唯一的要求是将输入输出格式在说明文档,在这次是readme.md里面进行必要的说明,只要求语言人性化一点,助教可以马上看懂即可.

2.4 不同编译选项输出的汇编码要贴到answer吗?
> 可以不贴,但需要给出必要的描述.可以贴,但需要必要的注释,不建议大段的粘贴.

2.5 平时这种小实验是独立做了就满分吗?
> 嗯,但是会指出存在的问题.

2.6 提交到git的目录结构?
> 就是子目录下的`README.md`是写对目录里文件的使用，`answer.md`是写对作业中问题的回答和分析。写readme的目的是希望让你们养成在发布的文件夹上写说明的习惯

2.7 现在才给评价标准是不是晚了点?
> 我们的评价标准是根据第一次大家的提交发现的问题总结的.目的是为了让大家在之后的lab/hw提交中知道标准.

### new [9.21 updated.]

2.8 纸质作业交到哪里?什么时候交?
> 纸质作业交到讲桌旁边的白色小桌子上,截止日期当天上课前交.

<a id="3"/>
 
## 3. Lab相关

3.1 antlr用4.5行吗？因为想直接apt解决，apt里的最新版本是4.5.3?
> 严格按照文档要求来，之后实验批改是半自动的，不要因为版本问题给自己和助教找麻烦。

3.2 怎么确认装好了llvm？
> 可以写个简单的程序,用安装好的目录的clang编译一下.

3.3 lab1的ddl是什么时候?
> 老师没有明确给出ddl的实验,至少会在一周之后以后才截止.但是根据往年的经验,你做得越早,效果越好!

3.4 llvm打包错误是什么意思?
> 这个是去年助教的说法,我去问一下.[to be continued.]

3.5 能不能解释一下C1语言中Identifier,IntConst,FloatConst的自然语言定义？参考的文件打不开.
> 今年我们的C1是参照标准的C99进行修改的,参照的这个pdf文件,我们放在了qq群文件里.在这里建议大家学会科学上网.科大LUG(Linux User Group)是个分享技术的好平台,大家可以去交流/学习一下.

3.6 编译llvm的时候卡住是不是意味着又爆内存了?
> 这个可以通过top/htop等指令查看内存的使用情况.

3.7 执行antlr4指令之后提示 Error: Could not find or load main class org.antlr.v4.Tool什么意思?
> CLASSPATH变量没有配置好,或者配置好了,但是没有更新Shell,可以source sh, 或者重新打开该shell.
> 配置方式:把.jar文件本身的路径放到CLASSPATH里

### new [9.21 updated.]

3.8 '\\'除了注释中需要考虑吗?
> 不需要,我们在本次实验中只考虑注释中的'\\'.

3.9 ft_测试是要 lexer 报错退出吗?
> 可以报error,也可以是其他的识别错误的例子.测试样例不需要想的很复杂.这个我们的要求不是很严格,你言之有理即可.

3.10 整型常理忽略后缀的话，八进制不就包含在十进制的表达中了，都不用分那么细了吧?
> 并不,017是八进制,而且文法中0是八进制,二者并无重合.

3.11 ISO/IEC为什么没有提到负整型常量啊?
> 看文法.运算符.

3.12 虚拟机编译安装llvm时候 内存不足卡住怎么办?
> make -j1, 单线程占用的内存少.然后多分配内存.
> make -j的话,会按照你给虚拟机分配的cpu，自动多线程。多线程会占用更多的内存

3.13 请问下3e4这种应该被看做是int还是float啊？
> 看文法.

3.14 C1语言不用识别字符串的吗？
> 看文档.没有字符串这个类型.

3.15 请问token中没有预定义注释，我们是自己新建一个token吗？
> 注释是给人看的，编译器不需要注释，所以就就直接扔掉了. ('->skip')

3.16 关于注释中'\\'的其他问题?
> 不建议大家过度的考虑由于反斜杠导致错误情况，错误的测试用例应该根据同学们之前编写程序的经验去构造，而不是凭空的去构造。错误用例不再数量多少，关键是要能够反映出大家的思考。

3.17 像x=09这种这种问题，antlr会识别成0和9两个intconst，而不是报错，这种类型的错误是不是要留到语法的部分处理？
> 是的.
<a id="4"/>

## 4. 其他系统/平台/环境等相关 

4.1 64位机器没办法运行32位的程序怎么办?
> wsl一般情况下只支持64位.ubuntu可以通过`apt-get install gcc-multilib`

4.2 linux可以查看xlsl文件？
> 可以.openoffice, soffice

4.3 `top`指令里的buff/cache是什么?
> 记得谷歌,谷歌之后,你会发现 [linux - What do the "buff/cache" and "avail mem" fields in top](https://unix.stackexchange.com/questions/390518/what-do-the-buff-cache-and-avail-mem-fields-in-top-mean) 这一条,然后发现:

``` text
[buffers]
    Memory used by kernel buffers (Buffers in /proc/meminfo)
[cache]
    Memory used by the page cache and slabs (Cached and  SReclaimable in /proc/meminfo)
[buff/cache]
    Sum of buffers and cache
```

<a id="5"/>

## 5. 课程资源 

4.1  bison-examples.zip解压缩不了?
> 通过快压可以.....

4.2 老师上课放的例子在主页的什么位置?
> 在bison-examples同一个[页面](<http://staff.ustc.edu.cn/~yuzhang/compiler/second/2017f.html>)下面,叫flex-examples.

<a id="6"/>

## 6. 目录结构 

### 6.1 HW 目录结构

6.1.1 HW1
``` text
- <your repo>
  | H1
    | c
      | readme.md
      | *.c 
      | Makefile / *.sh
    | lexer
      | readme.md
      | *.c
      | Makefile / *.sh
    | answer.md
  ...
```

### 6.2 Lab 目录结构

6.2.1 Lab1-1
``` text
- <your repo>
  | c1recognizer         复制自公共仓库的 c1recognizer 项目，请勿遗漏内容。
    | cmake/
>>  | grammar/           修改其中的 C1Lexer.g4
    | include/c1recognizer/ 
    | src/
>>  | test/test_cases/   增加你的测试程序
>>  | doc/               增加文档描述实验中遇到的问题、分析和设计，文件名前缀为lab1-1
    | 其他已有的文件
```
