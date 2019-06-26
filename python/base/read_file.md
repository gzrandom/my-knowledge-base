# 读取文件

## open(filename, mode)

返回文件对象

模式(mode)|作用
:-:|:-
'r'|open for reading (default)
'w'|open for writing, truncating the file first
'x'|create a new file and open it for writing
'a'|open for writing, appending to the end of the file if it exists
'b'|binary mode
't'|text mode (default)
'+'|open a disk file for updating (reading and writing)
'U'|universal newline mode (deprecated)

## filename.read()

读取文件内容

例:

```python
from sys import argv

script, filename = argv

txt = open(filename)

print(f"Here's your file {filename}:")
print(txt.read())

txt.close()

print("Type the filename again:")
file_again = input("> ")

txt_again = open(file_again,)

print(txt_again.read())

txt_again.close()
```
