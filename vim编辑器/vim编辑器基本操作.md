#Vim 编辑器基本操作  
### vim有三种模式  
命令模式:使用vim打开或创建文件的时候进入的模式就是命令模式。这种模式下可以进行剪切、删除、粘贴、撤销等操作。  
插入模式:当键入aio字母的时候进入插入模式，此时可以键入文字等内容。  
a 在光标所在字符后插入  
A 在光标所在行尾插入  
i 在光标所在字符前插入  
I 在光标所在行行首插入  
o 在光标下插入新行  
O 在光标上插入新行  
  
扩展模式：以:开头,可以进行保存、退出等操作  
			change		delete		(yanked)copy  
line		cc			dd			yy  
letter		cl			dl			yl  
word		cw			dw			yw  

c means cut and enter insert mode  
d means delete  
y means copy(yanked)  

u 撤销最近的一次操作  
ctrl + r 回撤  
U  撤销最近的所有修改  

4dd 删除当前光标所在行下面的4行  
dG 删除光标所在行到文件末尾内容  
D 删除光标所在处到行尾内容  
:n1, n2d删除指定范围的行  
4yy 复制当前光标所在行下面的4行  
4x	删除光标所在的后面4个字符  
p,P粘贴在当前关掉所在行下或行上  

R 进入替换模式,按ESC键退出  

### 快速定位
G 跳转到当前文件的最后一行 
gg 跳转到第一行 
1g 跳转到当前文件的第一行  
nG 跳转都第n行   
:n 跳转到第n行  
$ 移至行尾  
0 移至行首  

ctrl + d 向下滚动半屏  
ctrl + u 向上滚动半屏  

H	跳转到当前屏的第一行  
M	跳转到当前屏的中间  
L	跳转到当前屏的最后一行  

z + enter 使当前行成为当前屏的第一行  
z -使当前行成为当前屏的最后一行  

### 查找和批量替换
sed  
:s/i/_将当前行的第一个i替换成_  
:s/i/_/g当前行的所有i替换成_  
:1,10s/i/_/g将第1行到第10行的所有i替换成_  
:1,$s/i/_/g将当前文件中的所有i替换成_
:%s/old/new/g 全文替换指定字符串    

### 扩展模式下：  
:r file将该文件插入到当前文件的光标下面  
:r !command 将命令执行的结构插入到光标所在的位置  
:1,20 w file 将1-20行的内容写到一个file中 类似于文件的拆分  
:1,$ w file将整个文件复制到另一个文件中 常用于备份操作(编辑配置文件,将当前编辑的文件备份下又不想修改当前文件的内容)  
：1,20 w >>file将1-20行的数据追加到file中 追加位置  
:w filename 另存为  
### 定义快捷键  
扩展模式下 输入map, 然后按下ctrl + v 再按下要定义的 ctrl + p 快捷键，后面跟要执行的操作，比如 I#<ESC> 表示按下 ctrl + p 的时候执行大写的I，跳到行首并进入插入模式，然后输入#，并按ESC进入命令模式   

### 设置
:set all 显示所有的可设置项  
:set 显示所有  
