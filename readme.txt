## QR二维码生成工具

windows下用vs编译qrencode需要四个库已放在lib目录下。

用vs编译qrencode时可能会报几个错误，下边是解决方法：

1.报__attribute__ 是错误的标识符，这是因为__attribute__就linux下的编译修饰符，在vs里定义一个宏来直接忽略这个标识符就好
  解决方法，在这个标识符上定义下边的宏就好

```C++
#define __attribute__(x)

```
2.报png库的一些相关类型错误

解决办法：

把libpng库编译后的debug下的pnglibconfg.h文件复制到libpng的源码目录下，如果在编译libpng时报zlib.h的错误，解决办法也是把zlib的debug下的zlibconfg.h文件复制到zlib的源码目录下。

##编译后的qrencode使用方法

可以在cmd命令行下运行qrencode.exe程序看说明，下边是一个把字符串生成二维码的例子。

.\qrencode.exe https://fengmm521.taobao.com image.png

这样会生成一个我网店链接的二维码图片在qrencode.exe同一个目录下