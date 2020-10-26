"# Data-Driven-Modeling" 
"# Data-Driven-Modeling" 
"# Data-Driven-Modeling" 
"# Data-Driven-Modeling" 
"# Data-Driven-Modeling" 
2.
##生成100个文件夹##
Mkdir DDM{1..100}
##生成文本文档##
touch time_till_now.txt
##写入unix时间戳##
date +%s>time_till_now.txt
##将文本文档复制入100个文件夹中##
echo /home/ztangat/DDM1/ /home/ztangat/DDM99 | xargs -n 1 cp /home/ztangat/time_till_now.txt


3.
##加载正则模块##
import re
##打开文件，读取文件到一个列表中##
with open('blocklist.xml','r') as f:
    lines = f.readlines()

print("Answer of Question 1:")
##遍历每一行，检测其中的blockID是否满足条件##
for line in lines:
    result = re.findall(r'emItem blockID="[ig].*\d"',line)
    if result != []:
        print(line.lstrip().rstrip())

print()
print('='*50)
print("Answer of Question 2:")
##遍历每一行，检测其中的id是否满足条件##   
for line in lines:
    result = re.findall(r'id="[a-zA-Z0-9_-]+@[a-zA-Z0-9_-]+(\.[a-zA-Z0-9_-]+)+"',line)
    if result != []:
        print(line.lstrip().rstrip())
