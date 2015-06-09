#Fudan ICS Spring 2013
####Lab 3: Pipelined Y86 Implementation
##### 张谦 13307130226 13级计算机科学与技术


#1 Introduction
In this lab, you will learn about the design and implementation of a pipelined
Y86 processor. You can design this lab based on textbook Sec. 4.5 Pipelined
Y86 Implementations (Page 317, English-Version).
This lab is team work, 2-4 persons for each group. Each team should has
a team leader who assigns the tasks and give the nal presentation (report).
Three persons per team is appropriate, one for design GUI, one for design Y86
instuctions, one for documentation and presentation.

#2 Example
In textbook, Figure 4.42 (Page 324) gives us the example of Y86 instruction.
This code loads values 10 and 3 into program registers %edx and %eax.

```
# prog1
0x000: irmov1 $10, %edx
0x006: irmovl $3, %eax
0x00c: nop
0x00d: nop
0x00e: nop
0x00f: add %edx, %eax
0x011: halt
```
Figure 1 shows the pipelined execution of prog1 without special pipeline control.

#3 Y86 Implementation
You can use any programming language to nish this lab, such as C/C++,
Java, VB, C#, Lisp, Python and etc.
In this lab, you should implement the basic functions as follow.
1. Design a GUI for users, which shows the following infomations (30 pts):
* For each cycle, GUI shows the each stage's opration (Fetch, Decode,
Execute, Memory, Write back). 
* For example, (Figure 1) the opration
in cycle 6: R[%eax] 3.
* For each cycle, show the register, condition code register,the data memory,
and the program counter.
2. Y86 instruction implementation (15+15+15+5 pts)
four move instructions (irmovl, rrmovl, mrmovl,rmmovl)
four integer operation instructions (addl, subl, andl, xorl)
seven jump instructions (jmp, jle, jl, je, jge, jg)
two selective instructions from call, pushl, popl, halt.
3. Implement one of avoiding data hazards and give corresponding test instance.
(10 pts)
__Note__: Any addtional implementations and test instaces will for 10 pts.

# 4 Hand In Instructions
![haha](https://raw.githubusercontent.com/qzane/gitpic/master/ics.p1.png)

0. install python3 `$> sudo apt-get install python3`
2. run `$> python3 gui.py`

# 5 功能描述
*  Y86模拟器内核，见pipe.py，使用了面向对象的变成方法，把流水线的每一层都作为一个layer处理
* 内核部分无需修改代码即可兼容python2/python3
* 在代码区会提示流水线每块此时正在执行的代码
* 有容量为5Byte的Cache
* GUI界面使用python内置的Tkinter编写，全部使用官方标准库


####张谦 13307130226 13级计算机科学与技术



