# NSD-Py01-Day03

## 文件

- 文件操作的三个步骤：打开、读写、关闭

### 文本文件的操作

- str：字符。一个英文字符是一个字符，一个中文字符也是一个字符
- bytes：字节。存储单位。不同的字符所占用的字节数不一样

- 将一串2进制的01组合表示成相应的字符，是编码。美国常用的编码是ASCII，欧洲常用的ISO-8859-1（Latin1）,中国常用GBK/GB2312/GB18030。如ASCII：

  A -> 01000001; B -> 01000010; C-> 01000011

- 不同编码方案，导致相同的一个文件使用不同编码格式打开，看到的内容不一致。所以ISO推出了万国码Unicode，utf-8是其中的一套解决方案。UTF8是变长的，一个英文字符占一个字节，一个中文字符一般占3个字节。

  ```bash
  >>> s1 = 'a'
  >>> s2 = '中'
  >>> type(s1)
  <class 'str'>
  >>> type(s2)
  <class 'str'>
  >>> b1 = s1.encode()   # 将str转为bytes
  >>> b2 = s2.encode()
  >>> type(b1)
  <class 'bytes'>
  >>> type(b2)
  <class 'bytes'>
  
  >>> b1
  b'a'   # 前缀b表示bytes  0b01100001
  # 当一个字节正好能对应成一个字符，就显示为字符。如果一个字节不能对应成一个字符，将会显示这个字节的16进制数。
  >>> b2
  b'\xe4\xb8\xad'   # \x表示16进制
  >>> bin(0xe4b8ad)
  '0b111001001011100010101101'
  
  >>> b1.decode()   # 将bytes转成str
  'a'
  >>> b2.decode()
  '中'
  ```

- 打开并读取文件

  ```bash
  [root@localhost day03]# cp /etc/passwd /tmp/mima
  # 默认以r读的方式打开，文件不存在则报错
  >>> f = open('/tmp/passwd')
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  FileNotFoundError: [Errno 2] No such file or directory: '/tmp/passwd'
  >>> f = open('/tmp/mima')  # 打开文件，返回一个文件对象
  >>> data = f.read()  # read默认读取全部数据
  >>> f.close()        # 关闭文件
  >>> print(data)
  
  >>> f = open('/tmp/mima')
  >>> data = f.read()  # 读取全部数据赋值给data
  >>> data = f.read()  # 继续读数据，重新赋值给data
  >>> data
  ''
  >>> f.close()
  
  >>> f = open('/tmp/mima')
  >>> f.readline()  # 读一行
  'root:x:0:0:root:/root:/bin/bash\n'
  >>> f.readline()  # 继续向后读一行
  'bin:x:1:1:bin:/bin:/sbin/nologin\n'
  >>> f.readlines() # 继续将后面所有行读出来，存入列表
  >>> f.readline()
  ''
  >>> f.read()
  ''
  >>> f.readlines()
  []
  >>> f.close()
  
  # 重要：读文本文件最常用的方法是for循环
  >>> f = open('/tmp/mima')
  >>> for line in f:
  ...   print(line, end='')
  >>> f.close()
  ```

  

- 打开并写入文件

  ```bash
  #以w方式打开文件，文件不存在则创建，存在则清空
  >>>f = open('/tmp/mima','w')
  ```

  

