---
title: awk and sed
tags: [IT]
date: 2017-05-22
---

好记性不如烂笔头，记录目前用过awk和sed的功能，另外解析个中含义，达到知其所以然的效果。

### awk

#### 多行变一行：

    awk '{a=a" "$1}/   rn/{print a;a=""}' inputfile > outputfile
    
a是字符串变量，在读多行文件，把每一行的第一个字段内容在a后面拼接到a(顺序输出)，当行出现 rn 标识的时候，输出a， 然后 a=""则是把a赋值为空。如此循环把文件内容读完。

    awk '{a=a?$1" "a:$1}/^   Ccy/{print a;a=""}' inputfile > outputfile
    awk '{if(a){a=$1" "a} else{a=$1}}/^  Ccy/{print a;a=""}' inputfile > outputfile
    
上面两句意思一样，判断变量是否为非空，非空就执行a=$1" "a, 空就执行a=$1, 如此形成倒序输出。一般第一次a肯定是空的，就把第一行的第一个字段内容写入a，后面a就不空了，就执行a=$1" "a，遇到Ccy就结束，输出a,  然后a赋值为空。


#### 关联查询，类似sql关联查询输出

    awk 'FNR==NR{a[$2]=$4;next}{if(a[$6]) {print $0,a[$6]} else{print $0,"rn=""\047"1"\047"}}'  file2 file1 > outputfile

NR,表示awk开始执行程序后所读取的数据行数；
FNR,与NR功用类似,不同的是awk每打开一个新文件,FNR便从0重新累计。

数组变量a是给file2用 ,，将文件file2字段4（$4）内容赋值给a[$2]，$2就是键（下标），$4就是值，
FNR==NR为真，读第一个文件file2，{a[$2]=$4;next}就是循环地把file2文件每行的$4内容赋值给数组a[$2],$2是下标。
FNR==NR为假，读第二个文件file1, {if(a[$6]) {print $0,a[$6]} else{print $0,"rn=""\047"1"\047"}}
file1的$6和file2的$2 是关联的对象,类似sql的内外键，二者相等，因为现在读的是file1，此时数组a下标用file1的$6表示。
这里先判断数组a[$6]是否存在，即是file2文件的$4是否存在，存在则输出；否则赋值  "rn=""\047"1"\047"（rn='1'，这是字符串，所以前后都有双引号）, \047代表单引号'
$0是文件file1每行内容。



### sed

#### 一行拆成多行

sed -n '/[头标识]/,/[尾标识]/p' [input-file] > [output-file]
例如： 

    sed -n '/GerneratedPK=/,/\//p' inputfile > outputfile   
    
转义字符\/ ，代表/ 。


#### 替换

    sed "s/\/>/  rn='1'/g" inputfile > outputfile 
    
把所有的 />替换为 rn='1', 转义字符\/> 
类似地，

    sed "s/TradeID/TradeId/g" infile > outfile




#### 添加内容

    sed "s/^/BEGIN &/g" inputfile > outputfile
    
在每一行头部加入BEGIN


 * * *



  
