# Assignments

对网络提交（包括Git仓库和发送至助教）的作业，截止时间统一为所述日期22时整。

对纸质提交的作业，截止时间统一为所述日期课前。


| Date       | Homework        | Project                                  | HW Due     | Proj Due                                 |
| :--------- | :-------------- | :--------------------------------------- | :--------- | :--------------------------------------- |
| 9.6, Tue   | [H1](#h1)       | None                                     | 9.9, Sun  | -                                        |
| 9.3, Mon   | [H0](#h0)       | None                                     | 9.6, Thu  | -                                        |

## 习题课课件


## Homework

### H0

使用`ssh-keygen`生成公私钥，并将公钥发送至助教张宇翔。命名应为`名的全拼-姓的全拼.pub`(名和姓的全拼均小写)，请按照自己的姓名修改文件名。

### H1
**
本次作业请在git仓库中`HW/H1`中添加文件`answer.md`并附上**源程序文件**以及编译和运行程序的 `Makefile` 文件或**shell脚本**来回答问题。

1. 安装一个具备完善GNU工具链的环境，如任意Linux发行版/Windows Subsystem for Linux/MacOS（至少你要一个brew）；

2. 在你安装的环境下，练习使用GCC/Clang，结合使用-E（预处理器，结果大致阅读了解，在作业中指出做了哪些类型的变换）、-S、-c、-o、-m32/64参数，观察程序编译后输出的代码。请：
	- 在`HW/H1/c`中添加你的源程序、`Makefile`、shell脚本等
	- 在`HW/H1/c`中添加`answer.md`中说明该目录下的文件及子目录和使用方式
	- 在`HW/H1/answer.md`中回答本题，指出你的源代码在`HW/H1`中的位置、不同编译选项下输出的汇编码，并对汇编码加注释
	  - **注释**至少要说明不同汇编命令的含义、源程序中的变量以及中间结果在汇编码中的对应

3. 根据[课件](http://staff.ustc.edu.cn/~yuzhang/compiler/2017f/lectures/lexicalAnalysis.pdf)第16页的NFA，手工编写能识别输入串中多个满足NFA的记号的词法分析程序，写出<==><、a<=b的识别过程。**注意**：非关系运算符识别输出为other。**高级要求**：能输出每个记号对应在字符流中的起止位置。请：
	- 将源代码、`Makefile`、shell脚本等存档在在`HW/H1/lexer`目录中
	- 在`HW/H1/lexer`中添加`readme.md`中说明该目录下的文件及子目录和使用方式（包括Building和Usage）
	- 在`HW/H1/answer.md`中给出在做这一题的主要考虑、问题以及解答
	- 关于**编程语言**，默认是C语言。希望学生在提交作业时不要把检查者当成专家，要提供脚本和说明，告诉检查者怎么快速编译运行你写的程序以及程序中的要点


**注意**
- 临时文件和编译生成的目标文件、可执行程序不要提交到库中。
- `.md`是现在最常用的简单样式说明用途的文本格式之一Markdown的后缀名，你们应大致了解Markdown的排版方式，以合理的形式展现代码。关于Markdown的使用可以参考[GitHub Guide: Mastering Markdown](https://guides.github.com/features/mastering-markdown)，你也可以自行查找一些资料来了解这一Markup Language的使用方式。
- 自行查找 Makefile 文件的编写，也可以参考 [bison-examples](http://staff.ustc.edu.cn/~yuzhang/compiler/proj/bison-examples.zip) 中的 Makefile